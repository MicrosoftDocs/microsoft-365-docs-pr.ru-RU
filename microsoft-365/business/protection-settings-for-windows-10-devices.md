---
title: Изменение или настройка параметров защиты приложений для устройств с Windows 10
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
description: Узнайте, как создавать или изменять политики управления приложениями и защищать рабочие файлы на личных устройствах пользователей с Windows 10.
ms.openlocfilehash: f85a59649e43c141b62091337b842a490d411833
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289206"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Установка или изменение параметров защиты приложений для устройств с Windows 10

Эта статья относится к Microsoft 365 бизнес премиум.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Изменение политики управления приложениями для Windows 10

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. On the left nav, choose **Devices** \> **Policies** .
1. Выберите существующую политику приложений для Windows, а затем **редактирование.**
1. Choose **Edit** next to a setting you want to change and then **Save**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Создание политики управления приложениями для Windows 10

Если у ваших пользователей есть личные устройства с Windows 10, используемые для выполнения рабочих задач, на этих устройствах также можно настроить защиту данных компании.
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. On the left nav, choose **Devices** \> **Policies** \> **Add**.
3. На панели **Добавить политику** введите уникальное имя политики. 
4. В поле **Тип политики** выберите **Управление приложениями для Windows 10**.
5. В **области "Тип устройства"** выберите **"Личное"** или **"Принадлежит компании".**
6. Параметр **Шифровать рабочие файлы** включается автоматически. 
7. Если вы не хотите, чтобы пользователи сохраняли рабочие файлы на компьютере, **включите** параметр **Запретить копирование данных компании в личные файлы и обязать хранить рабочие файлы в OneDrive для бизнеса**. 
9. Раз **развернуть данные восстановления на устройствах с Windows.** Мы рекомендуем включить **его.**
    Прежде чем перейдите к расположению сертификата агента восстановления данных, необходимо создать его. Инструкции см. в инструкциях по созданию и проверке сертификата агента восстановления данных (DRA) шифрованой файловой системы [(EFS).](https://go.microsoft.com/fwlink/p/?linkid=853700)
    
    По умолчанию рабочие файлы шифруются с помощью секретного ключа, хранящегося на устройстве и связанного с профилем пользователя. Открыть и расшифровать файл может только пользователь. Однако в случае потери устройства или удаления пользователя файл может остаться в зашифрованном виде. Администратор может использовать сертификат агента восстановления данных (DRA) для расшифровки файла.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Если **вы** хотите добавить дополнительные домены или расположения SharePoint Online, чтобы убедиться, что файлы во всех перечисленных приложениях защищены, разоширите раздел "Защита дополнительных сетевых и облачных местоположений". Если в каком-либо поле вам нужно ввести несколько элементов, разделяйте их точкой с запятой (;).
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
12. Нажмите кнопку **Добавить**, чтобы сохранить политику и назначить ее устройствам. 
