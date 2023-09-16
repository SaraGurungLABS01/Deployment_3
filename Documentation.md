


## STEPS:

## 1. Starting a new Repository
1. Created a new Repository under the name Deployment_2
2. Downloaded the zip files from the Repository : C4_deployment-3 and unzipped them
3. Uploaded the unzipped files to the new repository that was created

## 2. Steps for Launching an EC2 with Jenkins installed and activated
1. Launch a new EC2 to install Jenkins with "python3.10-venv", "python-pip", "unzip". Instruction to install Jenkins; Link : https://pkg.jenkins.io/debian/
2. Update the package list and install Python 3.10 virtual environment (venv)
"sudo apt update && sudo apt install python3.10-venv"
3. Install Python package manager (pip) for Python 2 (optional)
"sudo apt install python-pip"  - OR - if you're using Python 3: "sudo apt install python3-pip"
4. Install the "unzip" utility "sudo apt install unzip"
5. Access Initial Admin Password: "sudo cat /var/lib/jenkins/secrets/initialAdminPassword"
6. Access Jenkins Web Interface: http://[18.212.141.203:8080]
7. Enter the initial admin password and follow the setup wizard.
8. Create a multibranch pipeline, select "GitHub" under branch sources, and provide your GitHub link and credentials to run the application build
9. If you need a new personal token, please refer to the steps on how to create a new personal token from the previous repositories ( Deployment-1 for instance)
10. Monitor the pipeline and once its successful proceed to next step 
    
    
![image](https://github.com/SaraGurungLABS01/Deployment_3/assets/140760966/23820817-5e5d-4d85-9a98-2ca0f0f81dce)

## 3. Install AWS EB CLI and Initial Deployment
1. Makesure that you install AWS CLI using the following instruction link : https://scribehow.com/shared/How_to_Install_AWS_CLI__1MnhqmpcRxupkx_F-EcreQ
2. Follow the instruction in given link : https://scribehow.com/shared/How_to_install_AWS_EB_CLI__J6eBRB9FQl2fGenfUVemlA
3. Once you run the 'eb create', you will notice that it will take couple of minutes to finish and you will also notice all the different activities that are taking place.
   
   ![IAM](https://github.com/SaraGurungLABS01/Deployment_3/assets/140760966/dcafc952-0e39-4e80-b7ab-96b1f011c076)

4. Once EB finishes, you can see the application URL on the third to last line (Application available at URL)
   
   http://url-shortener-dev22222.us-east-1.elasticbeanstalk.com/
5. Afterward, copy and paste the link into your web browser to verify the successful deployment of the application.

![image](https://github.com/SaraGurungLABS01/Deployment_3/assets/140760966/f34cf51d-1fe9-4b1d-925e-b02ccffacfa9)



## 4. Editing the Jenkins File and redeploying the application
1. Open the jenkins file from the repository - Deployment_3 and add the following line of code : "stage ('Deploy') { steps { sh '/var/lib/jenkins/.local/bin/eb deploy' } } "
2. Click commit changes and go to the Jenkins Web interface and click build now
3. Monitor the pipeline and notice a new stage : Deploy
4. Once its successful, click on the link for url-shortener and made sure its successfully deployed
5. Noticed that the deployment process was initiated by Jenkins through the Deploy stage in the Jenkinsfile.


 ![Build 2](https://github.com/SaraGurungLABS01/Deployment_3/assets/140760966/a2c2bb15-01a9-4659-a05e-7316e5a65d51)
  

## 5. Configuring Webhook
1. Follow the link to set up a GitHub webhook for Jenkins deployment which serves to automate build and deployment processes triggered by code changes in a GitHub repository
   Link: https://scribehow.com/shared/Setting_up_a_GitHub_webhook_for_Jenkins_deployment__OCRQGNvARfWF4clyeFcsGQ
2. Once the webhook was configured, 















