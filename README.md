Forked from https://github.com/bogem/dockerfiles, but as that is a folder of other containers, I've split this out seperately.

I've then removed the VOL commands from the Dockerfile as I don't want them created.

Simple ftp server based on vsftpd.
Minimalistic clone of [fauria/vsftpd](https://hub.docker.com/r/fauria/vsftpd/).

# Usage
	$ docker run -d -v <host folder>:/home/vsftpd \
					-p 20:20 -p 21:21 -p 47400-47470:47400-47470 \
					-e FTP_USER=<username> \
					-e FTP_PASS=<password> \
					-e PASV_ADDRESS=<ip address of your server> \
					--name ftp \
					--restart=always bogem/ftp
