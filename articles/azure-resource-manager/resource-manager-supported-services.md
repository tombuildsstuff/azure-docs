---
title: Resource Manager supported services | Microsoft Docs
description: Describes the resource providers that support Resource Manager, their schemas and available API versions, and the regions that can host the resources.
services: azure-resource-manager
documentationcenter: na
author: tfitzmac
manager: timlt
editor: tysonn

ms.assetid: 3c7a6fe4-371a-40da-9ebe-b574f583305b
ms.service: azure-resource-manager
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/27/2016
ms.author: magoedte;tomfitz

---
# Resource Manager providers, regions, API versions and schemas
Azure Resource Manager provides a new way for you to deploy and manage the services that make up your applications. Most, but not all, services support Resource Manager, and some services support Resource Manager only partially. This topic provides a list of supported resource providers for Azure Resource Manager.

When deploying your resources, you also need to know which regions support those resources and which API versions are available for the resources. The section [Supported regions](#supported-regions) shows you how to find out which regions work for your subscription and resources. The section [Supported API versions](#supported-api-versions) shows you how to determine which API versions you can use.

To see which services are supported in the Azure portal and classic portal, see [Azure portal availability chart](https://azure.microsoft.com/features/azure-portal/availability/). To see which services support moving resources, see [Move resources to new resource group or subscription](resource-group-move-resources.md).

The following tables list which Microsoft services support deployment and management through Resource Manager and which do not. The link in the column **Quickstart Templates** sends a query to the Azure Quickstart Templates repository for the specified resource provider. Quickstart templates are added and updated frequently. The presence of a link for a particular service does not necessarily mean the query returns templates from the repository. There are also many third-party resource providers that support Resource Manager. You learn how to see all the resource providers in the [Resource providers and types](#resource-providers-and-types) section.

## Compute
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Batch |Yes |[Batch REST](/rest/api/batchservice) |[Batch Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-12-01/Microsoft.Batch.json) | |
| Container Registry |Yes |[Container Registry REST](/rest/api/containerregistry) |[Container Registry Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-06-27-preview/Microsoft.ContainerRegistry.json) |[Microsoft.ContainerRegistry](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.ContainerRegistry%22&type=Code) |
| Container Service |Yes |[Container Service REST](/rest/api/compute/containerservices) |[Container Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-03-30/Microsoft.ContainerService.json) |[Microsoft.ContainerService](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.ContainerService%22&type=Code) |
| Dynamics Lifecycle Services |Yes | | | |
| Scale Sets |Yes |[Scale Set REST](/rest/api/compute/virtualmachinescalesets) |[Scale Set Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Compute.json) |[virtualMachineScaleSets](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=virtualMachineScaleSets&type=Code) |
| Service Fabric |Yes |[Service Fabric Rest](/rest/api/servicefabric) | [Service Fabric Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-09-01/Microsoft.ServiceFabric.json) |[Microsoft.ServiceFabric](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.ServiceFabric%22&type=Code) |
| Virtual Machines |Yes |[VM REST](/rest/api/compute/virtualmachines) |[VM Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Compute.json) |[virtualMachines](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Compute%2Fvirtualmachines%22&type=Code) |
| Virtual Machines (classic) |Limited |- |- |- |
| Remote App |No |- |- |- |
| Cloud Services (classic) |Limited (see below) |- |- |- |

Virtual Machines (classic) refers to resources that were deployed through the classic deployment model, instead of through the Resource Manager deployment model. In general, these resources do not support Resource Manager operations, but there 
are some operations that have been enabled. For more information about these deployment models, see [Understanding Resource Manager deployment and classic deployment](resource-manager-deployment-model.md). 

Cloud Services (classic) can be used with other classic resources. However, classic resources do not take advantage of all Resource Manager features and are not a good option for future solutions. Instead, consider changing your application infrastructure to use resources from the Microsoft.Compute, Microsoft.Storage, and Microsoft.Network namespaces.

## Networking
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Application Gateway |Yes |[Application Gateway REST](https://msdn.microsoft.com/library/azure/mt684939.aspx) | |[applicationGateways](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FapplicationGateways%22&type=Code) |
| DNS |Yes |[DNS REST](/rest/api/dns) |[DNS Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-04-01/Microsoft.Network.json) |[dnsZones](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FdnsZones%22&type=Code) |
| ExpressRoute |Yes |[ExpressRoute REST](https://msdn.microsoft.com/library/azure/mt586720.aspx) | |[expressRouteCircuits](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FexpressRouteCircuits%22&type=Code) |
| Load Balancer |Yes |[Load Balancer REST](https://msdn.microsoft.com/library/azure/mt163651.aspx) |[Load Balancer Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Network.json) |[loadBalancers](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2Floadbalancers%22&type=Code) |
| Traffic Manager |Yes |[Traffic Manager REST](https://msdn.microsoft.com/library/azure/mt163667.aspx) |[Traffic Manager Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-11-01/Microsoft.Network.json) |[trafficmanagerprofiles](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2Ftrafficmanagerprofiles%22&type=Code) |
| Virtual Networks |Yes |[Virtual Network REST](https://msdn.microsoft.com/en-us/library/azure/mt163650.aspx) |[Virtual Network Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Network.json) |[virtualNetworks](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FvirtualNetworks%22&type=Code) |
| VPN Gateway |Yes |[Network Gateway REST](https://msdn.microsoft.com/library/azure/mt163859.aspx) | |[virtualNetworkGateways](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FvirtualNetworkGateways%22&type=Code) <br /> [localNetworkGateways](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2FlocalNetworkGateways%22&type=Code) <br />[connections](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Network%2Fconnections%22&type=Code) |

## Storage
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- | --- |
| Storage |Yes |[Storage REST](/rest/api/storagerp) |[Storage account](resource-manager-template-storage.md) |[Microsoft.Storage](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Storage%22&type=Code) |
| StorSimple |Yes | | | |

## Databases
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- | --- |
| DocumentDB |Yes |[DocumentDB REST](/rest/api/documentdbresourceprovider) |[DocumentDB Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-04-08/Microsoft.DocumentDB.json) |[Microsoft.DocumentDB](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.DocumentDb%22&type=Code) |
| Redis Cache |Yes | [Redis Cache REST](/rest/api/redis) |[Redis Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-04-01/Microsoft.Cache.json) |[Microsoft.Cache](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Cache%22&type=Code) |
| SQL Database |Yes |[SQL Database REST](/rest/api/sql) |[SQL Database Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2014-04-01-preview/Microsoft.Sql.json) |[Microsoft.Sql](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Sql%22&type=Code) |
| SQL Data Warehouse |Yes | | | |

## Web & Mobile
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| API Apps |Yes | [App Service REST](/rest/api/appservice) |[API Apps Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Web.json) |[API Apps](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22kind%22%3A+%22apiApp%22&type=Code) |
| API Management |Yes |[API Management REST](/rest/api/apimanagement) |[API Management Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-07-07/Microsoft.ApiManagement.json) |[Microsoft.ApiManagement](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.ApiManagement%22&type=Code) |
| Content Moderator |Yes | | | |
| Function App |Yes | [Function App REST](/rest/api/appservice) | |[functionApp](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22functionApp%22&type=Code) |
| Logic Apps |Yes |[Logic Apps REST](/rest/api/logic) |[Logic Apps Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-06-01/Microsoft.Logic.json) |[Microsoft.Logic](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Logic%22&type=Code) |
| Mobile Apps |Yes | [App Service REST](/rest/api/appservice) |[Mobile Apps Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Web.json) |[mobileApp](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22mobileApp%22&type=Code) |
| Mobile Engagements |Yes |[Mobile Engagement REST](https://msdn.microsoft.com/library/azure/mt683754.aspx) | |[Microsoft.MobileEngagements](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.MobileEngagement%22&type=Code) |
| Search |Yes |[Search REST](/rest/api/searchservice) | [Search Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-19/Microsoft.Search.json) |[Microsoft.Search](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Search%22&type=Code) |
| Web Apps |Yes | [Web Apps REST](/rest/api/appservice/webapps) |[Web Apps Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.Web.json) |[Microsoft.Web](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Web%22&type=Code) |

## Intelligence + Analytics
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Analysis Services | Yes | [Analysis Service REST](/rest/api/analysisservices) | [Analysis Services Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-05-16/Microsoft.AnalysisServices.json) | |
| Cognitive Services |Yes | [Cognitive Services REST](/rest/api/cognitiveservices) |[Cognitive Services Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-02-01-preview/Microsoft.CognitiveServices.json) | |
| Data Catalog |Yes |[Data Catalog REST](/rest/api/datacatalog) |[Data Catalog Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-03-30/Microsoft.DataCatalog.json) | |
| Data Factory |Yes |[Data Factory REST](/rest/api/datafactory) | |[Microsoft.DataFactory](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.DataFactory%22&type=Code) |
| Data Lake Analytics |Yes | [Data Lake REST](/rest/api/datalakeanalytics) |[Data Lake Analytics Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-10-01-preview/Microsoft.DataLakeAnalytics.json) |[Microsoft.DataLakeAnalytics](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.DataLakeAnalytics%22&type=Code) |
| Data Lake Store |Yes |[Data Lake Store REST](/rest/api/datalakestore) |[Data Lake Store Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-10-01-preview/Microsoft.DataLakeStore.json) |[Microsoft.DataLakeStore](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.DataLakeStore%22&type=Code) |
| HDInsights |Yes |[HDInsights REST](/rest/api/hdinsight) | |[Microsoft.HDInsight](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.HDInsight%22&type=Code) |
| Machine Learning |Yes |[Machine Learning REST](/rest/api/machinelearning) |[Machine Learning Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-05-01-preview/Microsoft.MachineLearning.json) | |
| Stream Analytics |Yes |[Steam Analytics REST](/rest/api/streamanalytics) | | |
| Power BI |Yes |[Power BI Embedded REST](/rest/api/powerbiembedded) |[Power BI Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-01-29/Microsoft.PowerBI.json) | |


## Internet of Things
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Event Hub |Yes |[Event Hub REST](/rest/api/eventhub) |[Event Hub Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.EventHub.json) |[Microsoft.EventHub](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.EventHub%22&type=Code) |
| IoTHubs |Yes |[IoT Hub REST](/rest/api/iothub) |[IoT Hub Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-02-03/Microsoft.Devices.json) |[Microsoft.Devices](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Devices%22&type=Code) |
| Notification Hubs |Yes |[Notification Hub REST](/rest/api/notificationhubs) |[Notification Hub Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-04-01/Microsoft.NotificationHubs.json) |[Microsoft.NotificationHubs](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.NotificationHubs%22&type=Code) |

## Media & CDN
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| CDN |Yes |[CDN REST](/rest/api/cdn) |[CDN Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-04-02/Microsoft.Cdn.json) |[Microsoft.Cdn](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Cdn%22&type=Code) |
| Media Service |Yes |[Media Services REST](/rest/api/media) |[Media Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-10-01/Microsoft.Media.json) |[Microsoft.Media](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Media%22&type=Code)  |

## Hybrid Integration
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| BizTalk Services |Yes | |[BizTalk Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2014-04-01/Microsoft.BizTalkServices.json) | |
| Recovery Service |Yes |[Recovery Services REST](/rest/api/recoveryservices) |[Recovery Services Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-06-01/Microsoft.RecoveryServices.json) |[Microsoft.RecoveryServices](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.RecoveryServices%22&type=Code) |
| Service Bus |Yes |[Service Bus REST](/rest/api/servicebus) |[Service Bus Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-08-01/Microsoft.ServiceBus.json) |[Microsoft.ServiceBus](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.ServiceBus%22&type=Code) |

## Identity & Access Management
Azure Active Directory works with Resource Manager to enable role-based access control for your subscription. To learn about using role-based access control and Active Directory, see [Azure Role-based Access Control](../active-directory/role-based-access-control-configure.md).

## Developer Services
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Monitor |Yes |[Monitor REST](/rest/api/monitor) |[Insights Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2014-04-01/Microsoft.Insights.json) |[Microsoft.insights](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.insights%22&type=Code) |
| Bing Maps |Yes | | | |
| DevTest Labs |Yes | [DevTest REST](/rest/api/dtl) |[DevTest Lab Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-05-15/Microsoft.DevTestLab.json) |[Microsoft.DevTestLab](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.DevTestLab%22&type=Code) |
| Visual Studio account |Yes | |[Visual Studio Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2014-02-26/microsoft.visualstudio.json) | |

## Management and Security
| Service | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- |
| Automation |Yes |[Automation REST](https://msdn.microsoft.com/library/azure/mt662285.aspx) |[Automation Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2015-10-31/Microsoft.Automation.json) |[Microsoft.Automation](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Automation%22&type=Code) |
| Key Vault |Yes |[Key Vault REST](/rest/api/keyvault) |[Key vault](resource-manager-template-keyvault.md)<br />[Key vault secret](resource-manager-template-keyvault-secret.md) |[Microsoft.KeyVault](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.KeyVault%22&type=Code) |
| Operational Insights |Yes | | | |
| Scheduler |Yes |[Scheduler REST](/rest/api/scheduler) |[Scheduler Schema](https://github.com/Azure/azure-resource-manager-schemas/blob/master/schemas/2016-03-01/Microsoft.Scheduler.json) |[Microsoft.Scheduler](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Scheduler%22&type=Code) |
| Security (preview) |Yes |[Security REST](https://msdn.microsoft.com/library/azure/mt704034.aspx) | |[Microsoft.Security](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Security%22&type=Code) |

## Resource Manager
| Feature | Resource Manager Enabled | REST API | Schema | Quickstart Templates |
| --- | --- | --- | --- | --- | --- |
| Authorization |Yes |[Authorization REST](/rest/api/authorization) |[Resource lock](resource-manager-template-lock.md)<br />[Role assignments](resource-manager-template-role.md) |[Microsoft.Authorization](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Authorization%22&type=Code) |
| Resources |Yes |[Resources REST](/rest/api/resources) |[Resource links](resource-manager-template-links.md) |[Microsoft.Resources](https://github.com/Azure/azure-quickstart-templates/search?utf8=%E2%9C%93&q=%22Microsoft.Resources%22&type=Code) |

## Resource providers and types
When deploying resources, you frequently need to retrieve information about the resource providers and types. You can retrieve this information through REST API, Azure PowerShell, or Azure CLI.

To work with a resource provider, that resource provider must be registered with your account. By default, many resource providers are automatically registered; however, you may need to manually register some resource providers. The examples below show how to get the registration status of a resource provider, and register the resource provider, if needed.

### Portal
You can easily see a list of supported resources providers by selecting **Resource providers** from the subscription blade. To register your subscription with a resource provider, select the **Register** link.
   
![list resource providers](./media/resource-manager-supported-services/view-resource-providers.png)

### REST API
To get all the available resource providers, including their types, locations, API versions, and registration status, use the [List all resource providers](https://docs.microsoft.com/rest/api/resources/providers#Providers_List) operation. If you need to register a resource provider, see [Register a subscription with a resource provider](https://docs.microsoft.com/rest/api/resources/providers#Providers_Register).

### PowerShell
The following example shows how to get all the available resource providers.

    Get-AzureRmResourceProvider -ListAvailable


The next example shows how to get the resource types for a particular resource provider.

    (Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Web).ResourceTypes

The output is similar to:

    ResourceTypeName                Locations                                         
    ----------------                ---------                                         
    sites/extensions                {Brazil South, East Asia, East US, Japan East...} 
    sites/slots/extensions          {Brazil South, East Asia, East US, Japan East...} .
    ...

To register a resource provider, provide the namespace:

    Register-AzureRmResourceProvider -ProviderNamespace Microsoft.ApiManagement

### Azure CLI
The following example shows how to get all the available resource providers.

    azure provider list

The output is similar to:

    info:    Executing command provider list
    + Getting registered providers
    data:    Namespace                        Registered
    data:    -------------------------------  -------------
    data:    Microsoft.ApiManagement          Unregistered
    data:    Microsoft.AppService             Registered
    data:    Microsoft.Authorization          Registered
    ...

You can save the information for a particular resource provider to a file with the following command:

    azure provider show Microsoft.Web -vv --json > c:\temp.json

To register a resource provider, provide the namespace:

    azure provider register -n Microsoft.ServiceBus

## Supported regions
When deploying resources, you typically need to specify a region for the resources. Resource Manager is supported in all regions, but the resources you deploy might not be supported in all regions. In addition, there may be limitations on your subscription that prevent you from using some regions that support the resource. These limitations may be related to tax issues for your home country, or the result of a policy placed by your subscription administrator to use only certain regions. 

For a complete list of all supported regions for all Azure services, see [Services by region](https://azure.microsoft.com/regions/#services). However, this list may include regions that your subscription does not support. You can determine the regions for a particular resource type that your subscription supports through the portal, REST API, PowerShell, or Azure CLI.

### Portal
You can see the supported regions for a resource type through the following steps:

1. Select **More services** > **Resource Explorer**.
   
    ![resource explorer](./media/resource-manager-supported-services/select-resource-explorer.png)
2. Open the **Providers** node.
   
    ![select providers](./media/resource-manager-supported-services/select-providers.png)
3. Select a resource provider, and view the supported regions and API versions.
   
    ![view provider](./media/resource-manager-supported-services/view-provider.png)

### REST API
To discover which regions are available for a particular resource type in your subscription, use the [List all resource providers](https://docs.microsoft.com/rest/api/resources/providers#Providers_List) operation. 

### PowerShell
The following example shows how to get the supported regions for web sites.

    ((Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Web).ResourceTypes | Where-Object ResourceTypeName -eq sites).Locations

The output is similar to:

    Brazil South
    East Asia
    East US
    Japan East
    Japan West
    North Central US
    North Europe
    South Central US
    West Europe
    West US
    Southeast Asia
    Central US
    East US 2

### Azure CLI
The following example returns all the supported locations for each resource type.

    azure location list

You can also filter the location results with a JSON utility like [jq](https://stedolan.github.io/jq/).

    azure location list --json | jq '.[] | select(.name == "Microsoft.Web/sites")'

Which returns:

    {
      "name": "Microsoft.Web/sites",
      "location": "Brazil South,East Asia,East US,Japan East,Japan West,North Central US,
            North Europe,South Central US,West Europe,West US,Southeast Asia,Central US,East US 2"
    }

## Supported API versions
When you deploy a template, you must specify an API version to use for creating each resource. The API version corresponds to a version of REST API operations that are released by the resource provider. As a resource provider enables new features, it releases a new version of the REST API. Therefore, the version of the API you specify in your template affects which properties you can specify in the template. In general, you want to select the most recent API version when creating templates. For existing templates, you can decide whether you want to continue using an earlier API version, or update your template for the latest version to take advantage of new features.

### Portal
You determine the supported API versions in the same way you determined supported regions (shown previously).

### REST API
To discover which API versions are available for resource types, use the [List all resource providers](https://docs.microsoft.com/rest/api/resources/providers#Providers_List) operation. 

### PowerShell
The following example shows how to get the available API versions for a particular resource type.

    ((Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Web).ResourceTypes | Where-Object ResourceTypeName -eq sites).ApiVersions

The output is similar to:

    2015-08-01
    2015-07-01
    2015-06-01
    2015-05-01
    2015-04-01
    2015-02-01
    2014-11-01
    2014-06-01
    2014-04-01-preview
    2014-04-01

### Azure CLI
You can save the information (including the available API versions) for a resource provider to a file with the following command:

    azure provider show Microsoft.Web -vv --json > c:\temp.json

You can open the file and find the **apiVersions** element

## Next steps
* To learn about creating Resource Manager templates, see [Authoring Azure Resource Manager templates](resource-group-authoring-templates.md).
* To learn about deploying resources, see [Deploy an application with Azure Resource Manager template](resource-group-template-deploy.md).

