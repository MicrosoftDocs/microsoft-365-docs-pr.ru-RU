---
title: Применение меток к персональным данным
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Узнайте, как использовать ярлыки Office как часть вашего плана защиты Общего Регламента Защиты Данных (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126820"
---
# <a name="apply-labels-to-personal-data"></a>Применение меток к персональным данным

 Указания в этой статье помогут вам, если вы используете метки классификации для защиты данных в соответствии с регламентом GDPR. 

Если вы используете метки для защиты персональных данных в Microsoft 365, корпорация Майкрософт рекомендует начать работу с [метками хранения](retention.md#retention-labels). С помощью меток хранения вы можете:
- Использовать расширенное управление данными, чтобы автоматически применять метки в зависимости от типов конфиденциальной информации или других условий.
- Применять защиту, используя метки хранения с защитой от потери данных. 
- Использовать метки с функциями обнаружения электронных данных и поиска контента. 

Cloud App Security сейчас не поддерживает метки хранения, но вы можете использовать типы конфиденциальной информации Microsoft 365 с Cloud App Security для отслеживания персональных данных, которые хранятся в других приложениях SaaS.

В настоящее время [метки конфиденциальности](sensitivity-labels.md) рекомендуется использовать для применения меток к файлам в локальной среде, других облачных службах и поставщиках, Их также рекомендуется использовать для файлов в Microsoft 365, требующих защиты данных с помощью шифрования Azure Information Protection. Например, такие файлы могут содержать коммерческую тайну.

Сейчас Azure Information Protection не рекомендуется использовать для шифрования файлов Microsoft 365 с данными, на которые распространяется регламент GDPR. Службы Microsoft 365 в настоящее время не могут считывать файлы, зашифрованные с использованием AIP, поэтому не могут находить конфиденциальные данные в этих файлах.

К почте в Exchange Online можно применять метки хранения. Кроме того, их можно использовать при защите от потери данных в Microsoft 365. 

![Метки Microsoft 365 и Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


На этом рисунке:

-   Используйте метки хранения для персональных данных, строго регулируемых файлов и файлов с коммерческими тайнами в SharePoint Online и OneDrive для бизнеса.
-   Типы конфиденциальной информации Microsoft 365 можно использовать в Microsoft 365 и с Cloud App Security для отслеживания персональных данных, хранящихся в других приложениях SaaS.
-   Используйте метки конфиденциальности для строго регулируемых файлов и файлов с коммерческими тайнами, электронной почты Exchange Online, файлов в других службах SaaS, файлов в локальных центрах обработки данных и других облачных службах.


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Использование меток хранения и типов конфиденциальной информации в Microsoft 365 для защиты данных

На рисунке ниже показано, как метки хранения и типы конфиденциальной информации можно использовать в политиках в отношении меток, политиках защиты от потери данных и политиках Cloud App Security.

![Метки и типы конфиденциальной информации Office](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Элементы классификации</strong></th>
<th align="left"><strong>Политики в отношении меток — 2 примера</strong></th>
<th align="left"><strong>Политики защиты от потери данных — 2 примера</strong></th>
<th align="left"><strong>Политики Cloud App Security для всех приложений SaaS — 1 пример</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Метки хранения. Примеры: "Персональные", "Общедоступные", "Данные клиента", "Данные о персонале" "Конфиденциально", "Строго конфиденциально"</td>
<td align="left"><p>Auto apply this label . . .</p>
<p>Данные клиента</p>
<p>. . . to documents that match these sensitive information types . . .</p>
<p>&lt;список примеров типов конфиденциальной информации&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;определение защиты&gt;</p>
<p>. . . to documents with this label . . .</p>
<p>Данные клиента</p></td>
<td align="left"><p>Alert when files with these attributes . . .</p>
<p>Выберите один или несколько атрибутов: предопределенный атрибут PII, тип конфиденциальной информации Microsoft 365, метка конфиденциальности (AIP), настраиваемое выражение</p>
<p>. . . в любом санкционированном приложении SaaS предоставляется общий доступ за пределами организации</p><p>Примечание. Метки хранения сейчас не поддерживаются в Cloud App Security.</td>
</tr>
<tr class="even">
<td align="left">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</td>
<td align="left"><p>Publish these labels for users to manually apply . . .</p>
<p>&lt;выберите метки&gt;</p>
<p>. . . to these locations . . .</p>
<p>&lt;все расположения или выберите расположения&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;определение защиты&gt;</p>
<p>. . . to documents that match these sensitive information types&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>Определение приоритетных политик автоматического применения меток

For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.

The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.

### <a name="one-label-at-a-time"></a>По одной метке

Документу можно назначить только одну метку.

### <a name="older-auto-apply-policies-win"></a>Установка приоритета для политик автоматического применения более ранних версий

If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>Метки, вручную примененные пользователем, имеют приоритет над автоматическими метками

Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.

### <a name="auto-assigned-labels-can-be-updated"></a>Возможность обновления автоматически назначаемых меток

Автоматически назначаемые метки можно обновлять с помощью новых политик в отношении меток или путем обновления существующих политик.

Убедитесь, что ваш план по внедрению меток предусматривает следующее:

- Определение приоритетного порядка создания политик автоматического применения.

- Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>Пример установки приоритета для создания политик автоматического применения

<table>
<thead>
<tr class="header">
<th align="left"><strong>Метки</strong></th>
<th align="left"><strong>Приоритетный порядок создания политик автоматического применения</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Отдел кадров — данные о сотрудниках</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">Данные клиента</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">Строго конфиденциально</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">Отдел кадров — данные о зарплате</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">Конфиденциально</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">Общедоступные</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">Персональные</td>
<td align="left">Без политики автоматического применения</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>Создание меток и политик их автоматического применения

Метки и политики создаются в Центре безопасности и соответствия требованиям.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Шаг</strong></th>
<th align="left"><strong>Описание</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Предоставление разрешений ответственным за обеспечение соответствия требованиям</p></td>
<td align="left"><p>Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</p>
<p>См. статью <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Предоставление пользователям доступа к Центру безопасности и/или Центру соответствия требованиям</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Создание меток хранения.</p></td>
<td align="left">Перейдите в раздел классификаций в Центре безопасности или Центре соответствия требованиям, выберите "Метки хранения" и создайте метки для вашей среды.</td>
</tr>
<tr class="odd">
<td align="left"><p>Создание политик автоматического применения меток</p></td>
<td align="left">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</td>
</tr>
</tbody>
</table>

Ни рисунке ниже показано, как создать автоматическую метку "Данные клиента".

![Создание и применение метки для данных клиента](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

На этом рисунке:

- Создается метка "Данные клиента".

- Перечисляются типы конфиденциальной информации для соблюдения регламента GDPR: "Внутренний идентификационный номер гражданина Бельгии", "Номер кредитной карты", "Номер идентификационной карты гражданина Хорватии", "Национальный идентификационный номер гражданина Финляндии".

- Создается политика автоматического применения, которая назначает метку "Данные клиента" всем файлам, включающим один из типов конфиденциальной информации, добавленных в политику.
