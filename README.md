
Commands for shell programming, command-line interface (CLI)

Command	Purpose	Example
pwd	Show current directory path	pwd
ls	List files and directories	ls, ls -l
cd	Change directory	cd Documents
mkdir	Create new directory	mkdir test
rmdir	Remove empty directory	rmdir test
touch	Create empty file	touch file.txt
cp	Copy file	cp file1.txt file2.txt
mv	Move or rename file	mv file1.txt newfile.txt
rm	Delete file	rm file.txt
cat	Display file content	cat file.txt
nano	Open text editor	nano file.txt
clear	Clear terminal screen	clear
echo	Print text output	echo Hello
whoami	Show current user	whoami
date	Show system date C time	date
cal	Show calendar	cal
man	Show manual of command	man ls
history	Show previous commands	history
chmod	Change file permissions	chmod 755 file.sh
chown	Change file owner	chown user file.txt
grep	Search text in file	grep "hello" file.txt
find	Search files	find . -name file.txt
wc	Count words, lines, characters	wc file.txt
 
head	Show first lines of file	head file.txt
Command	Purpose	Example
grep -i	Search text ignoring case	grep -i "hello" file.txt
grep -n	Show line number of match	grep -n "hello" file.txt
grep -r	Search text in all files inside folder	grep -r "hello" /home
grep -v	Show lines NOT matching text	grep -v "hello" file.txt



Write a program using shell programming to implement an address book.
echo "===== ADDRESS BOOK ====="
while true
do
echo "1. Add Contact"
echo "2. View Contacts"
echo "3. Search Contact"
echo "4. Delete Contact"
echo "5. Exit"
read choice
case $choice in
1)
echo "Enter Name:"
read name
echo "Enter Phone:"
read phone
echo "Enter Email:"
read email
echo "$name | $phone | $email" >> address.txt
echo "Contact Added!"
;;
2)
echo "---- Contact List ----"
cat address.txt 2>/dev/null
;;
3)
echo "Enter name to search:"
read sname
grep -i "$sname" address.txt 2>/dev/null
;;
4)
echo "Enter name to delete:"
read dname
grep -iv "$dname" address.txt > temp.txt 2>/dev/null
mv temp.txt address.txt
echo "Contact Deleted!"
;;
5)
echo "Exiting..."
break
;;
*)
echo "Invalid choice"
;;
esac
echo ""
done


Q) Write a program using shell programming to implement an address book with options
given below: a) create address book.
echo "===== ADDRESS BOOK ====="
echo "Enter name of address book file:"
read filename
if [ -f "$filename" ]
then
 echo "Address book already exists."
else
 touch "$filename"
 echo "Address book created successfully



 Q) write a program using shell programming to implement an address book with
options given below: a) create address book. b) view address book. c) insert a
record.
Code:
echo "===== ADDRESS BOOK MENU ====="
while true
do
echo "1. Create Address Book"
echo "2. View Address Book"
echo "3. Insert Record"
echo "4. Exit"
read choice
case $choice in
1)
echo "Enter address book file name:"
read file
if [ -f "$file" ]
then
 echo "Address book already exists."
else
 touch "$file"
 echo "Address book created successfully."
fi
;;
2)
echo "Enter file name to view:"
read file
if [ -f "$file" ]
then
 echo "---- Address Book ----"
 cat "$file"
else
 echo "File does not exist."
fi
;;
3)
echo "Enter file name:"
read file
if [ -f "$file" ]
then
 echo "Enter Name:"
 read name
 echo "Enter Phone:"
 read phone
 echo "Enter Email:"
 read email
 echo "$name | $phone | $email" >> "$file"
 echo "Record inserted successfully."
else
 echo "Address book not found. Create it first."
fi
;;
4)
echo "Exiting program..."
break
;;
*)
echo "Invalid choice"
;;
esac
echo ""
done

write a program using shell programming to implement an address book with options given
below: a) create address book. b) view address book. c) insert a record. d) delete a record.
e) modify a record. f) exit
Code:
echo "========== ADDRESS BOOK =========="
while true
do
echo "1. Create Address Book"
echo "2. View Address Book"
echo "3. Insert Record"
echo "4. Delete Record"
echo "5. Modify Record"
echo "6. Exit"
echo "Enter your choice:"
read ch
case $ch in
1)
echo "Enter file name:"
read file
if [ -f "$file" ]
then
 echo "Address book already exists."
else
 touch "$file"
 echo "Address book created."
fi
;;
2)
echo "Enter file name:"
read file
if [ -f "$file" ]
then
 echo "----- Address Book -----"
 cat "$file"
else
 echo "File not found."
fi
;;
3)
echo "Enter file name:"
read fil
if [ -f "$file" ]
then
 echo "Enter Name:"
 read name
 echo "Enter Phone:"
 read phone
 echo "Enter Email:"
 read email
 echo "$name | $phone | $email" >> "$file"
 echo "Record inserted."
else
 echo "Create address book first."
