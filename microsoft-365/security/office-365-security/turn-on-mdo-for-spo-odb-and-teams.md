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
description: Администраторы могут узнать, как включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, включая набор оповещений для обнаруженных файлов.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083096"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Включение безопасных вложений для SharePoint, OneDrive и Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного обмена вредоносными файлами. Дополнительные сведения см. [в Сейф вложениях SharePoint, OneDrive и Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

В этой статье содержатся действия для включения и настройки Сейф вложений для SharePoint, OneDrive и Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>. Чтобы перейти непосредственно **на страницу Сейф вложения,** откройте <https://security.microsoft.com/safeattachmentv2> .

- Чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, необходимо быть членом групп ролей управления организацией  или  администратора безопасности на Microsoft 365 Defender портале. Дополнительные сведения см. в статье [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Чтобы использовать SharePoint PowerShell для предотвращения скачивания вредоносных файлов, необходимо [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) быть членом [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) глобального администратора или администратора SharePoint в Azure AD.

- Убедитесь, что журнал аудита включен для организации. Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

- Разрешить до 30 минут, чтобы параметры вступили в силу.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Шаг 1. Используйте портал Microsoft 365 Defender, чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams

1. На портале Microsoft 365 Defender перейдите в раздел **Политики & правила** политики угрозы Сейф \>  \>  \> **Вложения**.

2. На странице **Сейф вложения нажмите** **глобальные параметры**.

3. В **глобальной настройки** вылет, который появляется, перейдите к защите файлов **в SharePoint, OneDrive и Microsoft Teams** разделе.

   Переместите включаем **защитника для Office 365 для SharePoint, OneDrive** и Microsoft Teams переключив вправо, чтобы включить Сейф вложения для ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive и Microsoft Teams.

   По завершении нажмите **Сохранить**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Используйте Exchange Online PowerShell, чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams

Если вы хотите использовать [PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) чтобы включить Сейф вложения для SharePoint, OneDrive и Microsoft Teams, подключите Exchange Online PowerShell и запустите следующую команду:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Шаг 2. (Рекомендуется) Использование SharePoint PowerShell для предотвращения скачивания пользователями вредоносных файлов

По умолчанию пользователи не могут открывать, перемещать, копировать или делиться вредоносными файлами, обнаруженными Сейф вложениями для SharePoint, OneDrive и <sup>\*</sup> Microsoft Teams. Однако они могут удалять и скачивать вредоносные файлы.

<sup>\*</sup> Если пользователи перейдут **на управление доступом,** параметр **Share** по-прежнему доступен.

Чтобы запретить пользователям скачивать вредоносные файлы, [подключите SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и запустите следующую команду:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Примечания**:

- Этот параметр влияет как на пользователей, так и на администраторов.
- Люди по-прежнему могут удалять вредоносные файлы.

Подробные сведения о синтаксисах и параметрах см. [в инструкции Set-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Шаг 3 (Рекомендуется) Использование портала Microsoft 365 Defender для создания политики оповещения для обнаруженных файлов

Вы можете создать политику оповещения, которая оповещает вас и других администраторов, Сейф вложения для SharePoint, OneDrive и Microsoft Teams обнаруживает вредоносный файл. Дополнительные новости о оповещениях см. в [сайте Create activity alerts in the Microsoft 365 Defender.](../../compliance/create-activity-alerts.md)

1. На портале Microsoft 365 Defender перейдите к **политике & правил Оповещения или** \>  откройте <https://security.microsoft.com/alertpolicies> .

2. На странице **Политика оповещения** нажмите кнопку Новая **политика оповещения**.

3. Мастер **политики оповещения открывается** при вылете. На странице **Имя оповещений** настройте следующие параметры:
   - **Имя.** Введите уникальное и описательное имя. Например, вредоносные файлы в библиотеках.
   - **Описание.** Введите необязательное описание. Например, сообщает администраторам об обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.
   - **Серьезность:** Выберите **низкий,** **средний** или **высокий** из списка выпаданий.
   - **Категория.** Выберите **управление угрозами** из списка выпаданий.

   По завершении нажмите кнопку **Далее**.

4. На странице **Создание параметров оповещения** настройте следующие параметры:
   - **О чем нужно оповещать?** Раздел \> **Действия — это** \> выберите **обнаруженную вредоносную программу в файле** из списка drop down.
   - **Как срабатывает оповещение?** раздел. Оставьте значение по умолчанию **каждый раз,** когда действие соответствует выбранному правилу.

   По завершении нажмите кнопку **Далее**.

5. На странице **Set your recipients** настройте следующие параметры:
   - Проверка **выбора уведомлений отправки** электронной почты. В поле **получателей** электронной почты выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла.
   - **Дневное ограничение** уведомлений. Оставьте выбранное **значение без ограничения** по умолчанию.

   По завершении нажмите кнопку **Далее**.

6. На странице **Обзор параметров** просмотрите параметры. Вы можете выбрать **Изменить** в любом разделе, чтобы изменить параметры в этом разделе. Вы также можете щелкнуть **Назад** или выбрать определенную страницу в мастере.

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

- Чтобы убедиться, что вы успешно включили Сейф вложения для SharePoint, OneDrive и Microsoft Teams, используйте один из следующих действий:

  - На портале Microsoft 365 Defender перейдите в раздел Политики **политики &** правила политики угроз Сейф Вложения, выберите глобальные параметры и проверьте значение параметра Turn on Defender для Office 365 для \>  \>  \>  **SharePoint, OneDrive и Microsoft Teams.** 

  - В Exchange Online PowerShell запустите следующую команду, чтобы проверить параметр свойства:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)

- Чтобы убедиться, что вы успешно заблокировали загрузку вредоносных файлов, откройте SharePoint PowerShell и запустите следующую команду, чтобы проверить значение свойства:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Подробные сведения о синтаксисах и параметрах см. [в обзоре Get-SPOTenant.](/powershell/module/sharepoint-online/Set-SPOTenant)

- Чтобы убедиться, что вы успешно настроили политику оповещения для обнаруженных файлов, используйте любой из следующих действий:
  - На портале Microsoft 365 Defender перейдите к политике **& правила** Оповещения выберите политику оповещения и проверьте \>  \> параметры.
  - В Microsoft 365 Defender портале PowerShell замените имя политики оповещения, запустите следующую команду и проверьте \<AlertPolicyName\> значения свойств:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-ActivityAlert.](/powershell/module/exchange/get-activityalert)

- Используйте отчет [о состоянии защиты от](view-email-security-reports.md#threat-protection-status-report) угроз, чтобы просмотреть сведения о обнаруженных файлах в SharePoint, OneDrive и Microsoft Teams. В частности, вы можете использовать **данные View по: Просмотр \> вредоносных программ** контента.
