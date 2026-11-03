# Download minio s3 for ubuntu
1. open url https://dl.min.io/aistor/minio/release/linux-amd64/
2. click on minio.deb file

# install minios3
1. go to Downloads by `cd ~/Downloads`
2. Run the command `sudo dpkg -i minio.deb`
   ```
[sudo] password for atulkrishnathakur: 
Selecting previously unselected package aistor.
(Reading database… 234432 files and directories currently installed.)
Preparing to unpack minio.deb…
Unpacking aistor (20260919170525.0.0)…
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
   

