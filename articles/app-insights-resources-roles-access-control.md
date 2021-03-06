<properties 
	pageTitle="Resources, roles and access control in Application Insights" 
	description="Owners, contributors and readers of your organization's insights." 
	services="application-insights" 
    documentationCenter=""
	authors="alancameronwills" 
	manager="ronmart"/>

<tags 
	ms.service="application-insights" 
	ms.workload="tbd" 
	ms.tgt_pltfrm="ibiza" 
	ms.devlang="na" 
	ms.topic="article" 
	ms.date="04/21/2015" 
	ms.author="awills"/>
 
# Resources, roles, and access control in Application Insights

You can control who has read and update access to your data in Visual Studio [Application Insights][start], by using [Role-based access control in Microsoft Azure](role-based-access-control-configure.md).

> [AZURE.IMPORTANT] Assign access to users in the **resource group or subscription** to which your application resource belongs - not in the resource itself. Assign the **Application Insights component contributor ** role. This ensures uniform control of access to web tests and alerts along with your application resource. 


## Set access in the resource group

It's important to understand that in addition to the resource you created for your application, there are also separate hidden resources for alerts and web tests. They are attached to the same [resource group](#resource-groups) as your application. You might also have put other Azure services in there, such as websites or storage.

![Resources in Application Insights](./media/app-insights-resources-roles-access-control/00-resources.png)

To control access to these resources it's therefore recommended to:

* Control access at the **resource group or subscription** level.
* Assign the **Application Insights Component contributor** role to users. This allows them to edit web tests, alerts, and Application Insights resources, without providing access to any other services in the group. 

## To provide access to another user

You must have Owner rights to the subscription or the resource group.

The user must have a Windows Live ID. You can provide access to individuals, and also to user groups defined in Azure Active Directory.

#### Navigate to the resource group

Add the user there.

![In your application's resource blade, open Essentials, open the resource group, and there select Settings/Users. Click Add.](./media/app-insights-resources-roles-access-control/01-add-user.png)

Or you could go up another level and add the user to the Subscription.

#### Select a role

![Select a role for the new user](./media/app-insights-resources-roles-access-control/03-role.png)

Role | In the resource group
---|---
Owner | Can change anything, including user access
Contributor | Can edit anything, including all resources
Application Insights Component contributor | Can edit Application Insights resources, web tests and alerts
Reader | Can view but not change anything

'Editing' includes creating, deleting and updating:

* Resources
* Web tests
* Alerts
* Continuous export

#### Select the user


![Type the email address of a new user. Select the user](./media/app-insights-resources-roles-access-control/04-user.png)

If the user you want isn't in the directory, you can invite anyone with a Microsoft account. 
(If they use services like Outlook.com, OneDrive, Windows Phone, or XBox Live, they have a Microsoft account.)



## Users and roles

* [Role based access control in Azure](role-based-access-control-configure.md)


## Resources, groups and subscriptions

Some definitions:

* **Resource** - An instance of a service you use in Microsoft Azure. When you configure Application Insights to monitor your application, you create a Microsoft Azure resource. Azure resources are services of different types, such as web apps, databases, VMs, or Application Insights monitors. Each resource has a unique ID.
* **Resource group** - Every resource belongs to one group. A group is a convenient way to manage related resources, particularly for access control. For example, a group might contain a Web App, an Application Insights resource to monitor the app, and a Storage resource to keep exported data.
* **Subscription** - To use Application Insights or other Azure resources, you login to an Azure subscription. Every resource group belongs to one Azure subscription, where you choose your price package and, if it’s an organization subscription, choose the members and their access permissions. 
* **Microsoft account** - The username and password that you use to login to Microsoft Azure subscriptions, XBox Live, Outlook.com, and other Microsoft services.


#### How to find your resources

Browse either everything (all your resources) or filter on your Application Insights resources, or other types.

![Choose Browse, then either Everything or Filter by Application Insights](./media/app-insights-resources-roles-access-control/10-browse.png)

The icons in the list show whether there are active [alerts][alerts].

## Resource groups

Use resource groups for related resources. For example, you could group together a web app hosted in Azure with an Application Insights resource that monitors it. If you have phone apps that wrap access to the web service, create Application Insights resources to monitor them in the same group.

![Choose Browse, Resource groups, then choose a group](./media/app-insights-resources-roles-access-control/11-group.png)

<!--Link references-->

[alerts]: app-insights-alerts.md
[android]: https://github.com/Microsoft/AppInsights-Android
[api]: app-insights-custom-events-metrics-api.md
[apiproperties]: app-insights-custom-events-metrics-api.md#properties
[apiref]: http://msdn.microsoft.com/library/azure/dn887942.aspx
[availability]: app-insights-monitor-web-app-availability.md
[azure]: insights-perf-analytics.md
[azure-availability]: insights-create-web-tests.md
[azure-usage]: insights-usage-analytics.md
[azurediagnostic]: insights-how-to-use-diagnostics.md
[client]: app-insights-web-track-usage.md
[config]: app-insights-configuration-with-applicationinsights-config.md
[data]: app-insights-data-retention-privacy.md
[desktop]: app-insights-windows-desktop.md
[detect]: app-insights-detect-triage-diagnose.md
[diagnostic]: app-insights-diagnostic-search.md
[eclipse]: app-insights-java-eclipse.md
[exceptions]: app-insights-web-failures-exceptions.md
[export]: app-insights-export-telemetry.md
[exportcode]: app-insights-code-sample-export-telemetry-sql-database.md
[greenbrown]: app-insights-start-monitoring-app-health-usage.md
[java]: app-insights-java-get-started.md
[javalogs]: app-insights-java-trace-logs.md
[javareqs]: app-insights-java-track-http-requests.md
[knowUsers]: app-insights-overview-usage.md
[metrics]: app-insights-metrics-explorer.md
[netlogs]: app-insights-asp-net-trace-logs.md
[new]: app-insights-create-new-resource.md
[older]: http://www.visualstudio.com/get-started/get-usage-data-vs
[perf]: app-insights-web-monitor-performance.md
[platforms]: app-insights-platforms.md
[portal]: http://portal.azure.com/
[qna]: app-insights-troubleshoot-faq.md
[redfield]: app-insights-monitor-performance-live-website-now.md
[roles]: app-insights-role-based-access-control.md
[start]: app-insights-get-started.md
[trace]: app-insights-search-diagnostic-logs.md
[track]: app-insights-custom-events-metrics-api.md
[usage]: app-insights-web-track-usage.md
[windows]: app-insights-windows-get-started.md
[windowsCrash]: app-insights-windows-crashes.md
[windowsUsage]: app-insights-windows-usage.md

