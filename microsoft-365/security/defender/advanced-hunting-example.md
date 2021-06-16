---
title: Расширенный пример охоты для Microsoft Defender для Office 365
description: Начало поиска угроз электронной почты с помощью продвинутой охоты
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, microsoft 365, m365, поиск, запрос, телеметрия, пользовательские обнаружения, схема, кусто
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965152"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="a1141-104">Расширенный пример охоты для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="a1141-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a1141-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a1141-105">**Applies to:**</span></span>
- <span data-ttu-id="a1141-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1141-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a1141-107">Хотите начать поиск угроз электронной почты с помощью расширенных методов поиска?</span><span class="sxs-lookup"><span data-stu-id="a1141-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="a1141-108">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a1141-108">Try this:</span></span>

<span data-ttu-id="a1141-109">В разделе [Начало работы](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) статьи [Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) предварительно логические блоки конфигурации выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a1141-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="a1141-110">Настройте все с помощью "Anti" в имени.</span><span class="sxs-lookup"><span data-stu-id="a1141-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="a1141-111">Функции защиты от вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="a1141-111">Anti-malware</span></span>
   - <span data-ttu-id="a1141-112">Anti-phishing</span><span class="sxs-lookup"><span data-stu-id="a1141-112">Anti-phishing</span></span>
   - <span data-ttu-id="a1141-113">Защита от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="a1141-113">Anti-spam</span></span>
2. <span data-ttu-id="a1141-114">Настройка всего с помощью Сейф в имени.</span><span class="sxs-lookup"><span data-stu-id="a1141-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="a1141-115">Безопасные ссылки</span><span class="sxs-lookup"><span data-stu-id="a1141-115">Safe Links</span></span>
   - <span data-ttu-id="a1141-116">Безопасные вложения</span><span class="sxs-lookup"><span data-stu-id="a1141-116">Safe Attachments</span></span>
3. <span data-ttu-id="a1141-117">Защищайте рабочие нагрузки (например,</span><span class="sxs-lookup"><span data-stu-id="a1141-117">Defend the workloads (ex.</span></span> <span data-ttu-id="a1141-118">SharePoint Online, OneDrive и Teams).</span><span class="sxs-lookup"><span data-stu-id="a1141-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="a1141-119">Защита с помощью автоматической очистки нулевого часа.</span><span class="sxs-lookup"><span data-stu-id="a1141-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="a1141-120">Вместе со [ссылкой](../office-365-security/protect-against-threats.md), по которой можно сразу приняться за дело и перейти к настройке в день 1.</span><span class="sxs-lookup"><span data-stu-id="a1141-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="a1141-121">Последний шаг в разделе **Начало работы** — защита пользователей с помощью **автоматической очистки**, известной также как ZAP.</span><span class="sxs-lookup"><span data-stu-id="a1141-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="a1141-122">Очень важно знать, были ли успешными попытки автоматической очистки подозрительной или вредоносной почты после доставки.</span><span class="sxs-lookup"><span data-stu-id="a1141-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="a1141-123">Быстрый переход к языку запросов Kusto для охоты на проблемы является преимуществом совмещения этих двух центров безопасности.</span><span class="sxs-lookup"><span data-stu-id="a1141-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="a1141-124">Группы безопасности могут отслеживать промахи ZAP, предприняв следующие действия [здесь,](https://security.microsoft.com/advanced-hunting)в **статье Hunting** \> **Advanced Hunting**.</span><span class="sxs-lookup"><span data-stu-id="a1141-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="a1141-125">На странице Расширенный поиск нажмите **запрос**.</span><span class="sxs-lookup"><span data-stu-id="a1141-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="a1141-126">Скопируйте приведенный далее запрос в окно для запроса.</span><span class="sxs-lookup"><span data-stu-id="a1141-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="a1141-127">Выберите **запрос Run**.</span><span class="sxs-lookup"><span data-stu-id="a1141-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Страница Advanced hunting (в статье Hunting) с запросом, выбранным в верхней части панели запросов, и запуск запроса Kusto для захвата действий ZAP в течение последних 7 дней.":::

<span data-ttu-id="a1141-129">Данные по этому запросу будут отображаться на панели результатов под самим запросом.</span><span class="sxs-lookup"><span data-stu-id="a1141-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="a1141-130">Результаты включают такие сведения, как "DeviceName", "AccountDisplayName" и "ZapTime". Это набор результатов, который можно настраивать. </span><span class="sxs-lookup"><span data-stu-id="a1141-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="a1141-131">Результаты также можно экспортировать для хранения.</span><span class="sxs-lookup"><span data-stu-id="a1141-131">Results can also be exported for your records.</span></span> <span data-ttu-id="a1141-132">Если запрос вам может снова понадобиться, выберите **Сохранить** > **Сохранить как** и добавьте запрос в свой список запросов, общий список или список запросов сообщества.</span><span class="sxs-lookup"><span data-stu-id="a1141-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="a1141-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a1141-133">Related information</span></span>
- [<span data-ttu-id="a1141-134">Передовые методы охоты</span><span class="sxs-lookup"><span data-stu-id="a1141-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a1141-135">Обзор — расширенный поиск</span><span class="sxs-lookup"><span data-stu-id="a1141-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
