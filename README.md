# Sphix deployment with Ansible and Docker

This demo uses the official *sphinxdoc/sphinx* image available in dockerhub to generate 'My Example Documentation' with the *Read the Docs* theme.

---
## Prerequisites

* For localhost, you need a machine with **Docker** and **Docke -Compose** installed.
* For remote host deployment, just need **Ansible**.

---
## Usage
Add your project details in /sphinx/docs/source/**conf.py**

Write your documentation files '.rst' under the **source/** directory.

---
## Deployment

### Localhost

In the **sphinx/** directory, run:
`docker-compose up -d`

This will build the documentation and launch a http static server. Open your browser and go to http://0.0.0.0 to see your documentation

### Remote host
Under **ansible/**, create a directory named *.inventory* and a **hosts** file with your remote host details.

Run: `ansible-playbook build_stack.yaml`

The script will install docker in the remote host, copy the files, build the images and launch the stack.
