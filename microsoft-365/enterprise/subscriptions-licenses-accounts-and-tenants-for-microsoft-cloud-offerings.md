---
title: Подписки, лицензии, учетные записи и клиенты для облачных предложений корпорации Майкрософт
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Общие сведения о связи между организациями, подписками, лицензиями, учетными записями пользователей и клиентами в облачных предложениях корпорации Майкрософт.
ms.openlocfilehash: e79189ac4c95f735597352d115038e994710852b
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357962"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="579e8-103">Подписки, лицензии, учетные записи и клиенты для облачных предложений корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="579e8-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="579e8-104">Для облачных решений Майкрософт предусмотрена иерархия организаций, подписок, лицензий и учетных записей пользователей. Это обеспечивает согласованное использование удостоверений и выставление счетов.</span><span class="sxs-lookup"><span data-stu-id="579e8-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="579e8-105">Microsoft 365 и Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="579e8-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="579e8-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="579e8-106">Microsoft Azure</span></span>
- <span data-ttu-id="579e8-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="579e8-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="579e8-108">Элементы иерархии</span><span class="sxs-lookup"><span data-stu-id="579e8-108">Elements of the hierarchy</span></span>

<span data-ttu-id="579e8-109">Ниже перечислены элементы иерархии.</span><span class="sxs-lookup"><span data-stu-id="579e8-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="579e8-110">Организация</span><span class="sxs-lookup"><span data-stu-id="579e8-110">Organization</span></span>

<span data-ttu-id="579e8-p101">Организация представляет субъект бизнес-деятельности, использующий облачные решения Майкрософт. Как правило, он определяется по одному или нескольким именам общедоступного домена службы доменных имен (DNS), например contoso.com. Организация является контейнером для подписок.</span><span class="sxs-lookup"><span data-stu-id="579e8-p101">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com. The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="579e8-113">Подписки</span><span class="sxs-lookup"><span data-stu-id="579e8-113">Subscriptions</span></span>

<span data-ttu-id="579e8-114">Подписка — это соглашение с корпорацией Майкрософт на использование одной или нескольких облачных платформ или служб Майкрософт, за которые взимается плата (по лицензиям отдельных пользователей или по использованию облачных ресурсов).</span><span class="sxs-lookup"><span data-stu-id="579e8-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="579e8-115">В облачных предложениях корпорации Майкрософт на основе SaaS (Microsoft 365 и Dynamics 365) оплата взимается за лицензии пользователей.</span><span class="sxs-lookup"><span data-stu-id="579e8-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="579e8-116">В облачных предложениях корпорации Майкрософт (Azure) на основе PaaS (платформа как услуга) и IaaS (инфраструктура как услуга) оплата взимается за использование облачных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="579e8-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="579e8-p102">Вы также можете использовать пробную подписку, срок действия которой истекает через определенное время или после использования определенного количества ресурсов. Вы можете преобразовать пробную подписку в платную.</span><span class="sxs-lookup"><span data-stu-id="579e8-p102">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges. You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="579e8-119">У организации может быть несколько подписок на облачные предложения корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="579e8-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="579e8-120">На рисунке 1 показана одна организация с несколькими подписками на Microsoft 365 и Azure, а также подпиской на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="579e8-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="579e8-121">**Рис. 1. Пример использования нескольких подписок для организации**</span><span class="sxs-lookup"><span data-stu-id="579e8-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Пример организации с несколькими подписками на облачные предложения корпорации Майкрософт.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="579e8-123">Лицензии</span><span class="sxs-lookup"><span data-stu-id="579e8-123">Licenses</span></span>

