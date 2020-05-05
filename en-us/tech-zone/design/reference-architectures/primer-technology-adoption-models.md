## Technology Delivery/Adoption Models - a Primer

Citrix Virtual Apps and Desktops technology can be 'consumed' or implemented many different ways. The most common methods can be described generally as **Customer Managed** and **Cloud Services**. A third model is also worth mentioning - **Partner Managed**. We'll describe this model here for clarity, but from an architectural design perspective, the first two are the most relevant.

The choice of adoption or 'consumption' model has a substantial impact upon the system design, capabilities, cost, and delineation of management responsibilities. This primer will define and explore these models, and provide some general guidance to help customers make informed choices as they design a Citrix virtualization system.

## Customer Managed

For many years, businesses wanting to consume technology had no choice but to buy, install, configure, and maintain the entire technology stack required to build a Citrix virtualization system. Citrix's virtualization software was only available as installable binaries.
Customers who bought Citrix's virtualization software would download these binaries (often in the form of a downloadable ISO disk image or self-extracting executables) then install, configure, and maintain the software themselves. The Citrix software (and networking hardware) was most commonly installed into/on infrastructure the customer owned and maintained, in data centers they also owned and maintained.

Conceptually speaking, a Citrix virtualization system is made up of various different Citrix components, many of which we'll describe in detail in this paper. They also require different layers of third-party components which must be provided before you can do anything with the Citrix bits. Ultimately, they all come together to create a functional Citrix virtualization system. For the sake of clarity, this document refers to this technology adoption model as **"Customer Managed"**.
We use this term to describe various different components in a Citrix virtualization system, including the requisite third party components in the layers underneath, next to, and 'above' the Citrix components. This model can also be called "Self-Managed."

Today, customers have very compelling alternatives to a customer managed adoption model, yet some still adopt elements of their technology stack using this model for various reasons. While this model provides customers with the **most control over each component**, it comes at a cost: the customer takes on the responsibility to manage and maintain the component, including securing, operating, patching, upgrading, and maintaining high availability. 

In the context of Citrix virtualization technologies, the following are considered **Customer Managed**:
-  **Citrix Virtual Apps and Desktops (CVAD)**, either Long Term Service Release (LTSR) or Current Release (CR) versions. If you install and configure a delivery controller in your environment, this is what you're running.
-  **Citrix StoreFront**, delivered as a component of CVAD, it's installed/configured/maintained on customer managed Windows Servers.
-  **Citrix ADC/Gateway**, available as physical or virtual appliances, this networking component is deployed into customer environments and configured/managed by the customer.

#### Cloud Services

Over the last 15 years, technological advancements across many different fields have given rise to hyper scale public clouds, sophisticated cloud services, microservice architectures, DevOPS/Agile delivery frameworks, subscription licensing models, and 'evergreen' software and systems.
These advancements have revolutionized the way technology is acquired, adopted, delivered, and maintained across almost every industry in the world.

Today, many of the components or layers that comprise a Citrix virtualization system are available "as a Service." In contrast to the Customer Managed adoption model (where customers buy technology as a corporate asset and build/maintain systems themselves), customers "subscribe" to various services, and the service provider takes on the responsibility for delivering and managing these services. These services are often consumed over public networks (that is, the Internet) leading some to call this a "Cloud Service" or "Web Service" adoption model. In this paper we're going to refer to this type of adoption model as "Cloud Managed Services," or simply the **"Cloud Service"** model.

Citrix offers many of its traditional products 'as a Service', using its platform partners' latest technological advancements to simplify and streamline adoption, accelerate the pace of innovation, improve quality, and deliver more incremental value to their customers over time. Citrix calls this service delivery platform "Citrix Cloud," and it represents the current and future state of the art from Citrix.

In the context of Citrix Virtualization technologies, anything delivered from Citrix Cloud would be considered a **Cloud Service**. Examples include:
-  **Citrix Virtual Apps and Desktops Service**
-  **Citrix Gateway Service**
-  **Citrix Workspace Service**
-  **Citrix Analytics Service**

#### Partner Managed

While many organizations choose to build their own Citrix virtualization system, some customers seek to get out of the business of managing IT so they can focus resources and attention on serving their own customers and markets. To serve these customers, Citrix works with integration partners who use Citrix technologies to provide a 'finished goods' service to their customers.

Defining and differentiating the different integration partners/types and offerings available are outside of the scope of this primer. However, Citrix partners face the same choices customers face when designing a Citrix virtualization system. The Citrix partner may choose to use one or more services from Citrix Cloud, or they may choose to build and manage some components of the system for their customers' specific needs. As such, the guidance provided in Citrix reference architecture documentation is relevant to both the Citrix partner and their customers, just for different reasons.