# HILL CIPHER

EX. NO: 3 
## AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. 

STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
~~~
text = input("Enter plaintext: ").upper()
key = []

print("Enter 3x3 key matrix:")
for i in range(3):
    row = list(map(int, input().split()))
    key.append(row)

print("\nKey Matrix:")
for r in key:
    print(r)

while len(text) % 3 != 0:
    text += 'X'

print("Processed Text:", text)

cipher = ""

for i in range(0, len(text), 3):
    pt = [ord(text[i+j]) - 65 for j in range(3)]
    ct = [0, 0, 0]

    print("\nBlock:", text[i:i+3])

    for r in range(3):
        for c in range(3):
            ct[r] += key[r][c] * pt[c]
        ct[r] %= 26

    print("Numeric:", ct)

    for num in ct:
        cipher += chr(num + 65)

print("\nFinal Cipher Text:", cipher)
~~~
## OUTPUT
<img width="1441" height="860" alt="output" src="https://github.com/user-attachments/assets/c5f286a0-2198-4d84-a94b-5dab6379584e" />

## RESULT
Thus the implementation of hill cipher had been executed successfully.