<span data-ttu-id="579e8-124">В случае облачных предложений корпорации Майкрософт на основе SaaS лицензия позволяет определенному пользователю пользоваться услугами облачной службы.</span><span class="sxs-lookup"><span data-stu-id="579e8-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="579e8-125">В рамках подписки ежемесячно взимается фиксированная плата.</span><span class="sxs-lookup"><span data-stu-id="579e8-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="579e8-126">Администраторы назначают лицензии отдельным учетным записям пользователей в подписке.</span><span class="sxs-lookup"><span data-stu-id="579e8-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="579e8-127">Например, на рисунке 2 у корпорации Contoso есть подписка на Microsoft 365 E5 со 100 лицензиями, что позволяет 100 отдельным пользователям использовать функции и службы Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="579e8-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="579e8-128">**Рис. 2. Лицензии в рамках подписок на основе SaaS для организации**</span><span class="sxs-lookup"><span data-stu-id="579e8-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Пример нескольких лицензий в подписках на облачные предложения корпорации Майкрософт на основе SaaS.](../media/Subscriptions/Subscriptions-Fig2.png)
  
<span data-ttu-id="579e8-130">В случае облачных служб на основе Azure PaaS стоимость лицензий на программное обеспечение включается в цену службы.</span><span class="sxs-lookup"><span data-stu-id="579e8-130">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="579e8-p105">Для виртуальных машин на основе Azure IaaS могут потребоваться дополнительные лицензии на использование ПО или приложений, установленных в образе виртуальной машины. В некоторых образах виртуальных машин установлены лицензированные версии программного обеспечения, цены которых включаются в поминутный тариф для сервера. К примерам таких виртуальных машин относятся образы для SQL Server 2014 и SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="579e8-p105">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required. Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server. Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="579e8-p106">В некоторых образах виртуальных машин установлены пробные версии приложений, а для их использования по завершении пробного периода требуются дополнительные лицензии. Например, образ виртуальной машины для пробной версии SharePoint Server 2016 включает предустановленную пробную версию SharePoint Server 2016. Чтобы продолжать использовать SharePoint Server 2016 по истечении пробного периода, необходимо приобрести у корпорации Майкрософт лицензию на SharePoint Server 2016 и клиентские лицензии. Эта плата взимается отдельно от платы за подписку Azure и не отменяет поминутный тариф на работу виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="579e8-p106">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period. For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed. To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft. These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="579e8-138">Учетные записи пользователей</span><span class="sxs-lookup"><span data-stu-id="579e8-138">User accounts</span></span>

