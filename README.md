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

Created 2 markdown file:
1. index.md
2. resume.md

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
6. Create 2 html pages:  
    1. index.html - journal of my cloud resume progress
    2. resume.html - my cloud resume page


## Challenges  
1. Need to create javascript for counter 
2. Need to change the custom URL for Cloudfront Distribution  
    - Need to create customize SSL with ACM  
    - updated the SSL to have both: www.serheang.com and resume.serheang.com  
3. How to ensure newly uploaded static html is being served immediately for verification  
    - Invalidate the AWS Cloudfront: `aws cloudfront create-invalidation --distribution-id <cloudfront distribution id> --paths "/*"`  
4. Need to find a proper CSS style guide for my pandoc-markdown conversion.
    > Will need to adapt a few of the css style that I found (which I had checked into here)
5. Time to do the work and study about JS/python
