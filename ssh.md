## Steps to SSH into EC2 Instance on AWS from PowerShell

- First create a Key-pair in PS
  ``` ssh-keygen -t ed25519 ```

- Get your public key
  ``` Get-Content ~/.ssh/id_ed25519.pub ```

- Add your new public key to EC2. Inside the EC2 instance:
  ``` vim ~/.ssh/authorized_keys ```

- Paste the Public Key in File
- In your PS, copy paste the ssh command from AWS

### Diagramatic Flow

  Windows PowerShell
       │
       │  1. Create key pair
       ▼
~/.ssh/id_ed25519          ← Private key
~/.ssh/id_ed25519.pub      ← Public key
       │
       │  2. Copy PUBLIC key
       ▼
AWS EC2
~/.ssh/authorized_keys
       │
       │  3. SSH using PRIVATE key
       ▼
Windows PowerShell ────────→ EC2
