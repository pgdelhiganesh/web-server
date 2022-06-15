# File Transfer Between Local and Remote Server via SSH Connection
\
**Run the below commands in CMD prompt**
\
If files not transfered/copied due to permission denied, then run ***sudo chmod 777 /etc/your/folder/*** for your remover server folder.



## Upload file from local to remote server
> pscp -i <local_putty_ppk_file_path> <local_file_path> <server_username@ip_address:sever_folfer_path>
```
pscp -i C:\Users\IIoT-DG\Desktop\test\Linux-kp.ppk C:\Users\IIoT-DG\Desktop\test\filename.zip ubuntu@100.0.0.101:/var/www/mywebsite.com/html
```

## Upload folder (entire directory) from local to remote server
> pscp -i <local_putty_ppk_file_path> <local_folder_path> <server_username@ip_address:sever_folfer_path>
```
pscp -i C:\Users\IIoT-DG\Desktop\test\Linux-kp.ppk -r C:\Users\IIoT-DG\Desktop\test ubuntu@100.0.0.101:/var/www/mywebsite.com/html
```

## Download file from remote server to local
> pscp -i <local_putty_ppk_file_path> <server_username@ip_address:sever_file_path> <local_folder_path>
```
pscp -i C:\Users\IIoT-DG\Desktop\test\Linux-kp.ppk ubuntu@100.0.0.101:/var/www/mywebsite.com/html/filename.zip C:\Users\IIoT-DG\Desktop\test\
```

## Download folder (entire directory) from remote server to local
> pscp -i <local_putty_ppk_file_path> <server_username@ip_address:sever_folfer_path> <local_folder_path>
```
pscp -i C:\Users\IIoT-DG\Desktop\test\Linux-kp.ppk -r ubuntu@100.0.0.101:/var/www/mywebsite.com/html C:\Users\IIoT-DG\Desktop\test\
```
\
\
\
**-------------------------------------------------**
\
**Delete file in remoter server**
> rm myFile.txt

**Delete folder (entire directory) in remote server**
> rm -rf foldername/

**Delete all file/folder in remote server**
> rm -rf *"
  
**-------------------------------------------------**
