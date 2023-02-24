---
created: 2023-02-17T08:58:32 (UTC +01:00)
tags: []
source: https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#stage-1-access-with-any-user-9
author: 
---

# Web Hacking Playground | Is A Controlled Web Hacking Environment - Tools & Scripts - OneHack.Us | Tutorials For Free, Guides, Articles & Community Forum

> ## Excerpt
> Web Hacking Playground  Description Web Hacking Playground is a controlled web hacking environment. It consists of vulnerabilities found in real cases, both in pentests and in Bug Bounty programs. The objective is that users can practice with them, and learn to detect and exploit them.  Other topics of interest will also be addressed, such as: bypassing filters by creating custom payloads, executing chained attacks exploiting various vulnerabilities, developing proof-of-concept scripts, among...

---
![image](https://onehack.us/uploads/default/original/3X/a/7/a78462bcdcd41c531590e0948eef4a5ee8453673.jpeg)

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#web-hacking-playground-1)Web Hacking Playground

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#description-2)Description

Web Hacking Playground is a controlled web hacking environment. It consists of vulnerabilities found in real cases, both in pentests and in Bug Bounty programs. The objective is that users can practice with them, and learn to detect and exploit them.

Other topics of interest will also be addressed, such as: bypassing filters by creating custom payloads, executing chained attacks exploiting various vulnerabilities, developing proof-of-concept scripts, among others.

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#important-3)Important

The application source code is visible. However, the lab’s approach is a black box one. Therefore, the code should not be reviewed to resolve the challenges.

Additionally, it should be noted that fuzzing (both parameters and directories) and brute force attacks do not provide any advantage in this lab.

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#setup-4)Setup

It is recommended to use [Kali Linux](https://www.kali.org/get-kali/) to perform this lab. In case of using a virtual machine, it is advisable to use the [VMware Workstation Player](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html) hypervisor.

The environment is based on Docker and Docker Compose, so it is necessary to have both installed.

To install Docker on Kali Linux, run the following commands:

```
sudo apt update -y
sudo apt install -y docker.io
sudo systemctl enable docker --now
sudo usermod -aG docker $USER
```

To install Docker on other Debian-based distributions, run the following commands:

```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo systemctl enable docker --now
sudo usermod -aG docker $USER
```

It is recommended to log out and log in again so that the user is recognized as belonging to the docker group.

To install Docker Compose, run the following command:

```
sudo apt install -y docker-compose
```

**Note:** In case of using M1 it is recommended to execute the following command before building the images:

```
export DOCKER_DEFAULT_PLATFORM=linux/amd64
```

The next step is to clone the repository and build the Docker images:

```
git clone https://github.com/takito1812/web-hacking-playground.git
cd web-hacking-playground
docker-compose build
```

Also, it is recommended to install the [Foxy Proxy](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/) browser extension, which allows you to easily change proxy settings, and [Burp Suite 1](https://portswigger.net/burp/communitydownload), which we will use to intercept HTTP requests.

We will create a new profile in Foxy Proxy to use Burp Suite as a proxy. To do this, we go to the Foxy Proxy options, and add a proxy with the following configuration:

-   **Proxy Type:** HTTP
-   **Proxy IP address:** 127.0.0.1
-   **Port:** 8080

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#deployment-5)Deployment

Once everything you need is installed, you can deploy the environment with the following command:

```
git clone https://github.com/takito1812/web-hacking-playground.git
cd web-hacking-playground
docker-compose up -d
```

This will create two containers of applications developed in Flask on port 80:

-   **The vulnerable web application (Socially)**: Simulates a social network.
-   **The exploit server:** You should not try to hack it, since it does not have any vulnerabilities. Its objective is to simulate a victim’s access to a malicious link.

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#important-6)Important

It is necessary to add the IP of the containers to the /etc/hosts file, so that they can be accessed by name and that the exploit server can communicate with the vulnerable web application. To do this, run the following commands:

```
sudo sed -i '/whp-/d' /etc/hosts
echo "$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' whp-socially) whp-socially" | sudo tee -a /etc/hosts
echo "$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' whp-exploitserver) whp-exploitserver" | sudo tee -a /etc/hosts
```

Once this is done, the vulnerable application can be accessed from [http://whp-socially](http://whp-socially/) and the exploit server from [http://whp-exploitserver](http://whp-exploitserver/).

When using the exploit server, the above URLs must be used, using the domain name and not the IPs. This ensures correct communication between containers.

When it comes to hacking, to represent the attacker’s server, the local Docker IP must be used, since the lab is not intended to make requests to external servers such as Burp Collaborator, Interactsh, etc. A Python http.server can be used to simulate a web server and receive HTTP interactions. To do this, run the following command:

```
sudo python3 -m http.server 80
```

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#stages-7)Stages

The environment is divided into three stages, each with different vulnerabilities. It is important that they are done in order, as the vulnerabilities in the following stages build on those in the previous stages. The stages are:

-   **Stage 1:** Access with any user
-   **Stage 2:** Access as admin
-   **Stage 3:** Read the /flag file

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#important-8)Important

Below are spoilers for each stage’s vulnerabilities. If you don’t need help, you can skip this section. On the other hand, if you don’t know where to start, or want to check if you’re on the right track, you can extend the section that interests you.

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#stage-1-access-with-any-user-9)Stage 1: Access with any user

Display

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#stage-2-access-as-admin-10)Stage 2: Access as admin

Display

### [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#stage-3-read-the-flag-file-11)Stage 3: Read the /flag file

Display

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#solutions-12)Solutions

Detailed solutions for each stage can be found in the [Solutions](https://github.com/takito1812/web-hacking-playground/tree/main/Solutions) folder.

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#resources-13)Resources

The following resources may be helpful in resolving the stages:

-   [Google](https://www.google.com/)
-   [Twitter Advanced Search](https://twitter.com/search-advanced)
-   [HackTricks 1](https://book.hacktricks.xyz/)
-   [PortSwigger Learning Materials](https://portswigger.net/web-security/all-materials)
-   [Payloads All The Things](https://github.com/swisskyrepo/PayloadsAllTheThings)
-   [Payload Box](https://github.com/payloadbox)

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#collaboration-14)Collaboration

Pull requests are welcome. If you find any bugs, please open an issue.

## [](https://onehack.us/t/web-hacking-playground-is-a-controlled-web-hacking-environment/233213#github-15)GitHub:
