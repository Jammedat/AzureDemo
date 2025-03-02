## Deploy your app in Azure using HTTPD
1. Create a VM
2. Add an inbound rule to allow HTTP traffic -> Network Security Group ->  Crete port rule -> service -> HTTP
3. Login to the VM from AzureCLI or GitBash
4. Switch to root user:
   
   ```
   sudo su -
   ```
6. Update OS system files:
   
   ```
   sudo apt update -y
   ```
7. Install git if not installed and clone the GitHub repo where your app is

## Install the apache web sever

```
sudo apt install apache2 -y
```
## Apache will only host your app if and only if you app is in /var/www/html Directory.
### So copy the files and folders to this directory:

Copy files:
```
cp <file_name> /var/www/html
```

Copy folders:
```
cp -r <folder_name> /var/www/html
```

## Now change the directory to /var/www/html

## Then start the service as:
```
sudo systemctl start apache2
sudo systemctl enable apache2
```

## Check the service as:
```
sudo systemctl status apache2
```

## Hurray now you can access your app through the public ip of your VM.
