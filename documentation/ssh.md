#Understand SSH
##What is SSH?
-SSH, which stands for Secure Shell, it is a protocol that sets up remote encrypted connections between computers. It also enables tunneling. It is a cryptographic network protocol that creates a secure, encrypted connection between two computers over an unsecured network like the internet. SSH involves using cryptography to authenticate (verify identity) and encrypt connections amongst devices. SSH monitors servers remotely, controls infrastructure and allows transferring files between devices. 
##Why is SSH important to Cloud Engineers?
It provides Engineers with encrypted remote access (cloud virtual machines), SSH uses asymmetric cryptography (private and public keys) to identify the identity of the cloud engineer by encrypting raw credentials from across the network. It helps manage tools like configuration tools and automate routine maintenance across multiple servers. Assist in securely moving configuration files, backups and application code between local machines and cloud server.
##Which port does SSH normally use?
SSH (Secure Shell) normally uses TCP port 22. SSH use TCP port 22 which allows it to authenticate, encrypt, and provides integrity to protect data send over unsecured networks.
##What is authentication?
Authentication is the process of confirming a client's, device's, or system's identity to confirm they are who they claim to be. It addresses the question "Who are you?" as to confirm the identity of the user.
##What is the difference between password authentication and SSH-key authentication?
The main difference is how identity is proven. Password authentication it based on a shared secret a client must recall and input to be granted access and SSH-key authentication is based on public-private key pair generated cryptographically whereby a client has to prove the ownership of the secret key without revealing it to the network. 
##Where is your private key stored?
The private key is a separate file that’s used in the encryption/decryption of data sent between your server and the connecting clients. A private key is stored locally on the specific device, server, or hardware system where it was generated.
###Apache
Your private key file’s location will be referenced in the main Apache configuration file, which is httpd.conf or apache2. conf. OpenSSL, the most popular SSL library on Apache, will save private keys to /usr/local/ssl by default.
###Nginx
You will be able to find the private key’s location in your site’s virtual host file. Navigate to the server block for that site (by default, within the /var/www/ directory). 
###Windows (IIS)
On Windows servers, the OS manages your certificate files for you in a hidden folder, but you can retrieve the private key by exporting a “.pfx” file that contains the certificate(s) and private key.
##Why must a private key never be committed to GitHub?
A private key must never be committed to GitHub because doing so permanently compromises the security of the systems it protects, exposing them to malicious access, automated scraping, and architectural vulnerabilities.
When you execute an SSH connection, what is actually happening between your computer and the Linux server? You should understand the process rather than simply know the command.
When you run a command like ssh user@server_ip, a secure connection is being established. The established connection shifts from an unsecured public network to a highly encrypted, authenticated private connection. They establish a network connection, agree on encryption methods, validate identities, exchange cryptographic keys, and generate a secure communication path.
The secure shell reduces the risk by using encryption mechanism which are intentionally used to encrypt contents of transmission from an observer, whether the observer has access to the entire data stream. 

