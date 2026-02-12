# k3d

## Requirements

### You need a Server

- Create one using the slackbot in `#developer-workspaces` or provision your own ad-hoc Server on a cloud of your choice

- Clone your captain
- `cd` into your _captain_
  
Run:
```bash
curl https://raw.githubusercontent.com/GlueOps/k3d/main/k3d-config.yaml -o k3d-config.yaml && k3d cluster create --config k3d-config.yaml && bash <(curl -sL https://raw.githubusercontent.com/GlueOps/k3d/main/add-machineid.sh)
```

Run the request for new chisel nodes and then take the output to run against your k3ds cluster: https://tools.glueopshosted.rocks/docs#/default/create_chisel_nodes_v1_chisel_post


