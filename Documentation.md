


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
9. if you need a new personal token, please refer to the steps on how to create a new personal token from the previous repositories ( Deployment-1 for instance)
![image](https://github.com/SaraGurungLABS01/Deployment_3/assets/140760966/23820817-5e5d-4d85-9a98-2ca0f0f81dce)