fi
;;
4)
echo "Enter file name:"
read file
if [ -f "$file" ]
then
 echo "Enter name to delete:"
 read delnam
 grep -iv "$delname" "$file" > temp.txt
 mv temp.txt "$file"
 echo "Record deleted."
else
 echo "File not found."
fi
;;
5)
echo "Enter file name:"
read file
if [ -f "$file" ]
then
 echo "Enter name to modify:"
 read mname
 grep -iv "$mname" "$file" > temp.txt
 echo "Enter new Phone:"
 read phone
 echo "Enter new Email:"
 read email
 echo "$mname | $phone | $email" >> temp.tx
 mv temp.txt "$file"
 echo "Record modified."
else
 echo "File not found."
fi
;;
6)
echo "Exiting program..."
break
;;
*)
echo "Invalid choice."
;;
esac
echo ""
done
Output:



Q1 )Address book creation 

#!/bin/bash

while true
do
echo "-----------------------------"
echo " ADDRESS BOOK MENU"
echo "1. Create Address Book"
echo "2. View Address Book"
echo "3. Insert Record"
echo "4. Delete Record"
echo "5. Modify Record"
echo "6. Exit"
echo "-----------------------------"

echo "Enter your choice:"
read ch

case $ch in

1)
echo "Enter address book file name:"
read file

> $file
echo "Address book '$file' created successfully"
;;

2)
echo "Enter file name to view:"
read file

if [ -f $file ]
then
cat $file
else
echo "File not found"
fi
;;

3)
echo "Enter file name:"
read file

echo "Enter Name:"
read name

echo "Enter Phone:"
read phone

echo "Enter Email:"
read email

echo "$name | $phone | $email" >> $file

echo "Record inserted successfully"
;;

4)
echo "Enter file name:"
read file

echo "Enter name to delete:"
read name

grep -v "$name" $file > temp.txt
mv temp.txt $file

echo "Record deleted"
;;

5)
echo "Enter file name:"
read file

echo "Enter name to modify:"
read name

grep -v "$name" $file > temp.txt
mv temp.txt $file

echo "Enter new phone:"
read phone

echo "Enter new email:"
read email

echo "$name | $phone | $email" >> $file

echo "Record modified successfully"
;;

6)
echo "Exiting..."
exit
;;

*)
echo "Invalid choice"
;;

esac
done

chmod +x addressbook.sh



Q2. First come first serve 
#include <stdio.h>

int main() {
    int n, i;
    
    printf("Enter number of processes: ");
    scanf("%d", &n);

    int at[n], bt[n], ct[n], tat[n], wt[n];

    for(i = 0; i < n; i++) {
        printf("\nProcess %d\n", i+1);
        printf("Arrival Time: ");
        scanf("%d", &at[i]);
        printf("Burst Time: ");
        scanf("%d", &bt[i]);
    }

    // FCFS Calculation
    ct[0] = at[0] + bt[0];

    for(i = 1; i < n; i++) {
        if(ct[i-1] < at[i])
            ct[i] = at[i] + bt[i];
        else
            ct[i] = ct[i-1] + bt[i];
    }

    for(i = 0; i < n; i++) {
        tat[i] = ct[i] - at[i];      // Turnaround Time
        wt[i] = tat[i] - bt[i];      // Waiting Time
    }

    // Display
    printf("\nPID\tAT\tBT\tCT\tTAT\tWT\n");

    float total_tat = 0, total_wt = 0;

    for(i = 0; i < n; i++) {
        printf("%d\t%d\t%d\t%d\t%d\t%d\n",
               i+1, at[i], bt[i], ct[i], tat[i], wt[i]);

        total_tat += tat[i];
        total_wt += wt[i];
    }

    printf("\nAverage Turnaround Time = %.2f", total_tat/n);
    printf("\nAverage Waiting Time = %.2f\n", total_wt/n);

    return 0;
}


Q3)Bankers algorithm

#include <stdio.h>

int main() {
    int n, m, i, j, k;
    
    printf("Enter number of processes: ");
    scanf("%d", &n);

    printf("Enter number of resource types: ");
    scanf("%d", &m);

    int alloc[n][m], max[n][m], need[n][m];
    int avail[m], finish[n], safeSeq[n];

    printf("\nEnter Allocation Matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            scanf("%d", &alloc[i][j]);
        }
    }

    printf("\nEnter Maximum Matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            scanf("%d", &max[i][j]);
        }
    }

    printf("\nEnter Available Resources:\n");
    for (j = 0; j < m; j++) {
        scanf("%d", &avail[j]);
    }

    // Calculate Need matrix
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            need[i][j] = max[i][j] - alloc[i][j];
        }
    }

    // Initialize finish array
    for (i = 0; i < n; i++) {
        finish[i] = 0;
    }

    int count = 0;
    while (count < n) {
        int found = 0;

        for (i = 0; i < n; i++) {
            if (finish[i] == 0) {
                int possible = 1;

                for (j = 0; j < m; j++) {
                    if (need[i][j] > avail[j]) {
                        possible = 0;
                        break;
                    }
                }

                if (possible) {
                    for (k = 0; k < m; k++) {
                        avail[k] += alloc[i][k];
                    }

                    safeSeq[count++] = i;
                    finish[i] = 1;
                    found = 1;
                }
            }
        }

        if (found == 0) {
            break;
        }
    }

    printf("\nNeed Matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            printf("%d ", need[i][j]);
        }
        printf("\n");
    }

    if (count == n) {
        printf("\nSystem is in SAFE state.\nSafe Sequence: ");
        for (i = 0; i < n; i++) {
            printf("P%d", safeSeq[i]);
            if (i != n - 1)
                printf(" -> ");
        }
        printf("\n");
    } else {
        printf("\nSystem is NOT in safe state.\n");
    }

    return 0;
}

