A simple test K8s service to verify the gRCP connectivity. Credits to [grpc-fortune-teller](https://github.com/kubernetes/ingress-nginx/tree/master/images/grpc-fortune-teller)


### Run
```
kubectl apply -f grcp_test_service.yml
```

It should create a load balancer on your cloud environment, AWS, or Azure.



### Test 
- install `grpcurl` command
- run 
```
grpcurl -insecure ${LoadBalancer_IP}:50051  build.stack.fortune.FortuneTeller/Predict
```
You should expect something like 
```
{
  "message": "Whenever the literary German dives into a sentence, that is the last\nyou are going to see of him until he emerges on the other side of his\nAtlantic with his verb in his mouth.\n\t\t-- Mark Twain \"A Connecticut Yankee in King Arthur's Court\""
}
```
