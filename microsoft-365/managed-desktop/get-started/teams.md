---
title: Microsoft Teams
description: Как Teams устанавливается на устройства и обновляется после этого
keywords: Microsoft Managed Desktop, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950943"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) обмена сообщениями для вашей организации, которое также предоставляет рабочее пространство для совместной работы и общения в режиме реального времени, собраний, общего доступа к файлам и приложениям.

## <a name="initial-deployment"></a>Начальное развертывание

Большинство поставщиков оборудования пока не включают Teams в свои образы, поэтому компьютеры, управляемые Майкрософт, развертывают Teams на ваших устройствах с помощью Microsoft Intune. На всех управляемых устройствах установлен пакет [Microsoft MSI Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) благодаря которому все пользователи, во время которых вход на устройство, готовы к использованию Microsoft Teams. После завершения установки пакета Teams автоматически запускается и добавляет ярлык на рабочий стол.

### <a name="microsoft-intune-changes"></a>Изменения Microsoft Intune

Компьютеры, управляемые Майкрософт, добавляют два приложения в организацию Azure AD для Microsoft Teams. Они развертываются в 64- или 32-битных клиентах, если это необходимо для устройства:  

- Современное рабочее место — teams Machine Wide Installer x64  
- Современное рабочее место — teams Machine Wide Installer x32

## <a name="updates"></a>Обновления

Teams следует отдельному пути обновления от приложений Microsoft 365 для предприятий, а клиент для настольных ПК обновляется автоматически. Teams проверяет наличие обновлений каждые несколько часов, скачивает их, а затем ждет, пока компьютер не будет в бездействии, прежде чем автоматически установить обновление.  

Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому на компьютере, управляемом Майкрософт, используется стандартный канал [автоматического обновления.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Обновление Teams вручную

Отдельные пользователи также могут скачивать обновления, выбрав пункт "Проверить обновления" в выпадаемом меню "Профиль" в верхней    правой части ****   приложения. Если обновление доступно, оно будет загружено и установлено автоматически, когда компьютер находится в простое.

## <a name="delivery-optimization-of-updates"></a>Оптимизация доставки обновлений

Оптимизация доставки для обновлений Teams включена по умолчанию и не требует действий от администраторов или пользователей. 