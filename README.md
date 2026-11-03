# Download and install
1. Run the below command
```
atulkrishnathakur@atul-pc:~$ curl --progress-bar -L dl.min.io/aistor/minio/release/linux-amd64/minio.deb -o minio.deb
sudo dpkg -i minio.deb
```


```
################################################################################################################################################################################# 100.0%################################################################################################################################################################################# 100.0%
(Reading database… 234437 files and directories currently installed.)
Preparing to unpack minio.deb…
Unpacking aistor (20260919170525.0.0) over (20260919170525.0.0)…
Setting up aistor (20260919170525.0.0)…

================================================================================
  MinIO Installation Complete
================================================================================

  1. Configure MinIO volumes in /etc/default/minio:

     sudo vi /etc/default/minio

     Set:
       MINIO_VOLUMES="http://node{1...4}/mnt/data{1...4}"

  2. Configure credentials in /etc/minio/config.env:

     sudo vi /etc/minio/config.env

     Set:
       MINIO_ROOT_USER=<your-admin-user>
       MINIO_ROOT_PASSWORD=<your-admin-password>

  3. Start MinIO:

     sudo systemctl start minio

  4. Enable MinIO to start on boot:

     sudo systemctl enable minio

  5. Check status:

     sudo systemctl status minio

  Documentation: https://docs.min.io/aistor/installation/linux/

================================================================================

```
   
# set the below configuration 
1. run the command
   ```
      atulkrishnathakur@atul-pc:~/Downloads$ sudo vi /etc/default/minio
   ```
2. change or add the configuration
```
## Volume to be used for MinIO server.
##
 MINIO_VOLUMES="/home/atulkrishnathakur/minios3data"

## Use if you want to run MinIO on a custom port.
## add --address and --console-address to MINIO_OPTS:
# MINIO_OPTS="--address :9000 --console-address :9001 [OTHER_PARAMS]"
#
MINIO_OPTS="--address :9000 --console-address :9001"


## Root User credentials (Required for MinIO to start)
MINIO_ROOT_USER="minioadmin"
MINIO_ROOT_PASSWORD="minioadmin"

## Point to the main configuration file
# MINIO_CONFIG_ENV_FILE=/etc/minio/config.env

```

# Create the directory
```
atulkrishnathakur@atul-pc:~/Downloads$ sudo mkdir /mnt/minios3data
```


# Run below command for ownership and permission
```
atulkrishnathakur@atul-pc:~/Downloads$ sudo chmod u+rxw /mnt/ /usr/local/bin/minio
atulkrishnathakur@atul-pc:~/Downloads$ sudo chown -R minio-user /mnt/ /usr/local/bin/minio

```
