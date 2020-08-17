---
title: Параметры взаимодействия между группами Microsoft 365, Teams и SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Сведения о взаимодействии параметров между группами Microsoft 365, Teams и SharePoint
ms.openlocfilehash: 3ad5011c2d7b4579e054b014237d5771049b3c91
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662799"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Параметры взаимодействия между группами Microsoft 365, Teams и SharePoint

Некоторые параметры для групп Microsoft 365, Microsoft Teams и SharePoint в Microsoft 365, особенно связанных с совместным использованием и объединением групп и групп, а также создания сайтов SharePoint, перекрывают друг друга. В этой статье приводятся описания этих взаимодействий и рекомендации по работе с этими параметрами.

![Диаграмма Венна компонентов SharePoint, Teams и Groups](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Влияние параметров SharePoint на группы и команды

|Параметр SharePoint|Описание|Влияют на группы и Teams Microsoft 365|Рекомендация|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Внешний общий доступ для Организации и сайта|Определяет, можно ли предоставлять доступ к сайтам, файлам и папкам пользователям, не входящим в эту организацию.|Если параметры SharePoint, группы и Teams не совпадают, гости в команде могут блокировать доступ к сайту или может произойти непредвиденный внешний доступ.|При изменении параметров общего доступа, проверьте параметры групп, параметры Teams и параметры сайта SharePoint для сайтов групп, подключенных к группам.<br><br> Просмотр [совместной работе с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Разрешить или запретить домен|Разрешает или запрещает доступ к контенту с указанными доменами.|Группы и Teams не распознают списки разрешенных и запрещенных SharePoint. Пользователи из доменов, запрещенных в SharePoint, могут получить доступ к сайтам и контенту SharePoint с помощью команды.|Управление списками разрешенных и запрещенных доменов для Azure AD и SharePoint. Создайте процесс управления на уровне Организации, чтобы разрешить и блокировать домены.<br><br>Просмотр [параметров домена SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) и [параметров домена Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Разрешить доступ к внешним данным только пользователям из определенных групп безопасности|Задает группы безопасности, которые могут использовать внешние сайты, папки и файлы SharePoint.|Этот параметр не запрещает владельцам команд извне предоставлять доступ к Teams. Группы гостей имеют доступ к связанному сайту SharePoint.||
|Параметры общего доступа к сайту SharePoint|Определяет, кто может предоставлять доступ к сайту напрямую за преличное членство в группе. Эта настройка настраивается владельцем группы или сайта.|Этот параметр не влияет на команду непосредственно, но позволяет добавлять пользователей на сайт и не иметь доступ к самой группе или другим ресурсам Teams.|Рекомендуется использовать этот параметр, чтобы ограничить общий доступ к сайту напрямую и управлять доступом к сайту с помощью команды.|
|Разрешите пользователям создавать сайты на начальной странице SharePoint и OneDrive|Указывает, могут ли пользователи создавать новые сайты SharePoint.|Если этот параметр отключен, пользователи могут по-прежнему создавать сайты групп, подключенных к группам, путем создания команды.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Влияние параметров групп в Teams

|Параметр Microsoft 365 Groups|Описание|Влиянии на Teams|Рекомендация|
|:---------------------------|:----------|:--------------|:-------------|
|Политики именования|Указывает префиксы имен групп и суффиксы, а заблокированные слова для создания группы|Политики применяются для пользователей, создающих Teams.||
|Гостевой доступ к группе|Указывает, можно ли добавлять в группы людей за прев Организации.|Если параметры общего доступа к гостевым учетным данным отключены, команда не может быть предоставлена гостям.|При изменении параметров общего доступа для гостей Проверьте параметры для Teams, групп и сайта SharePoint, связанного с командой.<br><br> Просмотр [совместной работе с гостями в команде](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Создание групп по группам безопасности|Группы могут создавать только участники определенной группы безопасности.|Пользователи, не являющиеся участниками группы безопасности, не смогут создавать команды.|Убедитесь, что процесс запроса группы содержит инструкции по запросу группы или сайта SharePoint.|
|Политика истечения срока действия групп|Задает период времени, по истечении которого неактивно используемые группы будут автоматически удалены.|При удалении группы также удаляются группа и связанный сайт SharePoint. Сохраняется содержимое, защищенное политиками хранения.|Используйте политики истечения срока действия, чтобы избежать растянутости неиспользуемых команд, групп и сайтов.|

## <a name="related-topics"></a>Связанные статьи

[Совместное работа с людьми за прев Организации](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Управление созданием сайтов в SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)