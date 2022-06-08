# Container Cost Allocation

Allocation of resource is a goal of FinOps. This section will detail common use case around container applications.

# Selected Use Case: Shared Platform for Product Teams

A shared Platform (AWS, Kubernetes) provided and operated by a central Platform Engineering Team that is used as the deployment target for 20+ Teams that develop business capabilities on it by also using external cloud Resources (S3,RDS,DynamoDB,Lambda and others).

![Selected Use Case](/assets/images/cost-allocation-chared-platform-team.png)

## Story and Personas

- During a board meeting the **Executives** were speaking about company goals and strategies and wondered what would be the impact of cloud costs in correlation to a new product launch and the continuous user growth, **Finance** was called in and they explained their evenly distributed allocation model across teams for the cloud invoice that has been applied since months, but it lead too many questions open also it was found to be very inaccurate so it was decided to improve that.

- As the Finance Team on their own were struggling how to start with more accurate cost allocation of cloud costs they reached out to the **Business** (Product Management and Owners) but they were not able to answer it either. Finally there was a cost transparency initiative triggered on Program level which increased the priority for implementing cost transparency throughout the Platform.

- In the initial Kickoff the task was given to the **Platform Engineering Team and Development Teams** so they should think of how to make the costs as transparent as needed for the business so they are able to report along with their value stream out of analytics data to the digital controlling department for mapping costs to value.


| Description | Context | Common <br>Resource(s) to label | label alias | Example Values | label | Executive | Business/Product Owner | Finance/Procurement | Engineering and Operations | Maturity |
|---|---|---|---|---|---|---|---|---|---|---|
| Application | App / Service Hierarchy | namespace<br>pod<br>deployment | application<br>app<br>application-name<br>application-id | ACME Fitness | application | No | Yes | Yes | Yes | 1-crawl |
| Product | App / Service Hierarchy | namespace<br>pod<br>deployment | product<br>workload<br>project | ACME Fitness Store<br>ACME Fitness+ Video Streaming | product | No | Yes | Yes | No | 2-walk |
| Service | App / Service Hierarchy | pod<br>deployment | service<br>service-id | Point of Sale<br>Store Shopping Cart<br>Store Catalog | service | No | No | Yes | Yes | 3-run |
| Microservice / Component / Function | App / Service Hierarchy | namespace,pod | component<br>tier | database<br>storage | component | No | Yes | No | Yes | 3-run |
| Business Unit / Department | Business organization | namespace<br>pod<br>deployment | business-unit<br>department<br>business-domain<br>domain | retail BU<br>streaming BU | department | No | Yes | Yes | No | 2-walk |
| Cost Center | Business organization | namespace<br>pod<br>deployment | psp-element<br>cost-center | [alpha-numeric codes] | cost-center | No | No | Yes | No | 1-crawl |
| Team | Business organization | namespace<br>pod<br>deployment | team<br>squad<br>group<br>owner<br>maintainer<br>contact | [team name]<br>[team id] | team | Yes | Yes | Yes | Yes | 1-crawl |
| Stage / Environment | Platform + Operations | namespace<br>pod<br>deployment | stage<br>environment<br>env | dev<br>staging<br>prod | environment | No | Yes | No | Yes | 2-walk |
| Technology Stack by Purpose | Platform + Operations | namespace<br>pod<br>deployment | stack<br>servicegroup | observability<br>build-tools<br>automation<br>security | tech-stack | No | Yes | Yes | Yes | 3-run |
| Customer (e.g. Multitenant platform) | Business organization | namespace<br>pod<br>deployment | customer | [customer-id]<br>[customer-name] | customer | Yes | Yes | Yes | No | 2-walk |


![Label Dictionary](/assets/images/cost-allocation-label-dictonary.png)
