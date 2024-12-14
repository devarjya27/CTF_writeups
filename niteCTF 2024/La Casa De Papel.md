# Challenge Description
Word on the street is Bob's about to make a big withdrawal. Too bad you're the one holding his ID. Can you charm Alice into making the transfer before she catches on?

Author: Wixter_07

Category: `Crypto`

Points: 50

# My Solve
Opening `chall.py` we can see that `practice convo` hashes our input with `secret` keeping this in mind lets move forward.
```
def practice_convo(secret):
    message = input("Send a message: ")
    hash = md5(secret, message.encode('latin-1'))
    print(f"Here is your encrypted message: {hash}")
```

Now `fool_alice` prompts us for our name and if our name contains `Bob` then we have succeeded in semi-fooling alice. Now we are prompted for `HMAC` now this should match with the hashed `user_name`.
```
def fool_alice(secret):
    print("\nBot: Okay, let's see if you're the real deal. What's your name?")
    user_name = input("Your name: ").encode('latin-1')
    user_name = user_name.decode('unicode_escape').encode('latin-1')
    print("\nBot: Please provide your HMAC")
    user_hmac = input("Your HMAC: ").encode('latin-1')

    if b"Bob" in user_name:
        hash = base64.b64decode(md5(secret, user_name))
        if user_hmac == hash:
            print("\nAlice: Oh hey Bob! Here is the vault code you wanted:")
            with open('secret.txt', 'r') as file:
                secret_content = file.read()
                print(secret_content)
        else:
            print("\nAlice: LIARRRRRRR!!")
    else:
        print("\nAlice: IMPOSTERRRR")
```

So all i did was connect to the remote server and initially did `practice convo` and hashed `Bob`. Now for `fool alice` entered the username `Bob` and entered the hash which was returned in `practice_convo` when we are prompted for `HMAC`

The bot returns `G0t_Th3_G0ld_B3rl1nale`
```
Now we enter this password in `crack the vault`
def crack_the_vault():
    print("\nVault Person: Enter password")
    passs = input("Password: ")

    with open('secret.txt', 'r') as file:
        secret_content = file.read().strip()
        if passs == secret_content:
            with open('flag.txt', 'r') as flag_file:
                flag_content = flag_file.read().strip()
                print(f"\nVault Unlocked! The flag is: {flag_content}")
        else:
            print("Incorrect password!")
```
Entering the password gives us the flag:
```
Vault Person: Enter password
Password: G0t_Th3_G0ld_B3rl1nale

Vault Unlocked! The flag is: nite{El_Pr0f3_0f_Prec1s10n_Pl4ns}
```
