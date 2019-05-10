---
title: Автоматическая установка и удаление Office на устройствах с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Установка или удаление Office на устройствах с Windows 10 из центра администрирования Microsoft 365 бизнес. '
ms.openlocfilehash: 94e5761b516c150caa11048be73d97f468b09fb5
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660613"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Автоматическая установка и удаление Office на устройствах с Windows 10

![Баннер, который указывает https://aka.ms/aboutM365previewна.](media/m365admincenterchanging.png)

Из центра администрирования Office 365 бизнес вы можете легко и быстро установить Office на компьютерах с Windows 10.
  
Прежде чем начать, прочитайте статью [Подготовка к установке Office для клиентов](prepare-for-office-client-deployment.md), чтобы понять, как это работает с ранее установленными приложениями Office. 
  
## <a name="manage-office-deployments"></a>Управление развертываниями Office

1. Войдите в [центр администрирования](https://aka.ms/bcsportal) с учетными данными глобального администратора. 
    
2. На карточке **Устройства** выберите **Управление развертыванием Office**.
      Если вы не видите карточки **действий устройства** , на **домашней** странице центра администрирования нажмите **добавить** (+), чтобы добавить ее на домашнюю страницу администрирования.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. На панели **Управление развертыванием Office** нажмите кнопку **Добавить группу** и выберите группы, которые хотите использовать.
    
4. Выбрав группу или группы, в раскрывающемся списке **Действие развертывания** выберите одно из действий: **Установить Office как можно быстрее** или **Удалить Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Choose **Next** \> review the settings and then choose **Confirm**.
    
32-разрядная версия Office будет автоматически установлена на устройствах пользователей, входящих в указанные вами группы, или удалена с них.
  
Для проверки откройте диспетчер задач на компьютере, выбранном для установки Office, и найдите процесс "Microsoft Office нажми и работай".
  


