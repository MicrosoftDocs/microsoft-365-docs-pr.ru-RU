---
title: Изменение или установка параметров защиты приложений для Windows 10 устройств
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Узнайте, как создавать или изменять политики управления приложениями и защищать рабочие файлы на личных Windows 10 устройствах.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580021"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Установка или изменение параметров защиты приложений для Windows 10 устройств

Эта статья применима к Microsoft 365 бизнес премиум.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Изменение политики управления приложениями для Windows 10

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Слева от nav выберите **политики** \> **устройств.**
1. Выберите существующую политику Windows приложения, а затем **изменить**.
1. Выберите **Изменить** рядом с параметром, который необходимо изменить, а затем **сохранить**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Создание политики управления приложениями для Windows 10

Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. В левом окантове выберите **Политики устройств** \>  \> **Добавить**.
3. На панели **Добавить политику** введите уникальное имя политики. 
4. В поле **Тип политики** выберите **Управление приложениями для Windows 10**.
5. В **соответствии с типом** устройства выберите **личный** или **собственный.**
6. Параметр **Шифровать рабочие файлы** включается автоматически. 
7. Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**. 
9. Расширение **данных восстановления на Windows устройствах.** Рекомендуется включить **его.**
    Прежде чем просмотреть расположение сертификата агента восстановления данных, сначала необходимо создать его. Инструкции см. в справке Создание и проверка сертификата агента восстановления данных [(DRA) системы шифрования файлов (EFS).](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)
    
    По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Администратор может использовать сертификат агента восстановления данных (DRA) для расшифровки файла.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. **Расширите** защиту дополнительных сетевых и облачных местоположений, если вы хотите добавить дополнительные домены или SharePoint в Интернете, чтобы убедиться, что файлы во всех перечисленных приложениях защищены. Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
12. Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам.