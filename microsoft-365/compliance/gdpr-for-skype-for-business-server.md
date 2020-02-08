---
title: GDPR для Skype для бизнеса Server
description: Узнайте, как обеспечивать соблюдение требований GDPR в локальном развертывании Skype для бизнеса Server и Lync Server.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: aa0d66bcf727b7dd3c545384ec3a4838667a9183
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596406"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a>GDPR для Skype для бизнеса Server и Lync Server

Большая часть данных Skype для бизнеса Server и Lync Server хранится в Exchange Server. К этим данным относятся:

-   журнал бесед;

-   уведомления и записи голосовой почты;

-   приглашения на собрания.

Используйте процедуры, описанные в статье [GDPR для Exchange Server](gdpr-for-exchange-server.md), чтобы находить, экспортировать и удалять эти данные по запросам GDPR.

Списки контактов хранятся в базе данных SQL Server. Их можно экспортировать следующими способами:

-   Пользователи могут самостоятельно экспортировать контакты, щелкнув правой кнопкой мыши заголовок группы и выбрав команду "Копировать". При этом все контакты из этой группы будут скопированы в буфер обмена, после чего их можно будет вставить в любом приложении.

-   Вы можете экспортировать эти данные с помощью командлета [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata).

Контент, отправленный (файлы или раздаточные материалы PowerPoint) или созданный (доска, опросы или ответы на вопросы) на собрании хранится в систематизаторе. Его также можно экспортировать, если пользователь снова войдет в собрание, срок действия которого еще не истек, и скачает отправленный контент или сделает снимки экрана (в случае созданного контента).

Собрания MeetNow, не занесенные в Календарь Exchange и список контактов, а также права контактов (родственники, сотрудники и т. д.) хранятся в базе данных пользователей. В Lync Server 2013 и более поздних версий эти данные можно экспортировать с помощью командлета [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata).
