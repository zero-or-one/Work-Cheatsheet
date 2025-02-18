## Definition

SSH (Secure Shell) is a protocol that allows secure remote login from one computer to another. It provides encrypted communication between two machines over an insecure network.

## SSH Command Usage

```bash
ssh [options] username@hostname
```

Example:

```bash

ssh user@example.com      # Logs in as 'user' on 'example.com'
ssh -p 2222 user@192.168.0.1  # Connects to IP '192.168.0.1' via port 2222
```

Advanced SSH Usage with Private Key

```bash

ssh -i /path/to/privateKey user@hostname

    -i /path/to/privateKey: Specifies the private key for authentication.
```

Example:

```bash

ssh -i ~/.ssh/id_rsa user@example.com
```

## 🔄 SSH Configuration Tips

To simplify SSH connections, you can add shortcuts in the ~/.ssh/config file:

```bash
Host my-server
  HostName example.com
  User user
  IdentityFile ~/.ssh/id_rsa
  Port 22
```

Now you can connect with:

```bash
ssh my-server
```
