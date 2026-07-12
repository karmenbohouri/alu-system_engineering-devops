# SSH

This directory contains exercises on SSH: generating RSA key pairs,
configuring the local SSH client, connecting to a remote server without
a password, and managing authorized keys — including automating the
client configuration with Puppet.

## Files

- `0-use_a_private_key`: connects via SSH using the private key `~/.ssh/school`
- `1-create_ssh_key_pair`: generates a 4096-bit RSA key pair protected by a passphrase
- `2-ssh_config`: SSH client configuration using the `school` key and disabling password authentication
- `100-puppet_ssh_config.pp`: Puppet manifest applying the same SSH client configuration
