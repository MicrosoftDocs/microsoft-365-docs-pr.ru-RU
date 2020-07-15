---
title: Соблюдение правила 17a-4 SEC с помощью Exchange Online и Центра безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Настройте Exchange Online и Центр соответствия требованиям для соблюдения нормативных требований правила 1.31 (c)–(d) CFTC, правила 4511 FINRA и правила 17a-4 SEC.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127306"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Соблюдение правила 17a-4 SEC с помощью Exchange Online и Центра безопасности и соответствия требованиям

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

Чтобы помочь этим организациям лучше понять, как использовать Центр безопасности и соответствия требованиям для выполнения обязательств по соответствию нормативным требованиям для Exchange Online, в частности в отношении требований правила 17a-4, мы произвели оценку в сотрудничестве с Cohasset Associates.

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>Скачивание оценки Cohasset

Вы можете скачать оценку Cohasset [здесь](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Титульная страница доступной для загрузки оценки Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>Эта оценка относится к Exchange Online

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>Использование блокировки для сохранения является ключевым пунктом рекомендованной конфигурации

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- Записи хранятся в течение обязательного периода хранения, который нельзя сократить, а можно только увеличить.
- Записи являются неизменяемыми, то есть их нельзя перезаписывать, удалять или изменять в течение обязательного периода хранения.

In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- Период хранения политики может быть только увеличен, а не уменьшен.
- Пользователи могут быть добавлены в политику, но не могут быть удалены из нее.
- Администратор не может удалить политику хранения.

Блокировка для сохранения может обеспечить соответствие нормативным требованиям SEC 17a-4.

## <a name="how-to-set-up-preservation-lock"></a>Настройка блокировки для сохранения

Можно заблокировать политику хранения с помощью PowerShell. Дополнительные сведения см. в статье [Использование блокировки для сохранения с целью соблюдения нормативных требований](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).

## <a name="known-limitations"></a>Известные ограничения

В настоящее время существует несколько ограничений для Exchange Online:

- Сообщения в чатах и каналах Teams нельзя объединить в цепочки.
- Отметки "Мне нравится" не сохраняются для сообщений в чатах и каналах Teams.

> [!NOTE]
> Аудит на уровне элементов теперь доступен для почтовых ящиков групп Microsoft 365. Дополнительные сведения см. в статье [Управление аудитом почтовых ящиков](enable-mailbox-auditing.md).
