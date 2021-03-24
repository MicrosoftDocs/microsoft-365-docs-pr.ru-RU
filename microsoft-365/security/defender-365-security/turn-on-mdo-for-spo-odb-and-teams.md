---
title: Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Администраторы могут узнать, как включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, включая набор оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 07aea9551faa280cd51bda1d57f017e0a24028ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071085"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от непреднамеренного обмена вредоносными файлами. Дополнительные сведения см. в [разделЕ Безопасные вложения для SharePoint, OneDrive и Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

В этой статье содержатся действия для включения и настройки безопасных вложений для SharePoint, OneDrive и Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>. Чтобы перейти непосредственно на страницу БЕЗОПАСНЫЕ вложения **ATP,** откройте <https://protection.office.com/safeattachmentv2> .

- Чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams,  необходимо  быть членом групп ролей управления организацией или администратора безопасности в Центре & соответствия требованиям. Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

- Чтобы использовать SharePoint Online PowerShell для предотвращения скачивания вредоносных [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) файлов, необходимо быть членом роли глобального администратора или администратора [SharePoint](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD.

- Убедитесь, что журнал аудита включен для организации. Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

- Разрешить до 30 минут, чтобы параметры вступили в силу.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Шаг 1. Использование Центра & безопасности для вложения в SharePoint, OneDrive и Microsoft Teams

1. В Центре & безопасности перейдите к  политике управления угрозами \>  \> **ATP Safe Attachments** и щелкните **глобальные параметры.**

2. В глобальных **параметрах,** которые появляются, перейдите к параметру **Turn on Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams.** Переместите окантовку вправо, чтобы включить безопасные вложения ![ ](../../media/scc-toggle-on.png) для SharePoint, OneDrive и Microsoft Teams.

   Когда закончите, нажмите кнопку **Сохранить**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Используйте PowerShell Exchange Online, чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams

Если вы хотите использовать [PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) чтобы включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, подключитесь к Exchange Online PowerShell и запустите следующую команду:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Шаг 2. (Рекомендуется) Использование SharePoint Online PowerShell для предотвращения скачивания пользователями вредоносных файлов

По умолчанию пользователи не могут открывать, перемещать, копировать или делиться вредоносными файлами, обнаруженными ATP. Однако они могут удалять и скачивать вредоносные файлы.

Чтобы запретить пользователям скачивать вредоносные файлы, подключитесь [к SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Примечания.**

- Этот параметр влияет как на пользователей, так и на администраторов.
- Люди по-прежнему могут удалять вредоносные файлы.

Подробные сведения о синтаксисах и параметрах см. [в инструкции Set-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Шаг 3 (Рекомендуется) Использование Центра & безопасности для создания политики оповещения для обнаруженных файлов

Вы можете создать политику оповещения, которая оповещает вас и других администраторов, когда безопасные вложения для SharePoint, OneDrive и Microsoft Teams обнаруживают вредоносный файл. Дополнительные дополнительные информацию о оповещениях см. в центре Создания оповещений о действиях в центре [& безопасности.](../../compliance/create-activity-alerts.md)

1. В Центре [& безопасности](https://protection.office.com)перейдите к политикам **оповещения** оповещений или \>  откройте <https://protection.office.com/alertpolicies> .

2. На странице **Политики оповещения** нажмите кнопку Новая **политика оповещения**.

3. Мастер **политики оповещения открывается** при вылете. На странице **Имя оповещений** настройте следующие параметры:

   - **Имя.** Введите уникальное и описательное имя. Например, вредоносные файлы в библиотеках.
   - **Описание.** Введите необязательное описание. Например, сообщает администраторам, когда вредоносные файлы обнаруживаются в SharePoint Online, OneDrive или Microsoft Teams.
   - **Серьезность.** Оставьте значение **Low** выбранное по умолчанию или выберите **Medium** или **High**.
   - **Выберите категорию**: Выберите **управление угрозами.**

   По завершении нажмите кнопку **Далее**.

4. На странице **Создание параметров оповещения** настройте следующие параметры:

   - **Что нужно предупредить?: Действие:** Выберите **обнаруженную** вредоносную программу в файле .
   - **Как срабатывает** оповещение? : Оставьте значение по умолчанию каждый раз, когда действие соответствует **выбранному** правилу.

   По завершении нажмите кнопку **Далее**.

5. На странице **Set your recipients** настройте следующие параметры:

   - **Отправка уведомлений электронной** почты. Убедитесь, что выбран этот параметр. В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.
   - **Дневное ограничение** уведомлений. Оставьте выбранное **значение без ограничения** по умолчанию.

   По завершении нажмите кнопку **Далее**.

6. На странице **Обзор параметров** просмотрите параметры и нажмите **кнопку Изменить** в любом из разделов, чтобы внести изменения.

   В разделе Вы хотите включить политику **сразу?** оставьте значение **Да,** включив ее сразу же выбранной.

   Закончив, нажмите кнопку **Готово**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Используйте службу & powerShell для создания политики оповещения для обнаруженных файлов

Если вы хотите использовать PowerShell для создания той же политики оповещений, что и в предыдущем разделе, подключись к центру обеспечения безопасности [& PowerShell](/powershell/exchange/connect-to-scc-powershell) и запустите следующую команду:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Примечание.** Значение _серьезности по умолчанию_ является низким. Чтобы указать Medium или High, включай параметр _Severity_ и значение в команду.

Подробные сведения о синтаксисах и параметрах см. [в обзоре New-ActivityAlert.](/powershell/module/exchange/new-activityalert)

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

- Чтобы убедиться, что вы успешно включили безопасные вложения для SharePoint, OneDrive и Microsoft Teams, используйте один из следующих действий:

  - В Центре обеспечения [&](https://protection.office.com)безопасности перейдите  к политике управления угрозами ATP Safe Attachments, выберите глобальные параметры и проверьте значение параметра Turn \>  \> on Defender для **Office 365 для SharePoint, OneDrive** и Microsoft Teams.

  - В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)

- Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint Online PowerShell и запустите следующую команду, чтобы проверить значение свойства:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Подробные сведения о синтаксисах и параметрах см. [в обзоре Get-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)

- Чтобы убедиться, что вы успешно настроили политику оповещения для обнаруженных файлов, используйте любой из следующих действий:

  - В Центре & безопасности перейдите к политикам **оповещения** оповещений, выберите политику оповещения и проверьте \>  \> параметры.

  - В центре & безопасности PowerShell замените имя политики оповещения, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-ActivityAlert.](/powershell/module/exchange/get-activityalert)

- Используйте отчет [о состоянии защиты от угроз,](view-email-security-reports.md#threat-protection-status-report) чтобы просмотреть сведения о обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams. В частности, вы можете использовать **данные View по: Просмотр \> вредоносных программ** контента.