# SockShop Load Tests
This directory contains load tests developed using [Locust](https://locust.io/), for activating various parts of the SockShop application. The intention is to see how the application performs both without instrumentation, as well as with instrumentation using various techniques.

These load tests will record request latencies and throughput, while resource consumption of the SockShop services is assumed to be measured by the Kubernetes cluster. The workloads are described below.

## Realistic workload
The file `commerce_client.py` contains a workload that simulates a real user browsing the web page. This client simulates all requests for web resources that are normally invoked when accessing the frontend. These requests were derived from intercepting network traffic with the tool [Postman](https://www.postman.com/) while manually browsing the webshop.

The client performs the following requests (relative weight):
- Opening the catalogue (5)
- View details on a specific product (10)
- Add a product to the basket (7)
- Proceed to checkout and finalize the purchase (5)
