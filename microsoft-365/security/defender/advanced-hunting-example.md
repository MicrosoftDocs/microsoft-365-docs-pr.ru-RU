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
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Расширенный пример охоты для Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Хотите начать поиск угроз электронной почты с помощью расширенных методов поиска? Выполните следующие действия.

В разделе [Начало работы](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) статьи [Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) предварительно логические блоки конфигурации выглядят следующим образом:

1. Настройте все с помощью "Anti" в имени.
   - Функции защиты от вредоносных программ
   - Anti-phishing
   - Защита от нежелательной почты
2. Настройка всего с помощью Сейф в имени.
   - Безопасные ссылки
   - Безопасные вложения
3. Защищайте рабочие нагрузки (например, SharePoint Online, OneDrive и Teams).
4. Защита с помощью автоматической очистки нулевого часа.

Вместе со [ссылкой](../office-365-security/protect-against-threats.md), по которой можно сразу приняться за дело и перейти к настройке в день 1.

Последний шаг в разделе **Начало работы** — защита пользователей с помощью **автоматической очистки**, известной также как ZAP. Очень важно знать, были ли успешными попытки автоматической очистки подозрительной или вредоносной почты после доставки.

Быстрый переход к языку запросов Kusto для охоты на проблемы является преимуществом совмещения этих двух центров безопасности. Группы безопасности могут отслеживать промахи ZAP, предприняв следующие действия [здесь,](https://security.microsoft.com/advanced-hunting)в **статье Hunting** \> **Advanced Hunting**.

1. На странице Расширенный поиск нажмите **запрос**.
1. Скопируйте приведенный далее запрос в окно для запроса.
1. Выберите **запрос Run**.

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

Данные по этому запросу будут отображаться на панели результатов под самим запросом. Результаты включают такие сведения, как "DeviceName", "AccountDisplayName" и "ZapTime". Это набор результатов, который можно настраивать.  Результаты также можно экспортировать для хранения. Если запрос вам может снова понадобиться, выберите **Сохранить** > **Сохранить как** и добавьте запрос в свой список запросов, общий список или список запросов сообщества.

## <a name="related-information"></a>Статьи по теме
- [Передовые методы охоты](advanced-hunting-best-practices.md)
- [Обзор — расширенный поиск](advanced-hunting-overview.md)
