<h1>Network-aware Container Distribution System</h1>

<h2>Project Outline</h2>

<p>“Network-aware Container Distribution System” is a project which aims at creating a solution to use idle networking resource of a datacenter to distribute data inside that datacenter (private cloud) . This project is mentored by Andrey Turkovsky.</p>

<p>The following points outline the key points of the project :</p>
####Aim : 

Create a solution to use idle networking resource of a datacenter to distribute data inside that datacenter without interfering current network traffic. 

####Functionality :  
A tool to send a docker container from several machines to many machines and this needs to be done with the understanding that there should be no effect on the current network traffic(which means we need to monitor the network bandwidth being used for higher priority task in real time). 

####Performance :  
The goal is to have the highest performance with minimal effect on other stuff running on the network.

####Scalability :  
We expect the solution will have the scalability between 60,000 - 1,000,000 nodes.

####Scope :  
Be able to run a large cluster test and get performance with a number of different network loads.

####Security Needs :  
Since our project works within a private datacenter, the security is not a pressing issue.

####Things to Explore :  
We need to do some research on low-level network protocols, figure out how to send file between two nodes using docker(need to figure out how to use docker as well), then we gradually add nodes. The language we decided to use is Node.js so we need to get familiar with its APIs too. For the sake of the need to come up with a solution to monitor the network resource in real time and testing, we also need to figure out a way to simulate a busy network environment between nodes.

####Users/Personas of the project :  
“Network-aware Container Distribution System” , if successful, will be used as a part of Jisto.co’s private cloud solution. The project targets to deliver data inside datacenter with a “max network resource utilization” manner.  The users of the project will likely to be those companies who use Jisto’s solution to build private cloud on their idle computing resources.
