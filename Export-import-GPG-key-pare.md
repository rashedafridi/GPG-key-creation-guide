## How to Export GPG keys from one Device to Import those to other Device (Tested on Windows and ubuntu)

### Export Command

```bash
gpg --armor --output public-gpg.asc --export <Key ID >
gpg --armor --output privat-gpg.asc --export-secret-key <Key ID >
gpg --armor --export-ownertrust > gpg-ownertrust.asc
# you can find your key id when you list all the keys, using the command "gpg --list-secret-keys --keyid-format=long"
# id can be found here "sec   ed25519/< Key Id >1 2024-07-10 [SC]"
# ex: "sec   ed25519/F□□□□□□□□□□□□□B 2024-07-10 [SC]"
```

### Import Command

- copy those 3 fime to the Device you want to use it on and run the below command.

```bash
gpg --armor  --import  public-gpg.asc
gpg --armor  --import  privat-gpg.asc
gpg --armor --import-ownertrust gpg-ownertrust.asc 
```

<p align="center">
 ----- end -----
</p>