# Compress Image on the fly using AWS Lambda and Node

More details at: https://coderecipe.ai/architectures/47740119

**Problem Statement**

I’m working on an on a very image-heavy website where users upload lots of their own content. As any web-developer knows: large, slow loading images can be the easiest way to make your website look slow and destroy the UX, no matter which lightning-fast front-end framework or cloud content delivery network you have.
  

**Solution**

I decided to use **AWS Lambda** to automate the process of compressing the images. Lambda is a pay-as-you-go service that lets you run code without provisioning or managing servers, and is an extremely **cost effective** way of relieving load off your own servers.


## Prerequisites
npm install serverless-pseudo-parameters

npm install serverless-iam-roles-per-function


Note:
If deploying from a non linux machine (osx, etc), npm install with docker so that the native extensions required are installed properly: `docker run --rm -v $PWD:/data -w /data node:8.10 npm install imagemin imagemin-mozjpeg`


## Deploy
`serverless deploy --stage <stage-name> --COMPRESSED_BUCKET_NAME <name-of-the-bucket-that-stores-compressed-images> --UNCOMPRESSED_BUCKET_NAME <name-of-the-bucket-that-stores-uncompressed-images>`
