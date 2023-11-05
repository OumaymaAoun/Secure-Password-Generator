# Secure-Password-Generator
import string
import random
s1 = list(string.ascii_lowercase)
s2 = list(string.ascii_uppercase)
s3 = list(string.digits)
s4 = list (string.punctuation)

charaters_number = input("please enter the number of characters for your password")

while True :
    try:
        charaters_number = int(charaters_number)
        if charaters_number < 6 :
            print ("you need at least 6 characters")
            charaters_number = input("please enter the number of characters for your password again")

        else:
            break
    except:
        print("please enter numbers only")
        charaters_number = input("please enter the number of characters for your password")


random.shuffle(s1)
random.shuffle(s2)
random.shuffle(s3)
random.shuffle(s4)

part1= round(charaters_number * (30/100))
part2= round(charaters_number * (20/100))

password = []
for i in range(part1):
    password.append(s1[i])
    password.append(s2[i])

for i in range(part2):
    password.append(s3[i])
    password.append(s4[i])

password = "".join(password[0:])
print(password)
