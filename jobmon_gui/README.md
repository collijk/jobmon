# Jobmon GUI
A GUI to visualize Jobmon Workflows.

## Overview
This application uses React, Flask, and Bootstrap.

The Jobmon GUI was originally created by create-react-app.

## Roadmap
You can see the roadmap of the upcoming deployments here: https://hub.ihme.washington.edu/display/DataScience/Jobmon+GUI+Design+and+Initial+Roadmap

## Testing Locally

### Deploying the Flask Server App Locally
To deploy the Flask app locally:

1. Open a terminal
2. Make a conda environment and activate it
3. Navigate to the top of the Jobmon repository
4. Run `nox -s launch_gui_test_server`
5. Run `python jobmon_gui/local_testing/jobmon_gui/testing_servers/functionaltest_server.py`
    - This command will spin up a local version of the Flask backend, running on 127.0.0.1:8070 by default. You can then configure the React app to point to this URL for testing purposes.

### Deploying the React App Locally
To deploy the React app locally:

1. Open a new terminal
2. Install npm
3. Navigate to the jobmon_gui subdirectory
4. Run `npm install`
5. Run `npm start`

Note: When running locally the React app uses the Webpack Dev Server to serve its assets.

You can then access the site at: http://localhost:3000

## Deploying to Kubernetes
The Jobmon GUI is deployed via the primary Jobmon Jenkins deployment pipelines i.e. you cannot deploy the Jobmon GUI with out deploying Jobmon and vice versa.
The build follows the dev (dev k8s cluster) -> stage (dev k8s cluster) -> prod deployment (prod k8s cluster) process:
- Development Jenkins pipeline: https://jenkins.scicomp.ihme.washington.edu/job/jobmon/job/release/job/jobmon.dev.deploy/
- Stage Jenkins pipeline: https://jenkins.scicomp.ihme.washington.edu/job/jobmon/job/release/job/jobmon.stage.deploy/
- Prod Jenkins pipeline: https://jenkins.scicomp.ihme.washington.edu/job/jobmon/job/release/job/jobmon.prod.deploy/

If the pipelines were successful you should be able to see the webpage and the pods spun up in Rancher.
