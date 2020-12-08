---
title: Интеграция билетов с ServiceNow в центр безопасности и соответствия требованиям Microsoft 365
description: Узнайте, как создавать и отслеживать билеты в ServiceNow с помощью центра обеспечения безопасности Microsoft 365 и центра соответствия требованиям.
keywords: безопасность, Microsoft 365, M365, соответствие требованиям, центр обеспечения безопасности, ServiceNow, билеты, задачи, SNOW, подключение
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 1d629de983e73258e491f18f7a34403d6f522520
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588545"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="a1524-104">Интеграция билетов с ServiceNow в центр безопасности и соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1524-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="a1524-105">**Период предварительной версии соединителя ServiceNow завершен**</span><span class="sxs-lookup"><span data-stu-id="a1524-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="a1524-106">Эта возможность больше недоступна.</span><span class="sxs-lookup"><span data-stu-id="a1524-106">This capability is no longer available.</span></span> <span data-ttu-id="a1524-107">Благодарим вас за отзыв и продолжение поддержки, пока мы определим дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="a1524-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="a1524-108">ServiceNow — это популярная платформа облачных вычислений, которая помогает компаниям управлять цифровыми рабочими процессами для корпоративных операций.</span><span class="sxs-lookup"><span data-stu-id="a1524-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="a1524-109">На их платформах теперь есть рабочие процессы, рабочие процессы сотрудников и рабочие процессы клиентов.</span><span class="sxs-lookup"><span data-stu-id="a1524-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="a1524-110">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="a1524-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="a1524-111">Корпорация Майкрософт поделилась с ServiceNow, чтобы облегчить ИТ-администраторам управлять своими билетами и задачами на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="a1524-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="a1524-112">[Центр безопасности microsoft 365](overview-security-center.md) и [центр соответствия требованиям корпорации майкрософт (Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) ) позволяют улучшить создание и отслеживание билетов в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="a1524-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>
