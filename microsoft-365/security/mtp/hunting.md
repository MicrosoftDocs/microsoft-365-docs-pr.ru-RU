---
title: Поиск угроз в Microsoft 365
description: Использование возможностей поиска угроз в центре безопасности Microsoft 365 для профилактического обнаружения нарушений и других угроз
keywords: Microsoft 365, M365, защита от угроз Майкрософт, MTP, центр безопасности, поиск, Поиск угроз, поиск в киберугроз, поиск в защитнике Майкрософт, Office 365 ATP, Azure ATP, расширенный поиск
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: lomayor
author: lomayor
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: c2bb0b088a40511eea36348d39790fd5e88fa40b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210164"
---
# <a name="hunt-for-threats-in-microsoft-365"></a><span data-ttu-id="96232-104">Поиск угроз в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96232-104">Hunt for threats in Microsoft 365</span></span>

<span data-ttu-id="96232-105">С помощью возможностей поиска угроз в центре безопасности Microsoft 365 вы можете в Организации обнаружить угрозы, затрагивающие электронную почту и данные, устройства и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="96232-105">With threat hunting capabilities in the Microsoft 365 security center, you can proactively find threats in your organization affecting email and data, devices, and identities.</span></span> <span data-ttu-id="96232-106">С экрана \*\*\*\* поискового засистемы можно получить доступ к средствам по поиску угроз, доступным для различных решений:</span><span class="sxs-lookup"><span data-stu-id="96232-106">From the **Hunting** screen, you can access threat hunting tools made available by various solutions:</span></span>
- <span data-ttu-id="96232-107">Office 365 ATP: [слежение за угрозами для электронной почты и данных](../office-365-security/office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="96232-107">Office 365 ATP — [hunt for threats to email and data](../office-365-security/office-365-atp.md)</span></span>
- <span data-ttu-id="96232-108">Пакет ATP для защитника (Майкрософт) — [слежение за угрозами для устройств](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="96232-108">Microsoft Defender ATP — [hunt for threats to devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span></span>
- <span data-ttu-id="96232-109">Azure ATP — [слежение за угрозами для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)</span><span class="sxs-lookup"><span data-stu-id="96232-109">Azure ATP — [hunt for threats to identities](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)</span></span>

![Страница "Поиск"](../images/hunt.png)


## <a name="hunt-with-microsoft-threat-protection"></a><span data-ttu-id="96232-111">Слежение за защитой от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="96232-111">Hunt with Microsoft Threat Protection</span></span>

<span data-ttu-id="96232-112">[Включите защиту от угроз Майкрософт](mtp-enable.md) , чтобы получить расширенный интерфейс запросов поиска непосредственно в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96232-112">[Turn on Microsoft Threat Protection](mtp-enable.md) to get the advanced hunting query interface directly in the Microsoft 365 security center.</span></span> <span data-ttu-id="96232-113">С помощью [расширенного](advanced-hunting-overview.md)поиска вы можете создавать отдельные запросы, которые проверяют данные из пакета ATP для защитника Майкрософт, покрывающие данные с подключенных устройств и Office 365 ATP, предоставляя данные из электронных писем.</span><span class="sxs-lookup"><span data-stu-id="96232-113">With [advanced hunting](advanced-hunting-overview.md), you can create single queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span>

## <a name="related-topics"></a><span data-ttu-id="96232-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="96232-114">Related topics</span></span>
- [<span data-ttu-id="96232-115">Общие сведения о расширенном поиске</span><span class="sxs-lookup"><span data-stu-id="96232-115">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="96232-116">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="96232-116">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="96232-117">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="96232-117">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
