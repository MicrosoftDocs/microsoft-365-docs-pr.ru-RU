---
title: Включение и отключение аудита
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Как включить или отключить функцию поиска журнала аудита в Центр соответствия требованиям Microsoft 365, чтобы включить или отключить возможность администраторов для поиска журнала аудита.
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341500"
---
# <a name="turn-auditing-on-or-off"></a>Включение и отключение аудита

По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный. При включенном Центр соответствия требованиям Microsoft 365 аудите действия пользователя и администратора вашей организации записывают в журнал аудита и сохраняются в течение 90 дней и до одного года в зависимости от лицензии, назначенной пользователям. Однако у вашей организации могут быть причины, по которой вы не хотите записывать и хранить данные журнала аудита. В этих случаях глобальный администратор может принять решение отключить аудит в Microsoft 365.

При настройке Microsoft 365 или Office 365 организации можно проверить состояние аудита для организации. Инструкции см. в разделе Проверка состояния аудита для [вашей](#verify-the-auditing-status-for-your-organization) организации в этой статье.

> [!IMPORTANT]
> Если вы отключите аудит в Microsoft 365, вы не можете использовать API Office 365 управления или Azure Sentinel для доступа к данным аудита для вашей организации. Отключение аудита, следуя шагам в этой статье, означает, что результаты не будут возвращены при поиске журнала аудита с помощью Центр соответствия требованиям Microsoft 365 или при запуске **cmdlet Search-UnifiedAuditLog** в Exchange Online PowerShell. Это также означает, что журналы аудита не будут доступны через API Office 365 управления или Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Прежде чем включить аудит или отключить

- Для того чтобы включить или отключить аудит в Exchange Online организации, необходимо Exchange Online роли Microsoft 365 журналов аудита. По умолчанию эта роль назначена группам ролей управления соответствием требованиям и организации на странице **Permissions** в центре администрирования Exchange. Глобальные администраторы в Microsoft 365 являются членами группы ролей управления организацией в Exchange Online.

    > [!NOTE]
    > Пользователям должны быть назначены разрешения в Exchange Online, чтобы включить или отключить аудит. Если назначить пользователям роль журналов  аудита на странице Разрешения в Центр соответствия требованиям Microsoft 365, они не смогут включить или отключить аудит. Это потому, что в основном cmdlet является Exchange Online PowerShell.

- Пошаговая инструкция по поиску журнала аудита см. в [журнале Поиска аудита.](search-the-audit-log-in-security-and-compliance.md) Дополнительные сведения об API Microsoft 365 управления см. в Microsoft 365 [API](/office/office-365-management-api/get-started-with-office-365-management-apis)управления.

## <a name="verify-the-auditing-status-for-your-organization"></a>Проверка состояния аудита для организации

Чтобы убедиться, что аудит включен для организации, можно выполнить следующую команду в [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

Значение свойства `True`  _UnifiedAuditLogIngestionEnabled_ указывает, что аудит включен. Значение `False` указывает, что аудит не включен.

## <a name="turn-on-auditing"></a>Включи аудит

Если аудит не включен для организации, его можно включить в Центр соответствия требованиям Microsoft 365 или с помощью Exchange Online PowerShell. Может потребоваться несколько часов после того, как вы включит аудит, прежде чем вы сможете возвращать результаты при поиске журнала аудита.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Используйте центр соответствия требованиям, чтобы включить аудит

1. Перейдите на <https://compliance.microsoft.com> и войдите.

2. В левой области навигации Центр соответствия требованиям Microsoft 365 нажмите **кнопку Аудит**.

   Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.

   ![Баннер на странице Аудит](../media/AuditingBanner.png)

3. Нажмите **кнопку Начните запись пользователя и баннера действий администратора.**

   На то, чтобы изменение вступает в силу, может потребоваться до 60 минут.

### <a name="use-powershell-to-turn-on-auditing"></a>Чтобы включить аудит, используйте PowerShell

1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите следующую команду PowerShell, чтобы включить аудит.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Отображается сообщение о том, что для в действие изменения может потребоваться до 60 минут.
  
## <a name="turn-off-auditing"></a>Отключение аудита

Чтобы отключить аудит Exchange Online PowerShell, необходимо использовать Exchange Online PowerShell.
  
1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите следующую команду PowerShell, чтобы отключить аудит.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Через некоторое время убедитесь, что аудит отключен (отключен). Это можно сделать двумя способами:

    - В Exchange Online PowerShell запустите следующую команду:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Значение свойства  `False`  _UnifiedAuditLogIngestionEnabled_ указывает на отключение аудита.

    - Перейдите на **страницу Аудит** в Центр соответствия требованиям Microsoft 365.

      Если аудит не включен для вашей организации, отображается баннер, в результате чего начинается запись действий пользователя и администратора.
