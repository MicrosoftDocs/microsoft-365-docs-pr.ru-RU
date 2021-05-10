---
title: Пример фишинговой атаки электронной почты
description: Проанализив пример фишинговой атаки.
keywords: инциденты, оповещения, исследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверение, почтовый ящик, электронная почта, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299992"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="8effb-104">Пример фишинговой атаки электронной почты</span><span class="sxs-lookup"><span data-stu-id="8effb-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8effb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8effb-105">**Applies to:**</span></span>
- <span data-ttu-id="8effb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8effb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8effb-107">Microsoft 365 Defender может помочь обнаружить вредоносные вложения, доставленные по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="8effb-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="8effb-108">Так как [центр Office 365](https://protection.office.com/) безопасности и соответствия требованиям интегрируется с Microsoft 365 Defender, аналитики безопасности могут иметь видимость угроз, исходя Office 365, например с помощью вложений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8effb-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="8effb-109">Например, аналитику был назначен многоэтапный инцидент.</span><span class="sxs-lookup"><span data-stu-id="8effb-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Пример многоэтапного инцидента"::: 

<span data-ttu-id="8effb-111">На **вкладке Оповещения** об инциденте отображаются оповещения от Defender для Office 365 и Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8effb-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="8effb-112">Аналитик может сверлить в Defender для Office 365 оповещения, выбрав оповещений о сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8effb-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="8effb-113">Сведения об оповещении отображаются на боковой области.</span><span class="sxs-lookup"><span data-stu-id="8effb-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Пример оповещений по электронной почте":::
 
<span data-ttu-id="8effb-115">При прокрутке вниз далее отображаются дополнительные сведения, показывающие вредоносные файлы и пользователя, которые были сбиты.</span><span class="sxs-lookup"><span data-stu-id="8effb-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Пример воздействия оповещения электронной почты на пользователя и файл":::
  
<span data-ttu-id="8effb-117">Выбор страницы **"Открытое** оповещение" подходит к определенному оповещению, в котором различные сведения можно просмотреть более подробно, выбрав ссылку.</span><span class="sxs-lookup"><span data-stu-id="8effb-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="8effb-118">Фактическое сообщение электронной почты можно просмотреть, выбрав просмотр сообщений **в Explorer** в нижней части панели.</span><span class="sxs-lookup"><span data-stu-id="8effb-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Пример сведений о оповещении"::: 

<span data-ttu-id="8effb-120">Это выводит аналитика на страницу Управления угрозами, на которой отображаются тема электронной почты, получатель, отправитель и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="8effb-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="8effb-121">**ZaP** в **статье Special Actions** сообщает аналитику, что функция автоматической очистки нулевого часа реализована.</span><span class="sxs-lookup"><span data-stu-id="8effb-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="8effb-122">ZAP автоматически обнаруживает и удаляет вредоносные и нежелательные сообщения из почтовых ящиков по всей организации.</span><span class="sxs-lookup"><span data-stu-id="8effb-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="8effb-123">Дополнительные сведения см. в [Exchange Online.](../office-365-security/zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="8effb-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="8effb-124">Другие действия можно принять для определенных сообщений, выбрав **Действия**.</span><span class="sxs-lookup"><span data-stu-id="8effb-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Пример других действий можно принять в сообщениях электронной почты"::: 

## <a name="next-step"></a><span data-ttu-id="8effb-126">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8effb-126">Next step</span></span>

<span data-ttu-id="8effb-127">См. путь к расследованию [атаки на](first-incident-path-identity.md) основе удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8effb-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="8effb-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8effb-128">See also</span></span>

- [<span data-ttu-id="8effb-129">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="8effb-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8effb-130">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="8effb-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8effb-131">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="8effb-131">Manage incidents</span></span>](manage-incidents.md)
