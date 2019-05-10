---
title: Настройка параметров защиты приложений для устройств с Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Узнайте, как создать политику управления приложениями и защитить рабочие файлы на устройствах с Windows 10.
ms.openlocfilehash: f649454417dceae05255df6b37760af99c0b8d4f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660412"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Настройка параметров защиты приложений для устройств с Windows 10

## <a name="create-an-app-management-policy-for-windows-10"></a>Создание политики управления приложениями для Windows 10

Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.
  
1. Перейдите в центр администрирования по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. В левой панели навигации выберите пункт **** \> **политики** \> устройств **Добавить**.

3. На панели **Добавить политику** введите уникальное имя политики. 
    
4. В поле **Тип политики** выберите **Управление приложениями для Windows 10**.
    
5. В разделе **тип устройства**выберите **персональный** или **принадлежащий компании**.
    
6. Параметр **Шифровать рабочие файлы** включается автоматически. 
    
7. Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**. 
    
9. Разверните раздел **Восстановление данных на устройствах с Windows**. Рекомендуется его **включить**.
    
    Прежде чем выбирать сертификат агента восстановления данных, необходимо создать его. Инструкции см. в статье [Создание и проверка сертификата агента восстановления данных (DRA) шифрованной файловой системы (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Для расшифровки этого файла администратор может воспользоваться сертификатом агента восстановления данных.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Если вы хотите добавить еще домены или расположения SharePoint Online, чтобы защитить файлы во всех указанных приложениях, разверните параметр **Защитить дополнительные сетевые и облачные расположения**. Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
12. Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам. 