---
title: Интеграция Azure с Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Интеграция Microsoft 365 с Azure AD, если требуется синхронизация паролей или один вход с локальной средой.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905336"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="4d5c0-103">Интеграция Azure с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d5c0-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="4d5c0-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4d5c0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d5c0-105">Microsoft 365 использует Azure Active Directory (Azure AD) для управления идентификаторами пользователей за кулисами.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="4d5c0-106">Подписка на Microsoft 365 включает бесплатную подписку Azure AD, чтобы можно было интегрировать локальное доменное обслуживание Active Directory для синхронизации учетных записей и паролей пользователей или единой входной записи.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="4d5c0-107">Вы также можете приобрести расширенные функции для более эффективного управления учетной записью.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="4d5c0-108">Azure AD также предлагает другие функции, например управление интегрированными приложениями, которые можно использовать для расширения и настройки подписки microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="4d5c0-109">Консультанты по развертыванию Azure AD можно использовать для управляемой установки и настройки в центре администрирования Microsoft 365 (необходимо войти в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="4d5c0-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="4d5c0-110">Консультант Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="4d5c0-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="4d5c0-111">Консультант по развертыванию AD FS</span><span class="sxs-lookup"><span data-stu-id="4d5c0-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="4d5c0-112">Руководство по настройке Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d5c0-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="4d5c0-113">Выпуски Azure AD и управление удостоверениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d5c0-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="4d5c0-114">Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="4d5c0-115">Вы можете использовать Azure AD для создания и управления учетными записями пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="4d5c0-116">Чтобы активировать эту подписку, необходимо выполнить разовую регистрацию.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="4d5c0-117">После этого вы можете получить доступ к Azure AD из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4d5c0-118">Инструкции по регистрации бесплатной подписки На Azure AD см. в вашей бесплатной подписке [Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="4d5c0-119">Не перейдите непосредственно к azure.microsoft.com регистрации или получите пробную или платную подписку на Microsoft Azure, которая отделена от бесплатной подписки Azure AD с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="4d5c0-120">С помощью бесплатной подписки можно синхронизироваться с локальной каталогами, настроить один вход и синхронизировать со многими программами, такими как приложения-службы, такие как Salesforce, DropBox и многие другие.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="4d5c0-121">Если вы хотите повысить функциональность AD DS, двухнаправленную синхронизацию и другие возможности управления, вы можете обновить бесплатную подписку на платную премиум-подписку.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="4d5c0-122">Подробные сведения см. в [выпуске Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="4d5c0-123">Дополнительные сведения о Microsoft 365 и Azure AD см. в [моделях удостоверений Microsoft 365.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="4d5c0-124">Расширение возможностей клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d5c0-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="4d5c0-125">**Функция**</span><span class="sxs-lookup"><span data-stu-id="4d5c0-125">**Feature**</span></span>|<span data-ttu-id="4d5c0-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4d5c0-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d5c0-127">Интегрированные приложения</span><span class="sxs-lookup"><span data-stu-id="4d5c0-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="4d5c0-128">Вы можете предоставить отдельным приложениям доступ к данным Microsoft 365, таким как почта, календари, контакты, пользователи, группы, файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="4d5c0-129">Вы также можете разрешить эти приложения на глобальном уровне администратора и сделать их доступными для всей компании, зарегистрировав приложения в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="4d5c0-130">Более подробную информацию см. [в видеоролике Интегрированные приложения и Azure AD для администраторов Microsoft 365.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="4d5c0-131">Также [см. один вход.](/azure/active-directory/manage-apps/what-is-single-sign-on)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="4d5c0-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="4d5c0-132">PowerApps</span></span>  <br/> | <span data-ttu-id="4d5c0-133">Power apps — это целенаправленные приложения для мобильных устройств, которые могут подключаться к существующим источникам данных, таким как списки SharePoint и другие приложения данных.</span><span class="sxs-lookup"><span data-stu-id="4d5c0-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="4d5c0-134">Дополнительные сведения см. в раздел Создание PowerApp для [списка в SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и на странице [PowerApps.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="4d5c0-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4d5c0-135">См. также</span><span class="sxs-lookup"><span data-stu-id="4d5c0-135">See also</span></span>

[<span data-ttu-id="4d5c0-136">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4d5c0-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)