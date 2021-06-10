---
title: Microsoft Teams
description: Как Teams устанавливается на устройствах и обновляется впоследствии
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, приложения LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920660"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) приложение для обмена сообщениями для организации, которое также предоставляет рабочее пространство для совместной работы и общения в режиме реального времени, собраний, обмена файлами и приложениями.

## <a name="initial-deployment"></a>Начальное развертывание

Большинство поставщиков оборудования еще не включают Teams в свои изображения, поэтому компьютеры, управляемые Майкрософт развертывает Teams устройства с помощью Microsoft Intune. На всех управляемых [устройствах установлен Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) пакет, что позволяет всем пользователям, входивших на устройство Microsoft Teams быть готовыми к использованию. После первого завершения установки пакета Teams автоматически запускается и добавляет ярлык на рабочий стол.

### <a name="microsoft-intune-changes"></a>Microsoft Intune изменения

компьютеры, управляемые Майкрософт добавляет два приложения в организацию Azure AD для Microsoft Teams. Они развертываются для 64-битных или 32-битных клиентов, соответствующих устройству:  

- Современное рабочее место — Teams установки для компьютеров x64  
- Современное рабочее место — Teams установки для компьютеров x32

## <a name="updates"></a>Обновления

Teams следует отдельному пути обновления от Приложения Microsoft 365 для предприятий и клиент настольных компьютеров обновляется автоматически. Teams проверяет обновления каждые несколько часов, скачивает их, а затем ждет, пока компьютер не будет простаивать, прежде чем безмолвно установить обновление.  

Группа Teams не позволяет администраторам управлять обновлениями, поэтому компьютеры, управляемые Майкрософт использует стандартный канал [автоматического обновления.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Ручное обновление Teams

Отдельные пользователи также могут скачивать обновления, выбрав **пункт Проверка** обновлений в выпадаемом меню Profile в правом верхнем    ****   справа от приложения. Если обновление доступно, оно будет скачивано и тихо установлено, когда компьютер простаивает.

## <a name="delivery-optimization-of-updates"></a>Оптимизация доставки обновлений

Оптимизация доставки для Teams обновлений включена по умолчанию и не требует действий от администраторов или пользователей.