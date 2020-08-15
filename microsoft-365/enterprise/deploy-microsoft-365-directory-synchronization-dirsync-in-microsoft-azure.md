---
title: Развертывание синхронизации каталогов Microsoft 365 в Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Узнайте, как развернуть Azure AD Connect на виртуальной машине в Azure для синхронизации учетных записей между локальным каталогом и клиентом Azure AD.
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693319"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="335ef-103">Развертывание синхронизации каталогов Microsoft 365 в Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="335ef-104">Azure Active Directory (Azure AD) Connect (ранее известное как средство синхронизации каталогов, средство синхронизации каталогов или средство DirSync.exe) — это приложение, которое устанавливается на сервере, присоединенном к домену, для синхронизации локальных пользователей доменных служб Active Directory (AD DS) с клиентом Azure AD вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="335ef-105">Microsoft 365 использует Azure AD для службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="335ef-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="335ef-106">Ваша подписка на Microsoft 365 включает клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="335ef-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="335ef-107">Этот клиент также может использоваться для управления удостоверениями организации с другими облачными рабочими нагрузками, в том числе с другими приложениями SaaS и приложениями в Azure.</span><span class="sxs-lookup"><span data-stu-id="335ef-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="335ef-108">Вы можете установить средство Azure AD Connect как на локальном сервере, так и на виртуальной машине в Azure. Последний вариант установки возможен по причинам, указанным ниже:</span><span class="sxs-lookup"><span data-stu-id="335ef-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="335ef-109">Вы можете быстрее подготовить и настроить облачные службы, чтобы сделать их доступными для пользователей.</span><span class="sxs-lookup"><span data-stu-id="335ef-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="335ef-110">Azure обеспечивает высокую доступность сайтов и требует меньше усилий.</span><span class="sxs-lookup"><span data-stu-id="335ef-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="335ef-111">Вы можете сократить количество локальных серверов в своей организации.</span><span class="sxs-lookup"><span data-stu-id="335ef-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="335ef-p102">Для этого решения требуется соединение между локальной сетью и виртуальной сетью Azure. Дополнительные сведения см. в статье [Подключение локальной сети к виртуальной сети Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="335ef-p102">This solution requires connectivity between your on-premises network and your Azure virtual network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="335ef-114">В этой статье описывается синхронизация одного домена в одном лесу.</span><span class="sxs-lookup"><span data-stu-id="335ef-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="335ef-115">Azure AD Connect синхронизирует все домены AD DS в лесу Active Directory с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="335ef-116">Если вы используете несколько лесов Active Directory для синхронизации с Microsoft 365, ознакомьтесь со статьей [синхронизация каталогов нескольких лесов с использованием единого входа](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="335ef-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="335ef-117">Общие сведения о развертывании синхронизации каталогов Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="335ef-118">На следующей схеме показана служба Azure AD Connect, запущенная на виртуальной машине в Azure (сервер синхронизации каталогов), которая синхронизирует локальный лес доменных служб Active Directory с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Средство Azure AD Connect на виртуальной машине в Azure Синхронизация локальных учетных записей с клиентом Azure AD подписки на Microsoft 365 с потоком трафика](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="335ef-p104">На этой схеме показаны две сети, соединенные VPN-подключением типа "сеть-сеть" или подключением ExpressRoute. В локальной сети размещаются контроллеры доменов AD DS, а в виртуальной сети Azure — сервер синхронизации каталогов, виртуальная машина, на которой запущено [средство Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Из сервера синхронизации каталогов исходит два основных потока трафика:</span><span class="sxs-lookup"><span data-stu-id="335ef-p104">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection. There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="335ef-123">Средство Azure AD Connect отправляет контроллеру домена в локальной сети запросы на изменение учетных записей и паролей.</span><span class="sxs-lookup"><span data-stu-id="335ef-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="335ef-124">Azure AD Connect отправляет изменения учетных записей и паролей в экземпляр Azure AD вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="335ef-125">Так как сервер синхронизации каталогов находится в расширенной части локальной сети, эти изменения отправляются через прокси-сервер локальной сети.</span><span class="sxs-lookup"><span data-stu-id="335ef-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="335ef-126">В этом решении описывается синхронизация одного домена Active Directory в одном лесу.</span><span class="sxs-lookup"><span data-stu-id="335ef-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="335ef-127">Azure AD Connect синхронизирует все домены Active Directory в лесу Active Directory с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="335ef-128">Если вы используете несколько лесов Active Directory для синхронизации с Microsoft 365, ознакомьтесь со статьей [синхронизация каталогов нескольких лесов с использованием единого входа](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span><span class="sxs-lookup"><span data-stu-id="335ef-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](https://go.microsoft.com/fwlink/p/?LinkId=393091).</span></span> 
  
<span data-ttu-id="335ef-129">Развертывание этого решения делится на два основных этапа:</span><span class="sxs-lookup"><span data-stu-id="335ef-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="335ef-p107">Создание виртуальной сети Azure и настройка VPN-подключения типа "сеть-сеть" к локальной сети. Дополнительные сведения см. в статье [Подключение локальной сети к виртуальной сети Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="335ef-p107">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="335ef-132">Установите [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) на виртуальной машине с присоединением к домену в Azure, а затем синхронизируйте локальные доменные службы Active Directory с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="335ef-133">Этот процесс включает следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="335ef-133">This involves:</span></span>
    
    <span data-ttu-id="335ef-134">Создание виртуальной машины Azure для запуска Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="335ef-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="335ef-135">Установка и настройка [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="335ef-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="335ef-136">Для настройки Azure AD Connect необходимы учетные данные (имя пользователя и пароль) учетной записи администратора Azure AD и учетной записи администратора Active Directory для предприятия.</span><span class="sxs-lookup"><span data-stu-id="335ef-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="335ef-137">Azure AD Connect выполняется немедленно и непрерывно, чтобы синхронизировать локальный лес AD DS с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="335ef-138">Прежде чем развертывать это решение в рабочей среде, вы можете использовать инструкции, приведенные в [статье смоделированная Корпоративная конфигурация](simulated-ent-base-configuration-microsoft-365-enterprise.md) , чтобы настроить эту конфигурацию в качестве эксперимента, демонстраций или экспериментов.</span><span class="sxs-lookup"><span data-stu-id="335ef-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="335ef-139">После настройки средство Azure AD Connect не сохраняет учетные данные администратора предприятия AD DS.</span><span class="sxs-lookup"><span data-stu-id="335ef-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="335ef-140">Это решение описывает синхронизацию одного леса доменных служб Active Directory с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="335ef-141">Топология, описываемая в этой статье, предоставляет только один из способов реализации решения.</span><span class="sxs-lookup"><span data-stu-id="335ef-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="335ef-142">Топология организации может отличаться в зависимости от требований к сети и соображений безопасности.</span><span class="sxs-lookup"><span data-stu-id="335ef-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="335ef-143">Планирование хостинга сервера синхронизации каталогов для Microsoft 365 в Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="335ef-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="335ef-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="335ef-145">Требования</span><span class="sxs-lookup"><span data-stu-id="335ef-145">Prerequisites</span></span>

<span data-ttu-id="335ef-146">Прежде чем приступать к работе, изучите требования для развертывания этого решения:</span><span class="sxs-lookup"><span data-stu-id="335ef-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="335ef-147">Изучите соответствующие материалы по планированию в разделе [Планирование виртуальной сети Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span><span class="sxs-lookup"><span data-stu-id="335ef-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="335ef-148">Убедитесь, что ваша организация отвечает всем [требованиям](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) для настройки виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="335ef-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="335ef-149">У вас есть подписка на Microsoft 365, включающая в себя компонент интеграции с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="335ef-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="335ef-150">Для получения сведений о подписках на Microsoft 365 перейдите на [страницу подписки на microsoft 365](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span><span class="sxs-lookup"><span data-stu-id="335ef-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="335ef-151">Подготовьте одну виртуальную машину Azure, которая запускает Azure AD Connect для синхронизации локального леса AD DS с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="335ef-152">У вас должны быть учетные данные (имена и пароли) администратора предприятия AD DS и администратора Azure AD.</span><span class="sxs-lookup"><span data-stu-id="335ef-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="335ef-153">Допущения по архитектуре решения</span><span class="sxs-lookup"><span data-stu-id="335ef-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="335ef-154">Ниже приведены принятые проектные решения.</span><span class="sxs-lookup"><span data-stu-id="335ef-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="335ef-p112">Это решение использует одну виртуальную сеть Azure с VPN-подключением типа "сеть-сеть". В виртуальной сети Azure размещается одна подсеть с одним сервером синхронизации каталогов, на котором запущено средство Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="335ef-p112">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="335ef-157">В локальной сети размещены контроллер домена и DNS-серверы.</span><span class="sxs-lookup"><span data-stu-id="335ef-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="335ef-p113">Вместо единого входа средство Azure AD Connect выполняет синхронизацию хэша паролей. Вам не требуется развертывать инфраструктуру служб федерации Active Directory (AD FS). Дополнительные сведения о синхронизации хэша паролей и едином входе см. в статье [Выбор правильного метода аутентификации для гибридного решения для идентификации Azure Active Directory](https://aka.ms/auth-options).</span><span class="sxs-lookup"><span data-stu-id="335ef-p113">Azure AD Connect performs password hash synchronization instead of single sign-on. You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure. To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://aka.ms/auth-options).</span></span>
    
<span data-ttu-id="335ef-p114">При развертывании этого решения в своей среде вы можете рассмотреть дополнительные варианты структуры. К ним относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="335ef-p114">There are additional design choices that you might consider when you deploy this solution in your environment. These include the following:</span></span>
  
- <span data-ttu-id="335ef-163">Если в виртуальной сети Azure уже есть DNS-серверы, определите, должен ли сервер синхронизации каталогов использовать их вместо DNS-серверов в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="335ef-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="335ef-p115">Если в существующей виртуальной сети Azure есть контроллеры доменов, решите, будет ли настройка сайтов и служб Active Directory более подходящим вариантом для вашей организации. Вместо контроллеров доменов локальной сети сервер синхронизации каталогов может отправлять запросы контроллерам доменов в виртуальной сети Azure для поиска изменений в учетных записях и паролях.</span><span class="sxs-lookup"><span data-stu-id="335ef-p115">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you. The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="335ef-166">План развертывания</span><span class="sxs-lookup"><span data-stu-id="335ef-166">Deployment roadmap</span></span>

<span data-ttu-id="335ef-167">Развертывание Azure AD Connect на виртуальной машине в Azure состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="335ef-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="335ef-168">Этап 1. Создание и настройка виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="335ef-169">Этап 2. Создание и настройка виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="335ef-170">Этап 3. Установка и настройка Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="335ef-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="335ef-171">После развертывания необходимо также назначить расположения и лицензии для новых учетных записей пользователей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="335ef-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="335ef-172">Этап 1. Создание и настройка виртуальной сети Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="335ef-173">Чтобы создать и настроить виртуальную сеть Azure, выполните [Этап 1. Подготовка локальной сети](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) и [Этап 2. Создание виртуальной сети в Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) из схемы развертывания [Подключение локальной сети к виртуальной сети Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="335ef-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="335ef-174">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="335ef-174">This is your resulting configuration.</span></span>
  
![Этап 1 сервера синхронизации каталогов для Microsoft 365, размещенный в Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="335ef-176">На этом рисунке показана локальная сеть, подключенная к виртуальной сети Azure через подключение VPN типа "сеть-сеть" или ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="335ef-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="335ef-177">Этап 2. Создание и настройка виртуальной машины Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="335ef-p116">Создайте виртуальную машину в Azure, следуя инструкциям в статье [Создание первой виртуальной машины Windows на портале Azure](https://go.microsoft.com/fwlink/p/?LinkId=393098). Используйте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="335ef-p116">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use the following settings:</span></span>
  
- <span data-ttu-id="335ef-p117">В области **Основные** выберите ту же подписку, расположение и группу ресурсов, что и в виртуальной сети. Запишите имя пользователя и пароль в надежном месте. Они потребуются позже для подключения к виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="335ef-p117">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network. Record the user name and password in a secure location. You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="335ef-183">В области **Выберите размер** выберите размер **Стандартный A2**.</span><span class="sxs-lookup"><span data-stu-id="335ef-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="335ef-p118">В области **Параметры** в разделе **Хранилище** выберите тип хранилища **Стандартный**. В разделе **Сеть** выберите имя виртуальной сети и подсеть для размещения сервера синхронизации каталогов (не GatewaySubnet). Для всех остальных параметров оставьте значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="335ef-p118">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type. In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="335ef-187">Проверьте внутренний DNS, чтобы убедиться, что сервер синхронизации каталогов правильно использует DNS и для виртуальной машины добавлена запись адреса (A) с ее IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="335ef-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="335ef-p119">Воспользуйтесь инструкциями в разделе [Подключение к виртуальной машине и вход](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon), чтобы подключиться к серверу синхронизации каталогов через подключение к удаленному рабочему столу. После входа присоедините виртуальную машину к локальному домену AD DS.</span><span class="sxs-lookup"><span data-stu-id="335ef-p119">Use the instructions in [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection. After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="335ef-p120">Чтобы предоставить средству Azure AD Connect доступ к ресурсам Интернета, необходимо настроить сервер синхронизации каталогов на использование прокси-сервера локальной сети. Обратитесь к администратору сети за дополнительными инструкциями по настройке.</span><span class="sxs-lookup"><span data-stu-id="335ef-p120">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server. You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="335ef-192">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="335ef-192">This is your resulting configuration.</span></span>
  
![Этап 2 сервера синхронизации каталогов для Microsoft 365, размещенный в Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="335ef-194">На этом рисунке показана виртуальная машина сервера синхронизации каталогов в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="335ef-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="335ef-195">Этап 3. Установка и настройка Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="335ef-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="335ef-196">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="335ef-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="335ef-p121">Подключитесь к серверу синхронизации каталогов в режиме удаленного рабочего стола, используя учетную запись домена AD DS с правами локального администратора. См. статью [Подключение к виртуальной машине и вход](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="335ef-p121">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges. See [Connect to the virtual machine and sign on](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="335ef-199">На сервере синхронизации каталогов откройте статью [Настройка синхронизации каталогов для Microsoft 365](set-up-directory-synchronization.md) и следуйте инструкциям для синхронизации каталогов с синхронизацией хэша паролей.</span><span class="sxs-lookup"><span data-stu-id="335ef-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="335ef-p122">Программа установки создает учетную запись **AAD_xxxxxxxxxxxx** в подразделении "Локальные пользователи". Не перемещайте и не удаляйте эту учетную запись, иначе синхронизация будет невозможна.</span><span class="sxs-lookup"><span data-stu-id="335ef-p122">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU). Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="335ef-202">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="335ef-202">This is your resulting configuration.</span></span>
  
![Этап 3 сервера синхронизации каталогов для Microsoft 365, размещенный в Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="335ef-204">На этом рисунке показан сервер синхронизации каталогов со средством Azure AD Connect в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="335ef-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="335ef-205">Назначение местоположений и лицензий пользователям в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="335ef-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="335ef-206">Azure AD Connect добавляет учетные записи в свою подписку Microsoft 365 из локальных ДОМЕНных служб Active Directory, но чтобы пользователи могли входить в Microsoft 365 и использовать ее службы, необходимо настроить учетные записи с указанием расположения и лицензий.</span><span class="sxs-lookup"><span data-stu-id="335ef-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="335ef-207">Чтобы добавить расположение и активировать лицензии для соответствующих учетных записей пользователей, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="335ef-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="335ef-208">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com)и выберите **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="335ef-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="335ef-209">На панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="335ef-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="335ef-210">В списке учетных записей пользователей установите флажок рядом с нужным пользователем.</span><span class="sxs-lookup"><span data-stu-id="335ef-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="335ef-211">На странице пользователя выберите **Изменить** для пункта **Лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="335ef-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="335ef-212">На странице **Лицензии на продукты** выберите расположение пользователя и включите для него соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="335ef-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="335ef-213">По завершении нажмите кнопку **Сохранить**, а затем кнопку **Закрыть** дважды.</span><span class="sxs-lookup"><span data-stu-id="335ef-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="335ef-214">Вернитесь к шагу 3, чтобы повторить эти действия для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="335ef-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="335ef-215">См. также</span><span class="sxs-lookup"><span data-stu-id="335ef-215">See also</span></span>

[<span data-ttu-id="335ef-216">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="335ef-216">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="335ef-217">Подключение локальной сети к виртуальной сети Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="335ef-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="335ef-218">Скачать Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="335ef-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="335ef-219">Настройка синхронизации каталогов для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="335ef-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
  
