# Get Started with Eventarc: Challenge Lab || [ARC118](https://www.cloudskillsboost.google/focuses/63244?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export LOCATION=
```
```
gcloud services enable run.googleapis.com

gcloud services enable eventarc.googleapis.com

gcloud pubsub topics create $DEVSHELL_PROJECT_ID-topic

gcloud  pubsub subscriptions create --topic $DEVSHELL_PROJECT_ID-topic $DEVSHELL_PROJECT_ID-topic-sub

gcloud run deploy pubsub-events \
  --image=gcr.io/cloudrun/hello \
  --platform=managed \
  --region=$LOCATION \
  --allow-unauthenticated

gcloud eventarc triggers create pubsub-events-trigger \
  --location=$LOCATION \
  --destination-run-service=pubsub-events \
  --destination-run-region=$LOCATION \
  --transport-topic=$DEVSHELL_PROJECT_ID-topic \
  --event-filters="type=google.cloud.pubsub.topic.v1.messagePublished"

gcloud pubsub topics publish $DEVSHELL_PROJECT_ID-topic \
  --message="Test message"
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
