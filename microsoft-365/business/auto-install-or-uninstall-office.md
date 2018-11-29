---
title: Автоматическая установка и удаление Office на устройствах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Установка и удаление Office на устройствах Windows 10 из центра администрирования Microsoft 365 для бизнеса. '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870867"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Автоматическая установка и удаление Office на устройствах с Windows 10

Из центра администрирования Office 365 бизнес вы можете легко и быстро установить Office на компьютерах с Windows 10.
  
Прежде чем начать, прочитайте статью [Подготовка к установке Office для клиентов](prepare-for-office-client-deployment.md), чтобы понять, как это работает с ранее установленными приложениями Office. 
  
## <a name="manage-office-deployments"></a>Управление развертываниями Office

1. Войдите в [центр администрирования](https://aka.ms/bcsportal) с учетными данными глобального администратора. 
    
2. В карточке **устройств** выберите команду **Управление развертывания Office**.    Если карточке **действия устройства** не отображаются на **домашней** странице центра администрирования нажмите кнопку **Add** (+) для добавления к домашней администрирования.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. На панели **Управление развертыванием Office** нажмите кнопку **Добавить группу** и выберите группы, которые хотите использовать.
    
4. Выбрав группу или группы, в раскрывающемся списке **Действие развертывания** выберите одно из действий: **Установить Office как можно быстрее** или **Удалить Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Нажмите кнопку **Далее** \> просмотрите параметры и затем выберите **Подтверждение**.
    
32-разрядная версия Office будет автоматически установлена на устройствах пользователей, входящих в указанные вами группы, или удалена с них.
  
Для проверки откройте диспетчер задач на компьютере, выбранном для установки Office, и найдите процесс "Microsoft Office нажми и работай".
  


