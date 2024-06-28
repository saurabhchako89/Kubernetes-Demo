-- Create a symmetric encryption key pair
ssh-keygen   

-- Create Assymmetric encryption key pair
openssl genrsa -out my-key 1024
openssl rsa -in my-key -pubout > mykey.pub



