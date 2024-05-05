Use mkcert to create a local certificate.

mkcert -install
mkcert localhost 127.0.0.1 ::1

Rename the files to cert.pem and cert-key.pem
Make sure the files are in this directory

Anything that exists in /src/ will be loaded into /var/www/html/ once the container runs.

Dockerfile.local can be edited to include what you want to load i.e. use PHP 8.2 instead of 7.4, add MySQL, etc.


Run with

docker-compose -f docker-compose.local.yml up -d
