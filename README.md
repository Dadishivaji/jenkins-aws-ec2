<<<<<<< HEAD
\# Jenkins Installation on AWS EC2



\## Overview



This project demonstrates how to install and configure Jenkins on an AWS EC2 instance running Amazon Linux 2023.



Jenkins is used as a Continuous Integration and Continuous Delivery (CI/CD) automation server.



\## Technologies Used



\- AWS EC2

\- Amazon Linux 2023

\- Jenkins

\- Java 21

\- Linux

\- Git

\- GitHub

\- CI/CD



\## Prerequisites



Before installing Jenkins, make sure you have:



\- An AWS account

\- An EC2 Linux instance

\- SSH or EC2 Instance Connect access

\- Internet connectivity

\- Security Group access



\## Step 1: Launch EC2 Instance



Create an EC2 instance using Amazon Linux 2023.



Configure the Security Group with the following inbound rules:



| Type | Port | Source |

|---|---:|---|

| SSH | 22 | My IP |

| Custom TCP | 8080 | 0.0.0.0/0 |



Port 8080 is used to access the Jenkins web interface.



\## Step 2: Connect to EC2



Connect to the EC2 instance using EC2 Instance Connect.



```bash

ssh ec2-user@<PUBLIC-IP>

```



\## Step 3: Update the System



```bash

sudo dnf update -y

```



\## Step 4: Install Java



Install Java 21:



```bash

sudo dnf install java-21-amazon-corretto -y

```



Check the Java version:



```bash

java -version

```



\## Step 5: Add Jenkins Repository



Download the Jenkins repository:



```bash

sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/rpm-stable/jenkins.repo

```



Import the Jenkins key:



```bash

sudo rpm --import https://pkg.jenkins.io/rpm-stable/jenkins.io-2026.key

```



\## Step 6: Install Jenkins



```bash

sudo dnf install jenkins -y

```



\## Step 7: Enable Jenkins



Enable Jenkins to start automatically when the server starts:



```bash

sudo systemctl enable jenkins

```



\## Step 8: Start Jenkins



```bash

sudo systemctl start jenkins

```



\## Step 9: Check Jenkins Status



```bash

sudo systemctl status jenkins

```



Jenkins should show:



```text

Active: active (running)

```



\## Step 10: Verify Port 8080



Check whether Jenkins is listening on port 8080:



```bash

sudo ss -lntp | grep :8080

```



Expected output:



```text

LISTEN ... \*:8080 ... java

```



\## Step 11: Test Jenkins Locally



```bash

curl http://localhost:8080

```



If Jenkins responds with an authentication message, Jenkins is running correctly.



\## Step 12: Access Jenkins in Browser



Open:



```text

http://<PUBLIC-IP>:8080

```



Example:



```text

http://16.113.132.153:8080

```



\## Step 13: Get Initial Jenkins Password



Run:



```bash

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```



Copy the displayed password.



Paste it into the Jenkins \*\*Unlock Jenkins\*\* page.



\## Step 14: Install Suggested Plugins



After unlocking Jenkins:



1\. Select \*\*Install suggested plugins\*\*

2\. Wait for the installation to finish

3\. Create the first Jenkins administrator user

4\. Save the configuration

5\. Click \*\*Start using Jenkins\*\*



\## Step 15: Jenkins Dashboard



After completing the setup, the Jenkins Dashboard will be available at:



```text

http://<PUBLIC-IP>:8080

```



\## Jenkins Default Directory



Jenkins stores its main data under:



```text

/var/lib/jenkins

```



The initial administrator password is located at:



```text

/var/lib/jenkins/secrets/initialAdminPassword

```



\## Useful Jenkins Commands



\### Start Jenkins



```bash

sudo systemctl start jenkins

```



\### Stop Jenkins



```bash

sudo systemctl stop jenkins

```



\### Restart Jenkins



```bash

sudo systemctl restart jenkins

```



\### Check Jenkins Status



```bash

sudo systemctl status jenkins

```



\### Check Jenkins Port



```bash

sudo ss -lntp | grep :8080

```



\## Jenkins Architecture



```text

Developer

&#x20;   |

&#x20;   v

GitHub

&#x20;   |

&#x20;   v

Jenkins

&#x20;   |

&#x20;   v

Build

&#x20;   |

&#x20;   v

Test

&#x20;   |

&#x20;   v

Deploy

```



\## What I Learned



\- How to launch an EC2 Linux server

\- How to configure AWS Security Groups

\- How to install Java on Amazon Linux 2023

\- How to install Jenkins

\- How to manage Jenkins using systemctl

\- How to verify Jenkins on port 8080

\- How to access Jenkins through a web browser

\- How to configure the Jenkins administrator account

\- Basic CI/CD concepts



\## Author



\*\*Dadi Shivaji\*\*



B.Tech – Computer Science Engineering



\## License



This project is created for learning and educational purposes.


=======
\# Git Lab



This is my first Git repository.
>>>>>>> b23eb1ede82a8550be911304fa6eeceb9f862d67

