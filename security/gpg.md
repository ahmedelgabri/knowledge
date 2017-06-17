# GPG keys

## Generate key

```sh
$ gpg --gen-key
```

## Adding a new UID

```sh
$ gpg --edit-key <key>

gpg> adduid
Real Name: <name>
Email address: <email>
Comment: <comment or Return to none>
Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? O
Enter passphrase: <password>
gpg> uid <uid>
gpg> trust
Your decision? 5
Do you really want to set this key to ultimate trust? (y/N) y
gpg> save

$
```

## Set a primary uid

```sh
$ gpg --edit-key <key>

gpg> uid <uid> # Choose a uid to apply commands to
...
gpg> primary
gpg> save
```

## Export key

```sh
$ gpg --armor --export <key>
```

### Important resources
- https://alexcabal.com/creating-the-perfect-gpg-keypair/
- https://ekaia.org/blog/2009/05/10/creating-new-gpgkey/
- https://wiki.debian.org/Subkeys
