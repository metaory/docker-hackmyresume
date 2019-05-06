# docker-hackmyresume

hackmyresume on Alpine Linux

![License](https://img.shields.io/badge/License-GPLv3-blue.svg)
![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/jsloan117/hackmyresume.svg)
![Docker Build Status](https://img.shields.io/docker/cloud/build/jsloan117/deluge.svg)
[![Docker Pulls](https://img.shields.io/docker/pulls/jsloan117/hackmyresume.svg)](https://img.shields.io/docker/pulls/jsloan117/hackmyresume.svg)
[![](https://images.microbadger.com/badges/image/jsloan117/hackmyresume.svg)](https://microbadger.com/images/jsloan117/hackmyresume "Get your own image badge on microbadger.com")

Docker container that allows you to generate multiple output formats using hackmyresume. Please see [HackMyResume](https://github.com/hacksalot/HackMyResume) for all other things you can do with this application.

## Run container from Docker registry

The container is available from the Docker registry and this is the simplest way to get it.
To run the container use this command:

```bash
docker run --rm --name=hackmyresume -it \
-v resumes:/resumes \
-v /pathtoyourresume/resume.json:/resumes/resume.json \
jsloan117/hackmyresume:latest hackmyresume build /resumes/resume.json /resumes/resume.pdf \
-t /usr/lib/node_modules/jsonresume-theme-eloquent
```

```bash
docker run --rm --name=hackmyresume -it \
-v resumes:/resumes \
-v /pathtoyourresume/resume.json:/resumes/resume.json \
jsloan117/hackmyresume:latest hackmyresume build /resumes/resume.json /resumes/resume.pdf \
-t /usr/lib/node_modules/your-jsonresume-theme-name
```

## Obtaining the generated resume

```bash
ls -lh /var/lib/docker/volumes/resumes/_data/
total 904K
-rwxr-xr-x 1 root root    0 Feb 19 15:47 resume.json
-rw-r--r-- 1 root root 795K Feb 19 15:48 resume.pdf
-rw-r--r-- 1 root root 107K Feb 19 15:48 resume.pdf.html
```

## Installed [jsonresume](https://jsonresume.org/themes/) themes

| Theme Name                       |
|:--------------------------------:|
| `jsonresume-theme-eloquent`      |
| `jsonresume-theme-elegant`       |
| `jsonresume-theme-paper`         |
| `jsonresume-theme-kendall`       |
| `jsonresume-theme-modern`        |
| `jsonresume-theme-classy`        |
| `jsonresume-theme-class`         |
| `jsonresume-theme-short`         |
| `jsonresume-theme-slick`         |
| `jsonresume-theme-kwan`          |
| `jsonresume-theme-onepage`       |
| `jsonresume-theme-spartan`       |
| `jsonresume-theme-stackoverflow` |

## Use theme not installed

```bash
docker run --rm --name=hackmyresume -it \
-v resumes:/resumes \
-v /pathtoyourresume/resume.json:/resumes/resume.json \
jsloan117/hackmyresume:latest /bin/bash -c 'npm install -g jsonresume-theme-flat && hackmyresume build /resumes/resume.json /resumes/resume.pdf -t /usr/lib/node_modules/jsonresume-theme-flat'
```
