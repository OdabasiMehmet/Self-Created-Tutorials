# How to Use Filters Hands On study
**cat**

1. mkdir filters
2. cd filters
3. Create a `text` file named `days.txt`.
   vim days.txt
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday
4. Display the content of days.txt.
cat days.txt
5. Create a `text` file named `count.txt`.
​ vim count.txt
one
two
three
four
five
six
seven
eight
nine
ten
eleven 
6. Display the content of count.txt.
cat count.txt
7. Write the content of the count.txt file in reverse order to another file named temp.txt and display the content of temp.txt in reverse order.
tac count.txt | tee temp.txt | tac
8. Check whether the temp.txt file created and display the content.
​cat temp.txt
9. Print lines that match patterns. The most common use of grep is to filter lines of text containing (or not containing) a certain string.
10. Create a `text` file named `tennis.txt`.
​  cat > tennis.txt
​Amelie Mauresmo, Fra
Justine Henin, BEL
Serena Williams, USA
Venus Williams, USA
11. Display the content of tennis.txt.
cat tennis.txt
12. Display only the lines of tennis.txt that includes 'Williams'.
​cat tennis.txt | grep Williams
13. Display only the lines of tennis.txt that includes 'us'.
​cat tennis.txt | grep us
14.  Display the owners column (3rd column) of all the files in current 
ls -l | cut -d' ' -f3
15. Display the content of /etc/passwd directory.
cat /etc/passwd
16. Display only the usernames.
​cut -d: -f1 /etc/passwd
17. Create a `text` file named `clarusway.txt`.
​cat << EOF > clarusway.txt
Clarusway:Road to reinvent yourself.
EOF
18. Display the content of clarusway.txt.
​cat clarusway.txt
19. In the content of clarusway.txt, replace or translate aer letters with 'QAZ'.
cat clarusway.txt | tr aer QAZ
20. Write the content of count.txt on the same line.
​cat count.txt | tr '\n' ' '
21. Delete all the vowels in the content of clarusway.txt.
cat clarusway.txt | tr -d aeiou
22. Write the whole content of clarusway.txt in capital letters.
cat clarusway.txt | tr [a-z] [A-Z]
23. Find how many users are there in the computer.
wc -l /etc/passwd
24. Create a `text` file named `marks.txt`.
​cat << EOF > marks.txt
aeron-9
albert-9
james-9
john-10
oliver-7
tom-7
victor-10
walter-8
EOF
25. Display the content of marks.txt.
​cat marks.txt
26. Sort the content of marks.txt.
sort marks.txt
27. Sort the content of marks.txt in reverse order.
​sort -r marks.txt
28. Create a `text` file named `trainees.txt`.
​cat << EOF > trainees.txt
john
james
aeron
oliver
walter
albert
james
john
travis
mike
aeron
thomas
daniel
john
aeron
oliver
mike
john
EOF
29. Display the content of trainees.txt.
​cat trainees.txt
30. Display only the unique names in the content of trainees.txt.
​sort trainees.txt | uniq
31. Create a `text` file named `file1.txt`.
​cat << EOF > file1.txt
Aeron
Bill
James
John
Oliver
Walter
EOF
32. Create another `text` file named `file2.txt`.
​cat << EOF > file2.txt
Guile
James
John
Raymond
33. Compare file1.txt and file2.txt.
​comm file1.txt file2.txt
34.

- EXERCISE:
​
  - Create a file named `countries.csv`.
​
```bash
cat << EOF > countries.csv
Country,Capital,Continent
USA,Washington,North America
France,Paris,Europe
Canada,Ottawa,North America
Germany,Berlin,Europe
EOF
```
  - Cut only 'Continent' column | Remove header | Sort the output | List distinct values | Save it to 'continent.txt' and display on the screen.
​
```bash
********************************
```

## Solution:
cat countries.csv | cut -d',' -f3 | tail -4 | sort | uniq > countries.txt && cat countries.txt
