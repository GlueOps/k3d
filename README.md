# k3d

## Requirements

### You need a Server/VM

- Option #1 - A cloud server that is either debian/ubuntu. You can use [AWS](https://cde.glueops.dev) or [Hetzner](https://www.hetzner.com/) or any other cloud. It's recommended you have at least 16GB of RAM but 32-64GB would be optimal.
- Option #2 - Proxmox. (Recommended)
  
### Getting setup

- Login to your server using whatever method you like (SSH or password is fine) but you must login with a root or a user that has sudo access.
- Run:

  ```bash
  #If you are using proxmox you will not be able to do copy/paste in the web ssh console.
  bash <(curl -sL setup.glueops.dev)
  ```

- Once you finish following the prompts and the server reboots, you will need to connect to it using your private ssh key with the `vscode` username. If you are using proxmox the username is `root` and you will need to switch to `vscode` using: `su - vscode`
- Once logged in as the `vscode` user, type `cd` so that you are in `/home/vscode` and then just run `dev` and select the version you want (newest is recommended) and go ahead and get started to get a code tunnel/space going.

### Creating your cluster

- `cd` into your _captain_ directory
- Run:

```bash
curl https://raw.githubusercontent.com/GlueOps/k3d/main/k3d-config.yaml -o k3d-config.yaml && k3d cluster create --config k3d-config.yaml && bash <(curl -sL https://raw.githubusercontent.com/GlueOps/k3d/main/add-machineid.sh)
```

- Using our **lightsail AWS account** run this from a cloudshell session:

```bash
bash <(curl -s https://raw.githubusercontent.com/GlueOps/development-only-utilities/main/tools/aws/lightsail.sh)
```

- Take the output from the lightsail creation and run it against your k3s cluster.
- Continue with the rest of the docs in your captain README.md
