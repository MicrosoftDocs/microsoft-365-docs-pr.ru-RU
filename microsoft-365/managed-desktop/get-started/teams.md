---
title: Microsoft Teams
description: Как Microsoft Teams устанавливается на устройствах и обновляется позже
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, приложения, бизнес-приложения, бизнес-приложения
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

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для обмена сообщениями](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) , которое также предоставляет рабочую область для совместной работы и общения в реальном времени, собраний, собраний, а также совместного использования файлов и приложений.

## <a name="initial-deployment"></a>Начальное развертывание

Большинство производителей оборудования еще не включают в себя Teams в своих изображениях, поэтому управляемый Майкрософт Настольный компьютер развертывает Teams на своих устройствах с помощью Microsoft Intune. На всех управляемых устройствах установлен [пакет Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) , что гарантирует, что все пользователи, выполняющие вход на устройство, готовы к использованию Microsoft Teams. При первом завершении установки пакета Teams автоматически запускается и добавляется ярлык на Рабочий стол.

### <a name="microsoft-intune-changes"></a>Изменения в Microsoft Intune

Рабочий стол, управляемый Майкрософт, добавляет два приложения в организацию Azure AD для Microsoft Teams. Они разворачиваются как в 64, так и на клиентах 32, в соответствии с требованиями к устройству:  

- Современная Рабочая область — установщик на уровне компьютера для Teams x64  
- Современная Рабочая область — x32 установки для всего компьютера Teams

## <a name="updates"></a>Обновления

В Teams следует отдельный путь обновления от приложений Microsoft 365 для предприятий, а клиент для настольных ПК автоматически обновляется. Teams проверяет наличие обновлений каждые несколько часов, загружает их, а затем ждет, пока компьютер не простаивает, прежде чем устанавливать обновление автоматически.  

Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому для управляемого рабочего стола Майкрософт используется [стандартный канал автоматического обновления](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Ручное обновление Teams

Отдельные пользователи также могут скачивать обновления, выбрав пункт **проверить наличие обновлений**   в раскрывающемся меню **Профили**   в правом верхнем углу приложения. Если обновление доступно, оно будет загружено и автоматически установлено, когда компьютер простаивает.

## <a name="delivery-optimization-of-updates"></a>Оптимизация доставки обновлений

Оптимизация доставки для Teams включена по умолчанию и не требует никаких действий от администраторов и пользователей. 