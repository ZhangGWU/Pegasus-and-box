## Step-by-step guidance on how to connect rclone to Box account
-------------------------------------------------------------------------------------------
### Why r-clone? 
For sequencing data and its analysis, we need to move files between different clouds, r-clone enable us to move these big files without download them to local desktop. 
### 1. Configuration in rclone

#### 1.1 In the terminal run:
```
rclone config
```
#### 1.2 Select:  
n for new remote
#### 1.3 Name the remote: 
mybox; you can name it anything
#### 1.4 Choose the storage type: 
Scroll and find **Box**
#### 1.5 Client ID/Secret: 
when asked, just press **Enter** to use rclone's built-in Box app. 
#### 1.6 Advanced Config: 
press **n**.
#### 1.7 Auto config: press **y**
It will open your web browser and ask you to login into Box and approve access.
#### 1.8 Authorize and finish: 
After approve log in, close the browser window. Configuration should be done. 


### 2. Test the connection
After setup, run:
```
rclone lsd mybox:
```
### 3. Move files 
Upload a file:
```
rclone copy myfile.txt mybox:/path/in/box
```

Download a file:
```
rclone copy mybox:/path/in/box /local/path
```

Sync a local file: 
```
rclone sync /local/folder mybox:/remote/folder
```
