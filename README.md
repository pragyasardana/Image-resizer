# Image Resizer

## Objective

Come up with a solution that can resize that can resize an image in realtime with maximum of 100,000 RPS throughput 

## Example image resizer call

```
<img src="/resizer/image/width=80,quality=95/gs://image_bucket/image.jpg">
```

## Architecture

### Diagram

![Architecture](architecture.jpg)

### Assumptions
* The requesting website is professionally configured with a commercial CDN which will cache the image tag
* API Gateway limits are 10,000,000 per 100 seconds. [Source](https://cloud.google.com/api-gateway/docs/quotas)
* Cloudfunctions maximum concurrent invocations are 3000. [Source](https://cloud.google.com/functions/quotas)

## User Actions
* User will just have to upload the pictures to the Google Cloud storage bucket
