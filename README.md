# quota-documnet

Quota:

Quota is defined as range for resources such as CPU, memory, pods and storage. Request of minimums
and limits can be set across CPU and memory. Request level, minimums of resources such as CPU and
memory can be set for any application, this way it is guaranteed to have minimum set of resources for a
namespace. Limits on CPU, memory and number of pods can be set so there will not be any runaway
process or problems with maxing out resources on nodes and “hostile takeout” or internal ‘DOS’ attacks.
Quotas give guardrails on resources, so there will not be one pod taking over all of a node’s CP, memory
and more storage.
From OC command line interface by using the following commands with node names, CPU and memory
utilization of pods with quotas set can be achieved.


 oc get nodes
 
screen shot

 oc describe node
 
 screen shot
 


Request on a pod can go up to 100% where as limit on pod can go past 100%. Limit allows pod to ramp
to complete task.



Request and limit Settings for Different types of applications:

Java Based Applications:

Request CPU: 500 Millicore (or) 1/2 of a CPU core

Limit CPU: 1CPU or 500 MC

Memory: 500 Mi to 2 Gi (depending on app)

Node JS:

Request CPU: 250 Mc

Limit CPU: 750 MC

Memory: 250 Mi to 500 Mi for applications in node js

.Net core:

Request CPU: 250 Mc

Limit CPU: 750 MC

Memory: 250 Mi to 500 Mi for applications in .Netcore

There is no definite range as such, App will be unique on requirements. It has to start at some point, test and retest in development and test environment.However deployment strategy also comes into picture. A ‘Recreate’ strategy means destroy the pod and then recreate it, there will not be any resources added. when a resource usage is for a pod the request and the limit should be double or there might be chances of running into  resource quota issue. A requirement will dictate rolling or recreate strategies. More likely a development project can allow recreate, however production and staging or testing will probably need a rolling deployment. 




































https://docs.openshift.com/container-platform/3.11/dev_guide/compute_resources.html
