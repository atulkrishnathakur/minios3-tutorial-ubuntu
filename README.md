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

# check the minio version
```
atulkrishnathakur@atul-pc:~$ minio --version
minio version RELEASE.2026-09-19T17-05-25Z (commit-id=cea38c7e83d1ebafea7b9b5d1be53878deaa9772)
Runtime: go1.26.6 linux/amd64
License: MinIO AIStor License
Copyright: 2015-2026 MinIO, Inc.
atulkrishnathakur@atul-pc:~$ 

```

# create directory for storage
```
atulkrishnathakur@atul-pc:~$ sudo mkdir /mnt/minios3data
```

# change the permission
```
atulkrishnathakur@atul-pc:~$ sudo chmod u+rxw /mnt/ /usr/local/bin/minio
atulkrishnathakur@atul-pc:~$ sudo chown -R minio-user /mnt/ /usr/local/bin/minio

```

