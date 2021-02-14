---
title: Начало работы с политикой защиты от потери данных по умолчанию
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать отчет для уточнения политики защиты от потери данных (DLP) по умолчанию в организации.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817618"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="27772-103">Начало работы с политикой защиты от потери данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="27772-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="27772-104">Перед созданием первой политики защиты от потери данных защита от потери данных помогает защитить конфиденциальную информацию с помощью политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27772-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="27772-105">Эта политика по умолчанию и ее рекомендации (см. ниже) помогают защитить конфиденциальный контент, уведомляя вас о том, что к электронной почте или документам, содержащим номер кредитной карты, был предоставлен общий доступ пользователям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27772-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="27772-106">Вы увидите эту рекомендацию на **домашней** странице Центра соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="27772-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="27772-107">С помощью этого мини-приложения вы можете быстро просмотреть, когда и сколько конфиденциальной информации было общим, а затем уточнить политику DLP по умолчанию одним или двумя щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="27772-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="27772-108">Вы также можете изменить политику DLP по умолчанию в любое время, так как она полностью настраивается.</span><span class="sxs-lookup"><span data-stu-id="27772-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="27772-109">Обратите внимание, что если вы сначала не видите рекомендации, попробуйте нажать **кнопку +More** в нижней части раздела **"Рекомендуемые для вас".**</span><span class="sxs-lookup"><span data-stu-id="27772-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Мини-приложения с именем "Дополнительная защита общего содержимого"](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="27772-111">Просмотр отчета и уточнение политики DLP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="27772-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="27772-112">Когда в мини-приложениях показано, что пользователи поделились конфиденциальной информацией с людьми за пределами вашей организации, выберите "Уточнение политики **DLP"** в нижней части.</span><span class="sxs-lookup"><span data-stu-id="27772-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="27772-113">В подробном отчете показано, когда и сколько содержимого с номерами кредитных карт было предоставлено в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="27772-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="27772-114">Обратите внимание, что просмотр совпадений правил в мини-приложениях может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="27772-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="27772-115">Чтобы защитить конфиденциальную информацию, по умолчанию заданная политика DLP:</span><span class="sxs-lookup"><span data-stu-id="27772-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="27772-116">Определяет, когда контент в Exchange, SharePoint и OneDrive, содержащий по крайней мере один номер кредитной карты, передается людям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27772-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="27772-117">Отображает подсказку политики и отправляет уведомление по электронной почте пользователям при попытке поделиться этой конфиденциальной информацией с пользователями за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27772-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="27772-118">Дополнительные сведения об этих параметрах см. в сообщениях "Отправка уведомлений по электронной почте" и "Советы по политикам [DLP".](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="27772-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="27772-119">Создает подробные отчеты об активности, чтобы вы могли отслеживать такие действия, как кто поделился содержимым с людьми за пределами организации и когда они это сделали.</span><span class="sxs-lookup"><span data-stu-id="27772-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="27772-120">Для получения этих сведений можно использовать отчеты [DLP](view-the-dlp-reports.md) и данные журнала [аудита](search-the-audit-log-in-security-and-compliance.md) (где   =  **DLP** активности).</span><span class="sxs-lookup"><span data-stu-id="27772-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="27772-121">Чтобы быстро уточнить политику DLP по умолчанию, можно выбрать ее:</span><span class="sxs-lookup"><span data-stu-id="27772-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="27772-122">Отправьте вам сообщение с отчетом об инциденте, когда пользователи делятся этой конфиденциальной информацией с людьми за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27772-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="27772-123">Добавьте других пользователей в отчет об инциденте электронной почты.</span><span class="sxs-lookup"><span data-stu-id="27772-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="27772-124">Заблокировать доступ к содержимому, содержащим конфиденциальную информацию, но разрешить пользователю переопределять и отправлять их, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="27772-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="27772-125">Дополнительные сведения об отчетах об инцидентах или ограничении доступа см. в обзоре политик защиты от [потери данных.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="27772-125">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="27772-126">Если вы хотите изменить эти параметры позже, вы можете изменить политику DLP по умолчанию в любое время — см. следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="27772-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Параметры мини-приложения с именем "Дополнительная защита общего содержимого"](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="27772-128">Изменение политики DLP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="27772-128">Edit the default DLP policy</span></span>

<span data-ttu-id="27772-129">Эта политика называется **политикой защиты**  от потери данных по умолчанию и отображается в области защиты от потери данных **на** странице "Политика" Центра соответствия требованиям &amp; безопасности.</span><span class="sxs-lookup"><span data-stu-id="27772-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="27772-130">Эта политика полностью настраивается так же, как и любая политика DLP, которую вы создаете самостоятельно с нуля.</span><span class="sxs-lookup"><span data-stu-id="27772-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="27772-131">Вы также можете отключить или удалить политику, чтобы пользователи больше не получали подсказки политики или уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="27772-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Политика DLP с именем "Политика DLP по умолчанию"](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="27772-133">Когда виджет появляется и не появляется</span><span class="sxs-lookup"><span data-stu-id="27772-133">When the widget does and does not appear</span></span>

<span data-ttu-id="27772-134">Мини-приложения **с именем "Дополнительная защита** общего  содержимого" отображается в разделе "Рекомендуемые для вас" домашней страницы Центра соответствия требованиям  &amp; безопасности.</span><span class="sxs-lookup"><span data-stu-id="27772-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="27772-135">Это мини-виджет отображается только в том случае, если:</span><span class="sxs-lookup"><span data-stu-id="27772-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="27772-136">В Центре безопасности и администрирования Exchange нет политик защиты от потери &amp; данных.</span><span class="sxs-lookup"><span data-stu-id="27772-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="27772-137">Это мини-приложения призвано помочь вам начать работу с DLP, поэтому оно не появляется, если у вас уже есть политики DLP.</span><span class="sxs-lookup"><span data-stu-id="27772-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="27772-138">Содержимое, содержащее хотя бы одну кредитную карту, было предоставлено другому человеку за пределами вашей организации за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="27772-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="27772-139">Обратите внимание, что для получения сведений о совпадениях с правилом мини-приложения может потребоваться до 48 часов, поэтому после обнаружения конфиденциальной информации, к ней может потребоваться до двух дней.</span><span class="sxs-lookup"><span data-stu-id="27772-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="27772-140">Наконец, после использования мини-приложения для уточнения политики DLP по умолчанию виджет исчезает с **домашней** страницы.</span><span class="sxs-lookup"><span data-stu-id="27772-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

