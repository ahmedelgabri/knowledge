# Secure Weechat passwords

This will securely save your password in `sec.conf`, more info [here](https://weechat.org/files/doc/devel/weechat_user.en.html#secured_data)

```sh
/secure set <NAME> <PASSWORD>
```

then to use the encrypted password for your server you run

For example `irc`

```sh
/set irc.server.freenode.sasl_password "${sec.data.freenode}"
```

Running `/secure` alone will list all info regarding secured data.
