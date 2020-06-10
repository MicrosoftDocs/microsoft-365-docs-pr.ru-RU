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
ms.openlocfilehash: e9b1fadd3e9e6dab337a0c3ded380c5c49f53bab
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678674"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Безопасные документы в Office 365 Advanced Threat Protection

Безопасные документы — это функция в Office 365 Advanced Threat protection (Office 365 ATP), использующая [Advanced Threat Protection в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для сканирования документов и файлов, открытых в [режиме защищенного просмотра](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Эта функция доступна только пользователям, у которых есть лицензия на систему безопасности Microsoft 365 и Microsoft 365.

- Безопасные документы в настоящее время доступны для общедоступной предварительной версии, доступной пользователям, которые входят в состав [программы предварительной оценки Office](https://insider.office.com/en-us/join) на текущем канале (Предварительная версия) с office версии 2002 (12527,20092) или выше. Эта функция отключена по умолчанию и должна быть включена администратором безопасности.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Перед выполнением процедур, описанных в этом разделе, необходимо назначить разрешения. Чтобы включить и настроить безопасные документы, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ". Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>Как Майкрософт обрабатывает ваши данные?

Чтобы защититься от вирусов, безопасные документы отправляют файлы в облако [Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для анализа.

- Сведения о том, как служба защитника (Advanced Thread Protection) отвечает [за поиск данных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- В дополнение к рекомендациям, описанным выше, файлы, отправленные безопасными документами, не сохраняются в защитнике за пределами времени, необходимого для анализа, что обычно составляет менее 24 часов.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Использование центра безопасности & соответствия требованиям для настройки безопасных документов

1. Откройте центр соответствия требованиям по безопасности & по адресу <https://protection.office.com> .

2. Перейдите к разделу политика **управления угрозой** \> **Policy** \> **безопасные вложения ATP**.

3. В разделе **Помогите людям безопасно оставаться безопасными, когда вы доверяете файлу для открытия раздела "защищенный просмотр в приложениях Office** ", настройте один из следующих параметров:

   - **Включение безопасных документов для клиентов Office (файлы также будут отправляться в облако Майкрософт для глубокого анализа)**

   - **Разрешить пользователям щелкать в режиме защищенного просмотра, даже если документы распознает файл как вредоносный**: не рекомендуется включать этот параметр.

4. По завершении нажмите кнопку **Сохранить**.

![Страница безопасных вложений ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Настройка безопасных документов с помощью Exchange Online PowerShell или отдельного EOP PowerShell

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

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Как проверить, что это работает?

Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.

- В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** для \> **Policy** \> **безопасных вложений ATP**и убедитесь, что параметры, выбранные в **справке, остаются безопасными при доверии файлу для открытия в разделе "защищенный просмотр в приложениях Office** ".

- Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
