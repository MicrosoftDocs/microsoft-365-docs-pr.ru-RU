---
title: Настройка параметров защиты приложений для устройств с Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как создать политику управления приложениями и защитить рабочие файлы на персональных устройствах Windows 10.
ms.openlocfilehash: c3e003205da30fa79069946960ef00e4195f0cbc
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44386544"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Настройка параметров защиты приложений для устройств с Windows 10

## <a name="create-an-app-management-policy-for-windows-10"></a>Создание политики управления приложениями для Windows 10

Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. В левой панели навигации выберите пункт **Devices** \> **политики** устройств \> **Добавить**.

3. На панели **Добавить политику** введите уникальное имя политики. 
    
4. В поле **Тип политики** выберите **Управление приложениями для Windows 10**.
    
5. В разделе **тип устройства**выберите **персональный** или **принадлежащий компании**.
    
6. Параметр **Шифровать рабочие файлы** включается автоматически. 
    
7. Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**. 
    
9. Разверните узел **Восстановление данных на устройствах с Windows**. Рекомендуем **включить его.**
    
    Прежде чем переходить к расположению сертификата агента восстановления данных, необходимо сначала создать его. Инструкции приведены в разделе [Создание и проверка сертификата агента восстановления шифрованной файловой системы (DRA](https://go.microsoft.com/fwlink/p/?linkid=853700)).
    
    По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Администратор может использовать сертификат агента восстановления данных (DRA) для расшифровки файла.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Разверните раздел **Защита дополнительных сетевых и облачных расположений** , если вы хотите добавить дополнительные домены или расположения SharePoint Online, чтобы обеспечить защиту файлов во всех перечисленных приложениях. Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
12. Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам. 
