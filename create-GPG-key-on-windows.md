
## Generating a new GPG key on windows 

* Install required tools
  - go to `https://www.gpg4win.org/` download and install gpg4win.exe file.
- now open `powershell` and run the below command to check if gpg is installed properly
```powershell
gpg --version
``` 
- if the above command runs successfully then you have installed gpg properly.



* Now generate a GPG key pair by running the below command

```powershell
gpg --full-generate-key
```

```bash
gpg (GnuPG) 2.4.5; Copyright (C) 2024 g10 Code GmbH
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Please select what kind of key you want:
   (1) RSA and RSA
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (9) ECC (sign and encrypt) *default*
  (10) ECC (sign only)
  (14) Existing key from card
Your selection?
```
* now after this command we have to select kind of key we want. Input the number from the list or press Enter to select default
```powershell
Please select which elliptic curve you want:
   (1) Curve 25519 *default*
   (4) NIST P-384
   (6) Brainpool P-256
Your selection?
```
* now type the number elliptic curve you want.

```powershell
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0)

```
* in this step specify how long the key should be valid or press enter to accept 0 wich means it will not expire.

```powershell
Is this correct? (y/N) 
```
* If you are happy with your configeration press `Y` to continue

```powershell
GnuPG needs to construct a user ID to identify your key.

Real name:
```
* now provied your name that the key will use let set `example` as the name

```powershell
Email address: 
```
* now provied a valid Email adrees, let set `example@gmail.com` as the email. Oomthing to remember if you want to use this with your github use the same email that github was crete with.
```powershell
comment: 
```
* add a massage or short word you like.
```powershell
You selected this USER-ID:
    "example (gpg-key) <example@gmail.com>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? 
```
* in this step you can edit your name by pressing `N` ,comment by presing `C `And `E` for email. quit by presing `Q` . To continue creating key press `O` to create **Passphrase** whis will be like a Password

<br /><img src="./asset/w2.png" alt="Please enter the passphrase to protect your new key" width="500" /><br />

* here if  you want to  a create passphrase . type your Password on both of the field and prees `OK`. your key wll be generated ,
* on the other hand, if you dont want any Password/passphrase just prees `OK` with out putting any thing in the field . at this step it will show a massage saying `you have not enter passphrase...` . now select the option saying `Yes, potation not needed` remember you have to select the option **twice**. As the popup will paper twice

<br /><img src="./asset/w1.png" alt="you have not enter passphrase" width="500" /><br />

* now your Key generation is complete
```powershell
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: directory 'C:\\Users\\<user>\\AppData\\Roaming\\gnupg\\openpgp-revocs.d' created
gpg: revocation certificate stored as 'C:\\Users\\<user>\\AppData\\Roaming\\gnupg\\openpgp-revocs.d\\CD7□□□□□□□□□□□□□□□□□□□□□□□□□□□□11.rev'
public and secret key created and signed.

pub   ed25519 2024-07-10 [SC]
      CD7□□□□□□□□□□□□□□□□□□□□□□□□□□□□11
uid                      example (my-key) <example@gmail.com>
sub   cv25519 2024-07-10 [E]
```

* to check you keys thpe this command 
```bash
gpg --list-secret-keys --keyid-format=long
```
- output
```bash
sec   ed25519/2□□□□□□□□□□□□□1 2024-07-10 [SC]
      CD7□□□□□□□□□□□□□□□□□□□□□□□□□□□□11
uid                 [ultimate] example (my-key) <example@gmail.com>
ssb   cv25519/F□□□□□□□□□□□□□B 2024-07-10 [E]

```

<p align="center">
 ----- end -----
</p>