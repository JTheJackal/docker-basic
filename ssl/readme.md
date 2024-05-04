Use mkcert to create a local certificate.

[i]mkcert -install[/i]
[i]mkcert localhost 127.0.0.1 ::1[/i]

Rename the files to cert.pem and cert-key.pem
Make sure the files are in this directory

Anything that exists in /src/ will be loaded into /var/www/html/ once the container runs.


Run with

docker-compose -f docker-compose.local.yml up -d