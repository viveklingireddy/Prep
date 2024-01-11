[Amplify Hosting](https://aws.amazon.com/amplify/hosting/) is a service provided by Amazon Web Services (AWS) that allows developers to deploy static web applications with ease. It's a part of AWS Amplify, a suite of tools for building scalable full-stack applications.

Key features of Amplify Hosting include:

1. **Static Web Hosting:** Amplify Hosting simplifies the deployment process for static web applications, including single-page apps, static websites, or frontend frameworks like React, Angular, Vue.js, and more.

2. **Continuous Deployment:** It enables continuous deployment through integrations with version control systems (such as GitHub, GitLab, Bitbucket) or directly through the Amplify CLI. Changes pushed to your repository trigger automatic builds and deployments.

3. **Global Content Delivery:** Amplify Hosting leverages Amazon CloudFront, AWS's content delivery network (CDN), for global content distribution, improving the performance and scalability of your application.

4. **Custom Domains and HTTPS:** You can easily set up custom domains for your web applications, and Amplify Hosting provides built-in SSL certificate management to ensure secure connections using HTTPS.

5. **Branch Deployments and Previews:** Create separate deployment environments for different branches of your codebase. This allows you to test changes in isolated environments before merging them into the main production environment.

6. **Deployment Hooks and Workflows:** Customize deployment workflows with deployment hooks and scripts, enabling you to execute custom actions before or after deployment stages.

7. **CI/CD Integrations:** Amplify Hosting seamlessly integrates with various CI/CD pipelines, providing flexibility and automation in the deployment process.

8. **Scalability and Cost-Effectiveness:** It offers scalable hosting solutions that automatically handle traffic spikes and provide cost-effective solutions for hosting static content.

Amplify Hosting simplifies the deployment and hosting of static web applications, making it suitable for developers who want to focus on building their applications without worrying about managing servers or infrastructure.

To learn more about Amplify Hosting, its features, documentation, pricing, and getting started guides, you can visit the official [Amplify Hosting page](https://aws.amazon.com/amplify/hosting/).
![awsamplify](https://d1.awsstatic.com/AWS%20Amplify/Features/product-page-diagram_Amplify_How-it-works_Deliver%402x%20(1).26991c2935dc23236759635449c17c56e549658a.png)


Aws Amplify is a hosting service used to delpoy the static web pages, server side apps that can be scalable.  
connecting it to Version control system like GitHub,bitbucket, aws codecommit etc. With every every commit/ push it gets update, deploy changes. So CI CD runs on every code commit. 
Comes with built SSL certificates so it an be accesible on Https.  
Monitoring metrics of hosted sites, Creating custom notification if exceeds threshold limits etc. Redirects to hosting sites is easy.  


####  Basic web App deployment 
[host static website deploy on amplify ](https://aws.amazon.com/getting-started/hands-on/host-static-website/)

creating a basic react app
```
npx create-react-app amplifyapp
cd amplifyapp
npm start

```

do it the same folder create git and push to remote 

```
git init
git remote add origin git@github.com:viveklingireddy/reponame.git
git add .
git commit -m “initial commit”
git push origin main

```

or follow this has main branch
```bash
git remote add origin git@github.com:username/reponame.git
git branch -M main
git push -u origin main
```

Once you make changes to code in App.js
```bash
git add .
git commit -m “changes for v2”
git push origin main

```

Open AWS Amplify click get started build web app, attach the Git repo and build and deploy. The end. 

But if you want to add this to a domain Name here is the process
 [attach amplify app to domain name](https://docs.aws.amazon.com/amplify/latest/userguide/to-add-a-custom-domain-managed-by-amazon-route-53.html)

 Amplify adds two records automatically that is HTTP, HTTPS records \
 For Certificates SSL use AWS Certificate Manager


Handson Project 2
Amplify CLI – The Amplify CLI allows you to create, manage, and remove AWS services directly from your terminal.\

We will install Amplify CLI and intialize the app from terminal itself

#### Amplify CLI
```bash
npm install -g @aws-amplify/cli
```

`amplify configure`

[you will create a simple full-stack web application using AWS Amplify](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/?ref=gsrchandson&id=updated)
