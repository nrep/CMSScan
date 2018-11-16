# CMSScan
Scan Wordpress, Drupal, Joomla, vBulletin websites for Security issues.

[![platform](https://img.shields.io/badge/platform-osx%2Flinux-green.svg)](https://github.com/ajinabraham/CMSScan/)
[![License](https://img.shields.io/:license-gpl3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.html)
[![python](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/)

Made with ![Love](https://cloud.githubusercontent.com/assets/4301109/16754758/82e3a63c-4813-11e6-9430-6015d98aeaab.png) in India

CMSScan provides a centralized Security Dashboard for CMS Security scans. It is powered by wpscan, droopescan, vbscan and joomscan. It supports both on demand and scheduled scans and has the ability to sent email reports.

## Install
```
# Requires python3 and git
git clone https://github.com/ajinabraham/CMSScan.git
cd CMSScan
./setup.py
```
## Run

`./run.sh`

## Periodic Scans

You can perform periodic CMS scans with CMSScan. You must run CMSScan server separately and configure the following before running the `scheduler.py` script.

```
# SMTP SETTINGS
SMTP_SERVER = ''
FROM_EMAIL = ''
TO_EMAIL = ''

# SERVER SETTINGS
SERVER = ''

# SCAN SITES
WORDPRESS_SITES = []
DRUPAL_SITES = []
JOOMLA_SITES = []
VBULLETIN_SITES = []
```

Add a cronjob

```
crontab -e
@weekly /usr/bin/python3 scheduler.py
```

## Docker

### Local
```
docker build -t cmsscan .
docker run -it -p 7070:7070 cmsscan
```

### Prebuilt Image

```
docker pull opensecurity/cmsscan
docker run -it -p 7070:7070 opensecurity/cmsscan
```

### Screenshots


![](https://user-images.githubusercontent.com/4301109/48620839-855c9100-e9c7-11e8-97c6-1e25252d2d01.png)
![](https://user-images.githubusercontent.com/4301109/48620970-03b93300-e9c8-11e8-9962-714e8fea2c6c.png)
![](https://user-images.githubusercontent.com/4301109/48620969-03209c80-e9c8-11e8-9d88-1a12b216368e.png)
