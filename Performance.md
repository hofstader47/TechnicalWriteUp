# Overview

In this article I will share how we can possibly fix bottlenecks in our project infrastructure on the parameters of scaling and performance. As the result of our work, the project would be able to serve x of requests per second in y seconds.

The post starts with the general overview of our product and the issues faced related to performance and scalability and how to possibly overcome them using load balancing and a combination of horizontal scaling and vertical scaling.

# Project and the issue

The ever-growing varied devices that could be used to connect with the internet requires high performance software products to serve millions of devices all over the globe. Our product works in a real time environment and is used by a massive number of users, the request number of which rises at specific intervals of time. Therefore, we need highly responsive application experience. Our server fails to serve requests when there is a significant rise in the number of clients. The project is hosted on xyz, which provides an easy experience for developers looking to deploy their applications, but it is also difficult to work with when it comes to obtaining real performance numbers.. The original problem our client had was that as they grew, they recommended new clients that put a higher load on the application than it could ideally handle in its state at the time. As per the statistics, the product fails when there are 1000 requests per second. The main use case is to increase the performance of the system to serve millions of devices in real-time without any bottlenecks.

# Proposed Solution to fix the issue

The first step to solve this issue is to scale up the existing system. Scaling is defined as the ability for an IT resource to handle growing or decreasing demands in a capable manner. It is one of the widely used and beneficial features of cloud computing, as businesses can scale up or down to meet demands based on season, projects, growth and more. Firstly, one of the customers reported that they get 502 response status codes for their requests from the servers, which indicates server failure. According to the statistics, at around 1000 requests per second xyz server instance fails to deliver the response.



Error code faced by the client

There are two possible ways to perform scaling -

<ol>
<li>Horizontal Scaling</li>
<li>Vertical Scaling</li>

</ol>



**Horizontal Scaling** refers to upgrading the number of our existing computing devices or servers present on the cloud which would possibly distribute the requests equally amongst the present servers. In the former case, the communication would take place largely because of network calls or remote procedures and would also eradicate the tendency of our server being a single point of failure.



**Vertical Scaling**

Vertical Scaling refers to upgrading the efficiency of our existing computing devices or servers present on the cloud. In a layman language, a computer with better modifications in terms of RAM, I/O response times. In the latter case, the communication would largely take place because of inter communication calls. Eventually, this would increase the response retrieval time as method calls and fetching of results would be faster.



The single point of failure in vertical scaling remains the unwanted feature which could be overcome by designing a hybrid scaling architecture where the systems on the vertical scaling could be scaled horizontally as well.

In order to distribute the load, Load Balancers are used. Load balancing is the process of distributing workloads across multiple computing resources. This provides an efficient way to provide requests to the servers responsible to serve the requests based on health checkups, round robin algorithms, etc.
