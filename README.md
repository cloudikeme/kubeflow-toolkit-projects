# Kubeflow Project Setup

On windows (no wsl )

1. I started by setting up project and Debian VM on on google cloud console. Note external IP of your VM

2. Generate ssh keys ( we name it id_rsa) on windows powershell (Note the output paths for both private and public keys)

3. On google cloud console , copy pub ssh key value and add to VM securityy ssh access "add item"

4. on local windows computer, 
open Vscode - and install Remote ssh extension

open powershell as Admin and run:
```bash 
Start-Process notepad.exe -ArgumentList "C:\Users\Victo\.ssh\config" -Verb RunAs
```

edit or add this to your config file, replace ip with your Cloud VM IP and identity file to the location of tour id_rsa ssh keys we created earlier:

```bash
Host 34.42.30.50
  HostName 34.42.30.50
  IdentityFile C:\Users\cloudikeme\.ssh\id_rsa
  User cloudikeme
  ```

Open Vscode , Remote access connect to host, select your newly added IP from  the lists and connect by following the prompt

, you shouldf now have a sure connection to your VM on your local computer.

In my remote vm:

i install Docker Engine
Install Devbox
Do devbox init , replace devbox.json content with my own config n tools
