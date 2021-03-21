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
description: Узнайте, как настроить приложения Microsoft 365, такие как Teams, OneDrive и SharePoint для совместной работы с людьми за пределами организации.
ms.openlocfilehash: 359e72c12c43ca1ea984f93d87ab4868e6d1eb66
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916398"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="828e6-103">Совместная работа с людьми, находящимися за пределами организации</span><span class="sxs-lookup"><span data-stu-id="828e6-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="828e6-104">Внешние возможности общего доступа в Microsoft 365 предоставляют пользователям в вашей организации возможность сотрудничать с партнерами, поставщиками, клиентами и другими пользователями, у которых нет учетной записи в каталоге.</span><span class="sxs-lookup"><span data-stu-id="828e6-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="828e6-105">Вы можете обмениваться всеми группами или сайтами с людьми за пределами организации или просто отдельными файлами.</span><span class="sxs-lookup"><span data-stu-id="828e6-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="828e6-106">Совместная работа с людьми за пределами организации состоит из двух основных компонентов:</span><span class="sxs-lookup"><span data-stu-id="828e6-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="828e6-107">**Включить общий** доступ . Настройка элементов управления совместной деятельностью в Azure Active Directory, Teams, Microsoft 365 Groups и SharePoint, чтобы разрешить уровень общего доступа, который необходимо для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="828e6-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="828e6-108">**Включить** дополнительную безопасность . Хотя основные функции общего доступа можно настроить, чтобы требовать от пользователей вне организации проверки подлинности, Microsoft 365 предоставляет множество дополнительных функций безопасности и соответствия требованиям, которые помогут защитить данные и сохранить политики управления при внешнем совместном использовании.</span><span class="sxs-lookup"><span data-stu-id="828e6-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="828e6-109">Включить общий доступ</span><span class="sxs-lookup"><span data-stu-id="828e6-109">Enable sharing</span></span>

<span data-ttu-id="828e6-110">По умолчанию в Microsoft 365 включен общий доступ к людям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="828e6-110">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="828e6-111">Многие внешние сценарии общего доступа работают без дополнительной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="828e6-111">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="828e6-112">Чтобы подтвердить параметры сценария, который вы используете, или включить новый, выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="828e6-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="828e6-113">[Совместная](collaborate-on-documents.md) работа над документами . Узнайте, как настроить Microsoft 365, чтобы разрешить совместное использование и совместную работу с людьми за пределами организации (как гостями, так и недостоверными пользователями) в файлах и папках.</span><span class="sxs-lookup"><span data-stu-id="828e6-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="828e6-114">[Сотрудничество на сайте](collaborate-in-site.md) . Узнайте, как настроить Microsoft 365, чтобы включить совместное использование сайтов SharePoint с гостями.</span><span class="sxs-lookup"><span data-stu-id="828e6-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="828e6-115">[Совместная работа в команде](collaborate-as-team.md) . Узнайте, как настроить Microsoft 365, чтобы включить гостевую совместную работу в Teams.</span><span class="sxs-lookup"><span data-stu-id="828e6-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="828e6-116">Полный обзор параметров гостевых обменов, доступных в Microsoft 365, см. в разделе Параметры гостевых [параметров Microsoft 365.](microsoft-365-guest-settings.md)</span><span class="sxs-lookup"><span data-stu-id="828e6-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="828e6-117">Включить дополнительную безопасность</span><span class="sxs-lookup"><span data-stu-id="828e6-117">Enable additional security</span></span>

<span data-ttu-id="828e6-118">После включения сценария, который необходимо использовать для общего доступа к людям, не входящих в организацию, рассмотрите дополнительные меры защиты контента от случайного или намеренного ненадлежащего обмена.</span><span class="sxs-lookup"><span data-stu-id="828e6-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="828e6-119">[Лучшие практики для](best-practices-anonymous-sharing.md) совместного использования файлов и папок с недоверчивыми пользователями . Узнайте о лучших практиках для совместного использования с недоверчивыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="828e6-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="828e6-120">[Ограничить](share-limit-accidental-exposure.md) случайную экспозицию . Узнайте, как уменьшить вероятность случайного обмена конфиденциальным контентом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="828e6-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="828e6-121">[Создание безопасной](create-secure-guest-sharing-environment.md) среды обмена гостями . Узнайте о средствах, предоставляемых в Microsoft 365, чтобы обеспечить безопасное и безопасное совместное использование с людьми за пределами организации и соответствует вашим требованиям к управлению.</span><span class="sxs-lookup"><span data-stu-id="828e6-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="828e6-122">Сотрудничество с компаниями-партнерами</span><span class="sxs-lookup"><span data-stu-id="828e6-122">Collaborate with partner companies</span></span>

<span data-ttu-id="828e6-123">Когда вы работаете над большим проектом, в котором участвует много гостей из другой организации, или если у вас есть постоянные отношения поставщиков, в которых часто меняются гости, вы можете использовать управление правами в Azure Active Directory, чтобы упростить управление гостями и разрешить компании-партнеру делиться этой ответственностью.</span><span class="sxs-lookup"><span data-stu-id="828e6-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="828e6-124">Дополнительные сведения см. в материале [Create a B2B extranet with managed guests.](b2b-extranet.md)</span><span class="sxs-lookup"><span data-stu-id="828e6-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="828e6-125">Ограничение общего доступа</span><span class="sxs-lookup"><span data-stu-id="828e6-125">Limit sharing</span></span>

<span data-ttu-id="828e6-126">Если некоторые функции общего доступа в Microsoft 365 конфликтуют с политиками управления, см. в разделе Limit [sharing in Microsoft 365,](microsoft-365-limit-sharing.md) чтобы узнать о вариантах ограничения общего доступа.</span><span class="sxs-lookup"><span data-stu-id="828e6-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="828e6-127">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="828e6-127">Related topics</span></span>

[<span data-ttu-id="828e6-128">Интро для совместной работы с файлами в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="828e6-128">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="828e6-129">Планирование совместной работы с файлами в SharePoint с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="828e6-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)