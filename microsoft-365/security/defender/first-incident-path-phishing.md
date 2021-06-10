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
# <a name="example-of-a-phishing-email-attack"></a>Пример фишинговой атаки электронной почты

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Microsoft 365 Defender может помочь обнаружить вредоносные вложения, доставленные по электронной почте. Так как [центр Office 365](https://protection.office.com/) безопасности и соответствия требованиям интегрируется с Microsoft 365 Defender, аналитики безопасности могут иметь видимость угроз, исходя Office 365, например с помощью вложений электронной почты.

Например, аналитику был назначен многоэтапный инцидент.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Пример многоэтапного инцидента"::: 

На **вкладке Оповещения** об инциденте отображаются оповещения от Defender для Office 365 и Microsoft Cloud App Security. Аналитик может сверлить в Defender для Office 365 оповещения, выбрав оповещений о сообщениях электронной почты. Сведения об оповещении отображаются на боковой области.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Пример оповещений по электронной почте":::
 
При прокрутке вниз далее отображаются дополнительные сведения, показывающие вредоносные файлы и пользователя, которые были сбиты.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Пример воздействия оповещения электронной почты на пользователя и файл":::
  
Выбор страницы **"Открытое** оповещение" подходит к определенному оповещению, в котором различные сведения можно просмотреть более подробно, выбрав ссылку. Фактическое сообщение электронной почты можно просмотреть, выбрав просмотр сообщений **в Explorer** в нижней части панели.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Пример сведений о оповещении"::: 

Это выводит аналитика на страницу Управления угрозами, на которой отображаются тема электронной почты, получатель, отправитель и другие сведения. **ZaP** в **статье Special Actions** сообщает аналитику, что функция автоматической очистки нулевого часа реализована. ZAP автоматически обнаруживает и удаляет вредоносные и нежелательные сообщения из почтовых ящиков по всей организации. Дополнительные сведения см. в [Exchange Online.](../office-365-security/zero-hour-auto-purge.md)

Другие действия можно принять для определенных сообщений, выбрав **Действия**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Пример других действий можно принять в сообщениях электронной почты"::: 

## <a name="next-step"></a>Следующий этап

См. путь к расследованию [атаки на](first-incident-path-identity.md) основе удостоверений.

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Исследование инцидентов](investigate-incidents.md)
- [Управление инцидентами](manage-incidents.md)
