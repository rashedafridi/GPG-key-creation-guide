## Adding a GPG key to your GitHub account

- list all key and copy the key ID
```bash
gpg --list-secret-keys --keyid-format=long

```

```bash
# example Output----------------------------------
sec   rsa3072/0D6FB2D4EA477A09 2024-07-09 [SC]
      187BE138DCF51620C688FF880D6FB2D4EA477A09
uid                 [ultimate] examole (GPG-key) <example@gmail.com>
ssb   rsa3072/0F1ADC90102[][]E26 2024-07-09 [E]

```
- generate ASCII armor format public key
```bash
gpg --armor --export 0F1ADC90102[][]E26
```

```bash
# example Output----------------------------------
-----BEGIN PGP PUBLIC KEY BLOCK-----
mQGN............................................................
................................................................
...........................................................tmWM
-----END PGP PUBLIC KEY BLOCK-----
```

- In the upper-right corner of any page on GitHub, click your profile photo, then click Settings.
- In the "Access" section of the sidebar, click  SSH and GPG keys.
- Next to the "GPG keys" header, click New GPG key.
- In the "Title" field, type a name for your GPG key.
- In the "Key" field, paste the GPG key you copied when you generated your GPG key.
    - to get the key list all key and copy the key ID
    ```bash
    gpg --list-secret-keys --keyid-format=long

    ```

    ```bash
    # example Output----------------------------------
    sec   rsa3072/0D6FB2D4EA477A09 2024-07-09 [SC]
        187BE138DCF51620C688FF880D6FB2D4EA477A09
    uid                 [ultimate] examole (GPG-key) <example@gmail.com>
    ssb   rsa3072/0F1ADC90102[][]E26 2024-07-09 [E]

    ```
    - generate ASCII armor format public key
    ```bash
    gpg --armor --export 0F1ADC90102[][]E26
    ```

    ```bash
    # example Output----------------------------------
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    mQGN............................................................
    ................................................................
    ...........................................................tmWM
    -----END PGP PUBLIC KEY BLOCK-----
    ```
- now clock Click `Add GPG key` to add it.


- setup the `user.signingkey` so that it can be used when you make commit. you can find your key id when you list all the keys 
</br>sec   ed25519/**0F1ADC90102[][]26** 2024-07-10 [SC]

```bash
git config --global user.signingkey <Key ID>
# EX: git config --global user.signingkey  0F1ADC90102[][]26

```
 - to create a commit with signachar just add `-S`.

 ```bash
git commit -S -m "YOUR_COMMIT_MESSAGE"

```

- if you want  all commit to be signed by default set commit.gpgsign  value as true.

```bash
git config --global commit.gpgsign true
```
- if you want  all tag to be signed by default set `tag.gpgsign`  value as true.
```bash
git config --global tag.gpgsign true
```

- ⚠️ If your are on windows you must add `gpg.program` to point to `gpg` executable or you will see error like bellow ⚠️

    ```bash
    gpg: skipped "5EFF2D55A8A07709": No secret key
    gpg: signing failed: No secret key
    error: gpg failed to sign the data
    fatal: failed to write commit object
    ```
    - to slove it set  `gpg` executable in config. 
    ```bash
    # find executable path
    # on windows open powerShall use bellow command
    (Get-Command gpg).Path
    # output: C:\Program Files (x86)\Gpg4win\..\GnuPG\bin\gpg.exe

    # now addd the path to git config
    git config --global gpg.program "C:\Program Files (x86)\Gpg4win\..\GnuPG\bin\gpg.exe"
    ```

- you can use this command to list all config for verification purpose.

```bash
git config --global --list
```

<p align="center">
 ----- end -----
</p>