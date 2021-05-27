---
title: Сообщение о спаме, не спаме и фишинговых сообщениях в Корпорации Майкрософт
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
ms.openlocfilehash: 7b062c9529364e9fe26133fd1c039affcb8b7011
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689077"
---
# <a name="report-messages-and-files-to-microsoft"></a>Передача информации о сообщениях и файлах в корпорацию Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков, как пользователи, так и администраторы имеют несколько различных методов для отправки сообщений электронной почты и файлов в Корпорацию Майкрософт.

<br>

****

|Метод|Описание|
|---|---|
|[Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md)|Рекомендуемый метод отчетности для администраторов в организациях с Exchange Online почтовыми ящиками (недоступны в автономных EOP).|
|[Включить сообщение отчета или надстройки для фишинга отчетов](enable-the-report-message-add-in.md)|Работает с Outlook и Outlook в Интернете (ранее известный как Outlook Web App). <p> В зависимости от подписки сообщения, о которых пользователи сообщали с надстройки, доступны на портале [Представления](admin-submission.md)администратора, результатах автоматического расследования и ответа [(AIR),](air-view-investigation-results.md)отчете о сообщениях пользователя и обозревателе [](view-email-security-reports.md#user-reported-messages-report) [угроз.](threat-explorer-views.md#email--submissions) <p> Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)
|[Отчеты о ложных срабатываниях и ложных отрицаниях в Outlook](report-false-positives-and-false-negatives.md)|Отправка ложных срабатываний (хорошая электронная почта, которая была заблокирована или отправлена нежелательной папке) и ложных негативов (нежелательных сообщений электронной почты или фишинга, которые были доставлены в почтовый ящик) в Exchange Online Protection (EOP) с помощью функции Сообщение отчетов.|
|[Вручную отправлять сообщения в Корпорацию Майкрософт для анализа](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Вручную отправлять прикрепленные сообщения на конкретные адреса электронной почты Майкрософт для спама, а не нежелательной почты и фишинга.|
|[Использование правил потока почты для просмотра отчетов, передаваемых пользователями в Майкрософт](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Узнайте, как создать правило потока почты (также известное как правило транспорта), которое сообщает вам, когда пользователи сообщают сообщения в Корпорацию Майкрософт для анализа.|
|[Отправка вредоносных программ и не вредоносных программ в Корпорацию Майкрософт для анализа](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Используйте сайт портал для обнаружения угроз (Microsoft) для отправки вложений и других файлов.|
|

Если сообщения спама или фишинга были поставлены на карантин, а не доставлены, пользователи могут сообщать об этих сообщениях в Корпорацию Майкрософт с портала карантина в Центре & соответствия требованиям. Подробные сведения см. в материале [Find and release quarantined messages as a user in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Данные из представлений в Корпорацию Майкрософт находятся в Office 365 соответствия требованиям в центрах обработки данных в Северной Америке. Данные анализируют аналитики из инженерной группы, чтобы повысить эффективность фильтров.
