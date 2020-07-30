---
title: Совместное работа с людьми за прев Организации
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Узнайте, как настроить Microsoft 365 для совместной работы с пользователями, не входящими в вашу организацию.
ms.openlocfilehash: 8bde8a3ffe4ab4ec8d0a0ada8e7c6030d00a549b
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527852"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="4847d-103">Совместное работа с людьми за прев Организации</span><span class="sxs-lookup"><span data-stu-id="4847d-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="4847d-104">Функции внешнего общего доступа в Microsoft 365 предоставляют пользователям организации возможность совместной работы с партнерами, поставщиками, клиентами и другими пользователями, у которых нет учетной записи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4847d-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="4847d-105">Вы можете предоставить совместный доступ ко всем командам или сайтам пользователям за пределами вашей организации или только к отдельным файлам.</span><span class="sxs-lookup"><span data-stu-id="4847d-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="4847d-106">Совместное взаимодействие с пользователями за прев Организации состоит из двух основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="4847d-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="4847d-107">**Включите общий доступ** : Настройте общие элементы управления в Azure Active Directory, Teams, Microsoft 365 Groups и SharePoint, чтобы обеспечить необходимый уровень общего доступа для Организации.</span><span class="sxs-lookup"><span data-stu-id="4847d-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="4847d-108">**Включить дополнительную безопасность** — в то время как базовые функции общего доступа можно настроить так, чтобы пользователи за пределами вашей организации не могли пройти проверку подлинности, Microsoft 365 предоставляет множество дополнительных функций обеспечения безопасности и соответствия требованиям, которые помогут защитить данные и поддерживать политики управления при совместном доступе.</span><span class="sxs-lookup"><span data-stu-id="4847d-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="4847d-109">Разрешить общий доступ</span><span class="sxs-lookup"><span data-stu-id="4847d-109">Enable sharing</span></span>

<span data-ttu-id="4847d-110">По умолчанию в Microsoft 365 доступ к совместному использованию для пользователей за пределами вашей организации разрешен для SharePoint и OneDrive, но отключен для Teams.</span><span class="sxs-lookup"><span data-stu-id="4847d-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="4847d-111">Многие сценарии внешнего общего доступа SharePoint и OneDrive работают без дополнительной настройки.</span><span class="sxs-lookup"><span data-stu-id="4847d-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="4847d-112">Чтобы проверить параметры для сценария, который вы используете, или включить новый, выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4847d-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="4847d-113">[Совместная работа над документами](collaborate-on-documents.md) — Узнайте, как настроить Microsoft 365 для предоставления общего доступа и совместной работы с пользователями за пределом Организации (как гости, так и пользователей, не прошедших проверку подлинности) на файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="4847d-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="4847d-114">[Совместная работа на сайте](collaborate-in-site.md) Узнайте, как настроить Microsoft 365 для предоставления общего доступа к сайтам SharePoint с гостями.</span><span class="sxs-lookup"><span data-stu-id="4847d-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="4847d-115">[Совместная работа в Teams](collaborate-as-team.md) — Узнайте, как настроить Microsoft 365 для обеспечения совместной работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="4847d-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="4847d-116">Для получения подробных сведения о параметрах общего доступа гостей, доступных в Microsoft 365, обратитесь к разделу [Параметры общего доступа к гостевым системам microsoft 365](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4847d-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="4847d-117">Включение дополнительной защиты</span><span class="sxs-lookup"><span data-stu-id="4847d-117">Enable additional security</span></span>

<span data-ttu-id="4847d-118">После включения сценария, который вы хотите использовать для предоставления общего доступа пользователям за пререшениями вашей организации, рассмотрите дополнительные меры безопасности для защиты содержимого от случайного или умышленного решения для совместного доступа.</span><span class="sxs-lookup"><span data-stu-id="4847d-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="4847d-119">Рекомендации [по предоставлению общего доступа к файлам и папкам пользователям, не прошедшим проверку](best-practices-anonymous-sharing.md) подлинности. рекомендации по предоставлению общего доступа пользователям, не прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="4847d-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="4847d-120">[Ограничение случайной экспозиции](share-limit-accidental-exposure.md) — Узнайте, как уменьшить вероятность случайного предоставления конфиденциального содержимого пользователям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4847d-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="4847d-121">[Создание безопасной среды общего доступа](create-secure-guest-sharing-environment.md) : сведения о средствах, предоставляемых в Microsoft 365, чтобы обеспечить надежную и безопасную работу с пользователями, не связанными с вашей организацией, а также соответствие требованиям к управлению.</span><span class="sxs-lookup"><span data-stu-id="4847d-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="4847d-122">Совместное сотрудничество с компаниями-партнерами</span><span class="sxs-lookup"><span data-stu-id="4847d-122">Collaborate with partner companies</span></span>

<span data-ttu-id="4847d-123">При работе над большим проектом, включающим большое количество гостей из другой организации, или если у вас есть постоянная связь с поставщиками, в которой часто меняются гости, вы можете использовать управление обслуживанием в Azure Active Directory для упрощения управления гостями и предоставления партнерской компании доступа к ней в этой обязанности.</span><span class="sxs-lookup"><span data-stu-id="4847d-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="4847d-124">Для получения дополнительных сведений ознакомьтесь со статьей [Создание экстрасети для B2B с управляемыми гостями](b2b-extranet.md) .</span><span class="sxs-lookup"><span data-stu-id="4847d-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="4847d-125">Ограничение общего доступа</span><span class="sxs-lookup"><span data-stu-id="4847d-125">Limit sharing</span></span>

<span data-ttu-id="4847d-126">Если некоторые функции общего доступа в Microsoft 365 конфликтуют с политиками управления, ознакомьтесь с [разделом ограничение общего доступа в microsoft 365](microsoft-365-limit-sharing.md) , чтобы узнать о возможностях ограничения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="4847d-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4847d-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4847d-127">Related topics</span></span>

[<span data-ttu-id="4847d-128">Введение в совместную работу с файлами в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4847d-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="4847d-129">Планирование совместной работы с файлами в SharePoint с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4847d-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
