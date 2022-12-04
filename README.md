# AWS_CloudResumeChallenge
Challenge to put my Resume onto AWS according to the [Forrest Brazeal Cloud Resume Challenge here](https://cloudresumechallenge.dev/docs/the-challenge/aws/).  

## URL to my resume  
[Here](https://resume.serheang.com/) is a placeholder of the site that would be my future AWS Cloud Resume.  
  > Note: I got my own domain name - HOORAY!

## Converting markdown to html  
I am using `pandoc` to convert my markdown text into html page(s).  Here is the command I used to generate the `index.html`:  
```
pandoc index.md -f markdown -t html -s -o index.html --metadata title="Ser Heang TAN"  
```
> Note: 
> -f --> source file format 
> -t --> target file format 
> -s --> standalone 
> -o --> Output filename 
> --metadata title="" --> apply the "title" as metadata to the html page  

## Steps to build my resume on AWS
1. Create AWS Free tier account
   1. Secure AWS Root account
   2. Create AWS IAM Account
   3. Enable MFA
2. Create S3 bucket
   1. Ensure it is locked from public  
3. Create AWS CloudFront distribution  
4. Register domain with AWS Route 53  
5. Update AWS CloudFront distribution to use my domain (created in above step)  


