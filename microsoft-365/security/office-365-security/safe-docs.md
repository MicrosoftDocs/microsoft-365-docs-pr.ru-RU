---
title: Безопасные документы в Office 365 ATP
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
description: Сведения о безопасных документах в Microsoft 365 E5 или Microsoft 365 E5.
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827473"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Безопасные документы в Microsoft 365 E5

Безопасные документы — это функция в Microsoft 365 E5 или Microsoft 365 E5, использующая [Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для проверки документов и файлов, открытых в [режиме защищенного просмотра.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Теперь функция "Безопасные документы" общедоступна пользователям Office версии 2004 (12730.x) или более поздней версии! Эта функция отключена по умолчанию, и ее должен включить администратор безопасности.

- Эта функция доступна только пользователям, у которых имеется *лицензия microsoft 365 E5* *или Microsoft 365 E5 Security* (не включена в планы Office 365 ATP).

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Для выполнения процедур, описанных в этом разделе, необходимы права. Чтобы включить и настроить безопасные документы, вы должны быть членом **группы ролей "Управление организацией"** **или "Администратор** безопасности". Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>Как Корпорация Майкрософт обрабатывает ваши данные?

Чтобы защитить документы, безопасные документы отправляются в [облако Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) для анализа.

- Сведения о том, как Advanced Threat Protection обрабатывает ваши данные в Microsoft Defender, можно найти [здесь](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Кроме приведенных выше рекомендаций файлы, отправляемые функциями "Безопасные документы", не сохраняются в Защитнике, пока не достает времени, необходимого для анализа , что превышает 24 часа

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Настройка безопасных документов с помощью & Центра безопасности

1. Откройте Центр безопасности & соответствия требованиям на <https://protection.office.com> сайте.

2. Перейдите в **раздел "Безопасные** \> **Policy** \> **вложения ATP" в разделе "Политика управления угрозами".**

3. Настройте следующие параметры **в** разделе справки для пользователей.

   - **Включение безопасных документов для клиентов Office**

   - **Разрешить пользователям переходить в режиме защищенного просмотра, даже если система безопасных**документов определяет файл вредоносным. Мы не рекомендуем включать этот параметр.

4. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

![Страница "Безопасные вложения ATP"](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Настройка безопасных документов с помощью Exchange Online PowerShell или автономной службы EOP PowerShell

Используйте указанный ниже синтаксис.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Параметр _EnableSafeDocs включает_ или отключает функцию "Безопасные документы" для всей организации.

- Параметр _AllowSafeDocsOpen_ позволяет или запрещает пользователям выгрузить документ в режиме защищенного просмотра (то есть открывать документ), если он был определен как вредоносный.

В этом примере функцию "Безопасные документы" включается для всей организации и запрет открытия документов, определенных как вредоносные, от режима защищенного просмотра.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Дополнительные сведения о синтаксисе и параметрах см. в [описании Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>Как проверить, что это работает?

Чтобы убедиться, что вы включили и настроили безопасные документы, выполните одно из указанных ниже действий.

- В Центре безопасности & соответствия требованиям откройте **"Безопасные** вложения \> **Policy** \> **ATP"** и проверьте параметры, выбранные в параметрах безопасности, чтобы пользователи не **стали безопасными,** если файл открываться вне раздела приложений Office.

- Выполните следующую команду в Exchange Online PowerShell и проверьте значения свойств:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