Q4)POSIX Threads (with Mutex)

#include <stdio.h>
#include <pthread.h>

int shared = 0;                 // shared variable
pthread_mutex_t lock;           // mutex lock

void* increment(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&lock);   // critical section start
        shared++;
        pthread_mutex_unlock(&lock); // critical section end
    }
    return NULL;
}

void* decrement(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&lock);
        shared--;
        pthread_mutex_unlock(&lock);
    }
    return NULL;
}

int main() {
    pthread_t t1, t2;

    pthread_mutex_init(&lock, NULL);

    printf("Initial value of shared variable = %d\n", shared);

    // create threads
    pthread_create(&t1, NULL, increment, NULL);
    pthread_create(&t2, NULL, decrement, NULL);

    // wait for threads to finish
    pthread_join(t1, NULL);
    pthread_join(t2, NULL);

    printf("Final value of shared variable = %d\n", shared);

    pthread_mutex_destroy(&lock);

    return 0;
}


Q5) Two Threads with Lock (Mutex)

#include <stdio.h>
#include <pthread.h>

int shared = 0;                // shared variable
pthread_mutex_t mutex;         // lock

// Thread function to increment
void* increment(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&mutex);   // enter critical section
        shared++;
        pthread_mutex_unlock(&mutex); // exit critical section
    }
    return NULL;
}

// Thread function to decrement
void* decrement(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&mutex);
        shared--;
        pthread_mutex_unlock(&mutex);
    }
    return NULL;
}

int main() {
    pthread_t t1, t2;

    pthread_mutex_init(&mutex, NULL);

    printf("Initial value of shared variable = %d\n", shared);

    // Create threads
    pthread_create(&t1, NULL, increment, NULL);
    pthread_create(&t2, NULL, decrement, NULL);

    // Wait for threads to complete
    pthread_join(t1, NULL);
    pthread_join(t2, NULL);

    printf("Final value of shared variable = %d\n", shared);

    pthread_mutex_destroy(&mutex);

    return 0;
}

Q6)Two Threads using Semaphore (Process Synchronization)

#include <stdio.h>
#include <pthread.h>
#include <semaphore.h>

int shared = 0;     // shared variable
sem_t sem;          // semaphore

// Thread to increment
void* increment(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        sem_wait(&sem);   // acquire semaphore (enter critical section)
        shared++;
        sem_post(&sem);   // release semaphore (exit critical section)
    }
    return NULL;
}

// Thread to decrement
void* decrement(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        sem_wait(&sem);
        shared--;
        sem_post(&sem);
    }
    return NULL;
}

int main() {
    pthread_t t1, t2;

    sem_init(&sem, 0, 1);   // binary semaphore (mutex behavior)

    printf("Initial value of shared variable = %d\n", shared);

    // Create threads
    pthread_create(&t1, NULL, increment, NULL);
    pthread_create(&t2, NULL, decrement, NULL);

    // Wait for threads to finish
    pthread_join(t1, NULL);
    pthread_join(t2, NULL);

    printf("Final value of shared variable = %d\n", shared);

    sem_destroy(&sem);

    return 0;
}

Q7) Race condition

#include <stdio.h>
#include <pthread.h>

int shared = 0;              // shared variable
pthread_mutex_t lock;        // mutex for synchronization

// Thread function to increment
void* increment(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&lock);   // critical section start
        shared++;
        pthread_mutex_unlock(&lock); // critical section end
    }
    return NULL;
}

// Thread function to decrement
void* decrement(void* arg) {
    int i;
    for(i = 0; i < 100000; i++) {
        pthread_mutex_lock(&lock);
        shared--;
        pthread_mutex_unlock(&lock);
    }
    return NULL;
}

int main() {
    pthread_t t1, t2;

    pthread_mutex_init(&lock, NULL);

    printf("Initial value of shared variable = %d\n", shared);

    // Create two threads
    pthread_create(&t1, NULL, increment, NULL);
    pthread_create(&t2, NULL, decrement, NULL);

    // Wait for both threads to finish
    pthread_join(t1, NULL);
    pthread_join(t2, NULL);

    printf("Final value of shared variable = %d\n", shared);

    pthread_mutex_destroy(&lock);

    return 0;
}


