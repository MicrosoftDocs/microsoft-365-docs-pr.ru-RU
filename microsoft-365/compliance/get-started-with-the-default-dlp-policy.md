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
description: Узнайте, как использовать отчет для уточнения политики предотвращения потери данных по умолчанию в организации.
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114087"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="b47c6-103">Начало работы с политикой защиты от потери данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b47c6-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="b47c6-104">Перед созданием первой политики предотвращения потери данных DLP помогает защитить конфиденциальные сведения политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b47c6-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="b47c6-105">Эта политика по умолчанию и ее рекомендации (см. ниже) помогают сохранить конфиденциальное содержимое в безопасности, уведомив вас о том, что сообщения электронной почты или документы, содержащие номер кредитной карты, были предоставлены кому-либо за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="b47c6-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="b47c6-106">Эта рекомендация будет см. на **домашней** странице Центра соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="b47c6-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="b47c6-107">С помощью этого виджета можно быстро просмотреть, когда и сколько конфиденциальной информации было общим, а затем уточнить политику DLP по умолчанию одним или двумя щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="b47c6-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="b47c6-108">Вы также можете изменить политику DLP по умолчанию в любое время, так как она полностью настраиваема.</span><span class="sxs-lookup"><span data-stu-id="b47c6-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="b47c6-109">Обратите внимание, что если вы сначала не видите рекомендации, попробуйте нажать **кнопку +More** в нижней части раздела **Рекомендуемый для вас.**</span><span class="sxs-lookup"><span data-stu-id="b47c6-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Виджет с именем Further protect shared content](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="b47c6-111">Просмотр отчета и уточнение политики DLP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b47c6-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="b47c6-112">Когда виджет показывает, что пользователи делились конфиденциальной информацией с людьми за пределами организации, выберите политику **уточнения DLP** в нижней части.</span><span class="sxs-lookup"><span data-stu-id="b47c6-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="b47c6-113">В подробном отчете показано, когда и сколько контента, содержащего номера кредитных карт, было общим за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b47c6-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="b47c6-114">Обратите внимание, что совпадения правил могут занять до 48 часов для показа в виджете.</span><span class="sxs-lookup"><span data-stu-id="b47c6-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="b47c6-115">Чтобы защитить конфиденциальные сведения, политика DLP по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b47c6-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="b47c6-116">Определяет, когда контент в Exchange, SharePoint и OneDrive, содержащий по крайней мере один номер кредитной карты, передается людям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="b47c6-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="b47c6-117">Показывает подсказку политики и отправляет уведомление электронной почты пользователям при попытке поделиться этой конфиденциальной информацией с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="b47c6-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="b47c6-118">Дополнительные сведения об этих параметрах см. в таблице Отправка уведомлений электронной почты и советы по политике [политики DLP.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="b47c6-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="b47c6-119">Создает подробные отчеты о действиях, чтобы отслеживать такие вещи, как то, кто поделился содержимым с людьми за пределами организации и когда они это сделали.</span><span class="sxs-lookup"><span data-stu-id="b47c6-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="b47c6-120">Вы можете использовать [отчеты DLP и](view-the-dlp-reports.md) данные журнала аудита [(где](search-the-audit-log-in-security-and-compliance.md) **DLP активности)**  =  для получения этих сведений.</span><span class="sxs-lookup"><span data-stu-id="b47c6-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="b47c6-121">Чтобы быстро уточнить политику DLP по умолчанию, вы можете выбрать ее:</span><span class="sxs-lookup"><span data-stu-id="b47c6-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="b47c6-122">Отправьте сообщение сообщения об инциденте, когда пользователи делятся этой конфиденциальной информацией с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="b47c6-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="b47c6-123">Добавьте других пользователей в отчет об инциденте электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b47c6-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="b47c6-124">Заблокировать доступ к контенту, содержащим конфиденциальные сведения, но при необходимости разрешить пользователю переопределять и отправлять или отправлять.</span><span class="sxs-lookup"><span data-stu-id="b47c6-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="b47c6-125">Дополнительные сведения о отчетах об инцидентах или ограничении доступа см. в справке о предотвращении [потери данных.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b47c6-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="b47c6-126">Если вы хотите изменить эти параметры позже, вы можете изменить политику DLP по умолчанию в любое время — см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b47c6-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Параметры для виджета с именем Further protect shared content](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="b47c6-128">Изменение политики DLP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b47c6-128">Edit the default DLP policy</span></span>

<span data-ttu-id="b47c6-129">Эта политика называется политикой **DLP** по умолчанию и отображается в статье **Предотвращение** потери данных на странице **Политика** Центра соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="b47c6-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="b47c6-130">Эта политика полностью настраиваема, как и любая политика DLP, которую вы создаете с нуля.</span><span class="sxs-lookup"><span data-stu-id="b47c6-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="b47c6-131">Вы также можете отключить или удалить политику, чтобы пользователи больше не получали советы по политике или уведомления электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b47c6-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Политика DLP с именем политика DLP по умолчанию](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="b47c6-133">Когда виджет делает и не появляется</span><span class="sxs-lookup"><span data-stu-id="b47c6-133">When the widget does and does not appear</span></span>

<span data-ttu-id="b47c6-134">Виджет с **именем Further protect shared content** отображается  в разделе **Рекомендуемые** для вас домашняя страница Центра соответствия &amp; требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="b47c6-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="b47c6-135">Этот виджет появляется только тогда, когда:</span><span class="sxs-lookup"><span data-stu-id="b47c6-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="b47c6-136">Политики предотвращения потери данных не существуют в Центре соответствия требованиям безопасности &amp; или Exchange центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="b47c6-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="b47c6-137">Этот виджет предназначен для начала работы с DLP, поэтому он не появится, если у вас уже есть политики DLP.</span><span class="sxs-lookup"><span data-stu-id="b47c6-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="b47c6-138">Содержимое, содержащее хотя бы одну кредитную карту, было предоставлено кому-либо за пределами организации за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b47c6-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="b47c6-139">Обратите внимание, что совпадения правил могут занять до 48 часов, чтобы быть доступными для виджета, поэтому после обнаружения конфиденциальной информации, общей внешней стороной, может потребоваться до двух дней для появления рекомендации.</span><span class="sxs-lookup"><span data-stu-id="b47c6-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="b47c6-140">Наконец, после использования виджета для уточнения политики DLP по умолчанию виджет исчезает со **домашней** страницы.</span><span class="sxs-lookup"><span data-stu-id="b47c6-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

