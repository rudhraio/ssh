## Worke SSH 

This script allows you to execute SSH commands on a remote server using various authentication methods (password or SSH key).

## Usage

### Inputs

| Input Parameter         | Description                                                     | Default Value |
|-------------------------|-----------------------------------------------------------------|---------------|
| host                    | SSH host address                                                |               |
| user                    | SSH username                                                    |               |
| key                     | SSH private key                                                 |               |
| password                | SSH password                                                    |               |
| passphrase              | SSH key passphrase                                              |               |
| commands                | List of commands to execute on the server.                      |               |
| port                    | SSH port number                                                 | 22            |
| name                    | Server name or identifier                                       | server        |

### Sample code
Executing remote ssh commands.

```yaml
name: remote ssh command
on: [push]
jobs:
  deploy:
    name: deploy
    runs-on: ubuntu-latest
    steps:
    - name: executing remote ssh commands using key
      uses: rudhraio/ssh@v1
      with:
        host: ${{ secrets.HOST }}
        user: ${{ secrets.USER }}
        key: ${{ secrets.KEY }}
        commands: |
            whoami
            ls -l
```
