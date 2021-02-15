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
description: Интегрируйте Microsoft 365 с Azure AD, если вы хотите синхронизировать пароль или единый вход с локальной средой.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384748"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="59ee8-103">Интеграция Azure с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59ee8-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="59ee8-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="59ee8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="59ee8-105">Microsoft 365 использует Azure Active Directory (Azure AD) для управления удостоверениями пользователей.</span><span class="sxs-lookup"><span data-stu-id="59ee8-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="59ee8-106">Ваша подписка на Microsoft 365 включает бесплатную подписку На Azure AD, чтобы вы могли интегрировать свои локальное доменное службы Active Directory (AD DS) для синхронизации учетных записей пользователей и паролей или настроить единый вход.</span><span class="sxs-lookup"><span data-stu-id="59ee8-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="59ee8-107">Вы также можете приобрести дополнительные функции для более эффективного управления учетной записью.</span><span class="sxs-lookup"><span data-stu-id="59ee8-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="59ee8-108">Azure AD также предоставляет другие функции, например управление интегрированными приложениями, которые можно использовать для расширения и настройки подписок Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ee8-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="59ee8-109">Вы можете использовать помощники по развертыванию Azure AD для настройки и настройки в Центре администрирования Microsoft 365 (вам необходимо войти в Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="59ee8-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="59ee8-110">Помощник по Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="59ee8-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="59ee8-111">Помощник по развертыванию AD FS</span><span class="sxs-lookup"><span data-stu-id="59ee8-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="59ee8-112">Руководство по настройке Azure AD</span><span class="sxs-lookup"><span data-stu-id="59ee8-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="59ee8-113">Выпуски Azure AD и управление удостоверениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59ee8-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="59ee8-114">Если у вас есть платная подписка на Microsoft 365, у вас также есть бесплатная подписка на Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59ee8-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="59ee8-115">Azure AD можно использовать для создания учетных записей пользователей и групп и управления ими.</span><span class="sxs-lookup"><span data-stu-id="59ee8-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="59ee8-116">Чтобы активировать эту подписку, необходимо выполнить разовую регистрацию.</span><span class="sxs-lookup"><span data-stu-id="59ee8-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="59ee8-117">После этого вы сможете получить доступ к Azure AD из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ee8-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="59ee8-118">Инструкции по регистрации бесплатной подписки На Azure AD см. в этой [бесплатной подписке.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="59ee8-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="59ee8-119">Не перейдите непосредственно в azure.microsoft.com регистрации или получите пробную или платную подписку на Microsoft Azure, которая отделена от бесплатной подписки Azure AD с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ee8-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="59ee8-120">С помощью бесплатной подписки вы можете синхронизироваться с локальной службой каталогов, настроить единый вход и синхронизироваться со многими приложениями-службами, такими как Salesforce, DropBox и многие другие.</span><span class="sxs-lookup"><span data-stu-id="59ee8-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="59ee8-121">Если вам нужны расширенные функции AD DS, двунаправленная синхронизация и другие возможности управления, вы можете обновить бесплатную подписку до платной расширенной подписки.</span><span class="sxs-lookup"><span data-stu-id="59ee8-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="59ee8-122">Подробные сведения [см. в выпусках Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="59ee8-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="59ee8-123">Дополнительные сведения о Microsoft 365 и Azure AD см. в моделях [удостоверений Microsoft 365.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="59ee8-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="59ee8-124">Расширение возможностей клиента Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59ee8-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="59ee8-125">**Функция**</span><span class="sxs-lookup"><span data-stu-id="59ee8-125">**Feature**</span></span>|<span data-ttu-id="59ee8-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="59ee8-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="59ee8-127">Интегрированные приложения</span><span class="sxs-lookup"><span data-stu-id="59ee8-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="59ee8-128">Вы можете предоставить отдельным приложениям доступ к данным Microsoft 365, таким как почта, календари, контакты, пользователи, группы, файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="59ee8-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="59ee8-129">Вы также можете авторизировать эти приложения на уровне глобального администратора и сделать их доступными для всей компании, зарегистрировав их в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59ee8-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="59ee8-130">Более подробную информацию см. в [интегрированных приложениях и Azure AD для администраторов Microsoft 365.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="59ee8-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="59ee8-131">См. [также единый вход.](https://go.microsoft.com/fwlink/p/?LinkId=698604)</span><span class="sxs-lookup"><span data-stu-id="59ee8-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="59ee8-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="59ee8-132">PowerApps</span></span>  <br/> | <span data-ttu-id="59ee8-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span><span class="sxs-lookup"><span data-stu-id="59ee8-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="59ee8-134">Дополнительные сведения см. в подсети "Создание PowerApp для списка [в SharePoint Online"](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) и на странице [PowerApps.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="59ee8-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="59ee8-135">См. также</span><span class="sxs-lookup"><span data-stu-id="59ee8-135">See also</span></span>

[<span data-ttu-id="59ee8-136">Обзор Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="59ee8-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
