## Monthly Cost Analysis
Complete a month cost analysis of each Azure resource to give an estimate total cost using the table below:
 
| Azure Resource              | Service Tier            | Monthly Cost | Note                          |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
| Azure Postgres Database     | Basic                   | $104         | Single server                 |
|                             |                         |              | Hours: 2000                   |
|                             |                         |              | Storage: 5GB                  |
|                             |                         |              | Backup Storage: 100GB         |
|                             |                         |              | Compute: Gen5, 1vCore         |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
| Azure Service Bus           | Basic                   | $80.00       | Operations per month:         |    
|                             |                         |              |          1600 X 1 mil         |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
| Azure Function App          | Comsumption             | $45.40       | Memory size: 1.536MB          |
|                             |                         |              | Execution time: 100           |
|                             |                         |              | Execution per month: 2000000  |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
| Azure Web App               | Basic                   | $36          | OS: Linux                     |
|                             |                         |              | Instances: 1 (B1)             |
|                             |                         |              | Hours: 2000                   |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
| Azure Storage Account       | Standard                | $20          | Capacity: 1000GB              |
|                             |                         |              | Storage Account Type:         |
|                             |                         |              |  Genral Purpose V2            |
| --------------------------- | ----------------------- | ------------ | ----------------------------- |
|                             | TOTAL:                  | $240.44      |                               |
## Architecture Explanation
Azure Function App (Consumption):

Monthly Cost: $45.40
Reasoning: Azure Function App in the Consumption plan is a cost-effective choice for handling background tasks, especially when I have a variable load. I pay only for the actual execution time and resources used. This serverless architecture minimizes costs during periods of low activity and automatically scales as needed, making it a cost-effective choice for my use case.

Azure Web App (Basic):
Monthly Cost: $36
Reasoning: Choosing a Basic tier Azure Web App with a single B1 instance running Linux is cost-effective for hosting my web application. This tier offers sufficient resources for a low to moderate traffic website, and it aligns with my expected usage of 2000 hours per month, making it a cost-effective choice for my scenario.

My selection of Azure resources and service tiers appears to be well-considered in terms of cost-effectiveness for my application's requirements. My total monthly cost estimate of $240.44 is reasonable for the services and resources I've chosen, given the expected workload and usage patterns.
Drawbacks of the existing architecture include the risk of HTTP timeout errors, particularly for time-consuming tasks, which can hinder user experience and system stability.

The current architecture offers advantages by employing Azure Service Bus Queue and Azure Functions to decouple the web app's processes, enabling efficient background processing, such as sending emails. This decoupling improves performance, scalability, and cost-effectiveness, while also facilitating error isolation and streamlined task management.
