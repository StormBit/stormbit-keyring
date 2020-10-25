# StormBit KeyRing

The authorized_keys deployed throughout the StormBit fleet.

## Using StormBit KeyRing
The easy way, by adding the following to a crontab.
```
*/15 * * * * curl -o .ssh/authorized_keys https://raw.githubusercontent.com/StormBit/stormbit-keyring/master/authorized_keys >> /dev/null`
```


## Adding your key to StormBit KeyRing
To add a key to the StormBit KeyRing, please [add a SSH key to your Github Account](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account).

## How this works?
Every 15 minutes, a Github Action runs, which polls the public keys for everybody in the engineering team team.
It concatenates them into a single `authorized_keys` file, and if there are any changes, commits the change.