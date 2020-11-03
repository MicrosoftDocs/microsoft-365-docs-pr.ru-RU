---
title: Безопасные документы в защитнике Майкрософт для Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Сведения о надежных документах в Microsoft 365 и Microsoft 365 для обеспечения безопасности.
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845484"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Безопасные документы в Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Безопасные документы — это функция Microsoft 365, а также безопасность Microsoft 365, которая использует [защитник Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для сканирования документов и файлов, которые открываются в [режиме защищенного просмотра](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Безопасные документы доступны только пользователям, у которых есть лицензии на системы безопасности *microsoft 365* и *Microsoft 365* . Эти лицензии не включены в планах Microsoft Defender для Office 365.

- Безопасные документы поддерживаются в приложениях Microsoft 365 для предприятий (прежнее название — Office 365 профессиональный плюс) версии 2004 или более поздней.

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>. Чтобы перейти непосредственно к странице **безопасных вложений ATP** , откройте <https://protection.office.com/safeattachmentv2> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Перед выполнением процедур, описанных в этом разделе, необходимо назначить разрешения. Чтобы включить и настроить безопасные документы, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ". Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

### <a name="how-does-microsoft-handle-your-data"></a>Как Майкрософт обрабатывает ваши данные?

Чтобы защитить паролем, безопасные документы отправляют файлы в [защитник Майкрософт для](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) облачного облака для анализа. Сведения о том, как защитник Майкрософт для обработки конечных точек ваши данные можно найти здесь: [защитник Майкрософт для хранения и конфиденциальности данных конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Файлы, отправленные безопасными документами, не поддерживаются в защитнике за пределами времени, необходимого для анализа (как правило, меньше 24 часов).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Использование центра безопасности & соответствия требованиям для настройки безопасных документов

1. В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** \> **Policy** \> **ATP: безопасные вложения** , а затем щелкните **глобальные параметры**.

2. В открывшемся окне **глобальные параметры** настройте указанные ниже параметры.

   - **Включите безопасные документы для клиентов Office** : установите переключатель вправо, чтобы включить компонент: включен ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Разрешить пользователям переход по защищенному просмотру даже в том случае, если безопасные документы определяют файл как вредоносный** : Мы рекомендуем оставить этот параметр отключенным (не устанавливая флажок слева: выключено ![ ](../../media/scc-toggle-off.png) ).

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

   ![Параметры безопасных документов после выбора глобальных параметров на странице безопасные вложения.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Настройка безопасных документов с помощью Exchange Online PowerShell

Используйте указанный ниже синтаксис.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
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

- В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** \> **Policy** \> **ATP: безопасные вложения** , щелкните **глобальные параметры** и проверьте, **включены ли безопасные документы для клиентов Office** , и **разрешите пользователям перейти по защищенному просмотру даже в том случае, если они идентифицируют файл как вредоносные** параметры.

- Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Ниже приведены файлы, которые можно использовать для тестирования безопасности защищенных документов. Эти документы аналогичны файлу EICAR.TXT для тестирования антивредоносных и антивирусных решений. Файлы не являются вредоносными, но они активируют безопасную защиту документов.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
