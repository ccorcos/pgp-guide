# PGP Guide

Install GNU Privacy Guard.

```sh
brew install gnupg
```

## Make your own key

```sh
gpg --generate-key
```

Export your public key
```sh
gpg --output ./public-keys/me.key --armor --export [KEY_ID]
```

## Send a message

Get someone's public key and save it to `./public-keys/[name].key`.

You can import the key here.
```sh
gpg --import public-keys/[name].key
```

You can list the keys here:
```sh
gpg --list-keys
```

Grab the key id and create a message in `messages/message.txt`. The encrypt it!
```
gpg --encrypt --sign --armor -r [KEY_ID] messages/message.txt
```

## Decrypt a message

```
gpg messages/message.txt.asc
```

## Resources
- https://www.digitalocean.com/community/tutorials/how-to-use-gpg-to-encrypt-and-sign-messages