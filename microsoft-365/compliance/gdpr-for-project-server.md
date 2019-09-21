---
title: GDPR для Project Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Узнайте, как обеспечивать соблюдение требований GDPR в локальном развертывании Project Server.
ms.openlocfilehash: 8fb29c2d383c03c79d619d2c78df75cffb4eab27
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090191"
---
# <a name="gdpr-for-project-server"></a>GDPR для Project Server

Project Server использует специальные скрипты для экспорта и редактирования данных пользователя в Project Web App. Ниже описывается базовый процесс.

1.  Найдите сайты Project Web App в ферме.

2.  Найдите на каждом сайте проекты, содержащие данные пользователя.

3.  Экспортируйте и просмотрите нужные типы данных.

4.  Отредактируйте данные надлежащим образом.

Эти действия подробно рассматриваются в следующих статьях:

- [Экспорт данных пользователя из Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Удаление данных пользователя из Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Обратите внимание, что Project Server основан на SharePoint Server и регистрирует события в журналах ULS SharePoint и базе данных использования. Дополнительные сведения см. в статье [GDPR для SharePoint Server](gdpr-for-sharepoint-server.md).
