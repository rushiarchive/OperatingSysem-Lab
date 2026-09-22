POSIX Threads and Mutex Example

This C program demonstrates:

Creating multiple threads using pthread_create()

Waiting for threads using pthread_join()

Protecting a shared variable using a mutex

Passing an argument to a thread

Destroying a mutex after use

Source Code
#include <stdio.h>
#include <pthread.h>

int count = 0;
pthread_mutex_t lock;

void *work(void *args)
{
    for (int i = 0; i < 10000; i++) {
        // printf("%d\n", i);
        pthread_mutex_lock(&lock);
        count++;
        pthread_mutex_unlock(&lock);
    }

    printf("Count is: %d\n", count);
    return NULL;
}

void *lazy(void *args)
{
    for (int i = 0; i < 10000; i++) {
        // printf("User %d\n", i);
        pthread_mutex_lock(&lock);
        count++;
        pthread_mutex_unlock(&lock);
    }

    printf("Count is: %d\n", count);
    return NULL;
}

void *rest(void *args)
{
    int j = *(int *)args;

    for (int i = 0; i < 10; i++) {
        // printf("param %d is - %d\n", i, j);
    }

    return NULL;
}

int main()
{
    int id = 78;
    pthread_t t1, t2, t3;

    printf("Done\n");

    pthread_mutex_init(&lock, NULL);

    pthread_create(&t1, NULL, work, NULL);
    pthread_create(&t2, NULL, lazy, NULL);
    pthread_create(&t3, NULL, rest, &id);

    printf("In main thread, new threads created\n");

    pthread_join(t1, NULL);
    pthread_join(t2, NULL);
    pthread_join(t3, NULL);

    pthread_mutex_destroy(&lock);

    printf("Final count: %d\n", count);
    printf("Done\n");

    return 0;
}

How It Works
Shared Variable
int count = 0;


count is shared by t1 and t2. Both threads increment it 10,000 times.

Therefore:

10000 + 10000 = 20000


The expected final value is:

Final count: 20000

Mutex

The mutex protects the count++ operation:

pthread_mutex_lock(&lock);
count++;
pthread_mutex_unlock(&lock);


Only one thread can execute the critical section at a time.

Without the mutex, both threads could access and modify count simultaneously, causing a race condition and potentially producing a value less than 20000.

Creating Threads

Three threads are created:

pthread_create(&t1, NULL, work, NULL);
pthread_create(&t2, NULL, lazy, NULL);
pthread_create(&t3, NULL, rest, &id);


t1 executes work()

t2 executes lazy()

t3 executes rest()

Passing an Argument

The value 78 is passed to rest():

int id = 78;

pthread_create(&t3, NULL, rest, &id);


Inside rest():

int j = *(int *)args;


This converts the void * argument back to an int * and dereferences it.

Waiting for Threads

The main thread waits for all three threads:

pthread_join(t1, NULL);
pthread_join(t2, NULL);
pthread_join(t3, NULL);


Only after all three threads finish does the program continue.

Destroying the Mutex

After all threads have finished using the mutex:

pthread_mutex_destroy(&lock);


The mutex is safely destroyed.

Compilation

Compile the program with:

gcc program.c -o program -pthread


Run it:

./program

Important Note

The two lines:

printf("Count is: %d\n", count);


inside work() and lazy() may print different values depending on thread scheduling.

For example:

Done
In main thread, new threads created
Count is: 10000
Count is: 20000
Final count: 20000
Done


The intermediate values and their order are not guaranteed, but the final count should be 20000 because the increments are protected by the mutex.
