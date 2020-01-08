---
title: Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint (общедоступная предварительная версия)
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Вы можете применять метки к Microsoft Teams, группам Office 365 и сайтам SharePoint.
ms.openlocfilehash: 4a8cf810ba29c2bb025b50e1529081a1a9ba6843
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966897"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Использование меток конфиденциальности в Microsoft Teams, группах Office 365 и сайтах SharePoint (общедоступная предварительная версия)

При создании меток конфиденциальности в [Центре соответствия требованиям Microsoft 365](https://protection.office.com/) вы можете применить их в Microsoft Teams, к группам Office 365 и сайтам SharePoint. Вы можете связать политики с метками, чтобы управлять следующими компонентами:

- Открытые и закрытые параметры
- Гостевой доступ
- Доступ с неуправляемых устройств

Если вы применяете метку к команде или группе, эта метка автоматически применяется к подключенному сайту группы SharePoint и наоборот.

Теперь вы также можете включить метки конфиденциальности для файлов Office в SharePoint и OneDrive. Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive (общедоступная предварительная версия)](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Сведения об общедоступной предварительной версии для Microsoft Teams, групп Office 365 и сайтов SharePoint

Метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint постепенно разворачиваются в клиентах и могут быть изменены до окончательного выпуска.

Эта общедоступная предварительная версия не работает в сетях доставки содержимого Office 365 (CDN).

## <a name="overview"></a>Обзор

Когда вы публикуете метки конфиденциальности, пользователи в Office 365 получают доступ к этому списку меток.

На изображениях ниже показано следующее:

- Способ отображения списка при создании нового сайта группы в SharePoint

- Просмотр списка в Word

Пример:

![Метка конфиденциальности при создании сайта группы в SharePoint](media/sensitivity-label-new-team-site.png)

![Метка конфиденциальности, отображаемая в классическом приложении Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>Включение этой предварительной версии

Чтобы включить эту предварительную версию меток конфиденциальности в Microsoft Teams, группах Office 365 и на сайтах SharePoint, требуется использовать предварительную версию [Azure AD PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (название модуля — **AzureADPreview**).

- Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.

- Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.

- Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.

Теперь вы готовы к включению предварительной версии меток конфиденциальности в Microsoft Teams, группах Office 365 и на сайтах SharePoint:

1. В сеансе PowerShell с помощью рабочей или учебной учетной записи с правами глобального администратора подключитесь к Azure Active Directory. Например, выполните команду:
    
    ```powershell
    Connect-AzureAD
    ````
    
    Подробные инструкции см. в статье [Подключение к Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).

2. Выполните следующие команды:
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > Если вы включите эту предварительную версию, Office 365 больше не будет использовать старые классификации для новых групп и сайтов SharePoint. Если вы использовали [классификацию сайтов Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), существующие группы и сайты по-прежнему будут отображать старые классификации. Чтобы отобразить новые классификации, преобразуйте их. Сведения о способе преобразования см. в разделе [Если вы использовали классическую классификацию сайтов Azure AD](#if-you-used-classic-azure-ad-site-classification). 

3. В том же сеансе PowerShell подключитесь к Центру безопасности и соответствия требованиям с помощью рабочей или учебной учетной записи с правами глобального администратора. Инструкции см. в статье [Подключение к PowerShell Центра безопасности и соответствия требованиям Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

4. Выполните следующие команды для синхронизации ваших меток с Azure AD, чтобы их можно было использовать с группами Office 365:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Настройка параметров сайта и группы при создании или изменении меток конфиденциальности

Включив предварительную версию, выполните указанные ниже действия, чтобы создать или изменить метки конфиденциальности. Вы должны выполнить эти действия, чтобы новые метки конфиденциальности поддерживались на сайтах и в группах, даже если вы уже определили метки. Синхронизация изменений этих параметров может занять до 24 часов.

1. В Центре соответствия требованиям Microsoft 365 выберите **Классификация** > **Метки конфиденциальности**.

2. Нажмите **Создать метку**. Если у вас уже есть метка, перейдите к следующему действию.

3. Выберите нужные параметры, а затем на вкладке **Параметры сайта и группы** укажите следующее:
    
    - Конфиденциальность (открытая или закрытая). Вариант "Закрытая" означает, что только утвержденные участники из вашей организации могут просматривать содержимое группы. Все другие сотрудники вашей организации не могут просматривать содержимое группы. [Подробнее](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Гостевой доступ. Вы можете указать, можно ли добавлять гостей в группу. [Сведения об управлении гостевым доступом в группах Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Неуправляемые устройства. Этот параметр позволяет заблокировать или ограничить доступ к контенту SharePoint с устройств, не присоединенных к гибридной среде AD или не соответствующих требованиям в Intune. Если вы выбрали неуправляемые устройства, вам потребуется перейти в Azure AD, чтобы завершить настройку политики. Сведения см. в статье [Управление доступом с неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices).
    
    ![Вкладка "Параметры сайта и группы"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Когда вы применяете метку к команде, группе или сайту, в силу вступают только параметры сайта и группы. Другие параметры, например шифрование и маркировка контента, не применяются ко всему содержимому в команде, группе или на сайте.
> 
> Аналогичным образом, если вы создаете метку и не включаете параметры сайта и группы, метка по-прежнему будет доступна при создании пользователями команд, групп и сайтов, но ее классификация будет использоваться без применения каких-либо параметров.

[Дополнительные сведения о публикации меток конфиденциальности](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a>Управление метками конфиденциальности

> [!WARNING]
> Создание, изменение и удаление меток конфиденциальности, используемых для Microsoft Teams, групп Office 365 и сайтов SharePoint, требует тщательной координации с политиками публикации меток для пользователей. 

Чтобы избежать создания ошибок для сайтов и групп, которые могут повлиять на всех пользователей, воспользуйтесь следующим руководством.

**Создание и публикация меток**

После создания и публикации метки может потребоваться до 24 часов, чтобы она стала видимой для пользователей команд, групп и сайтов. Чтобы опубликовать метку для всех пользователей в клиенте, используйте следующие действия:

1. Создайте метку конфиденциальности и опубликуйте ее лишь для нескольких учетных записей пользователей в клиенте.

2. Подождите 24 часа.

3. После 24-часового ожидания используйте одну из учетных записей пользователя, указанных в действии 1, чтобы создать команду, группу Office 365 или сайт SharePoint с меткой, созданной в действии 1.

4. Если в действии 3 операции создания не возникают ошибки, опубликуйте метку для всех пользователей в клиенте. При возникновении ошибок обратитесь в службу поддержки Майкрософт.

**Изменение и удаление опубликованных меток**

Если вы изменяете или удаляете метку конфиденциальности, относящуюся к одной или нескольким политикам меток, эти действия могут привести к сбоям при создании любых команд, групп и сайтов. Чтобы избежать этой ситуации, используйте следующее руководство:

1. Удалите метку конфиденциальности из всех политик меток, содержащих ее.

2. Подождите 48 часов.

3. После 48-часового ожидания попробуйте создать команду, группу или сайт и убедитесь, что метка больше не отображается.

4. Если метка конфиденциальности не отображается, вы можете безопасно изменить или удалить ее. Если метка по-прежнему отображается, обратитесь в службу поддержки Майкрософт.

## <a name="troubleshoot-sensitivity-label-deployment"></a>Устранение неполадок при развертывании меток

### <a name="labels-not-visible-after-publishing"></a>Метки не отображаются после публикации
Если вы столкнулись с проблемами при создании команды или группы Office 365 после включения этих параметров или изменения описания метки конфиденциальности, сохраните метку, подождите несколько часов и вновь попробуйте создать команду или группу. Сведения см. в разделе [Планирование развертывания после создания или изменения метки конфиденциальности](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Если вы по-прежнему не видите новую метку конфиденциальности в SharePoint Online, обратитесь в службу поддержки Майкрософт.

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Ошибки при создании команды, группы или сайта SharePoint
Если у вас возникают ошибки создания при использовании предварительной версии, у вас есть два варианта:

- Убедитесь, что метки конфиденциальности не являются обязательными для каждого пользователя.

- Вы можете отключить метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint, выполнив те же инструкции из раздела [Включение этой предварительной версии](#enable-this-preview) на этой странице. Но чтобы отключить предварительную версию, выполните поиск строки `$setting["EnableMIPLabels"] = "True"` и измените значение **True** на **False**.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Применение метки конфиденциальности к новой команде

Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams. При выборе метки конфиденциальности параметры конфиденциальности изменяются по мере необходимости. В зависимости параметра гостевого доступа, выбранного для метки, пользователи могут или не могут добавлять в команду людей из-за пределов организации.

[Дополнительные сведения о метках конфиденциальности для Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Параметр конфиденциальности при создании новой команды](media/privacy-setting-new-team.png)

После создания команды метка конфиденциальности отображается в правом верхнем углу всех каналов.

![Отображение метки конфиденциальности в команде](media/privacy-setting-teams.png)

Служба автоматически применяет такую же метку конфиденциальности к группе Office 365 и подключенному сайту группы SharePoint.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Применение метки конфиденциальности к новой группе

В Outlook в Интернете новое поле **Конфиденциальность** содержит опубликованные метки. Если пользователям нужны дополнительные сведения, они могут щелкнуть значок справки, чтобы ознакомиться с подробностями о доступных метках и связанных политиках.

![Создание группы и выбор параметра в разделе "Конфиденциальность"](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Применение метки конфиденциальности к новому сайту

Администраторы и конечные пользователи могут выбирать метки конфиденциальности при создании современных сайтов групп и информационных сайтов.

[Сведения о создании сайта в новом Центре администрирования SharePoint](/sharepoint/create-site-collection)

Когда пользователи создают современный сайт группы или информационный сайт, метка конфиденциальности уже выбрана по умолчанию. Пользователи могут щелкнуть значок справки, чтобы узнать больше о метках.

![Создание сайта и выбор параметра в разделе "Конфиденциальность"](media/sensitivity-label-new-communication-site.png)

Когда пользователь переходит на сайт, он может увидеть имя метки и примененные политики.

![Сайт с примененной меткой конфиденциальности](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Управление метками конфиденциальности в Центре администрирования SharePoint

Чтобы просмотреть и изменить метки, используйте страницу "Активные сайты" в новом Центре администрирования SharePoint.

![Столбец "Конфиденциальность" на странице "Активные сайты"](media/manage-site-sensitivity-labels.png)

[Дополнительные сведения об управлении сайтами в новом Центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Изменение параметров сайта и группы для метки

Когда осуществляется изменение параметров сайта и группы для метки, требуется выполнить следующие команды PowerShell, чтобы ваши команды, сайты и группы могли использовать новые параметры. Рекомендуется не изменять параметры сайта и группы для метки после применения метки к нескольким командам, группам или сайтам.

1. Выполните следующие команды, чтобы подключиться к PowerShell Центра безопасности и соответствия требованиям Office 365 и получить список меток конфиденциальности и их идентификаторы GUID.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. Запишите GUID для измененных меток.

3. Подключитесь к Exchange Online PowerShell и выполните командлет Get-UnifiedGroup, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e": 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. Для каждой группы повторно примените метку конфиденциальности, указав GUID метки вместо GUID примера "e48058ea-98e8-4940-8db0-ba1310fd955e":
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a>Поддержка новых меток конфиденциальности

Следующие приложения и службы поддерживают метки конфиденциальности в этой предварительной версии:

- Центр соответствия требованиям Microsoft 365
- SharePoint
- Outlook в Интернете
- Teams
- Центр администрирования SharePoint
- Центр администрирования Azure AD

Вы не можете использовать следующие приложения и службы для создания групп Office 365 с новыми метками конфиденциальности:

- Outlook для Mac
- Outlook Mobile  
- Классическая версия Outlook для Windows
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Планировщик  
- Project  
- PowerBI  
- Центр администрирования Teams  
- Центр администрирования Microsoft 365  
- Центр администрирования Exchange

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Если вы использовали классическую классификацию сайтов Azure AD

Если вы включите эту предварительную версию, Office 365 больше не будет поддерживать старые классификации для новых групп и сайтов SharePoint. Однако существующие группы и сайты по-прежнему будут отображать старые классификации, если их не преобразовать. Старые классификации включают классификацию "современных" сайтов, которую вы настроили, с помощью Azure AD PowerShell или основной библиотеки PnP, определяющей значения параметра `ClassificationList`.

Например, в PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Дополнительные сведения о старом методе классификации см. в статье [Классификация "современных" сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Исходя из текущего развертывания, у вас есть два варианта преобразования старых классификаций в новые.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Если вы никогда не использовали метки конфиденциальности (единые метки защиты информации (Майкрософт)) для файлов и электронной почты

Вот несколько рекомендаций.

1. Создайте метки конфиденциальности в Центре соответствия требованиям Microsoft 365 с такими же именами, как у существующих классификаций.
2. Используйте PowerShell, чтобы применить новые метки к существующим группам Office 365 и сайтам SharePoint с помощью сопоставления имен.
3. Удалите старые классификации.

Приложения и службы, поддерживающие новые метки конфиденциальности, отобразят их. Вы можете создавать команды, группы и сайты с новыми метками. Пользователи по-прежнему смогут создавать группы из приложений и служб, не поддерживающих новые метки. Однако пользователи не могут применить метку к этим группам. Используйте PowerShell, чтобы применить новые метки конфиденциальности к этим группам.

Вы можете сохранить старые классификации, но мы настоятельно рекомендуем использовать PowerShell, чтобы применить новые метки конфиденциальности к этим группам.

Приложения и службы, поддерживающие новые метки конфиденциальности, будут созданы с новыми метками. Когда пользователи создают группы из приложений и служб, не поддерживающих новые метки, они могут выбрать классификацию.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Если вы используете метки конфиденциальности (единые метки защиты информации (Майкрософт)) для файлов и электронной почты

Как только вы включите эту предварительную версию, перейдите к каждой метке в Центре соответствия требованиям Microsoft 365 и примените нужные политики для сайтов и групп. Пользователи смогут просматривать существующие метки, доступные для сайтов и групп.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Подготовка командной консоли SharePoint Online перед переназначением меток групп Office 365

Перед применением новых меток убедитесь, что вы используете последнюю версию командной консоли SharePoint Online. Если вы уже используете последнюю версию, вы можете продолжить и [переназначить метки групп Office 365 с помощью новых меток конфиденциальности](#relabel-office-365-groups-with-new-sensitivity-labels).

Подготовка командной консоли SharePoint Online для предварительной версии:

1. Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удалите компонент "Командная консоль SharePoint Online".

2. В веб-браузере перейдите на страницу Центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Выберите язык и нажмите кнопку **Скачать**.

4. Выберите разрядность файла MSI (x64 или x86). Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86. Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system)

5. После скачивания файла запустите его и следуйте инструкциям мастера настройки.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Переназначение меток групп Office 365 с помощью новых меток конфиденциальности

1. Убедитесь, что вы используете последнюю версию командной консоли SharePoint Online. Инструкции см. в разделе [Подготовка командной консоли SharePoint Online перед переназначением меток групп Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Используя рабочую или учебную учетную запись с правами глобального администратора или администратора SharePoint в Office 365, подключитесь к командной консоли SharePoint Online. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Чтобы получить список меток конфиденциальности и их GUID, выполните следующую команду.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Запишите GUID для метки, которую нужно перезаписать. Например, для метки General (Общее).

5. Используйте следующую команду, чтобы получить список групп с классификацией General (Общее). При выполнении этой команды нужно подключиться к Exchange Online PowerShell и запустить командлет Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Для каждой группы добавьте GUID новой метки конфиденциальности.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
