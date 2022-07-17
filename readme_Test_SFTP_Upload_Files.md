# Github Actions upload a file to an SFTP site

```
on: [push]

jobs:
  upload_files:
    runs-on: ubuntu-latest
    name: Upload a builded file.
    steps:
    - name: Checkout
      uses: actions/checkout@v2.3.4
    - name: Upload Files
      id: upload
      uses: Creepios/sftp-action@v1.0.3
      with:
        host: '127.0.0.1'
        port: 22
        username: 'root'
        password: 'password'
        localPath: './dist/index.js'
        remotePath: './'
```
JUL 2022

sftp-action

This action can (currently only) upload files and directories over sftp with ssh login.

https://github.com/marketplace/actions/sftp-ssh-action
