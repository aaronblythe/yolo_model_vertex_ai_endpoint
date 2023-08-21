# yolo_model_vertex_ai_endpoint

A Notebook to set up a YoloV5 model on a Google Cloud Vertex AI Endpoint.

# Setup

## Starting from a new project

Navigate to Compute Engine and select Enable if it isn't already enabled. You'll need this to create your notebook instance.

Navigate to the Container Registry and select Enable if it isn't already. You'll use this to create a container for your custom training job.

Enable the Cloud Resource Manager API.

Navigate to the Vertex AI section of your Cloud Console and click Enable Vertex AI API.

In Vertex AI, Enbable the Notebooks API. This will use the latest version of Notebooks tooling.

### Create Networks if not already there

You will need at least a primary network and a subnet, with the firewall rules allowing tcp traffic.

## Create a notebook

Follow the step number "3. Setup your environment" HOWEVER: Select the **PyTorch** Environment
at: https://codelabs.developers.google.com/vertex_custom_training_prediction#2

## Open JupyterLab

If you get errors settting the project, then add a cell and execute:

```
!whoami
!gcloud auth list --filter=status:ACTIVE --format="value(account)"
!gcloud projects list
```

You may have to set the service account in IAM to have these Roles

* Compute Storage Admin
* Vertex AI Notebook Service Agent
* Vertex AI Service Agent
* Vertex AI Viewer

# References

Based Starts from: https://github.com/GoogleCloudPlatform/vertex-ai-samples/blob/main/notebooks/official/prediction/pytorch_image_classification_with_prebuilt_serving_containers.ipynb

Then the Custom Handler is used: https://gist.github.com/joek13/b895db0cd50a7c71a123611885057c69
