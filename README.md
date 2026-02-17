# Linux-Encryption-Decryption-Project
Linux Project Description
objective: This project is designed to teach you how encryption and decryption work using real Linux commands.
I will encrypt a file, verify it is unreadable, then decrypt it back to its original form.
This project uses tools that already exist on Linux systems.



PART 1: CREATE A PLAINTEXT FILE


STEP 1: OPEN YOUR TERMINAL 

STEP 2: CREATE A NEW FILE CALLED message.txt using echo command:

echo "Encryption hides data but does not make system secure." > messsage.txt

Step 3:
Confirm the file was created:

cat message.txt

You should see the original readable message.

--------------------------------------------------
PART 2: ENCRYPT THE FILE
--------------------------------------------------

Step 4:
Encrypt the file using OpenSSL AES encryption:

openssl enc -aes-256-cbc -salt -in message.txt -out message.enc

Step 5:
When prompted, enter a password.
Remember this password. You will need it to decrypt the file.

Step 6:
Confirm that the encrypted file exists:

ls

Step 7:
Try to read the encrypted file:

cat message.enc

You should see unreadable, scrambled output.

--------------------------------------------------
PART 3: DELETE THE ORIGINAL FILE
--------------------------------------------------

Step 8:
Delete the original plaintext file:

rm message.txt

Step 9:
Confirm the file is gone:

ls

Only the encrypted file should remain.

--------------------------------------------------
PART 4: DECRYPT THE FILE
--------------------------------------------------

Step 10:
Decrypt the encrypted file back to plaintext:

openssl enc -d -aes-256-cbc -in message.enc -out message_decrypted.txt

Step 11:
Enter the same password you used during encryption.

Step 12:
View the decrypted file:

cat message_decrypted.txt

You should see the original message again.

PART 5: UNDERSTANDING WHAT YOU DID
--------------------------------------------------

Explanation:
- message.txt was the original readable data.
- message.enc is the encrypted version of the data.
- Without the correct password, the encrypted file is useless.
- Encryption protected the data, not the system.
- If the password is exposed, encryption fails.

--------------------------------------------------
REQUIREMENTS
--------------------------------------------------

showing the following in plain text:
The command you used to encrypt the file.

 <img width="1346" height="206" alt="VirtualBox_Kali Linux_16_02_2026_17_59_40" src="https://github.com/user-attachments/assets/15d6ea99-99cd-405c-9f39-1e0fcee8a644" />


The command you used to decrypt the file.

 <img width="1366" height="140" alt="VirtualBox_Kali Linux_16_02_2026_18_01_46" src="https://github.com/user-attachments/assets/92f5c6d0-b689-43c6-b2d4-8b35792b32cf" />


One sentence explaining why encryption alone is not enough for security.


Encryption provides confidentiality by making data unreadable, but it lacks integrity protection, meaning an attacker could maliciously alter the encrypted file without being detected until you attempt to decrypt it.


WHY THIS PROJECT MATTERS
--------------------------------------------------

This project shows how encryption works in real systems.
It also shows why attackers target passwords and access instead of breaking encryption.
Understanding this is foundational before learning about passwords, hashes, and authentication.