<span data-ttu-id="579e8-139">Учетные записи для всех облачных предложений корпорации Майкрософт хранятся в клиенте Azure Active Directory (Azure AD), содержащем учетные записи и группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="579e8-139">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="579e8-140">Клиент Azure AD можно синхронизировать с имеющимися учетными записями доменных служб Active Directory (AD DS) с помощью Azure AD Connect, серверной службы Windows.</span><span class="sxs-lookup"><span data-stu-id="579e8-140">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="579e8-141">Это называется синхронизацией службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="579e8-141">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="579e8-142">На рис. 3 показан пример нескольких подписок организации, использующих общий клиент Azure AD с учетными записями организации.</span><span class="sxs-lookup"><span data-stu-id="579e8-142">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="579e8-143">**Рис. 3. Несколько подписок организации, использующих один клиент Azure AD**</span><span class="sxs-lookup"><span data-stu-id="579e8-143">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![Пример организации с несколькими подписками, использующими один и тот же клиент Azure AD.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="579e8-145">Клиенты</span><span class="sxs-lookup"><span data-stu-id="579e8-145">Tenants</span></span>

<span data-ttu-id="579e8-146">В случае облачных предложений на основе SaaS клиент — это регион, в котором располагаются серверы, предоставляющие облачные службы.</span><span class="sxs-lookup"><span data-stu-id="579e8-146">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="579e8-147">Например, корпорация Contoso выбрала европейский регион для размещения клиентов Microsoft 365, EMS и Dynamics 365, которыми пользуются 15 000 сотрудников главного офиса компании в Париже.</span><span class="sxs-lookup"><span data-stu-id="579e8-147">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="579e8-p109">Службы PaaS Azure и рабочие нагрузки на основе виртуальных машин, размещенные на платформе IaaS Azure, могут находиться в центре обработки данных Azure в любой точке мира. Центр обработки данных Azure, или расположение, указывается при создании приложения или службы PaaS Azure либо элемента рабочей нагрузки IaaS.</span><span class="sxs-lookup"><span data-stu-id="579e8-p109">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world. You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="579e8-150">Клиент Azure AD — это определенный экземпляр Azure AD, содержащий учетные записи и группы.</span><span class="sxs-lookup"><span data-stu-id="579e8-150">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="579e8-151">Платные и пробные подписки Microsoft 365 или Dynamics 365 включают бесплатный клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="579e8-151">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="579e8-152">Этот клиент Azure AD не включает службы Azure и не предоставляется с пробной или платной подпиской Azure.</span><span class="sxs-lookup"><span data-stu-id="579e8-152">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="579e8-153">Сводка по иерархии</span><span class="sxs-lookup"><span data-stu-id="579e8-153">Summary of the hierarchy</span></span>

<span data-ttu-id="579e8-154">Краткая сводка:</span><span class="sxs-lookup"><span data-stu-id="579e8-154">Here is a quick recap:</span></span>
  
- <span data-ttu-id="579e8-155">У организации может быть несколько подписок</span><span class="sxs-lookup"><span data-stu-id="579e8-155">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="579e8-156">В одной подписке может быть несколько лицензий</span><span class="sxs-lookup"><span data-stu-id="579e8-156">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="579e8-157">Лицензии можно назначать отдельным учетным записям</span><span class="sxs-lookup"><span data-stu-id="579e8-157">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="579e8-158">Учетные записи хранятся в клиенте Azure AD</span><span class="sxs-lookup"><span data-stu-id="579e8-158">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="579e8-159">Ниже приведен пример связи между организациями, подписками, лицензиями и учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="579e8-159">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="579e8-160">Организация определяется по имени общедоступного домена.</span><span class="sxs-lookup"><span data-stu-id="579e8-160">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="579e8-161">Подписка на Microsoft 365 E3 с лицензиями "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="579e8-161">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="579e8-162">Подписка на Microsoft 365 E5 с лицензиями "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="579e8-162">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="579e8-163">Подписка на Dynamics 365 с лицензиями "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="579e8-163">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="579e8-164">Несколько подписок на Azure.</span><span class="sxs-lookup"><span data-stu-id="579e8-164">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="579e8-165">Учетные записи пользователей организации на общем клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="579e8-165">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="579e8-166">Для нескольких подписок на облачные решения Майкрософт может использоваться один клиент Azure AD, выступающий в качестве поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="579e8-166">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="579e8-167">Благодаря центральному клиенту Azure AD, содержащему синхронизированные учетные записи из локальной службы AD DS, возможно предоставление удостоверений как услуги (IDaaS) для организации.</span><span class="sxs-lookup"><span data-stu-id="579e8-167">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="579e8-168">**Рис. 4. Синхронизированные локальные учетные записи и IDaaS для организации**</span><span class="sxs-lookup"><span data-stu-id="579e8-168">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![Идентификация как служба (IDaaS) для организации.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="579e8-p112">На рисунке 4 показано, как взаимодействуют с общим клиентом Azure AD облачные решения SaaS Майкрософт, приложения PaaS Azure и виртуальные машины на платформе IaaS Azure, использующие доменные службы Azure AD. Клиент Azure AD синхронизируется с локальным лесом AD DS с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="579e8-p112">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services. Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="579e8-172">Объединение подписок для нескольких облачных предложений корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="579e8-172">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="579e8-173">В приведенной ниже таблице показано, как объединить несколько облачных предложений корпорации Майкрософт на основе имеющейся подписки на облачное предложение одного типа (подписи в первом столбце) и добавленной подписки на другое решение (поперек столбцов).</span><span class="sxs-lookup"><span data-stu-id="579e8-173">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="579e8-174">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="579e8-174">**Microsoft 365**</span></span>|<span data-ttu-id="579e8-175">**Azure**</span><span class="sxs-lookup"><span data-stu-id="579e8-175">**Azure**</span></span>|<span data-ttu-id="579e8-176">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="579e8-176">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="579e8-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="579e8-177">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="579e8-178">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579e8-178">NA</span></span>  <br/> |<span data-ttu-id="579e8-179">Добавьте подписку Azure для организации с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="579e8-179">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="579e8-180">Добавьте подписку на Dynamics 365 для организации в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="579e8-180">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="579e8-181">**Azure**</span><span class="sxs-lookup"><span data-stu-id="579e8-181">**Azure**</span></span> <br/> |<span data-ttu-id="579e8-182">Добавьте подписку на Microsoft 365 для организации.</span><span class="sxs-lookup"><span data-stu-id="579e8-182">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="579e8-183">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579e8-183">NA</span></span>  <br/> |<span data-ttu-id="579e8-184">Добавьте подписку Dynamics 365 для организации.</span><span class="sxs-lookup"><span data-stu-id="579e8-184">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="579e8-185">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="579e8-185">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="579e8-186">Добавьте подписку на Microsoft 365 для организации.</span><span class="sxs-lookup"><span data-stu-id="579e8-186">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="579e8-187">Добавьте подписку Azure для организации с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="579e8-187">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="579e8-188">Н/Д</span><span class="sxs-lookup"><span data-stu-id="579e8-188">NA</span></span>  <br/> |
   
<span data-ttu-id="579e8-189">Вы можете с легкостью добавить подписки на службы Майкрософт на основе SaaS для организации, используя Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="579e8-189">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="579e8-190">Войдите в Центр администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="579e8-190">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="579e8-191">В левой части главной страницы **Центра администрирования** выберите **Выставление счетов** > **Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="579e8-191">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="579e8-192">На странице **Приобретение служб** купите новые подписки.</span><span class="sxs-lookup"><span data-stu-id="579e8-192">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="579e8-193">Центр администрирования назначает организации и клиенту Azure AD, у которых есть подписка на Microsoft 365, новые подписки на облачные решения на основе SaaS.</span><span class="sxs-lookup"><span data-stu-id="579e8-193">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="579e8-194">Чтобы добавить подписку Azure с теми же организацией и клиентом Azure AD, что и в подписке на Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="579e8-194">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="579e8-195">Войдите на портал Azure ([https://portal.azure.com](https://portal.azure.com)), используя учетную запись глобального администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="579e8-195">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="579e8-196">В области навигации слева выберите **Подписки** > **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="579e8-196">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="579e8-197">На странице **Добавление подписки** выберите предложение, а затем укажите платежную информацию и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="579e8-197">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="579e8-198">Если вы приобрели подписки на Azure и Microsoft 365 отдельно и хотите получить доступ к клиенту Azure AD в Microsoft 365, воспользуйтесь инструкциями в статье [Добавление существующей подписки на Azure с клиентом Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span><span class="sxs-lookup"><span data-stu-id="579e8-198">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="579e8-199">См. также</span><span class="sxs-lookup"><span data-stu-id="579e8-199">See also</span></span>

[<span data-ttu-id="579e8-200">Иллюстрации "Облако Майкрософт для корпоративных архитекторов"</span><span class="sxs-lookup"><span data-stu-id="579e8-200">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="579e8-201">Архитектурные модели для SharePoint, Exchange, Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="579e8-201">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="579e8-202">Гибридные решения</span><span class="sxs-lookup"><span data-stu-id="579e8-202">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="579e8-203">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="579e8-203">Next step</span></span>

[<span data-ttu-id="579e8-204">Оценка сетевого подключения Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="579e8-204">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
