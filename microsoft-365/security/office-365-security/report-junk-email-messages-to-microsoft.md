---
title: Составление отчетов о нежелательной почте и сообщениях фишинга в корпорацию Майкрософт
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о различных способах сообщить о хороших и плохом сообщениях в корпорацию Майкрософт.
ms.openlocfilehash: 19e00300b09674c5d44ffa7e38e0f4f3f93dda90
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634368"
---
# <a name="report-messages-and-files-to-microsoft"></a>Передача информации о сообщениях и файлах в корпорацию Майкрософт

Пользователи и администраторы в Microsoft 365 организации с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online имеют несколько различных способов создания отчетов для сообщений и файлов в корпорацию Майкрософт.

|||
|---|---|
|**Метод**|**Описание**|
|[Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md)|Рекомендуемый метод составления отчетов для администраторов в организациях с почтовыми ящиками Exchange Online (недоступен в автономном EOP).|
|[Включение надстройки Report Message в Microsoft 365](enable-the-report-message-add-in.md)|Работает с Outlook, Outlook для Mac и Outlook в Интернете (прежнее название — Outlook Web App) и является рекомендуемой надстройкой. <br/><br/> В зависимости от подписки сообщения, которые пользователи сообщили с помощью надстройки, доступны в [результатах автоматизированного исследования и ответа](air-view-investigation-results.md), [отчета о пользователях](view-email-security-reports.md#user-reported-messages-report)и [обозревателе угроз](threat-explorer-views.md#email--submissions).|
|[Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook в Microsoft 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Работает только в Outlook.|
|[Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете в Microsoft 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Использование встроенных возможностей Outlook в Интернете для организаций с почтовыми ящиками Exchange Online (недоступно в автономном EOP).|
|[Отправка сообщений в корпорацию Майкрософт для анализа вручную](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Вручную отправьте прикрепленные сообщения на конкретные адреса электронной почты Майкрософт для нежелательной почты, а не спама и фишинга. <br/><br/> Кроме того, Узнайте, как создать правило для процесса обработки почты (также называемое правилом транспорта), которое уведомляет вас, когда пользователи отправляют сообщения на эти электронные адреса отчетов.|
|[Передача вредоносных и невредоносных программ в корпорацию Майкрософт для анализа](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Используйте сайт Microsoft Security Intelligence для отправления вложений и других файлов.|
|

Если Нежелательная почта или фишинговые сообщения помещены в карантин, а не доставлены, пользователи могут отправлять сообщения в корпорацию Майкрософт из карантинного портала в центре безопасности & соответствия требованиям. Подробные сведения см. [в статье Поиск и освобождение сообщений, помещенных в карантин, в качестве пользователя в Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).