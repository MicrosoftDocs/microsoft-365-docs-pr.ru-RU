---
title: Просмотр приложений
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Просмотр приложений.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420263"
---
# <a name="view-your-apps"></a><span data-ttu-id="45847-103">Просмотр приложений</span><span class="sxs-lookup"><span data-stu-id="45847-103">View your apps</span></span>

><span data-ttu-id="45847-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="45847-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="45847-105">Управление приложениями Майкрософт позволяет быстро получить глубокие сведения о приложениях Microsoft 365 в клиенте.</span><span class="sxs-lookup"><span data-stu-id="45847-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="45847-106">Например, вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="45847-106">For example, you can see:</span></span>

- <span data-ttu-id="45847-107">Список приложений с поддержкой OAuth в клиенте, которые используют API Microsoft Graph, а также соответствующие метаданные приложений и данные об использовании.</span><span class="sxs-lookup"><span data-stu-id="45847-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="45847-108">Сведения о приложении с более подробной аналитикой и сведениями, выбрав приложение в списке.</span><span class="sxs-lookup"><span data-stu-id="45847-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="45847-109">Получение списка всех приложений в клиенте</span><span class="sxs-lookup"><span data-stu-id="45847-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="45847-110">Сводку приложений в клиенте можно найти в **Центре соответствия требованиям Microsoft 365 > Защита приложений и управление > Приложения**.</span><span class="sxs-lookup"><span data-stu-id="45847-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Страница сводки приложения MAPG в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="45847-112">Ваша учетная запись входа в систему должна иметь одну из [этих ролей](app-governance-get-started.md#administrator-roles) для просмотра любых данных управления приложениями.</span><span class="sxs-lookup"><span data-stu-id="45847-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="45847-113">Вы увидите список приложений и следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="45847-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="45847-114">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="45847-114">App Name</span></span>
- <span data-ttu-id="45847-115">Издатель</span><span class="sxs-lookup"><span data-stu-id="45847-115">Publisher</span></span>
- <span data-ttu-id="45847-116">Сертификация приложения</span><span class="sxs-lookup"><span data-stu-id="45847-116">App certification</span></span>

  <span data-ttu-id="45847-117">Указывает, совместимо ли приложение с технологиями Майкрософт, соответствует ли оно рекомендованным методикам безопасности облачных приложений и поддерживается ли корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="45847-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="45847-118">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="45847-118">Last modified</span></span>

  <span data-ttu-id="45847-119">Отображает дату установки управления приложениями в клиенте, если эта дата более поздняя, чем дата последнего изменения приложения.</span><span class="sxs-lookup"><span data-stu-id="45847-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="45847-120">Дата установки</span><span class="sxs-lookup"><span data-stu-id="45847-120">Date installed</span></span>
- <span data-ttu-id="45847-121">Уровень привилегий</span><span class="sxs-lookup"><span data-stu-id="45847-121">Privilege level</span></span>
- <span data-ttu-id="45847-122">Число пользователей</span><span class="sxs-lookup"><span data-stu-id="45847-122">Number of users</span></span>
- <span data-ttu-id="45847-123">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="45847-123">Data access</span></span>

  <span data-ttu-id="45847-124">Обзор отправки и скачивания данных этого приложения в клиенте за последний день вместе с изменением за предыдущий день.</span><span class="sxs-lookup"><span data-stu-id="45847-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="45847-125">Управление приложениями по умолчанию сортирует список приложений по **имени приложения**.</span><span class="sxs-lookup"><span data-stu-id="45847-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="45847-126">Чтобы отсортировать список по другому атрибуту приложения, выберите имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="45847-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="45847-127">Вы также можете выбрать **Поиск** для поиска приложения по имени.</span><span class="sxs-lookup"><span data-stu-id="45847-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="45847-128">Получение подробных сведений о приложении</span><span class="sxs-lookup"><span data-stu-id="45847-128">Getting detailed information on an app</span></span>

<span data-ttu-id="45847-129">Подробные сведения об определенном приложении в клиенте можно найти на странице \*\*Центр соответствия требованиям Microsoft 365 > Управление приложениями > Страница приложений > \*имя приложения\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="45847-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Область сведений о приложении для управления приложениями в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="45847-131">В области сведений о приложении есть дополнительные сведения на этих вкладках:</span><span class="sxs-lookup"><span data-stu-id="45847-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="45847-132">Имя вкладки</span><span class="sxs-lookup"><span data-stu-id="45847-132">Tab name</span></span> | <span data-ttu-id="45847-133">Описание</span><span class="sxs-lookup"><span data-stu-id="45847-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="45847-134">Details</span><span class="sxs-lookup"><span data-stu-id="45847-134">Details</span></span> | <span data-ttu-id="45847-135">См. дополнительные данные о приложении, такие как дата первого согласия и ИД приложения.</span><span class="sxs-lookup"><span data-stu-id="45847-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="45847-136">Чтобы просмотреть свойства приложения, зарегистрированного в Azure AD, выберите **Просмотреть приложение в Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="45847-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="45847-137">Использование</span><span class="sxs-lookup"><span data-stu-id="45847-137">Usage</span></span> | <span data-ttu-id="45847-138">Просматривайте данные, к которым обращается приложение в клиенте, составляйте график использования данных и показывайте использование наиболее популярными \<x> пользователями и пользователями с [приоритетными учетными записями](/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="45847-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="45847-139">Пользователи</span><span class="sxs-lookup"><span data-stu-id="45847-139">Users</span></span> | <span data-ttu-id="45847-140">Посматривайте список пользователей, которые используют приложение, независимо от того, являются ли они приоритетными</span><span class="sxs-lookup"><span data-stu-id="45847-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="45847-141">Разрешения</span><span class="sxs-lookup"><span data-stu-id="45847-141">Permissions</span></span> | <span data-ttu-id="45847-142">Посматривайте сводку разрешений, предоставленных и используемых приложением, а также список определенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="45847-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="45847-143">Дополнительные сведения см. в статье [Справочник по разрешениям Microsoft Graph](/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="45847-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="45847-144">Для включенного приложения также есть элемент управления **Отключить приложение** для отключения использования выбранного приложения и элемент управления **Включить приложение** для включения использования отключенного приложения.</span><span class="sxs-lookup"><span data-stu-id="45847-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="45847-145">Для этих действий требуются [роли администратора](app-governance-get-started.md#administrator-roles):</span><span class="sxs-lookup"><span data-stu-id="45847-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="45847-146">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="45847-146">Compliance Administrator</span></span>
- <span data-ttu-id="45847-147">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="45847-147">Global Administrator</span></span>
- <span data-ttu-id="45847-148">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="45847-148">Security Administrator</span></span>
- <span data-ttu-id="45847-149">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="45847-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="45847-150">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="45847-150">Next step</span></span>

<span data-ttu-id="45847-151">[Определение общего состояния соответствия приложения требованиям](app-governance-visibility-insights-compliance-posture.md).</span><span class="sxs-lookup"><span data-stu-id="45847-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
