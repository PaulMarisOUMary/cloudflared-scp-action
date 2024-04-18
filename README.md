# Cloudflared SCP

A barebones github action that lets you scp into a server behind a cloudflare tunnel

## Usage

Here is an example deploy.yaml file for the action:  
```yaml
name: Pull down and compose up
on: [push]
jobs:

  transfer:
    name: Transfer file to remote server
    runs-on: ubuntu-latest
    steps:
    - name: Connect to remote server
        uses: PaulMarisOUMary/cloudflared-scp-action@main
        with:
          host: ${{ secrets.HOST }}
          username: ${{ secrets.USERNAME }}
          private_key: ${{ secrets.PRIVATE_KEY }}
          port: ${{ secrets.PORT }}
          from: local_dir
          to: target_dir
```
