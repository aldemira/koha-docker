# koha-docker
This is an attempt to make a koha docker image for those who don't want to install gazillions of perl modules in their servers.

Start the container by:

* docker run --restart=always -e NO_MEMCACHED=true -v MYLOCALDIR:/var/lib/mysql -e INSTALL_LANG="tr-TR" -p 8081:8081 -p 8080:8080 -d --name koha --cap-add=SYS_NICE --cap-add=DAC_READ_SEARCH ghcr.io/aldemira/koha-docker:main

Get get the UI password

* docker exec -ti koha /opt/getpassword.sh

IMPORTANT: Do not forget to chown 101:101 MYLOCALDIR
