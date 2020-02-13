---
title: Безопасные документы в Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Сведения о безопасных документах в Office 365 ATP.
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960361"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Безопасные документы в Office 365 Advanced Threat protection

Безопасные документы — это функция в Office 365 Advanced Threat protection (ATP), использующая [Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для сканирования документов и файлов, которые открываются в [режиме защищенного просмотра](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

- Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Чтобы подключиться к Exchange Online Protection PowerShell, ознакомьтесь [со статьей подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Перед выполнением процедур, описанных в этом разделе, необходимо назначить разрешения. Чтобы включить и настроить безопасные документы, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ". Дополнительные сведения о группах ролей в центре безопасности & соответствия требованиям приведены в статье [разрешения в центре безопасности & Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Использование центра безопасности Office 365 & соответствия требованиям для настройки безопасных документов

1. Откройте центр соответствия требованиям & безопасности Office 365 по <https://protection.office.com>адресу.

2. Перейдите к разделу \> **Политика** \> **управления угрозой** **безопасные вложения ATP**.

3. В разделе **Помогите людям безопасно оставаться безопасными, когда вы доверяете файлу для открытия раздела "защищенный просмотр в приложениях Office** ", настройте один из следующих параметров:

   - **Включение безопасных документов для клиентов Office (файлы также будут отправляться в облако Майкрософт для глубокого анализа)**

   - **Разрешить пользователям щелкать в режиме защищенного просмотра, даже если документы распознает файл как вредоносный**: не рекомендуется включать этот параметр.

4. Когда закончите, нажмите кнопку **Сохранить**.

![Страница безопасных вложений ATP](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Настройка безопасных документов с помощью Exchange Online PowerShell или Exchange Online Protection PowerShell

Используйте следующий синтаксис:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- Параметр _енаблесафедокс_ включает или отключает безопасные документы для всей Организации.

- Параметр _алловсафедоксопен_ разрешает или запрещает пользователям оставлять защищенный просмотр (то есть открывать документ), если документ был определен как вредоносный.

В этом примере показано, как включить безопасные документы для всей Организации и запретить пользователям открывать документы, которые были определены как вредоносные из защищенного просмотра.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Как проверить, что это работает?

Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.

- В центре безопасности & соответствия требованиям перейдите к разделу \> **Политика** \> **управления угрозами** для **безопасных вложений ATP**и убедитесь, что параметры, выбранные в **справке, остаются безопасными при доверии файлу для открытия в разделе "защищенный просмотр в приложениях Office** ".

- Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
