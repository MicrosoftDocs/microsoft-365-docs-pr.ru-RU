---
title: Сообщение о спаме, не спаме и фишинговых сообщениях в Корпорации Майкрософт
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
description: Администраторы могут узнать о различных способах отчета о хороших и плохих сообщениях и файлах в Корпорации Майкрософт для анализа.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073182"
---
# <a name="report-messages-and-files-to-microsoft"></a>Передача информации о сообщениях и файлах в корпорацию Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online пользователи и администраторы имеют несколько различных методов для отправки сообщений электронной почты и файлов в Корпорацию Майкрософт.

****

|Метод|Описание|
|---|---|
|[Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md)|Рекомендуемый метод отчетности для администраторов в организациях с почтовыми ящиками Exchange Online (не доступны в автономных EOP).|
|[Включение надстройки Report Message](enable-the-report-message-add-in.md)|Работает с Outlook и Outlook в Интернете (ранее известный как Outlook Web App). <p> В зависимости от подписки сообщения, о которых пользователи сообщали с надстройки, доступны на портале [](view-email-security-reports.md#user-reported-messages-report) [Представления](admin-submission.md)администратора, результатах автоматического расследования и ответа [(AIR),](air-view-investigation-results.md)отчете о сообщениях пользователя и обозревателе [угроз.](threat-explorer-views.md#email--submissions) <p> Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)
|[Включение надстройки "Пожаловаться на фишинг"](enable-the-report-phish-add-in.md)|Работает с Outlook и Outlook в Интернете (ранее известный как Outlook Web App). <p> В зависимости от подписки сообщения, о которых пользователи сообщали с надстройки, доступны на портале [](view-email-security-reports.md#user-reported-messages-report) [Представления](admin-submission.md)администратора, результатах автоматического расследования и ответа [(AIR),](air-view-investigation-results.md)отчете о сообщениях пользователя и обозревателе [угроз.](threat-explorer-views.md#email--submissions) <p> Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)|
|[Установка и использование надстройки отчетов о нежелательной почте для Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Работает только в Outlook.|
|[Сообщение нежелательной и фишинговой почты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Используйте встроенные возможности в Outlook в Интернете для организаций с почтовыми ящиками Exchange Online (недоступны в автономных EOP). <p> Сообщения, о которых сообщают пользователи, доступны на [портале Отправки администратора.](admin-submission.md) <p> Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)|
|[Сообщение нежелательной и фишинговой почты в Outlook для iOS и Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Используйте встроенные возможности в Outlook для iOS и Android для организаций с почтовыми ящиками Exchange Online (недоступны в автономных EOP). <p> Сообщения, о которых сообщают пользователи, доступны на [портале Отправки администратора.](admin-submission.md) <p> Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)|
|[Вручную отправлять сообщения в Корпорацию Майкрософт для анализа](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Вручную отправлять прикрепленные сообщения на конкретные адреса электронной почты Майкрософт для спама, а не нежелательной почты и фишинга.|
|[Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Узнайте, как создать правило потока почты (также известное как правило транспорта), которое сообщает вам, когда пользователи сообщают сообщения в Корпорацию Майкрософт для анализа.|
|[Отправка вредоносных программ и не вредоносных программ в Корпорацию Майкрософт для анализа](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Используйте сайт Microsoft Security Intelligence для отправки вложений и других файлов.|

Если сообщения спама или фишинга были поставлены на карантин, а не доставлены, пользователи могут сообщать об этих сообщениях в Корпорацию Майкрософт с портала карантина в Центре & соответствия требованиям. Подробные сведения см. в материале [Find and release quarantined messages as a user in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Данные, полученные от отправки в Корпорацию Майкрософт, находятся в границах соответствия Office 365 в центрах обработки данных в Северной Америке. Данные анализируют аналитики из инженерной группы, чтобы повысить эффективность фильтров.
