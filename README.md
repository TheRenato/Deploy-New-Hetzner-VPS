# Deploy a VPS at Hetzner


## Description

This projects mission is to simplefy deployment of server in Hetzner with help of GitLab-CI.
It is recommended that you have a private gitlab runner and don't commit sensitive data to the repo.
The server created will have the repo name.

The ENV that will be used are:

* **CI_PROJECT_NAME**: Is a variable that is included from GitLab, it is already set and it will be the name of your GitLab project. It will be used to name and identify servers, volumes and IP's

* **API_HETZNER**: This one you should set your self in the GitLab project settings. It will be used for the Hetzner API Token. Don't forget to mask it.

* **HETZNER_SERVER_TYPE**: This should also be in the set in the GitLab project settings.

* **SSH_KEY**: This should also be in the set in the GitLab project settings.

The HETZNER variables is set in the settings just so you don't need to look in the file where to change them.

Go to: [Settings] -> [CI/CD] -> [Variables] to add/change those variables


The only job that will run in every commit is the ansible lint job.

## How to Run

All other jobs must be run in [CI/CD] -> [Pipelines] -> [RUN] and with the right variable value.

The variable that should be set there is:

**DO_THIS**

And that variable should have this values:

**get all info**    To get all information from Hetzner.

**get info**        To get server information.

**get ip**          To get server IP and it will save it as a variable *host_ip*.

**server create**   To create your server

**server delete**   To delete your server

**server restart**  To reboot/restart your server.


## Done

 * The server is created and can be deleted.
 * SSH to server and make it do stuff.
 * Add Swap file to the server.
 * Structure the GitLab-Ci so it uses child pipelines instead. It will be easier to incorporate it to a new repo later.
 * Seperate the creation of server and configuration.

## ToDo

 * The option to Pre install Docker.
 * The option to have a floating IP.

## In the future...

 * Add backup job.
 * Perform backups at x times.
 * The option to recreate server of backup.

