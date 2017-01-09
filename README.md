# pwmac
a stateless password manager
## Intro
pwmac ist a bash script that uses openssl's HMAC function to generate for any domain (e.g. github.com) a domain specific password from one single master password. That way domain passwords don't need to be remembered or stored in a keystore.

The benefits are
 1. Passwords can't get lost through data loss as long as you know your master password.
 2. You can retrieve your passwords on any computer that has pwmac installed as long as you have your master password with you. You don't need access to a hard drive with your keystore on it.
 3. Passwords cannot be retrieved from your computer if it gets lost, stolen or corrupted (This is actually also true for encrypted keystores).

**But...**
- Be very careful to choose a master password with enough entropy to resist an offline brute force attack. Otherwise an attacker that knows one domain password can retrieve all of them.
- If the master password is corrupted all domain passwords are corrupted and need to be changed.
- Use at your own risk. There are certainly pros an cons for this and it is just an experiment to test if the approach is workable. I will be glad for any feedback.

## Example
The following example prompts for a master password and outputs the generated domain password `v90cRxOw`
```bash
$ pwmac github.com
master password:
v90cRxOw
```
