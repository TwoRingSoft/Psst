# psst

Insert secrets into codebases that don't want to commit them to history.

## How?

Throughout your codebase, replace credentials with unique strings as templates. Instead of your actual AWS key, commit the string `MY_AWS_KEY` and add that string to the listing in `.psst/keys` (commit this file in git).

You have a few options for how to specify the secret values:

- in `.psst/values` (ignored by git!), a newline separated list of keys and their corresponding values (keys and values separated by a space):

```
MY_AWS_KEY 574832h478295h478325g47239
MY_AWS_SECRET f587vb30298trfo728tvb2079frfht879d4298g6t9r38dt6j89d6rt29
ANOTHER_SECRET 75h7g458920
```

- in environment variables of the same name, as in you CI system's settings
- in a Mac secure keychain committed in the codebase, which you must ensure is unlocked when `psst` runs

Then run from your root directory:
```
psst [/path/to/keychain]
```

## Where?

`brew tap tworingsoft && brew install psst` (in fish, `brew tap tworingsoft; and brew install psst`)

# Contribute

Issues and pull requests are welcome! 

If this project helped you, please consider <a href="https://www.paypal.me/armcknight">leaving a tip</a> 🤗

Do you need help with a project? [I'm currently available for hire or contract.](http://tworingsoft.com/contracts).
