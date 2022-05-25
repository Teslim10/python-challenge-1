# python-challenge-1
removing repeated or unwanted lines from a .txt file 
'''We have a .txt file that contains a list of users who responded to our questionnaire. Our questionnaire could be answered multiple times, so we ended up having duplicated names in our text file, as shown below:
Anderson
Olakunle
Ifeoma
Lee
Margaret
Olakunle
Musa
Musa
Lee
Anderson
Yvonne
Albert
Ofori
Ofori
Rofiyat
Rofiyat
Dele
Muhammed
Rofiyat
Ofori
Lee
Ifeoma
Create a file named 'users.txt' that contains the above list of names as is in a directory. (You should be able to select a text or long-press it to copy it from here.)
Now, write a program that removes the excess/duplicate names, and now saves them in a new file named 'new.txt', such that the new file now contains:
Anderson
Olakunle
Ifeoma
Lee
Margaret
Musa
Yvonne
Albert
Ofori
Rofiyat
Dele
Muhammed'''
#code to remove repeated or unwanted lines from a .txt file
x = open("user.txt", "r")
user = x.read()
print(user)
x.close()
lines_seen = set()
with open("user.txt","r+") as f:
    d = f.readlines()
    f.seek(0)
    for i in d:
        if i not in lines_seen:
            f.write(i)
             lines_seen.add(i)
    f.truncate()
