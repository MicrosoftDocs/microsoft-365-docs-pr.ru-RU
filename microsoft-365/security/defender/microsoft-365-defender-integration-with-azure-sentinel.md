---
title: Интеграция Microsoft 365 Defender с Azure Sentinel
description: Используйте Azure Sentinel в качестве SIEM для Microsoft 365 Defender инцидентов и событий.
keywords: инциденты, оповещения, исследование, анализ, ответ, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365
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
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229915"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="7cbb9-104">Интеграция Microsoft 365 Defender с Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="7cbb9-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7cbb9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7cbb9-105">**Applies to:**</span></span>
- <span data-ttu-id="7cbb9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cbb9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7cbb9-107">Соединитель Microsoft 365 Defender Azure Sentinel (предварительный просмотр) отправляет все Microsoft 365 Defender и оповещает о них в Azure Sentinel и сохраняет синхронизацию инцидентов.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="7cbb9-108">После добавления соединителя Microsoft 365 Defender инциденты, которые включают все связанные оповещения, объекты и релевантные сведения, полученные от Microsoft Defender для конечной точки, Защитника Майкрософт для удостоверений, Microsoft Defender для Office 365 и Microsoft Cloud App Security, будут передаваться в Azure Sentinel в качестве данных по безопасности и управлению событиями (SIEM), предоставляя контекст для выполнения триажа и реагирования на инциденты в &mdash; &mdash; Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="7cbb9-109">После работы в Azure Sentinel инциденты по-прежнему синхронизируются с Microsoft 365 Defender, что позволяет использовать преимущества центра безопасности Microsoft 365 и Azure Sentinel на портале Azure для расследования инцидентов и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="7cbb9-110">Просмотрите краткий обзор интеграции Azure Sentinel с Microsoft 365 Defender (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="7cbb9-111">Вот как это работает.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Поток и обмен данными об инцидентах между Microsoft 365 Defender и Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="7cbb9-113">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7cbb9-113">Next steps</span></span>

1. <span data-ttu-id="7cbb9-114">Получите более глубокое представление об [интеграции Microsoft 365 Defender Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="7cbb9-115">[Подключение от Microsoft 365 Defender до Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="7cbb9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7cbb9-116">See also</span></span>

- [<span data-ttu-id="7cbb9-117">Обзор инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cbb9-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="7cbb9-118">Расследование инцидентов с Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="7cbb9-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
