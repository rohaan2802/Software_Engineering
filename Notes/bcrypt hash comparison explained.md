# bcrypt Hash Comparison

## How bcrypt Compares a Password with a Stored Hash

The reason bcrypt hashes are different each time even for the same password lies in the  
use of salt.  

### 1. Salt:

bcrypt uses a random salt (a unique, random string) every time it hashes a  
password. This salt is combined with the password before hashing. This ensures  
that even if two users have the same password, their bcrypt hashes will be  
different because they will have different salts.  
The salt is stored along with the hash in the database.  

### 2. Hashing Process:

When you enter your password, the system retrieves the salt from the stored  
hash in the database.  
It then combines the entered password and the salt and hashes this  
combination using bcrypt. This results in a new hash that can be compared with  
the stored hash.  

### 3. Comparison:

The salt is embedded within the stored bcrypt hash itself. The bcrypt hash is  
typically represented in a format like:  
Here:  
$2a$ is the bcrypt version identifier.  
12 is the cost factor (work factor).  
wJd27Hk... is the salt used in the hashing.  
The rest is the actual hashed password.  

### 4. Rehashing:

When comparing the entered password to the stored hash, bcrypt uses the  
stored salt to hash the entered password, and then compares the newly  
generated hash to the stored one.  
Since bcrypt hashes include the salt and bcrypt is a slow hashing algorithm,  
comparing hashes is computationally expensive, preventing attackers from easily  
guessing passwords.  
So, to summarize:  
Even though bcrypt generates a different hash for the same password each time, the  
salt (which is stored with the hash) ensures that the comparison can be made. The  
entered password combined with the stored salt generates the same hash as the  
original one if the password is correct.  
$2a$12$wJd27HkUy5QYNU8vfsYgt.kM7MjsyZiOnK2IHTT7ic3hYec8JlaZC  

## Same Salt and Cost Give the Same Hash

Yes, exactly! If the salt and cost factor are the same, then the bcrypt hash for the same  
password will be the same.  
Here's the key breakdown:  

### 1. Salt:

The salt is a random string added to the password before hashing. It's unique for  
each user and stored along with the hashed password.  
If the salt is the same for the same password, the hash will be the same. In  
practice, though, salts are always randomly generated to ensure uniqueness.  

### 2. Cost Factor:

The cost factor (sometimes called the "work factor") determines how many  
iterations bcrypt will perform to hash the password. This makes the process  
slower to defend against brute-force attacks.  
If the cost factor is the same for the same password and salt, the resulting hash  
will be the same.  

### 3. Hash:

When bcrypt hashes a password, the result is determined by both the salt and  
the cost factor. So, as long as both the salt and the cost factor remain  
constant, the hash for the same password will be identical.  
Example Scenario:  
Password: mypassword123  
Salt: random_salt_12345  
Cost: 12 (let's assume cost factor of 12)  
If these values remain the same every time you hash mypassword123 (same salt, same  
cost), the resulting bcrypt hash will always be the same.  
However, since salts are designed to be random, each time you hash the same  
password, the salt is different, resulting in a different hash.  
To Summarize:  
Same salt + Same cost factor + Same password = Same hash.  
Different salt (even for the same password) = Different hash.  
This is why the hash can be different for the same password in practice — because of the  
random salt being used each time.  
