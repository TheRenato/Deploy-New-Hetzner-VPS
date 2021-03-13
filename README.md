# Deploy a VPS at Hetzner


## Description

This projects mission is to simplefy deployment of server in Hetzner with help of GitLab-CI.
It is recommended that you have a private gitlab runner and don't commit sensitive data to the repo.
The server created will have the repo name.

The ENV that will be used are:

* CI_PROJECT_NAME: Is a variable that is included from GitLab, it is already set and it will be the name of your GitLab project. It will be used to name and identify servers, volumes and IP's

* API_HETZNER: This one you should set your self in the GitLab project settings. It will be used for the Hetzner API Token.
