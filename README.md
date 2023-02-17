# Cloud Run (via Cloud Build)
Google provides great continuous integration and deployment tools. What these allow you to do is link github repositories to google cloud so that when the repo is updated, those changes get pulled and automatically deployed on google infrastructure.

# Steps
1. Go to Cloud Run at https://console.cloud.google.com/run
2. Create a Service
3. Select `Continuously deploy new revisions from a source repository` and connect your repositories `main` branch
4. Choose compute and memory appropriate for task
5. Allow unauthenticated invocations
6. Default everything else

# End Results
The end result is that when up push a change to your repos main branch, the following process will be triggered:
- Cloud Build will execute the Dockerfile in the repo to build a container
- If the container build is successful, Cloud Run will deploy that container
- The container's public URL can be found by clicking on the cloud run name
  - If you go to this URL, all your flask API endpoints will be available in your main.py app
