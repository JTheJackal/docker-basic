<h1>Basic Docker Container</h1>

<ul>

  <li>Apache2</li>
  <li>Ubuntu 20.04</li>
  <li>PHP 7.4</li>
  <li>SSL Support</li>
</ul>

<h3>Configuration</h3>

Use Dockerfile.local to add or alter any of the configuration, such as the PHP version, add node.js, etc.

<h3>Running locally in HTTPS</h3>

SSL support is in place, so localhost can be easily ran in HTTPS. 

<ol>
  <li>Install mkcert on your machine</li>
  <li>Run <code>mkcert -install</code></li>
  <li>Run <code>mkcert localhost 127.0.0.1 ::1</code></li>
  <li>Rename the files to cert.pem and cert-key.pem</li>
  <li>Make sure the files are in the ssl directory</li>
</ol>

<h3>Mounting your application</h3>

<p>All of your application files should be placed in the /src folder. Application files placed anywhere else, such as root, will be ignored.</p>
<p>When the container runs, it will take everything you have placed in /src and place it in /var/www/html/ in the Apache directory so it can be served.</p>

<h3>Changing ports</h3>

<p>If the default port is in use, you can change the port number in the following files:
<ul>
<li>docker-compose.local.yml</li>
<li>Dockerfile.local</li>
</ul>

<h3>Running the container</h3>

<p>Run the container with <code>docker-compose -f docker-compose.local.yml up -d</code></p>
<p>By default, your site will be accessible at https://localhost:1443</p>
<p></p>
<p>If you changed the port numbers in docker-compose.local.yml and Dockerfile.local, your site will be accessible at https://localhost:[port]
