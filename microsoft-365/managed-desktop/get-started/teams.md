---
title: Microsoft Teams
description: Как Teams устанавливается на устройствах и обновляется после этого
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
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

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) — это [приложение для](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) обмена сообщениями для организации, которое также предоставляет рабочее пространство для совместной работы и общения в режиме реального времени, собраний, обмена файлами и приложениями.

## <a name="initial-deployment"></a>Начальное развертывание

Большинство поставщиков оборудования еще не включают Teams в свои изображения, поэтому Microsoft Managed Desktop развертывает Teams на устройствах с помощью Microsoft Intune. На всех управляемых устройствах установлен [пакет Teams.msi,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) обеспечивающий готовность всех пользователей, входивших на устройство, к использованию Microsoft Teams. После первого завершения установки пакета Teams автоматически запускает и добавляет ярлык на рабочий стол.

### <a name="microsoft-intune-changes"></a>Изменения Microsoft Intune

Microsoft Managed Desktop добавляет два приложения в организацию Azure AD для Microsoft Teams. Они развертываются для 64-битных или 32-битных клиентов, соответствующих устройству:  

- Modern Workplace — Teams Machine Wide Installer x64  
- Modern Workplace — Teams Machine Wide Installer x32

## <a name="updates"></a>Обновления

Teams следует отдельному пути обновления от Microsoft 365 Apps для предприятия, и клиент настольных компьютеров обновляется автоматически. Команды проверяют обновления каждые несколько часов, загружают их, а затем ждут, пока компьютер не будет простаивать, прежде чем безмолвно установить обновление.  

Группа продуктов Teams не позволяет администраторам управлять обновлениями, поэтому Microsoft Managed Desktop использует стандартный канал [автоматического обновления.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Ручное обновление Teams

Отдельные пользователи также могут скачивать обновления, выбрав **пункт Проверка** обновлений в выпадаемом меню Profile в правом верхнем    ****   справа от приложения. Если обновление доступно, оно будет скачивано и тихо установлено, когда компьютер простаивает.

## <a name="delivery-optimization-of-updates"></a>Оптимизация доставки обновлений

Оптимизация доставки обновлений Teams включена по умолчанию и не требует действий от администраторов или пользователей.