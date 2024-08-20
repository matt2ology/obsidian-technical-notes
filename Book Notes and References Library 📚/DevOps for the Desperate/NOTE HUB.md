---
aliases:
note-type: hub
tags:
  - hub/books
---

# NOTE HUB - DevOps for the Desperate

[DevOps for the Desperate: A Hands-On Survival Guide by Bradley Smith](https://nostarch.com/devops-desperate)

Kindle notes and highlights :

- Synced by [Kindle Highlights](https://github.com/hadynz/obsidian-kindle-plugin): [Smith-DevOps for the Desperate](../../kindle-highlights/Smith-DevOps%20for%20the%20Desperate.md)
- Synced by [Readwise](https://readwise.io/): [DevOps for the Desperate](../../Readwise/Books/DevOps%20for%20the%20Desperate.md)

Related :

- [Infrastructure as Code (IaC)](<../../3-permanent-notes-🧲/Infrastructure%20as%20Code%20(IaC).md>)
- [Configuration Management (CM)](<../../3-permanent-notes-🧲/Configuration%20Management%20(CM).md>)

Topics : [DevOps](DevOps)

Links to all notes, questions, and insights made while reading

Source code samples: https://github.com/bradleyd/devops_for_the_desperate.git.

## Notes and Insights

### PART I: INFRASTRUCTURE AS CODE, CONFIGURATION MANAGEMENT, SECURITY, AND ADMINISTRATION

[Infrastructure as Code (IaC)](<../../3-permanent-notes-🧲/Infrastructure%20as%20Code%20(IaC).md>) and [Configuration Management (CM)](<../../3-permanent-notes-🧲/Configuration%20Management%20(CM).md>) builds systems with a repeatable, versioned, and predictable state.

#### **Chapter 1:** Setting Up a Virtual Machine

Discusses the concepts of [Infrastructure as Code (IaC)](<../../3-permanent-notes-🧲/Infrastructure%20as%20Code%20(IaC).md>) and
[Configuration Management (CM)](<../../3-permanent-notes-🧲/Configuration%20Management%20(CM).md>); also, introduces two technologies, Vagrant and Ansible,
that you’ll use to create and provision an Ubuntu VM.

- [VM Provisioning Basics](VM%20Provisioning%20Basics.md)
- [Vagrant and Ansible](../../3-permanent-notes-🧲/Vagrant%20and%20Ansible.md)

#### **Chapter 2:** Using Ansible to Manage Passwords, Users, and Groups

How to use CM for user and group creation to restrict file and directory access.
It also explains how to use CM to enforce complex passwords.

#### **Chapter 3:** Using Ansible to Configure SSH

How to set up public key and two-factor authentication over SSH, so making it harder for
unauthorized users to gain access to your host and sensitive data.

#### **Chapter 4:** Controlling User Commands with `sudo`

How to create a security policy that delegates command access for a specific user and group.
Controlling the command access that users and groups have on a host can help you avoid
unnecessary exposure to attackers. At a minimum, it prevents you from having a poorly
configured OS.

#### **Chapter 5:** Automating and Testing a Host-Based Firewall

How to create and test a minimal firewall that will block all unwanted access while
permitting approved traffic. By limiting port exposure, you can reduce the vulnerabilities
your host and application may encounter from the outside.

### **PART II: CONTAINERIZATION AND DEPLOYING MODERN APPLICATIONS**

Concepts of containerization, orchestration, and delivery. It also explores some of the
components that make up a modern stack.

#### **Chapter 6:** Containerizing an Application with Docker

Introduces containers and containerization, and it shows how to create a sample
containerized application. A basic understanding of containers and how to use them for local
development and production is key to your ability to work with any modern application
stack.

#### **Chapter 7:** Orchestrating with Kubernetes

Introduces container orchestration and explores how to use technologies like Kubernetes
and minikube to deploy an application on a local cluster. It also serves as an example of
how to set up a local development environment.

#### **Chapter 8:** Deploying Code

Discusses the concept of continuous integration and continuous deployment (CI/CD).
It also explores some core technologies, like Skaffold, that allow you to create a pipeline on
a local Kubernetes cluster. After building an effective CI/CD pipeline, you’ll have a good
understanding of how to build, test, and deploy software.

### **PART III: OBSERVABILITY AND TROUBLESHOOTING**

Concepts of monitoring, alerting, and troubleshooting. It looks at metric collection and
visualization for applications and hosts. It also discusses some common host and
application issues, as well as tools you can use to diagnose them.

#### **Chapter 9:** Observability

Concept of a monitoring and alerting stack, and it explores the technologies (Prometheus,
Alertmanager, and Grafana) that make up this stack. Learn how to detect a system’s state
and alert on it when things are out of scope.

#### **Chapter 10:** Troubleshooting Hosts

Discusses common issues and errors on a host and some tools you can use to troubleshoot
them. Being able to analyze issues on a host will help you in times of crisis and help you
understand performance issues in your own code and applications.

## Questions (Who, What, When, Where, Why, and How)

Check off notes with `-` instead of `x`, so it does not cross out line item in [Obsidian](https://obsidian.md/)

- [-] [What are the foundational concepts to DevOps?](What%20are%20the%20foundational%20concepts%20to%20DevOps.md)
- [-] [Why Use Code to Build Infrastructure?](Why%20Use%20Code%20to%20Build%20Infrastructure.md)
