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
description: Прежде чем создавать первую политику защиты от потери данных (DLP), DLP поможет защитить конфиденциальные данные с помощью политики по умолчанию. Эта политика по умолчанию и ее рекомендации (показанные ниже) помогут защитить конфиденциальный контент, уведомляя вас, когда к электронной почте или документам, содержащим номер кредитной карты, предоставлен доступ другому пользователю за пределом вашей организации.
ms.openlocfilehash: 687cfb50568310aa29f06da6bfbbc644d3edc853
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073132"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="4d716-104">Начало работы с политикой защиты от потери данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4d716-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="4d716-105">Прежде чем создавать первую политику защиты от потери данных (DLP), DLP поможет защитить конфиденциальные данные с помощью политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d716-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="4d716-106">Эта политика по умолчанию и ее рекомендации (показанные ниже) помогут защитить конфиденциальный контент, уведомляя вас, когда к электронной почте или документам, содержащим номер кредитной карты, предоставлен доступ другому пользователю за пределом вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4d716-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="4d716-107">Вы увидите эту рекомендацию на **домашней** странице центра безопасности &amp; и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4d716-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4d716-108">Это мини-приложение можно использовать для быстрого просмотра того, когда и сколько конфиденциальной информации было предоставлено, а затем для уточнения политики защиты от потери данных по умолчанию — по нажатию или двум.</span><span class="sxs-lookup"><span data-stu-id="4d716-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="4d716-109">Вы также можете изменить политику защиты от потери данных по умолчанию в любое время, так как она полностью настраиваемая.</span><span class="sxs-lookup"><span data-stu-id="4d716-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="4d716-110">Обратите внимание, что если вы не видите рекомендацию, нажмите кнопку **+ More (дополнительно** ) в нижней части раздела **рекомендуем для вас** .</span><span class="sxs-lookup"><span data-stu-id="4d716-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Мини-приложение с именем далее Защитите общий контент](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="4d716-112">Просмотр отчета и уточнение политики защиты от потери данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4d716-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="4d716-113">Когда мини-приложение показывает, что у пользователей есть доступ к конфиденциальной информации для людей за прев Организации, в нижней части выберите пункт **уточнение политики защиты от потери** данных.</span><span class="sxs-lookup"><span data-stu-id="4d716-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="4d716-114">Подробный отчет показывает, когда и сколько контента, содержащего номера кредитных карт, были предоставлены за прошедшие 30 дней.</span><span class="sxs-lookup"><span data-stu-id="4d716-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="4d716-115">Обратите внимание, что соответствие правила может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="4d716-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="4d716-116">Для защиты конфиденциальной информации политика защиты от потери данных по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="4d716-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="4d716-117">Определяет, когда контент в Exchange, SharePoint и OneDrive содержит по крайней мере один номер кредитной карты, к которому предоставлен доступ пользователям за прев Организации.</span><span class="sxs-lookup"><span data-stu-id="4d716-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="4d716-118">Показывает подсказку политики и отправляет пользователям уведомления по электронной почте при попытке поделиться конфиденциальной информацией с пользователями, не входящими в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="4d716-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="4d716-119">Более подробную информацию об этих параметрах можно узнать в статье [Отправка уведомлений по электронной почте и отображение советов политики для политик защиты от потери](use-notifications-and-policy-tips.md)данных.</span><span class="sxs-lookup"><span data-stu-id="4d716-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="4d716-120">Создает подробные отчеты об активности, чтобы можно было отслеживать такие аспекты, как доступ к контенту пользователям за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4d716-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="4d716-121">Для просмотра этих сведений можно использовать [отчеты о](view-the-dlp-reports.md) защите от потери [данных и журнал аудита](search-the-audit-log-in-security-and-compliance.md) **(где** = **DLP DLP**).</span><span class="sxs-lookup"><span data-stu-id="4d716-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="4d716-122">Чтобы быстро уточнить политику защиты от потери данных по умолчанию, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4d716-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="4d716-123">Отправьте вам сообщение по электронной почте, когда пользователи совместно используют эти конфиденциальные сведения с людьми, не входящими в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="4d716-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="4d716-124">Добавьте других пользователей в отчет об инцидентах электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4d716-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="4d716-125">Блокировать доступ к контенту, содержащему конфиденциальные данные, но разрешить пользователю переопределять и предоставлять общий доступ к ним, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="4d716-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="4d716-126">Дополнительные сведения об отчетах об инцидентах и ограничениях доступа приведены в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d716-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="4d716-127">Если вы хотите изменить эти параметры позже, вы можете изменить политику защиты от потери данных по умолчанию в любой момент, просмотрев следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="4d716-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Параметры для мини-приложения с именем "Дополнительно" защитить общий контент](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="4d716-129">Изменение политики защиты от потери данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4d716-129">Edit the default DLP policy</span></span>

<span data-ttu-id="4d716-130">Эта политика называется **Default DLP Office 365** и отображается в разделе **Защита от потери данных** на странице **Политика** центра соответствия требованиям безопасности &amp; .</span><span class="sxs-lookup"><span data-stu-id="4d716-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4d716-131">Эта политика является полностью настраиваемой, то же, что и любая политика защиты от потери данных, которую вы самостоятельно создаете с нуля.</span><span class="sxs-lookup"><span data-stu-id="4d716-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="4d716-132">Вы также можете отключить или удалить политику, чтобы пользователи больше не получали подсказки политики или уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="4d716-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Политика защиты от потери данных с именем Default DLP Office 365](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="4d716-134">Когда мини-приложение отображается и не отображается</span><span class="sxs-lookup"><span data-stu-id="4d716-134">When the widget does and does not appear</span></span>

<span data-ttu-id="4d716-135">Мини-приложение под названием " **дальнейшая Защита общего содержимого** " отображается в разделе **рекомендуемый для вас** на &amp; **домашней** странице центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4d716-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="4d716-136">Это мини-приложение отображается только в том случае, если:</span><span class="sxs-lookup"><span data-stu-id="4d716-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="4d716-137">В центре безопасности &amp; и в центре администрирования Exchange нет политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="4d716-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="4d716-138">Этот мини-приложение предназначено для начала работы с DLP, поэтому оно не отображается, если у вас уже есть политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="4d716-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="4d716-139">Контент, содержащий по крайней мере одну кредитную карту, предоставленный другим пользователям за пределами вашей организации за прошедшие 30 дней.</span><span class="sxs-lookup"><span data-stu-id="4d716-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="4d716-140">Обратите внимание, что соответствие правила может занять до 48 часов, поэтому после обнаружения конфиденциальной информации, которая будет доступна извне, может потребоваться до двух дней для отображения рекомендации.</span><span class="sxs-lookup"><span data-stu-id="4d716-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="4d716-141">Наконец, после использования мини-приложения для уточнения политики защиты от потери данных по умолчанию мини-приложение исчезает с **домашней** страницы.</span><span class="sxs-lookup"><span data-stu-id="4d716-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

