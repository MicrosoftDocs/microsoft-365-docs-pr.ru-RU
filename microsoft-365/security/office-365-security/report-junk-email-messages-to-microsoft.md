---
title: Сообщение о спаме, не спаме и фишинговых сообщениях в корпорацию Майкрософт
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о различных способах сообщить о сообщениях и файлах в корпорацию Майкрософт для анализа.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b75b05f33ab6c6a5827101ad2f5b14c94b932135
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166691"
---
# <a name="report-messages-and-files-to-microsoft"></a>Передача информации о сообщениях и файлах в корпорацию Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи и администраторы могут отправлять сообщения электронной почты и файлы в корпорацию Майкрософт различными способами.

****

|Метод|Описание|
|---|---|
|[Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md)|Рекомендуемый способ отчетности для администраторов в организациях с почтовыми ящиками Exchange Online (недоступны в автономных EOP).|
|[Включение надстройки Report Message](enable-the-report-message-add-in.md)|Работает с Outlook и Outlook в Интернете (прежнее название — Outlook Web App). <p> В зависимости от вашей подписки сообщения, о которых пользователи [](admin-submission.md)сообщили с помощью надстройки, доступны на портале отправки администраторов, в результатах автоматического анализа и реагирования [на них,](air-view-investigation-results.md)отчете о сообщениях, [](view-email-security-reports.md#user-reported-messages-report)сообщающих о пользователе, и в обозревателе [угроз.](threat-explorer-views.md#email--submissions) <p> Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик. Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)
|[Включение надстройки "Пожаловаться на фишинг"](enable-the-report-phish-add-in.md)|Работает с Outlook и Outlook в Интернете (прежнее название — Outlook Web App). <p> В зависимости от вашей подписки сообщения, о которых пользователи [](admin-submission.md)сообщили с помощью надстройки, доступны на портале отправки администраторов, в результатах автоматического анализа и реагирования [на них,](air-view-investigation-results.md)отчете о сообщениях, [](view-email-security-reports.md#user-reported-messages-report)сообщающих о пользователе, и в обозревателе [угроз.](threat-explorer-views.md#email--submissions) <p> Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик. Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)|
|[Установка и использование надстройки "Отчеты о нежелательной почте" для Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Работает только в Outlook.|
|[Отправка отчетов о нежелательной и фишинговой почте в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Используйте встроенные возможности Outlook в Интернете для организаций с почтовыми ящиками Exchange Online (недоступны в автономных EOP). <p> Сообщения, о которых сообщают пользователи, доступны на [портале отправки администраторов.](admin-submission.md) <p> Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик. Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)|
|[Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Используйте встроенные возможности Outlook для iOS и Android для организаций с почтовыми ящиками Exchange Online (недоступны в автономных EOP). <p> Сообщения, о которых сообщают пользователи, доступны на [портале отправки администраторов.](admin-submission.md) <p> Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик. Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)|
|[Отправка сообщений вручную в корпорацию Майкрософт для анализа](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Вручную отправлять вложенные сообщения на определенные адреса электронной почты Майкрософт для спама, а не спама и фишинга.|
|[Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Узнайте, как создать правило потока почты (также известное как правило транспорта), которое сообщает вам, когда пользователи сообщают о сообщениях в корпорацию Майкрософт для анализа.|
|[Отправка вредоносных программ и не вредоносных программ в корпорацию Майкрософт для анализа](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Используйте сайт microsoft Security Intelligence для отправки вложений и других файлов.|

Если нежелательные или фишинговые сообщения были поставлены на карантин вместо доставки, пользователи могут сообщить о них корпорации Майкрософт с портала карантина в Центре безопасности & соответствия требованиям. Подробные сведения см. в записи поиска и освобождения сообщений на карантине от пользователя [в Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Данные от от отправленных в корпорацию Майкрософт данных находятся на границе соответствия требованиям Office 365 в центрах обработки данных в Северной Америке. Данные проверяются аналитиками из группы разработки, чтобы повысить эффективность фильтров.
