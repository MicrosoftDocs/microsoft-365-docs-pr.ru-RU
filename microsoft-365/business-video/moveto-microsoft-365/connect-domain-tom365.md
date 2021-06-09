---
title: Подключение домена к Microsoft 365
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
description: Узнайте, как подключить домен к Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925114"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Подключение домена Microsoft 365 для бизнеса

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

После того как вы настроите Microsoft 365 и переместите данные электронной почты из Рабочей области Google, вы можете подключить домен к Microsoft 365. 

Сначала вам потребуется удалить существующие записи DNS из Google, затем мы можем добавить новые записи DNS из Microsoft 365.

## <a name="try-it"></a>Проверьте, как это работает!

1. Вопишитесь в консоль администратора Google Workspace в [admin.google.com](https://admin.google.com).
1. Выберите **домены,** **управление доменами,** **просмотр сведений,** **управление доменом,** **затем DNS** в левом nav.
1. Прокрутите вниз **до синтетических записей,** откройте рабочее пространство **Google,** выберите **Удалить**, а затем **удалить** снова.
1. Прокрутите вниз **до пользовательских** записей ресурсов и удалите все существующие записи DNS, которые отображаются, включая все, которые вы могли создать ранее для Microsoft 365.
1. Перейдите в [центр Microsoft 365 администрирования.](https://admin.microsoft.com)
1. В левом nav выберите, **Показать все**, **Параметры**, **Домены**.
1. Затем выберите домен по умолчанию.
1. Выберите **продолжить настройку,** затем, чтобы подключить домен, выберите  **Продолжить**.
1. Прокрутите вниз, чтобы просмотреть записи DNS, которые необходимо скопировать в Google.
1. Откройте **записи MX** и в соответствии с **пунктами** адрес или значение , скопируйте запись.
1. Вернись в Google и в разделе **Пользовательские** записи ресурсов откройте падение типа записи и выберите **MX**.
1. В поле **Данные** вклеить скопированную запись.
1. Затем нажмите **Добавить**.
1. Повторите процесс записей CNAME и TXT и добавьте значения на странице управления DNS Google.
1. Вернись в центр администрирования Microsoft 365 и выберите **Продолжить**.

    Настройка домена завершена.