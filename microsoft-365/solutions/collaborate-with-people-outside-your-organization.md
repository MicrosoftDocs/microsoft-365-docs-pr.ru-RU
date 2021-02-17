---
title: Совместная работа с людьми, находящимися за пределами организации
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Узнайте, как настроить приложения Microsoft 365, такие как Teams, OneDrive и SharePoint, для совместной работы с людьми за пределами вашей организации.
ms.openlocfilehash: 7b8e5e30d8222d055fc5f64472c4083db614d4bd
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261517"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="57c1b-103">Совместная работа с людьми, находящимися за пределами организации</span><span class="sxs-lookup"><span data-stu-id="57c1b-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="57c1b-104">Возможности внешнего общего доступа в Microsoft 365 предоставляют пользователям в вашей организации возможность сотрудничать с партнерами, поставщиками, клиентами и другими пользователями, у которых нет учетной записи в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="57c1b-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="57c1b-105">Вы можете делиться всеми командами или сайтами с людьми за пределами организации или только с отдельными файлами.</span><span class="sxs-lookup"><span data-stu-id="57c1b-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="57c1b-106">Совместная работа с людьми за пределами организации состоит из двух основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="57c1b-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="57c1b-107">**Включить общий** доступ . Настройте элементы управления совместным доступом в Azure Active Directory, Teams, группах Microsoft 365 и SharePoint, чтобы разрешить нужный для вашей организации уровень общего доступа.</span><span class="sxs-lookup"><span data-stu-id="57c1b-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="57c1b-108">Обеспечение дополнительной **безопасности.** Хотя основные функции общего доступа можно настроить так, чтобы требовать проверку подлинности пользователей за пределами организации, Microsoft 365 предоставляет множество дополнительных функций обеспечения безопасности и соответствия требованиям, которые помогут защитить ваши данные и поддерживать политики управления при внешнем совместном использовании.</span><span class="sxs-lookup"><span data-stu-id="57c1b-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="57c1b-109">Включить общий доступ</span><span class="sxs-lookup"><span data-stu-id="57c1b-109">Enable sharing</span></span>

<span data-ttu-id="57c1b-110">По умолчанию в Microsoft 365 включен общий доступ к людям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="57c1b-110">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="57c1b-111">Многие сценарии внешнего общего доступа работают без дополнительной настройки.</span><span class="sxs-lookup"><span data-stu-id="57c1b-111">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="57c1b-112">Чтобы подтвердить параметры сценария, который вы используете, или включить новый сценарий, выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="57c1b-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="57c1b-113">[Совместная](collaborate-on-documents.md) работа над документами. Узнайте, как настроить Microsoft 365, чтобы разрешить общий доступ и совместную работу с пользователями за пределами вашей организации (как гостями, так и пользователями, не непросвещенными) для файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="57c1b-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="57c1b-114">[Сотрудничество на сайте.](collaborate-in-site.md) Узнайте, как настроить Microsoft 365, чтобы включить общий доступ к сайтам SharePoint с гостями.</span><span class="sxs-lookup"><span data-stu-id="57c1b-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="57c1b-115">[Совместная работа в команде.](collaborate-as-team.md) Узнайте, как настроить Microsoft 365, чтобы включить гостевую совместную работу в Teams.</span><span class="sxs-lookup"><span data-stu-id="57c1b-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="57c1b-116">Полный обзор параметров гостевого общего доступа, доступных в Microsoft 365, см. в справочнике по настройкам гостевого общего доступа [в Microsoft 365.](microsoft-365-guest-settings.md)</span><span class="sxs-lookup"><span data-stu-id="57c1b-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="57c1b-117">Включить дополнительную безопасность</span><span class="sxs-lookup"><span data-stu-id="57c1b-117">Enable additional security</span></span>

<span data-ttu-id="57c1b-118">После включения сценария, который вы хотите использовать для общего доступа к людям за пределами организации, рассмотрите дополнительные меры защиты, чтобы защитить контент от случайного или преднамеренного несоответствующего общего доступа.</span><span class="sxs-lookup"><span data-stu-id="57c1b-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="57c1b-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span><span class="sxs-lookup"><span data-stu-id="57c1b-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="57c1b-120">[Ограничение случайного воздействия](share-limit-accidental-exposure.md) — узнайте, как снизить вероятность случайного обмена конфиденциальным содержимым с людьми за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="57c1b-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="57c1b-121">Создайте безопасную [среду](create-secure-guest-sharing-environment.md) гостевого общего доступа. Узнайте о средствах, предоставляемых в Microsoft 365, чтобы обеспечить безопасный и безопасный обмен данными с людьми за пределами вашей организации и обеспечить их безопасность и требования к управлению.</span><span class="sxs-lookup"><span data-stu-id="57c1b-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="57c1b-122">Сотрудничество с партнерскими компаниями</span><span class="sxs-lookup"><span data-stu-id="57c1b-122">Collaborate with partner companies</span></span>

<span data-ttu-id="57c1b-123">Если вы работаете над большим проектом, в котором участвует много гостей из другой организации, или если у вас есть постоянные отношения с поставщиками, в которых гости часто меняются, вы можете использовать управление правами в Azure Active Directory, чтобы упростить управление гостями и разрешить партнерской компании делиться этой ответственностью.</span><span class="sxs-lookup"><span data-stu-id="57c1b-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="57c1b-124">Дополнительные сведения см. в подсети ["Создание экстрасети B2B с управляемыми](b2b-extranet.md) гостями".</span><span class="sxs-lookup"><span data-stu-id="57c1b-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="57c1b-125">Ограничение общего доступа</span><span class="sxs-lookup"><span data-stu-id="57c1b-125">Limit sharing</span></span>

<span data-ttu-id="57c1b-126">Если некоторые функции общего доступа в Microsoft 365 конфликтуют с вашими политиками управления, см. раздел "Ограничение общего доступа в [Microsoft 365",](microsoft-365-limit-sharing.md) чтобы узнать о вариантах ограничения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="57c1b-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57c1b-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="57c1b-127">Related topics</span></span>

[<span data-ttu-id="57c1b-128">Intro to file collaboration in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57c1b-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="57c1b-129">Планирование совместной работы с файлами в SharePoint с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57c1b-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
