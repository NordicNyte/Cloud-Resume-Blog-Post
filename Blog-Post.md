# Completing the Cloud Resume Challenge: What Did I Learn?

## Embracing the Challenge
Over the Fall 2024 semester, I completed the Cloud Resume Challenge. When my Networking and Cloud Computing professor introduced it, I was both excited and nervous. He warned us about the complexity of connecting all the pieces, saying that people often fail. This wasn’t just about building a resume, it was about diving deep into professional cloud tech. It combined web development, cloud services, and DevOps practices into a single project.

The goal was to create an interactive online resume hosted in the cloud, complete with a visitor counter, HTTPS, Infrastructure as Code, and a CI/CD pipeline. Along the way, I learned far more than technical skills. This project encouraged me to think critically and take charge of my own learning. Here’s what I discovered about the tools and services I used, why they mattered, and how this experience shaped me.

--- 

## The What and Why Behind the Challenge

The Cloud Resume Challenge wasn’t just about making a fancy resume. It was about proving I could learn modern tech and create something meaningful. 

The challenge required me to:

## - Host my resume on AWS.
## - Add a JavaScript-based visitor counter backed by a database.
## - Use infrastructure as code (IaC) for deployment.
## - Automate workflows with CI/CD pipelines.
  
This project helped me showcase my ability to use tools that professional cloud engineers rely on. It also highlighted the importance of applying technical skills to solve real-world problems.

--- 

## My Experience

### Amazon S3 and CloudFront: Hosting and Delivery

To host my resume, I used Amazon S3, a simple, scalable storage service (the name makes sense now). S3 made it easy to upload and “curate” the content for my website: HTML, CSS, and JavaScript. It was super straightforward to use: upload the files, test the code, and the site was basically “live”.
To make sure my site loaded quickly, I paired S3 with CloudFront, AWS’s content delivery network. CloudFront saved my website files on servers around the world, allowing users to access the site faster, no matter where they were. It also enforced HTTPS, keeping the connection secure.

### Route 53 and Buying My Domain

While my S3 bucket did serve my website content, to make my resume accessible online, I needed a custom domain name. Simply put, I “bought myself”. I purchased "aidantaggart.com" from Namecheap at a great price. Afterward, I used AWS Route 53 to connect the domain to my cloud-hosted resume. That way, my content would appear if someone searched up my website.
Route 53 handled the DNS settings, which simply put, directs my visitors to my website when they typed in my domain name. It was my first time configuring DNS records like A and CNAME, and while it was a little confusing at first, I quickly learned how to set it up and connected it to my other AWS resources.

### DynamoDB: Managing Visitor Data

For the visitor counter, I needed a database that could handle frequent updates without slowing down. I chose AWS DynamoDB, a serverless NoSQL database, instead of a traditional SQL database. It was my first time working with NoSQL, and DynamoDB’s simplicity made it a great starting point.
I designed a table to store and retrieve the visitor count and connected it to my resume, which was so much more simple than creating an SQL db. Without the need for database normalization, and the simple storage format (Key/Value Pair) I was able to quickly establish the db without any issues the first time.

### API Gateway and Lambda: Backend Logic

To connect my visitor counter to DynamoDB, I used AWS API Gateway and Lambda functions. API Gateway acted as the “front door,” exposing visitors to my website, while Lambda handled the “backdoor” logic for updating the visitor counter.
Setting up Lambda was honestly tricky at first. Debugging the code without console logs was hilariously frustrating until I discovered AWS CloudWatch, which let me monitor and fix bugs so much more efficiently.

### Terraform: Infrastructure as Code

To manage my cloud resources, I used Terraform. With Terraform, I wrote scripts to automate the creation and updates of resources like my S3 buckets, Lambda function, and API Gateway endpoints. This saved time and ensured everything was consistent. One of the best things about Terraform is that the script (HCL) is simple English with some formatting.

However, getting Terraform to work wasn’t actually that easy. Small mistakes, like incorrect file extensions or incorrect implementation of authentication keys, caused hours of headache. Once I overcame these hurdles, Terraform became super valuable. I was able to automate changes to my front end code and backend code. This meant I didn’t have to manually upload newly updated code though the AWS console UI, then wait to see if the update worked. I was able to do automated code testing before it was uploaded using both Terraform and Playwright.

### GitHub Actions: Automating Workflows

To automate my workflow, I set up a CI/CD pipeline using GitHub Actions. With this setup, every time I pushed changes to my repository, GitHub Actions automatically tested the updates and deployed them to AWS. This automation saved time and reduced the risk of errors. Watching my code move seamlessly from development to production without manual intervention was also incredibly satisfying.

---

## Reflections and Takeaways

Working on this project was challenging but rewarding. There were moments of frustration, like debugging Terraform scripts at 2am or troubleshooting Lambda functions that wouldn’t update properly. Despite these obstacles, every problem I solved gave me a sense of accomplishment and built my confidence.

## Key Lessons Learned:

### - Planning Is Crucial: Breaking the project into smaller tasks kept me organized and motivated.

### - Documentation Matters: Reading AWS documentation and following my professor’s guides helped me troubleshoot effectively.

### - Failure Is Part of Growth: Every error I encountered taught me something new, turning setbacks into learning opportunities.

This project reaffirmed my passion for problem-solving and learning new tech. It showed me the importance of patience, curiosity, and self-directed learning when tackling new challenges. The Cloud Resume Challenge wasn’t just a technical exercise, it was a personal and professional milestone that prepared me for future projects and roles surrounding cloud tech.

