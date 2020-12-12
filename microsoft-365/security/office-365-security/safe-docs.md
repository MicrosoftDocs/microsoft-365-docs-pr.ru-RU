---
title: Безопасные документы в Microsoft Defender для Office 365
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
description: Узнайте о безопасных документах в Microsoft 365 E5 или Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659877"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Безопасные документы в Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5 Security, которая использует [Microsoft Defender для](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) конечной точки для сканирования документов и файлов, открытых в защищеном представлении. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Безопасные документы доступны только пользователям с лицензиями *microsoft 365 E5* или *Microsoft 365 E5 Security.* Эти лицензии не включены в планы Microsoft Defender для Office 365.

- Безопасные документы поддерживаются в приложениях Microsoft 365 для предприятий (прежнее название — Office 365 профессиональныйplus) версии 2004 или более поздней.

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>. Чтобы перейти непосредственно на страницу безопасных **вложений ATP,** откройте <https://protection.office.com/safeattachmentv2> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:
  - Чтобы настроить параметры безопасных документов, необходимо быть  членом группы ролей "Управление организацией" или "Администратор **безопасности".**
  - Для доступа только для чтения к параметрам безопасных документов необходимо  быть членом группы ролей **"Глобальный** читатель" или "Читатель безопасности".

  Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

  **Примечания**.

  - Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.

### <a name="how-does-microsoft-handle-your-data"></a>Как Майкрософт обрабатывает ваши данные?

Чтобы защитить вас, служба "Безопасные документы" отправляет файлы в [облако Microsoft Defender для конечных](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) точек для анализа. Подробные сведения о том, как Microsoft Defender для конечной точки обрабатывает ваши данные, можно найти здесь: Microsoft Defender для хранения данных и конфиденциальности [конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Файлы, отправленные с помощью безопасных документов, не сохраняются в Защитнике после времени, необходимого для анализа (обычно менее 24 часов).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Использование Центра безопасности & соответствия требованиям для настройки безопасных документов

1. In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments,** and then click **Global settings**.

2. Во время **отлета "Глобальные** параметры" настройте следующие параметры:

   - **Включив функцию**"Безопасные документы" для клиентов Office: переместите выключаель вправо, чтобы включить функцию: ![ "Включить". ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

   - Разрешите пользователям переходить через защищенный просмотр, даже если "Безопасные документы" идентифицируют файл как вредоносный. Рекомендуется оставить этот параметр отключенным (оставьте этот параметр выключенным (оставьте этот параметр слева: "Отключить"). ![ ](../../media/scc-toggle-off.png)

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

   ![Параметры безопасных документов после выбора глобальных параметров на странице "Безопасные вложения".](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Настройка безопасных документов с помощью Exchange Online PowerShell

Используйте указанный ниже синтаксис.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Параметр _EnableSafeDocs_ включает или отключает безопасные документы для всей организации.
- Параметр _AllowSafeDocsOpen_ разрешает или предотвращает выход пользователей из защищенного просмотра (т. е. открытие документа), если документ был определен как вредоносный.

Этот пример включает безопасные документы для всей организации и предотвращает открытие пользователями документов, которые были определены как вредоносные, из защищенного просмотра.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>Как проверить, что это работает?

Чтобы убедиться, что вы включили и настроили безопасные документы, сделайте следующее:

- В Центре безопасности & соответствия требованиям  перейдите к политике управления угрозами "Безопасные вложения" \>  \> **ATP,**   щелкните "Глобальные параметры" и проверьте, включите ли безопасные документы для клиентов **Office** и разрешите пользователям щелкнуть "Защищенное представление", даже если "Безопасные документы" идентифицируют файл как вредоносные параметры.

- Запустите следующую команду в Exchange Online PowerShell и проверьте значения свойств:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Для проверки защиты безопасных документов доступны следующие файлы. Эти документы похожи на EICAR.TXT для тестирования антивирусных и антивирусных решений. Файлы не являются вредоносными, но они запускают защиту безопасных документов.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
