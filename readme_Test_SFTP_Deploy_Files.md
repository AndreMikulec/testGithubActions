# Github Actions deploy a file to an SFTP site
```
on: [push]

jobs:
    deploy_job:
    runs-on: ubuntu-latest
    name: deploy
    steps:
        - name: Checkout
        uses: actions/checkout@v2
        - name: Deploy file
        uses: wlixcc/SFTP-Deploy-Action@v1.2.4
        with:
            username: ${{ secrets.FTP_USERNAME }}
            server: ${{ secrets.FTP_SERVER }}
            port: ${{ secrets.FTP_PORT }}
            local_path: './static/*'
            remote_path: '/var/www/app'
            sftp_only: true
            password: ${{ secrets.FTP_PASSWORD }}
```
```
ssh_private_key	- REQUIRED:yes 
    You can copy private key from your 
    ssh_private_key.pem file, and save to repo/settings/secrets
password	REQUIRE:no		
    SSH passsword, If a password is set, 
    ssh_private_key is ignored. for @v1.2.4 and greater
```
```
JUL 17 2022 - IN ACTION
SFTP Deploy action
Use this action to deploy your files to server using SSH Private Key
JUL 2022
https://github.com/marketplace/actions/sftp-deploy
```

