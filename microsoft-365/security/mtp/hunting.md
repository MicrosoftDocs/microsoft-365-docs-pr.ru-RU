---
title: Слежение за другими угрозами в Microsoft 365
description: Использование возможностей поиска угроз в центре безопасности Microsoft 365 для профилактического обнаружения нарушений и других угроз
keywords: безопасность, вредоносные программы, Microsoft 365, M365, центр обеспечения безопасности, поиск, поиск, пакет ATP для защитника, Office 365 ATP, Azure ATP, расширенный поиск
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
ms.openlocfilehash: 795a7d88c2b6021a5bdd665b3787644b50fb346a
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909433"
---
# <a name="hunt-for-threats-in-microsoft-365"></a>Поиск угроз в Microsoft 365

С помощью возможностей поиска угроз в центре безопасности Microsoft 365 вы можете в Организации обнаружить угрозы, затрагивающие электронную почту и данные, устройства и удостоверения. С экрана **** поискового засистемы можно получить доступ к средствам по поиску угроз, доступным для различных решений:
- Office 365 ATP: [слежение за угрозами для электронной почты и данных](../office-365-security/office-365-atp.md)
- Пакет ATP для защитника (Майкрософт) — [слежение за угрозами для устройств](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)
- Azure ATP — [слежение за угрозами для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)

![Страница "Поиск"](../images/hunt.png)


## <a name="hunt-with-microsoft-threat-protection"></a>Слежение за защитой от угроз Майкрософт

[Включите защиту от угроз Майкрософт](mtp-enable.md) , чтобы получить расширенный интерфейс запросов поиска непосредственно в центре безопасности Microsoft 365. С помощью [расширенного](advanced-hunting-overview.md)поиска вы можете создавать отдельные запросы, которые проверяют данные из пакета ATP для защитника Майкрософт, покрывающие данные с подключенных устройств и Office 365 ATP, предоставляя данные из электронных писем.

## <a name="related-topics"></a>Похожие темы
- [Общие сведения о расширенном поиске](advanced-hunting-overview.md)
- [Общие сведения о защите от угроз Майкрософт](microsoft-threat-protection.md)
- [Включение защиты от угроз Майкрософт](mtp-enable.md)