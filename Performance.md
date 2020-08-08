  # Impact of Scaling and Performance 
  
> The cloud is about how you do computing, not where you do computing. 


# Overview

In this article I will share how we can possibly fix bottlenecks in our project infrastructure on the parameters of *scaling* and *Performance*. As the desired result of our work, the project would be able to serve x of requests per second in y second.

The post starts with the outline of our product and the issues faced that could be eradicated using [*Load Balancing*](https://en.wikipedia.org/wiki/Load_balancing_(computing)) and a combination of [*Horizontal Scaling*](https://en.wikipedia.org/wiki/Scalability#Horizontal_(Scale_Out)_and_Vertical_Scaling_(Scale_Up)) and [*Vertical Scaling*](https://en.wikipedia.org/wiki/Scalability#Horizontal_(Scale_Out)_and_Vertical_Scaling_(Scale_Up)).



## Performance issue

<span style="font-size: 4vw;">T</span>he ever-growing varied devices that could be used to connect with the internet requires high performance software products to serve millions of devices all over the globe. Our product works in a real time environment and is used by a massive number of users, the request numbers of which rises at specific intervals of time. Therefore, we need highly responsive application experience. Our [*Server*](https://en.wikipedia.org/wiki/Server_(computing)) fails to serve requests when there is a significant rise in the number of clients. The project is hosted on **Jeroku**, which provides an easy experience for developers looking to deploy their applications, but it is also difficult to work with when it comes to obtaining real performance numbers. The original problem occured when our client numbers increased that subsequently puts a higher load on the application than it could ideally handle in its state at the time. As per the statistics, the product fails when there are 1000 requests per second. The main use case is to increase the performance of the product to serve million of devices in real-time without any bottlenecks.

!["Fig2"](https://support.cloudflare.com/hc/article_attachments/115003660331/image1.png)

**Fig. 2** The error displayed on the Interface

~~~
500 Internal Server Error
~~~

## What is Scaling

**Scaling** is defined as the ability for an IT resource to handle growing or decreasing demands in a capable manner. It is one of the widely used and beneficial features of [Cloud Computing](https://en.wikipedia.org/wiki/Cloud_computing), as businesses can scale up or down to meet demands based on season, projects, growth and more. Firstly, one of the customers reported that they get 502 response status codes for their requests from the servers, which indicates server failure. According to the statistics, at around 1000 requests per second xyz server instance fails to deliver the response.


Let’s assume you are going to holiday trip with your team. Actual problem is there are 50 members in your team & travel agent has sent only one bus having capacity of 25 passengers. What you will do? You need at least 2 buses. What you can do is either you can ask for two buses or you can ask for double-decker bus which can carry 50 passengers at a time .  Conclusion is you need to scale the basic resource (bus). If you choose option of double-decker then it is called ‘Vertical Scaling’ as you haven’t increased the number of buses, you just increased the capacity of a bus.  If you have opt for two buses then it is ‘Horizontal Scaling’ as you have increased the number of buses (resources).

!["Fig. 3"](https://i.stack.imgur.com/On3tO.png)





## Proposed Solution to fix the issue

Since, our product makes use of a single server on the cloud with a limited configuration,the first step to solve this issue is to scale up the existing system. 


### There are the possible ways to perform scaling :-

<ol>
<li> Horizontal Scaling</li>
<li>Vertical Scaling</li>
<li> Diagonal Scaling</li>
</ol>
<br>





**Horizontal Scaling** refers to upgrading the number of existing computing devices or servers present on the cloud which would possibly distribute the requests equally amongst the present servers. In the former case, the communication would take place largely because of network calls or remote procedures and would also eradicate the tendency of our server being a single point of failure. With horizontal-scaling it is often easier to scale dynamically by adding more machines into the existing pool — Vertical-scaling is often limited to the capacity of a single machine, scaling beyond that capacity often involves downtime and comes with an upper limit. Good examples of horizontal scaling are Cassandra, MongoDB, Google Cloud Spanner .. and a good example of vertical scaling is MySQL — Amazon RDS (The cloud version of MySQL). It provides an easy way to scale vertically by switching from small to bigger machines. This process often involves downtime.

![alt text](https://www.codit.eu/wp-content/uploads/2016/02/horizontal-scaling_330x199.png)
  
**Fig.3** Working of Horizontal Scaling 






**Vertical Scaling** refers to upgrading the efficiency of our existing computing devices or servers present on the cloud. In a layman language, a computer with better modifications in terms of RAM, I/O response times. In the latter case, the communication would largely take place because of inter communication calls. Eventually, this would increase the response retrieval time as method calls and fetching of results would be faster.Some of the reasons to scale vertically includes increasing IOPS (Input / Ouput Operations), amplifying CPU/RAM capacity, as well as disk capacity. However, even after using virtualization, whenever an improved performance is targeted, the risk for downtimes with it is much higher than using horizontal scaling.

![alt text](https://miro.medium.com/max/990/1*kzBKXvnoQZx_Pn-pk5XyCw.jpeg)

**Fig.4** Working of Vertical Scaling 
 <br>
 


**The single point of failure** in vertical scaling remains the unwanted feature which could be overcome by designing a hybrid scaling architecture where the systems on the vertical scaling could be scaled horizontally as well.

Horizontal Scaling is a must use technology – whenever a high availability of (server) services are required.

## The Difference


| Index      | Horizontal Scaling | Vertical Scaling     |
| :---        |    :----:   |          :------: |
| **1**      | The data resides on a multiple nodes.       |  The data resides on a single node.   |
| **2**   | Scaling dynamically is quite easy as you can add more machines into the existing pool.        | Vertical-scaling on the contrary is often limited to the capacity of a single machine. Scaling beyond that capacity results in downtime and comes with an upper limit.      |
| **3**   | One of the good example of horizontal scaling is Cassandra, MongoDB and that of vertical scaling is MySQL.         |    Scaling vertically can be achieved easily by switching from small to bigger machines. But this involves downtime.   |






## What to pick?


**Scaling horizontally** involves adding more processing units or phyiscal machines to your server or database. It involves growing the number of nodes in the cluster, reducing the responsibilities of each member node by spreading the key space wider and providing additional end-points for client connections. Horizontal Scaling has been historically much more used for high level of computing and for application and services.

Although this does not alter the capacity of each individual node, the load is decreased due to the distribution between separate server nodes.

Some of the reasons why organizations should choose to scale horizontally include increasing I/O concurrency, reducing the load on existing nodes, and increasing disk capacity.

The Internet and particular web services have boosted the use of Horizontal Scaling. Most giant companies that provide well known web services like Google (Gmail, YouTube), Yahoo, Facebook, EBay, Amazon etc. are using heavily horizontal scaling.


In order to distribute the load, Load Balancers are used. 

### Load Balancing

In computing, *Load Balancing* refers to the process of distributing a set of tasks over a set of resources (computing units), with the aim of making their overall processing more efficient. Load balancing techniques can optimize the response time for each task, avoiding unevenly overloading compute nodes while other compute nodes are left idle

Load balancing is the process of distributing workloads across multiple computing resources. This provides an efficient way to provide requests to the servers responsible to serve the requests based on health checkups, round robin algorithms, etc.


!["Fig. 4"](https://i0.wp.com/gbhackers.com/wp-content/uploads/2018/12/Load-Balancer.jpg?fit=759%2C387&ssl=1)
**Fig.4** Working of a Load Balancer 


### Conclusion

Therefore, a combination of vertical and horizontal scaling i.e Diagonal Scaling could be the best fit inorder to resolve the issue that we are currently facing. This would result in lesser downtime, quick responses and make our product fault tolerant.


### Referances
1.[*Wikipedia on Cloud Computing*](https://en.wikipedia.org/wiki/) <br>
2.[*Wikipedia on Scaling*](https://en.wikipedia.org/wiki/) <br>
3.[*Serving Millions of Users in Real Time*](https://blog.risingstack.com/nodejs-microservices-scaling-case-study/) <br>




