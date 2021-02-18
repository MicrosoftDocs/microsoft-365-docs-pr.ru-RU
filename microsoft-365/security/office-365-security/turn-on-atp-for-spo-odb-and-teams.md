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
description: Администраторы могут узнать, как включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams, включая настройка оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286373"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного совместного использования вредоносных файлов. Дополнительные сведения см. в записях ["Безопасные вложения" для SharePoint, OneDrive и Microsoft Teams.](atp-for-spo-odb-and-teams.md)

В этой статье содержатся действия по включаю и настройке безопасных вложений для SharePoint, OneDrive и Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com>. Чтобы перейти непосредственно на страницу безопасных **вложений ATP,** откройте <https://protection.office.com/safeattachmentv2> .

- Чтобы включить функцию "Безопасные вложения" для SharePoint, OneDrive и  Microsoft  Teams, необходимо быть членом группы ролей "Управление организацией" или "Администратор безопасности" в Центре безопасности & соответствия требованиям. Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

- Чтобы запретить скачивание вредоносных файлов с помощью SharePoint Online PowerShell, необходимо быть участником ролей глобального администратора или администратора [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD. [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)

- Убедитесь, что ведение журнала аудита включено для вашей организации. Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

- Чтобы параметры вступили в силу, в течение 30 минут.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Шаг 1. В Центре безопасности & соответствия требованиям включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams

1. В Центре безопасности & соответствия требованиям  перейдите в центр безопасных вложений ATP политики управления угрозами и щелкните \>  \>  **"Глобальные параметры".**

2. В **окнах** "Глобальные параметры" перейдите к параметру "Включить Защитник **для Office 365 для SharePoint, OneDrive** и Microsoft Teams". Переместите выключатель вправо, чтобы включить безопасные вложения для ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive и Microsoft Teams.

   По завершении нажмите кнопку **Сохранить**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams с помощью Exchange Online PowerShell

Если вы хотите включить безопасные вложения для SharePoint, OneDrive и Microsoft Teams с помощью [PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) подключитесь к Exchange Online PowerShell и запустите следующую команду:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Подробные сведения о синтаксис и параметрах см. в описании [Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Шаг 2. (Рекомендуется) Использование SharePoint Online PowerShell для предотвращения загрузки пользователями вредоносных файлов

По умолчанию пользователи не могут открывать, перемещать, копировать или совместно использовать вредоносные файлы, обнаруженные ATP. Однако они могут удалять и скачивать вредоносные файлы.

Чтобы запретить пользователям скачивать вредоносные файлы, подключитесь [к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Примечания**.

- Этот параметр влияет как на пользователей, так и на администраторов.
- Злоумышленники по-прежнему могут удалять вредоносные файлы.

Подробные сведения о синтаксисах и параметрах см. в [описании Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Шаг 3 (рекомендуется) Создание политики оповещений для обнаруженных файлов с помощью Центра безопасности & соответствия требованиям

Вы можете создать политику оповещений, которая будет оповещать вас и других администраторов о том, что безопасные вложения для SharePoint, OneDrive и Microsoft Teams обнаруживают вредоносный файл. Дополнительные информацию об оповещениях см. в центре безопасности [& соответствия требованиям.](../../compliance/create-activity-alerts.md)

1. В Центре [безопасности & соответствия](https://protection.office.com)требованиям  перейдите к политикам оповещений \> **или** откройте <https://protection.office.com/alertpolicies> .

2. На странице **"Политики оповещений"** щелкните **"Новая политика оповещений".**

3. Мастер **новой политики оповещений** откроется во время вылета. На странице **"Назовите оповещение"** настройте следующие параметры:

   - **Имя:** введите уникальное и описательное имя. Например, вредоносные файлы в библиотеках.
   - **Описание:** введите необязательное описание. Например, администраторам сообщается об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.
   - **Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.
   - **Выберите категорию**: выберите **управление угрозами.**

   По завершении нажмите кнопку **Далее**.

4. На странице **"Создание параметров оповещений"** настройте следующие параметры:

   - **Что нужно оповещать?: Действие:** выберите **обнаруженную вредоносную программу в файле.**
   - **Как следует запускать** оповещение? Оставьте значение по умолчанию каждый раз, когда действие соответствует **выбранному правилу.**

   По завершении нажмите кнопку **Далее**.

5. На странице **"Настройка получателей"** настройте следующие параметры:

   - **Отправка уведомлений по электронной** почте: убедитесь, что этот параметр выбран. В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.
   - **Ограничение на количество уведомлений за** день: оставьте значение по умолчанию **без** ограничения.

   По завершении нажмите кнопку **Далее**.

6. На странице **"Просмотр параметров"** просмотрите параметры и нажмите кнопку **"Изменить"** в любом из разделов, чтобы внести изменения.

   В разделе "Включить ли вы политику **сразу?",** оставьте значение по умолчанию **"Да",** включив ее сразу же.

   Закончив, нажмите кнопку **Готово**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Использование PowerShell & безопасности для обеспечения соответствия требованиям для создания политики оповещений для обнаруженных файлов

Если вы хотите использовать PowerShell для создания той же политики оповещений, которая описана в предыдущем разделе, подключите к [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Центра безопасности & соответствия требованиям и запустите следующую команду:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Примечание.** Значение _серьезности по_ умолчанию — Low. Чтобы указать medium или High, включаем параметр _Severity_ и значение в команду.

Подробные сведения о синтаксисах и параметрах см. в описании [New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

- Чтобы убедиться, что вы успешно включили безопасные вложения для SharePoint, OneDrive и Microsoft Teams, с помощью одного из следующих действий:

  - В Центре [безопасности &](https://protection.office.com)соответствия требованиям  перейдите в раздел "Безопасные вложения ATP политики управления угрозами", выберите глобальные параметры и проверьте значение параметра "Включить Защитник для \>  \>  **Office 365 для SharePoint, OneDrive** и Microsoft Teams". 

  - В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Подробные сведения о синтаксисах и параметрах см. в описании [get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)

- Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint Online PowerShell и запустите следующую команду, чтобы проверить значение свойства:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Подробные сведения о синтаксисах и параметрах см. в описании [Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)

- Чтобы убедиться, что вы успешно настроили политику оповещений для обнаруженных файлов, воспользуйтесь одним из следующих действий:

  - В Центре безопасности & соответствия требованиям  перейдите к политикам оповещений, выберите политику оповещений и проверьте \>  \> параметры.

  - В PowerShell Центра & безопасности замените имя политики оповещений, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Подробные сведения о синтаксисах и параметрах см. в описании [get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)

- Используйте отчет [о состоянии защиты от угроз для](view-email-security-reports.md#threat-protection-status-report) просмотра сведений об обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams. В частности, можно использовать данные **просмотра: представление "Вредоносные \> программы для** содержимого".
