
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
