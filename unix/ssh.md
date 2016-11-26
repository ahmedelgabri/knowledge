Some [recommended options to add to](https://github.com/drduh/macOS-Security-and-Privacy-Guide#ssh) `~/.ssh/ssh_config`

```
Host *
  PasswordAuthentication no
  ChallengeResponseAuthentication no
  HashKnownHosts yes
```

Note [macOS Sierra permanently remembers SSH key passphrases by default](https://openradar.appspot.com/28394826). Append the option `UseKeyChain no` to turn this feature off.
