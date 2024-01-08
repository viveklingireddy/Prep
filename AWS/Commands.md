## USER DATA LAUNCH COMMANDS
`
sudo apt update -y
sudo apt install apache2 -y
echo "<h1>Server Details</h1><p><strong>Hostname:</strong> $(hostname)</p><p><strong>IP Address:</strong> $(hostname -I)</p>" | sudo tee /var/www/html/index.html
sudo systemctl restart apache2
`

`#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
`
- for root user
` sudo su -
`
- for current running ports `netstat -tlnp`

`sudo su -
yum -y install nginx
systemctl status nginx
systemctl start nginx
systemctl enable nginx
systemctl status nginx

cd |usr|share|nginx|html
cat index.html
change the content through vi or nano editor
cat index.html`
- from aws tutorials

`#!/bin/bash
 yum install httpd -y 
systemctl start httpd 
systemctl stop firewalld 
cd /var/www/html 
echo "this is my test site and the instance-id is " > index.html curl http://169.254.169.254/latest/meta-data/instance-id >> index.html`



### git token in AWS 
`// Use this code snippet in your app.
// If you need more information about configurations or implementing the sample
// code, visit the AWS docs:
// https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/home.html

// Make sure to import the following packages in your code
// import software.amazon.awssdk.regions.Region;
// import software.amazon.awssdk.services.secretsmanager.SecretsManagerClient;
// import software.amazon.awssdk.services.secretsmanager.model.GetSecretValueRequest;
// import software.amazon.awssdk.services.secretsmanager.model.GetSecretValueResponse;	

public static void getSecret() {

    String secretName = "github-oauth-token";
    Region region = Region.of("us-east-1");

    // Create a Secrets Manager client
    SecretsManagerClient client = SecretsManagerClient.builder()
            .region(region)
            .build();

    GetSecretValueRequest getSecretValueRequest = GetSecretValueRequest.builder()
            .secretId(secretName)
            .build();

    GetSecretValueResponse getSecretValueResponse;

    try {
        getSecretValueResponse = client.getSecretValue(getSecretValueRequest);
    } catch (Exception e) {
        // For a list of exceptions thrown, see
        // https://docs.aws.amazon.com/secretsmanager/latest/apireference/API_GetSecretValue.html
        throw e;
    }

    String secret = getSecretValueResponse.secretString();

    // Your code goes here.
}`