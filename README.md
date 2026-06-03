# openssl

1. Generate RSA Private Key
  => openssl genrsa -out private.key 2048

    1.1 . To display the details of an RSA private key:
       => openssl rsa -in private.key -text -noout

2. Generate Public Key
   => openssl rsa -in private.key -pubout -out public.key

    2.1. To display the details of an public key:
	=> openssl rsa -pubin -in public.key -text -noout
3. Create Certificate (CSR)
    => openssl req -new -key private.key -out request.csr

4.  To view the contents of a CSR (Certificate Signing Request)
   => openssl req -in request.csr -text –noout

5. Generate a Self-Signed Certificate
 => openssl req -x509 -new -key private.key -out certificate.crt -days 365

6. View Certificate Expiration Date
  => openssl x509 -in certificate.crt -noout –enddate

 to verify certificate:-   => openssl verify certificate.crt

8. Encrypting a File with OpenSSL
 => openssl enc -aes-256-cbc -in file.txt -out file.enc

9.Decrypting the File 
   =>openssl enc -d -aes-256-cbc -in file.enc -out file.txt

10. Create Hash file  using SHA-256
    => openssl dgst -sha256 hash_file.txt

