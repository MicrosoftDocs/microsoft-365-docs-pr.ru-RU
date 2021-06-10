---
title: Просмотр состояния синхронизации каталогов в Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: В этой статье узнайте, как проверить состояние синхронизации каталогов в Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924664"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="148ea-103">Просмотр состояния синхронизации каталогов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="148ea-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="148ea-104">Если вы интегрировали локальное доменное обслуживание Active Directory (AD DS) с Azure Active Directory (Azure AD), синхронизируя локальное окружение с Microsoft 365, вы также можете проверить состояние синхронизации.</span><span class="sxs-lookup"><span data-stu-id="148ea-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="148ea-105">Просмотр состояния синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="148ea-105">View directory synchronization status</span></span>

- <span data-ttu-id="148ea-106">Ворегистрируйся [Microsoft 365 центр администрирования](https://admin.microsoft.com) и выберите **состояние DirSync** на домашней странице.</span><span class="sxs-lookup"><span data-stu-id="148ea-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="148ea-107">Поочередно вы можете перейти к **пользователям Active** Users, а на странице \>  **Активные** пользователи выберите **дополнительные** \> **синхронизации каталогов.**</span><span class="sxs-lookup"><span data-stu-id="148ea-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="148ea-108">На области **синхронизации каталогов** выберите **Перейти к управлению DirSync.**</span><span class="sxs-lookup"><span data-stu-id="148ea-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="148ea-109">Сведения на странице Синхронизация каталогов</span><span class="sxs-lookup"><span data-stu-id="148ea-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="148ea-110">В следующей таблице перечислены функции, которые можно получить на странице.</span><span class="sxs-lookup"><span data-stu-id="148ea-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="148ea-111">Если возникла проблема с синхронизацией каталогов, ошибки также перечислены на этой странице.</span><span class="sxs-lookup"><span data-stu-id="148ea-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="148ea-112">Дополнительные сведения о различных ошибках, с которыми вы можете столкнуться, см. в статью Определение ошибок синхронизации каталогов в [Microsoft 365.](identify-directory-synchronization-errors.md)</span><span class="sxs-lookup"><span data-stu-id="148ea-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="148ea-113">Item</span><span class="sxs-lookup"><span data-stu-id="148ea-113">Item</span></span>|<span data-ttu-id="148ea-114">Назначение</span><span class="sxs-lookup"><span data-stu-id="148ea-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="148ea-115">**Проверены домены**</span><span class="sxs-lookup"><span data-stu-id="148ea-115">**Domains verified**</span></span> | <span data-ttu-id="148ea-116">Количество доменов в Microsoft 365, которые вы проверили.</span><span class="sxs-lookup"><span data-stu-id="148ea-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="148ea-117">**Не проверены домены**</span><span class="sxs-lookup"><span data-stu-id="148ea-117">**Domains not verified**</span></span> | <span data-ttu-id="148ea-118">Домены, добавленные, но не проверенные.</span><span class="sxs-lookup"><span data-stu-id="148ea-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="148ea-119">**Включена синхронизация каталогов**</span><span class="sxs-lookup"><span data-stu-id="148ea-119">**Directory sync enabled**</span></span> |<span data-ttu-id="148ea-120">True или False.</span><span class="sxs-lookup"><span data-stu-id="148ea-120">True or False.</span></span> <span data-ttu-id="148ea-121">Указывает, включена ли синхронизация каталогов.</span><span class="sxs-lookup"><span data-stu-id="148ea-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="148ea-122">**Последняя синхронизация каталогов**</span><span class="sxs-lookup"><span data-stu-id="148ea-122">**Latest directory sync**</span></span> | <span data-ttu-id="148ea-123">Последняя синхронизация каталогов.</span><span class="sxs-lookup"><span data-stu-id="148ea-123">Last time directory sync ran.</span></span> <span data-ttu-id="148ea-124">Будет отображаться предупреждение и ссылка на средство устранения неполадок, если последняя синхронизация была более трех дней назад.</span><span class="sxs-lookup"><span data-stu-id="148ea-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="148ea-125">**Включена синхронизация паролей**</span><span class="sxs-lookup"><span data-stu-id="148ea-125">**Password sync enabled**</span></span> | <span data-ttu-id="148ea-126">True или False.</span><span class="sxs-lookup"><span data-stu-id="148ea-126">True or False.</span></span> <span data-ttu-id="148ea-127">Указывает, есть ли у вас синхронизация с hash паролем между нашими локальной и Microsoft 365 клиентом.</span><span class="sxs-lookup"><span data-stu-id="148ea-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="148ea-128">**Последняя синхронизация паролей**</span><span class="sxs-lookup"><span data-stu-id="148ea-128">**Last Password Sync**</span></span> | <span data-ttu-id="148ea-129">В последний раз синхронизация с hash паролей была задана.</span><span class="sxs-lookup"><span data-stu-id="148ea-129">Last time password hash sync ran.</span></span> <span data-ttu-id="148ea-130">Будет отображаться предупреждение и ссылка на средство устранения неполадок, если последняя синхронизация была более трех дней назад.</span><span class="sxs-lookup"><span data-stu-id="148ea-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="148ea-131">**Клиентская версия синхронизации каталогов**</span><span class="sxs-lookup"><span data-stu-id="148ea-131">**Directory sync client version**</span></span> | <span data-ttu-id="148ea-132">Содержит ссылку на скачивание, если была выпущена новая Подключение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="148ea-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="148ea-133">**Учетная запись службы синхронизации directory**</span><span class="sxs-lookup"><span data-stu-id="148ea-133">**Directory sync service account**</span></span> | <span data-ttu-id="148ea-134">Отображает имя учетной записи службы синхронизации Microsoft 365 каталога.</span><span class="sxs-lookup"><span data-stu-id="148ea-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="148ea-135">Отслеживание работоспособности функции синхронизации</span><span class="sxs-lookup"><span data-stu-id="148ea-135">Monitor synchronization health</span></span>

<span data-ttu-id="148ea-136">В этом разделе вы установите агент Azure AD Connect Health на все свои локальные контроллеры доменов AD DS, чтобы отслеживать инфраструктуру идентификации и службы синхронизации, предоставляемые Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="148ea-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="148ea-137">Сведения, полученные в результате отслеживания, доступны на портале Azure AD Connect Health. Там вы можете просматривать оповещения, результаты отслеживания производительности, аналитические данные об использовании и прочие сведения.</span><span class="sxs-lookup"><span data-stu-id="148ea-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="148ea-138">Ключевое решение о способе использования Azure AD Connect Health зависит от способа, которым вы используете Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="148ea-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="148ea-139">Если вы используете **управляемую проверку подлинности**, начните работу с прочтения статьи [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="148ea-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="148ea-140">Если вы синхронизируете только имена учетных записей и групп, используя **федеративную проверку подлинности** с помощью служб федерации Active Directory (AD FS), для начала прочитайте статью [Мониторинг AD FS с помощью Azure AD Connect Health](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="148ea-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="148ea-141">По завершению у вас будет:</span><span class="sxs-lookup"><span data-stu-id="148ea-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="148ea-142">На каждом из ваших локальных серверов поставщиков удостоверений установлен агент Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="148ea-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="148ea-143">На портале Azure AD Connect Health отображается текущее состояние вашей локальной инфраструктуры и действий по синхронизации с клиентом Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="148ea-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>