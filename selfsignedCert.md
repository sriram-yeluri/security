# How to create a self signed certificate for personal/internal use

Having a SSL certificate is worth than having no certificate at all.

```sh
openssl req -new -newkey rsa:4096 -x509 -days 365 -nodes -out MyCertificate.crt -keyout MyKey.key
```

## Result

```
Generating a 4096 bit RSA private key
................................++
.....................++
writing new private key to 'MyKey.key'
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) []:NL
State or Province Name (full name) []:Holland
Locality Name (eg, city) []:Amsterdam
Organization Name (eg, company) []:mylearning
Organizational Unit Name (eg, section) []:IT
Common Name (eg, fully qualified host name) []:mycertificate.example.com
Email Address []:reachme@somewhere.com
```

## Permissions

Once the certificate and key are generated, change the permissions of the key to 400
```sh
chmod 400 MyKey.key
```
