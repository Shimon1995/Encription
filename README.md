# How do I encrypt a file or folder in my home directory?
You can use PGP encryption to do this with the command-line tool gpg.

#### Turn a directory into a file                                                  
If you want to encrypt a directory, you will need to convert it to a file first. Run the command:

```sh
tar czf myfiles.tar.gz mydirectory/
```
This gives you a new file 'myfiles.tar.gz' which you can then encrypt/decrypt. To turn a tarball back into a directory:

```sh
tar xzf myfiles.tar.gz
```
#### Prepare GPG
You will need to create a private key with which you will encrypt your files. Type

```sh
gpg –-gen-key
```
You will be prompted to enter some security ;information. Use the defaults when available, otherwise enter your name and email address. You will also be prompted for a passphrase. Remember this passphrase.

#### Encrypt
To encrypt a file, type

```sh
gpg -e -r USERNAME ~USERNAME/filename
```
where filename is the name of some file in your account and USERNAME is your username. This command will create filename.gpg. At this point you may choose to remove filename in favor of the encrypted file filename.gpg.

#### Decrypt
To decrypt the file, type

```sh
gpg -d -o ~USERNAME/decrypted ~USERNAME/filename
```

which will create the new file decrypted.

[original](https://statistics.berkeley.edu/computing/encrypt)
