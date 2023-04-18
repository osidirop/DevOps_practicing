[![Python 3.8](https://github.com/osidirop/scaffold/actions/workflows/main.yml/badge.svg)](https://github.com/osidirop/scaffold/actions/workflows/main.yml)

[![Azure Python 3.9](https://github.com/osidirop/scaffold/actions/workflows/azure.yml/badge.svg)](https://github.com/osidirop/scaffold/actions/workflows/azure.yml)

# Continuous Integration Demo Repo

In this demo the Continuous Integration is tested by setting up GitHub Actions (SaaS build server) and the code will be tested automatically every time a change is made and an event is triggered. 

## 1) Setting up GitHub Actions from scratch

The *yml* files inside the workflows directories are configured such that:
- every time the ```push``` command is triggered the tests will ```run on``` an ubuntu container (this is defined in ```runs-on: ubuntu-latest``` ) 
- the steps that we want to perform are defined as ```run``` actions and can been seen in the ```Actions``` tab 

For this example there are two different environments that are tested:
 * From AWS Cloud9 the code runs with python 3.8
 * From Microsoft Azure the code runs with python 3.9
 
 The two batches that are found on top of this page and confirm that the tests are passed or not, have been added from the Actions tab:
 * From the workflow, press the *3 dots button -> Create status badge -> Copy Status Badge Markdown* and paste it in a markdown environment (for this example on top of this page)




## 2) Link this repo to different free cloud services for testing:
For this demo the following cloud services are tested:
 * AWS Cloud9 
 * Microsoft Azure Cloud Shell

    
To link a github repo to the cloud service, whatever the cloud provider, the steps are the following:
 * On the cloud shell:
   * Create ssh keys by leaving the default settings on where they will be stored (just press ```Enter```): ``` ssh-keygen -t rsa```
   * Look for the public key that was created, open it (for e.g. ```cat ..../ssh/id_rsa.pub```) and copy the string
 * On github:
   * Create a new SSH key: *Profile -> Settings -> SSH and GPG keys -> New SSH Key*, copy the string on *KEY* and give it a name *TITLE*
   * Go back to the repo and clone it: *Code->SSH* 
 * Go back to the cloud shell and clone the github repo to the cloud service:
   * ```git clone [repo_name]```. In case you get a message like ```The authenticity of host 'github.com (140.82.121.x)' can't be established``` probably  you were not authenticated to the cloud service. To do so type: ```ssh -T git@github.com```. After successful addition of the above address to the ```know_hosts```, rerun the ```git clone``` command and you should be able to see the repo (*check ). 
 
 

