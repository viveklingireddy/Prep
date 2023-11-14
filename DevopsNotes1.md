## SDLC 
- #### Software Development Life Cycle
- [SDLC]![879dca_dbbbcbf7e6564025a4afb533a1e6d622~mv2](https://github.com/viveklingireddy/Prep/assets/67540715/37a1c8a8-01c6-4ae3-a090-27a417e96f0f)
- [SDLC](https://aws.amazon.com/what-is/sdlc)
- #### PLANNING PHASE
- In planning phase, All the documentation of Client's requirements were gathered and documented.
- #### DESIGNING PHASE
- In Design phase Architects write a HLD **(High Level Design)**, **LLD (Low Level Design)**.
- #### BUILD PHASE, TEST, DEPLOY
- These are main functionalities of DeVops Engineer, Where Automation takes place. 
- Developers develop the code, Stores it in a Repo. QA Engineers deploy on server tests on it with Unit, Integration,
   User- Acceptance testing etc. Deployment and Release to Production.
- Main Goal of Devops Engineer is to Fasten Up theese phases to Continously Deliver the Code. Automation comes into play for
  Improvising Efficiency of this phases. 
- ![Resized-Agile-SDLC](https://github.com/viveklingireddy/Prep/assets/67540715/a7cc2c00-a123-4806-885d-9009755ac6eb)

- ### What is involved in the Automation then?
- In the Process of Automation many tools comes in picture such as **Jenkins** (for Building CI/CD ), Code quality check (**SonarQube**), Docker, Kubernetes (**Containers** / **Orchestration**), **Terraform** (IAC) , CodeMonitoring Tools (**Promotheus && Grafana**), etc.
-  ### PIPELINE STAGES (AWS/ CI CD)

![Product-Page-Diagram_AWS-CodePipeline 4a1bea38d3c8d3b2c1384dd0a7d2a858f4350471](https://github.com/viveklingireddy/Prep/assets/67540715/bcbc87b9-f5a9-4332-bc55-3b5e430b3480)

- ## What is Server?
- In Laymen terms, Server is one who serves something, providing some service.
- Similarly, Server in Computing terms is providing something. What is it serving ?
- Serving some client required services, that is providing applications, code etc.
- Basically, Assume I'm a client(I sell Branded Clothes at my Retail Store. Now, I want to capture the market by going Remote/ Online. So, I had asked you to Build me a Website where Customers can Look at available Items in Stock and buy them
  Online. So, I get Notified about Orders.
- As Developer you should write the code, Stores it Remote Repository. So, Other team mates can contribute on it.
- Now you are done with Coding part, it is Succesfully Running at your Local. Now you should deliver it to me. How do you do it ?
- Servers can be Hardware  / Software
- Hardware  server means serving through physical components such as PC, hard disk's to client etc. Ex Game CD's etc.
- Software server are Application that (serve Piece of code/ Data bases)**host** and client connects to server through Ip 
Address and  requests for services. Each Server(Device) has its own Ip.
- Now Server comes into play. Server nows servs what ?. A pieace of code/ application/ Data over to me by what Internet.
- ![server](https://github.com/viveklingireddy/Prep/assets/67540715/52b0b9de-d3f6-4846-8838-e3c35f97db12)
- ![1_yw7D8njef49dBsR15wMY9g](https://github.com/viveklingireddy/Prep/assets/67540715/c5c5c181-8f11-4b14-8735-7436f78bb550)

-   ![5d678947-2cad-44df-a4a4-5e78fd50fb52](https://github.com/viveklingireddy/Prep/assets/67540715/eaacbff9-1bed-47ec-bb59-94661361c3ea)

-   What are fixs, bugs, down time etc.
-   Fixes are nothing but corrections, mistake removal steps. Removing erros.
-   Bugs are like errors occur due to some vunerbility, code errors that damges process, interrupt.
-   Down time is when a new version deployed got some errors/ bug at prod level. The time taken to make it to earlier stable version. / When the servers crash due to High load etc.
-   ### What is Virtual?
-   Virtual means it exists but not Physically available. 
-   Ex: Virtual Library. Here you can access to books, audio files through medium called Online. So you can read a book Online but can't have it in your hand.
-   Neo Banking: You can avail all the banking services that include transcations, Online services etc. you can physicall have a bank there.
-   ## [Virtualization:](https://aws.amazon.com/what-is/virtualization/#:~:text=Virtualization%20is%20technology%20that%20you,on%20a%20single%20physical%20machine.)
-   The process of making something have in Virtual or **Technology** that can *replicate* an existing physical infrastructure available online / Virtual. Ex: Operating Systems (Virtual Machines), Storage services(**S3** Bucket), etc.
-   ##### How to access Virtual of Any system ?
-   Any virtual version can be operated through a physical medium.

-   [**Virtualization**](https://www.ibm.com/topics/virtualization)  enables the hardware resources of a single computer—processors, memory, storage and more—to be divided into multiple virtual computers, called virtual machines (VMs).
-   It's like converting one single PC to Multiple Virtual machines. Virtual Machines are environments that physical doesn't exist but virtual present. We allocate 1 device to convert to multiple VM's so that each VM can execute seperate tasks can have different os etc. that increase efficiency of system.


![image](https://github.com/viveklingireddy/Prep/assets/67540715/e09ab6a6-bfb0-4a48-abff-e2ee6daf8491)

- Basically a Physical Infrasructure like PC has CPU, Storage, OS etc. When a Hypervisor like VMware cordinates with these physicall infra to create multiple Virtual Machines in order to boost efficency. Each VM has same underlying infra of physical one.
  Memory allocation is done According to the use of each. By this Virtualization we can have better resource utilization.
-  Hypervisor's take care of each VM doesn't interfere with other resources/ memory space etc.
-  Similarly Same is involved with Cloud Service providers they have Data Center with Physical Infrastructure which are converted to multiple Virtual Machine's (EC2 Instances in AWS). They rent them as pay as go model. On Utilization of each Instance memory is allocated etc.

![image](https://github.com/viveklingireddy/Prep/assets/67540715/ee2da3e9-a9a3-4c57-b55a-1892310b2011)

- In Each Availability Zone(**Data Centers**) these Infrastructure is made available virtual using Technology called ~Virtualization~.
-   ---
-   Cloud is basically a Virtualization of Servers, Storage, Physical Data Center Services that provides Services as per customer requirements with Iaas, Paas, Saas models.
-   ### Hypervisors
  @c [IBM](https://www.ibm.com/topics/virtualization)
- A hypervisor is the software layer that coordinates VMs. It serves as an interface between the VM and the underlying physical hardware, ensuring that each has access to the physical resources it needs to execute. It also ensures that the VMs don’t interfere with each other by impinging on each other’s memory space or compute cycles.

- There are two types of hypervisors:

Type 1 or “bare-metal” hypervisors interact with the underlying physical resources, replacing the traditional operating system altogether. They most commonly appear in virtual server scenarios.
Type 2 hypervisors run as an application on an existing OS. Most commonly used on endpoint devices to run alternative operating systems, they carry a performance overhead because they must use the host OS to access and coordinate the underlying hardware resources.

### Hpervisors
The hypervisor is the virtualization software that you install on your physical machine. It is a software layer that acts as an intermediary between the virtual machines and the underlying hardware or host operating system. The hypervisor coordinates access to the physical environment so that several virtual machines have access to their own share of physical resources. 

For example, if the virtual machine requires computing resources, such as computer processing power, the request first goes to the hypervisor. The hypervisor then passes the request to the underlying hardware, which performs the task. 

The following are the two main types of hypervisors.

Type 1 hypervisors
A type 1 hypervisor—also called a bare-metal hypervisor—runs directly on the computer hardware. It has some operating system capabilities and is highly efficient because it interacts directly with the physical resources. 

Type 2 hypervisors 
A type 2 hypervisor runs as an application on computer hardware with an existing operating system. Use this type of hypervisor when running multiple operating systems on a single machine.   

---
 ![Image](https://insights.sei.cmu.edu/media/images/multicorevirtualization_firesm.max-1280x720.format-webp.webp)
 
### [Types of Virtualizations :](TypesOfVirtualization.md)

