---
title: 'Перенос файлов Google в Microsoft 365 для бизнеса '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как перенести файлы Google в Microsoft 365 для бизнеса с помощью Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928202"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Перенос файлов Google в Microsoft 365 для бизнеса 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

При переходе на Microsoft 365 для бизнеса вам необходимо перенести файлы с Google Drive. Вы можете использовать приложение Mover для перемещения файлов с персональных и общих дисков. Дополнительные сведения см. в сведениях [о миграции Mover Cloud](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover сделает копию файлов и переместит их в Microsoft 365 для бизнеса. Исходные файлы также останутся на дисках Google.

## <a name="before-you-start"></a>Перед началом работы

Все пользователи должны были в свои учетные записи в Microsoft 365 для бизнеса настроить OneDrive для бизнеса. Для этого перейдите в [office.com,](https://office.com)войдите с помощью учетных данных Microsft 365 для бизнеса и выберите OneDrive.

## <a name="try-it"></a>Проверьте, как это работает!

### <a name="install-mover"></a>Установка Mover

1. Во sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).

1. Choose **Apps**, **Google Workspace Marketplace apps**, Then Add app to Domain Install **list**.

1. Найщите Mover и выберите его.

1. Choose **Domain Install**, then **Continue**.

1. Просмотрите разрешения, выберите этот контрольный ящик, чтобы согласиться с условиями, а затем выберите "Разрешить", **"Далее"** и **"Готово".**

### <a name="create-connectors-and-run-the-migration"></a>Создание соединитеителей и запуск миграции

1. Вернись в **приложения Google Workspace Marketplace.**
1. Обновите браузер и выберите **приложение Mover.**
1. Прокрутите вниз и выберите ссылку универсальной навигации.
1. Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.
1. Измените **отображаемую именем,** если хотите, затем выберите **"Авторизировать".**
1. Выберите учетную запись администратора Google, просмотрите разрешения, а затем выберите **"Разрешить".**

    Mover отображает количество обнаруженных дисков группы и пользовательских дисков. 

1. В **области "Выбор назначения"** выберите **"Авторизовать новый соединители",**"Найти **Office 365"** и **"Авторизовать".**
1. Чтобы предоставить разрешения для приложения Mover в Azure Active Directory, перейдите [к](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth.
1. Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.
1. Выберите свою учетную запись, просмотрите разрешения и выберите **"Принять".**
1. Выберите **"Свойства"** и убедитесь, что назначение пользователя **обязательно?** Включено.
1. Вернись в приложение Mover, измените **отображаемую** именем , если вы хотите, выберите **Авторизировать**, а затем выберите учетную запись администратора Майкрософт.

    Mover сообщит вам о количестве обнаруженных сайтов SharePoint Online (или SPO) и пользователей.
1. Choose **Continue Migration Setup,** select **Add Users**, then **Automatically Discover and Add Users**.

    Приложение Mover попытается соединять диски из пути к источнику в Google с пунктом назначения в Microsoft 365. 

    Если диск не сопоает автоматически, добавьте его конечный путь в CSV-файл, который мы будем использовать позже для переноса общего диска в библиотеку документов SharePoint. 

1. В этом случае мы добавили сайт SharePoint с и названием "Перенесенные файлы" и занося url-адрес страницы документов. 
1. Затем мы создали CSV-файл в формате "Исходный путь", "Путь назначения" и "Теги". 

    Подробные сведения [см. в aka.ms/movercsv.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)

    При добавлении URL-адреса пути назначения удалите все после общих документов, например, этот полный URL-адрес не будет работать: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Замените его значением `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`.

1. Когда CSV-файл будет готов, выберите **"Действия** миграции", **"Добавить в** миграцию" и **"Выберите файл для отправки".**
1. Перейдите к CSV-файлу, выберите его, а затем выберите **"Открыть".**
1. Выберите диски пользователей, файлы которых нужно перенести, а затем выберите **"Начать миграцию пользователей".**
1. Просмотрите сведения о миграции, выберите время начала миграции, согласитесь с условиями и выберите **"Продолжить".**

Приложение Mover сообщит вам о том, что процесс миграции завершен.