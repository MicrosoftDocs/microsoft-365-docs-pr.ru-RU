---
title: 'Включение Office 365 ATP: SharePoint, OneDrive & Teams'
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Узнайте, как включить ATP для SharePoint, OneDrive и Teams, включая настройку оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c717a89492ea1160f26f26f13be6c36f348c79c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350659"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Включение ATP для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 Advanced Threat protection (ATP) для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного предоставления вредоносных файлов. Для получения дополнительных сведений ознакомьтесь [со статьей ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).

В этой статье описывается включение и настройка ATP для SharePoint, OneDrive и Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com>. Чтобы перейти непосредственно к странице **безопасных вложений ATP** , откройте <https://protection.office.com/safeattachmentv2> .

- Чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** " в центре безопасности & соответствия требованиям. Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

- Чтобы запретить пользователям загружать вредоносные файлы с помощью PowerShell из SharePoint Online, необходимо быть участником роли [глобального администратора](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) или [администратора SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) в Azure AD.

- Убедитесь, что ведение журнала аудита включено для вашей организации. Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

- Дождитесь вступления параметров в силу до 30 минут.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Шаг 1: воспользуйтесь центром безопасности & соответствия требованиям, чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams.

1. В центре безопасности & соответствия требованиям перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**и щелкните **глобальные параметры**.

2. В открывшемся окне **глобальные параметры** перейдите к параметру **включить ATP для SharePoint, OneDrive и Microsoft Teams** . Установите переключатель вправо, ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams.

   Выполнив необходимые действия, нажмите кнопку **Сохранить**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Включение ATP для SharePoint, OneDrive и Microsoft Teams с помощью Exchange Online PowerShell

Если вы предпочитаете использовать PowerShell, чтобы включить ATP для SharePoint, OneDrive и Microsoft Teams, [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) и выполните следующую команду:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Шаг 2: (рекомендуется) используйте PowerShell из SharePoint Online, чтобы запретить пользователям скачивать вредоносные файлы

По умолчанию пользователи не могут открывать, перемещать, копировать и совместно использовать вредоносные файлы, обнаруженные ATP. Тем не менее, они могут удалять и загружать вредоносные файлы.

Чтобы запретить пользователям скачивать вредоносные файлы, [подключитесь к SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и выполните следующую команду:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Примечания.**

- Этот параметр влияет на пользователей и администраторов.
- Пользователи по-прежнему могут удалить вредоносные файлы.

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Шаг 3 (рекомендуется) использование центра безопасности & соответствия требованиям для создания политики оповещений для обнаруженных файлов

Вы можете создать политику оповещений, которая сообщит вам и другим администраторам, когда ATP для SharePoint, OneDrive и Microsoft Teams обнаружит вредоносный файл. Чтобы узнать больше об оповещениях, ознакомьтесь со статьей [Создание оповещений о действиях в центре безопасности & соответствия требованиям](../../compliance/create-activity-alerts.md).

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)перейдите к разделу **оповещения** о \> **политиках оповещений** или откройте окно "оповещения" <https://protection.office.com/alertpolicies> .

2. На странице **политики оповещений** щелкните **создать политику оповещений**.

3. Мастер **создания политики оповещений** открывается на лету. На странице " **назвать оповещение** " настройте следующие параметры:

   - **Name**: введите уникальное описательное имя. Например, вредоносные файлы в библиотеках.
   - **Описание**: введите необязательное описание. Например, уведомляет администраторов об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.
   - **Severity**: **оставьте значение по** умолчанию — "средний" или " **средний** " или " **высокий**".
   - **Выберите категорию**: выберите **Управление угрозами**.

   По завершении нажмите кнопку **Далее**.

4. На странице " **Создание параметров оповещений** " настройте следующие параметры.

   - **Что вы хотите оповещать?: действие**: выберите **обнаруженную вредоносную программу в файле**.
   - **Как вы хотите инициировать оповещение?**: оставьте значение по умолчанию при **каждом соответствии действия выбранному правилу** .

   По завершении нажмите кнопку **Далее**.

5. На странице " **Настройка получателей** " настройте следующие параметры:

   - **Отправлять уведомления по электронной почте**: Убедитесь, что этот параметр выбран. В поле **получатели электронной почты** выберите одного или нескольких глобальных администраторов, администраторов безопасности или средств чтения безопасности, которые должны получать уведомление при обнаружении вредоносного файла.
   - **Максимальное количество ежедневных уведомлений**: оставьте значение по умолчанию **не** выбрано.

   По завершении нажмите кнопку **Далее**.

6. На странице " **Проверка параметров** " Проверьте параметры и нажмите кнопку **изменить** в любом из разделов, чтобы внести изменения.

   В разделе вы **хотите включить политику** сразу же? оставьте значение по умолчанию **Да, включить его сразу после** выбора.

   Закончив, нажмите кнопку **Готово**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Создание политики оповещений для обнаруженных файлов с помощью PowerShell & обеспечения безопасности

Если вы предпочитаете использовать PowerShell, чтобы создать ту же политику оповещений, как описано в предыдущем разделе, [подключитесь к PowerShell центра безопасности & центра соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) и выполните следующую команду:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Note**: значение _степени серьезности_ по умолчанию — мала. Чтобы указать средний или высокий уровень, включите параметр _Severity_ и значение в команду.

Подробные сведения о синтаксисе и параметрах можно найти в статье [New – ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Как проверить, что эти процедуры выполнены?

- Чтобы убедиться, что вы успешно включили ATP для SharePoint, OneDrive и Microsoft Teams, выполните одно из указанных ниже действий.

  - В [центре безопасности & соответствия требованиям](https://protection.office.com)перейдите к разделу политика **управления угрозами** : \> **Policy** \> **безопасные вложения ATP**, выберите **глобальные параметры**и проверьте значение параметра **включить ATP для SharePoint, OneDrive и Microsoft Teams** .

  - В Exchange Online PowerShell выполните следующую команду, чтобы проверить значение свойства:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Чтобы убедиться, что пользователи успешно заблокировали загрузку вредоносных файлов, Откройте SharePoint Online PowerShell и выполните следующую команду, чтобы проверить значение свойства:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Чтобы убедиться, что вы успешно настроили политику оповещений для обнаруженных файлов, выполните одно из указанных ниже действий.

  - В центре безопасности & соответствия требованиям перейдите к разделу **оповещения** о политиках оповещений \> **Alert policies** \> , выберите политику оповещений и проверьте параметры.

  - В PowerShell центра безопасности & соответствия требованиям замените \<AlertPolicyName\> имя политики оповещений, выполните следующую команду и проверьте значения свойств:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Используйте [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report) для просмотра сведений об обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams. В частности, вы можете использовать представление " **Просмотр данных: контент \> от вредоносных программ** ".
