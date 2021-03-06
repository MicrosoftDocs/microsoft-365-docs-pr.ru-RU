---
title: Параметры взаимодействия между Microsoft 365 и SharePoint
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Узнайте о взаимодействии параметров между Microsoft 365 и SharePoint
ms.openlocfilehash: 23e9553ce07514b18bafada5c93bcadab19806fe
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538163"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Параметры взаимодействия между Microsoft 365 и SharePoint

Некоторые параметры Microsoft 365 групп и SharePoint в Microsoft 365, в частности связанные с совместной работой и созданием сайтов групп и групп, совпадают друг с другом. В этой статье описаны эти взаимодействия и передовая практика работы с этими настройками.

![Схема venn функций SharePoint, Yammer и групп](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Влияние параметров SharePoint для Microsoft 365 групп

|SharePoint|Описание|Влияние на Microsoft 365 групп|Рекомендация|
|:-----------------|:----------|:-----------------------------|:-------------|
|Внешний общий доступ для организации и сайта|Определяет, можно ли совместно использовать сайты, файлы и папки с людьми за пределами организации.|Если SharePoint и параметры групп не совпадают, гостям группы может быть заблокирован доступ к сайту, а также может быть доступен внешний доступ на сайте, но не в группе.|При изменении параметров общего доступа проверьте параметры групп и SharePoint параметров сайта для сайтов групп, подключенных к группе.<br><br>См. [совместное взаимодействие с гостями на сайте](./collaborate-in-site.md).|
|Домен разрешить/заблокировать|Позволяет или предотвращает общий доступ контента к указанным доменам.|Группы не распознают SharePoint или блокируют списки. Пользователи из доменов, не SharePoint могут получить доступ к SharePoint через группу.|Управление списками домена разрешить или блокировать для Azure AD и SharePoint вместе. Создание процесса управления на всей организации для допуска и блокировки доменов.<br><br>См. [SharePoint параметров домена](/sharepoint/restricted-domains-sharing) [и параметров домена Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Разрешить только пользователям из определенных групп безопасности предоставлять внешний общий доступ|Указывает группы безопасности, которые могут обмениваться сайтами, папками и файлами внешне.|Этот параметр не влияет на внешние группы общего доступа владельцев групп. Гости группы имеют доступ к связанному сайту SharePoint.||
|SharePoint параметров общего доступа к сайтам|Определяет, кто может делиться сайтом непосредственно за пределами членства в группе. Это настраивается группой или владельцем сайта.|Этот параметр не влияет на группу напрямую, но может разрешить пользователям добавляться на сайт и не иметь доступа к другим групповым ресурсам|Рассмотрите возможность использования этого параметра для ограничения прямого доступа к сайту и управления доступом к сайту через группу.|
|Позвольте пользователям создавать сайты со SharePoint и OneDrive|Указывает, могут ли пользователи создавать новые SharePoint сайты.|Если этот параметр отключен, пользователи по-прежнему могут создавать сайты групп, подключенные к группе, создав группу.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Влияние параметров Microsoft 365 групп на SharePoint

|Microsoft 365 групп|Описание|Влияние на SharePoint|Рекомендация|
|:---------------------------|:----------|:-------------------|:-------------|
|Политики именования|Указывает префиксы и суффиксы имен группы и заблокированные слова для создания группы|Политики применяются для пользователей, создав сайты групп, связанных с группой, но не сайты связи или сайты с другими шаблонами.|Создайте отдельные рекомендации по именоведению для сайтов связи, если это необходимо.|
|Доступ к группе гостей|Указывает, можно ли добавлять в группы людей за пределами организации.|Если SharePoint и параметры групп не совпадают, гостям группы может быть заблокирован доступ к сайту, а также может быть доступен внешний доступ на сайте, но не в группе.|При изменении параметров общего доступа проверьте параметры групп и SharePoint параметров сайта для сайтов групп, подключенных к группе.<br><br>См. [совместное взаимодействие с гостями на сайте](./collaborate-in-site.md)|
|Создание группы группой безопасности|Группы могут создаваться только членами определенной группы безопасности.|Пользователи, которые не являются членами группы безопасности, не смогут создать сайт группы, подключенный к группе.|Убедитесь, что процесс запроса группы включает инструкции по запросу сайта.|
|Политика истечения срока действия группы|Указывает период времени, после которого группы, которые не активно используются, будут автоматически удалены.|При удалении группы также удаляется связанный SharePoint сайт. Контент, защищенный политиками хранения, сохраняется.|Используйте политики истечения срока действия, чтобы избежать разрастания неиспользваемой группы и сайтов.|

## <a name="related-topics"></a>Статьи по теме

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Совместная работа с людьми, находящимися за пределами организации](./collaborate-with-people-outside-your-organization.md)

[Управление созданием сайтов в SharePoint](/sharepoint/manage-site-creation)