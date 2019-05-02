# Compress Image on the fly using AWS Lambda and Node

More details at: https://coderecipe.ai/architectures/47740119

**Problem Statement**

I’m working on an on a very image-heavy website where users upload lots of their own content. As any web-developer knows: large, slow loading images can be the easiest way to make your website look slow and destroy the UX, no matter which lightning-fast front-end framework or cloud content delivery network you have.
  

**Solution**

I decided to use **AWS Lambda** to automate the process of compressing the images. Lambda is a pay-as-you-go service that lets you run code without provisioning or managing servers, and is an extremely **cost effective** way of relieving load off your own servers.


## Prerequisites
```console
npm install serverless

export AWS_ACCESS_KEY_ID=<your-key-here>

export AWS_SECRET_ACCESS_KEY=<your-secret-key-here>
```

## Deploy
```console
serverless create --template-url https://github.com/CodeRecipe-dev/ImageCompressor-AWS --path image-compression

cd image-compression

npm install

serverless deploy --stage sample --COMPRESSED_BUCKET_NAME coderecipe-images-compressed --UNCOMPRESSED_BUCKET_NAME coderecipe-images-uncompressed

```