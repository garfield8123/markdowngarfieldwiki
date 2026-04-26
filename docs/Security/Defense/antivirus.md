# Antivirus software

## Linux

### CLAMAV

```shell
sudo apt-get install clamav -y
mkdir clamAV
mkdir -p clamAV/db
cd clamAV
clamconf -g freshclam.conf > freshclam.conf
clamconf -g clamd.conf > clamd.conf
clamconf -g clamav-milter.conf > clamav-milter.conf
freshclam --config-file=freshclam.conf
sudo useradd 
sudo clamd --config-file=clamd.conf
```

### CLAM AV Scan
```shell
sudo clamdscan --config-file=clamd.conf <directory_path>
```