# Continuous Delivery Demo Repo

In this demo, CD is tested with the Cloud Build of Google Cloud. For this purpose a simple webpage is created with flask. 

To test auto-deployment the following steps are required on Google Cloud:

1. A new project was created and linked with the repository which contains a cloudbuild.yaml file and tested locally
2. To deploy it in a server run ```gcloud app deploy``` using a region (us-central1 was tested). Once this is done, a ```target url``` will be provided to check the webpage.
3. A Trigger on Cloud Build was enabled with "Push to branch" and the repository was connected.
4. On the Settings the following should be enabled:
   * App Engine
   * Service Account

    this will allow the build server on our behalf to do the deploy for us

5. Whenever a change is made on github on the ```main.py``` will trigger the build. The auto-deployment can be checked on the History tab and by checking the target url

