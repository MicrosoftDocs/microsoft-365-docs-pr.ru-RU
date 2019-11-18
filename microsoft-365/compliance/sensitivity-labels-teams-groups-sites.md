---
title: Использование меток конфиденциальности при работе с Microsoft Teams, группами Office 365 и сайтами SharePoint (общедоступная Предварительная версия)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Вы можете применять метки к Microsoft Teams, группам Office 365 и сайтам SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687492"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Использование меток конфиденциальности при работе с Microsoft Teams, группами Office 365 и сайтами SharePoint (общедоступная Предварительная версия)

Когда вы создаете метки конфиденциальности в [центре соответствия требованиям microsoft 365](https://protection.office.com/), вы можете применить их к Microsoft Teams, группам Office 365 и сайтам SharePoint. Вы можете связать политики с метками для управления:

- Общедоступные и закрытые параметры
- Гостевой доступ
- Доступ с неуправляемых устройств

Когда вы применяете метку к группе или группе, метка автоматически применяется к подключенному сайту группы SharePoint и наоборот.

Теперь вы также можете включить метки конфиденциальности для файлов Office в SharePoint и OneDrive. [Подробнее](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Общие сведения об общедоступной предварительной версии для Microsoft Teams, Office 365 Groups и сайтов SharePoint

Метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint постепенно выходят на клиентов и могут быть изменены до окончательного выпуска.

## <a name="overview"></a>Обзор

При публикации меток конфиденциальности пользователи в Office 365 имеют доступ к одному и тому же списку меток.

На этих изображениях показаны:

- Способ отображения списка при создании нового сайта группы из SharePoint

- При просмотре списка в Word

![Метка чувствительности при создании сайта группы из SharePoint](media/sensitivity-label-new-team-site.png)

![Метка конфиденциальности, отображаемая в классическом приложении Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Включение этого предварительного просмотра с помощью Azure PowerShell

1. Войдите в Azure как глобальный администратор с помощью Azure PowerShell. Инструкции можно найти [в разделе Вход с помощью Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Выполните следующую команду:

```powershell
  Connect-AzureAD
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

Office 365 больше не использует старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра. Если вы использовали [классификацию сайтов Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["классификатионлист"]), существующие группы и сайты по-прежнему будут отображать старые классификации. Чтобы отобразить новые классификации, преобразуйте их. Сведения о том, как их преобразовать, можно узнать в статье [использование классического класса классификации сайта Azure AD](#if-you-used-classic-azure-ad-site-classification).

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a>Настройка параметров сайтов и групп при создании меток конфиденциальности

После включения предварительной версии выполните указанные ниже действия.

1. В центре соответствия требованиям Microsoft 365 выберите**метки чувствительности** **классификации** > .

2. Выберите **создать метку**.

3. Выберите нужные параметры, а затем на вкладке **Параметры сайта и группы** выберите:

    - Конфиденциальность (общедоступная или частная): Частная означает, что в группе могут видеть только утвержденные участники. Все остальные пользователи в вашей организации не могут видеть содержимое группы. [Подробнее](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Гостевой доступ: вы можете указать, можно ли добавлять гостей в группу. [Сведения об управлении гостевым доступом в группах Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Неуправляемые устройства: этот параметр позволяет заблокировать или ограничить доступ к контенту SharePoint с устройств, не являющихся гибридными или не связанными с Intune в Intune. Если вы выбрали неуправляемые устройства, вам нужно перейти в Azure AD, чтобы завершить настройку политики. Сведения см. [в статье Управление доступом с неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices).

![Вкладка "Параметры сайта и групп"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Только параметры сайта и групп вступают в силу при применении метки к команде, группе или сайту. Другие параметры, такие как шифрование и маркировка содержимого, не применяются ко всему контенту в группе, группе или на сайте. Аналогичным образом, если вы создаете метку и не включаете параметры сайта и группы, метка будет доступна, когда пользователи создают команды, группы и сайты, но не будут ничего делать при его применении пользователями.

[Сведения о публикации метки чувствительности](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Применение метки конфиденциальности к новой команде

Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams. При выборе уровня чувствительности параметры конфиденциальности изменяются по мере необходимости. В зависимости от параметров гостевого доступа, выбранных для метки, пользователи могут или не могут добавлять людей, не входящих в организацию, в команду.

![Параметр конфиденциальности при создании новой команды](media/privacy-setting-new-team.png)

После создания команды метка чувствительности отображается в правом верхнем углу всех каналов.

![Метка чувствительности отображается в команде](media/privacy-setting-teams.png)

Служба автоматически применяет ту же метку конфиденциальности к группе Office 365 и подключенному сайту группы SharePoint.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Применение метки конфиденциальности к новой группе

В Outlook в Интернете новое поле " **чувствительность** " содержит опубликованные метки. Если пользователям нужна дополнительная информация, они могут щелкнуть значок Справка, чтобы прочитать сведения о доступных метках и связанных с ними политиках.

![Создание группы и выбор параметра в разделе чувствительность](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Применение метки конфиденциальности к новому сайту

Администраторы и конечные пользователи могут выбирать метки конфиденциальности при создании современных сайтов группы и сайтов для общения.

[Узнайте, как создать сайт в новом центре администрирования SharePoint.](/sharepoint/create-site-collection)

Когда пользователи создают современные группы и сайты для общения, метка чувствительности уже выбрана по умолчанию. Пользователи могут выбрать значок справки, чтобы узнать больше о метках.

![Создание сайта и выбор параметра в соответствии с чувствительностью](media/sensitivity-label-new-communication-site.png)

Когда пользователи просматривают сайт, они могут видеть имя метки и примененные политики.

![Сайт, к которому применена метка чувствительности](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Управление метками конфиденциальности в центре администрирования SharePoint

Для просмотра и редактирования меток используйте страницу "активные сайты" в новом центре администрирования SharePoint.

![Столбец "чувствительность" на странице активных сайтов](media/manage-site-sensitivity-labels.png)

[Узнайте больше об управлении сайтами в новом центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Изменение параметров сайта и группы для метки

Рекомендуется не изменять параметры после применения метки к нескольким командам, группам или сайтам. Если необходимо внести изменения, необходимо использовать сценарий PowerShell для Azure AD для применения обновлений вручную. Этот метод обеспечивает применение нового параметра ко всем существующим командам, сайтам и группам.

## <a name="support-for-the-new-sensitivity-labels"></a>Поддержка новых меток конфиденциальности

Следующие приложения и службы поддерживают метки конфиденциальности в данном предварительном просмотре:

- Центр соответствия требованиям Microsoft 365
- SharePoint
- Outlook в Интернете
- Teams
- Центр администрирования SharePoint
- Центр администрирования Azure AD

Вы не можете использовать следующие приложения и службы для создания групп Office 365 с новыми метками конфиденциальности:

- Outlook для Mac
- Outlook Mobile  
- Настольный Outlook для Windows
- формы;  
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

Office 365 больше не поддерживает старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра. Однако существующие группы и сайты по-прежнему отображают старые классификации, пока не будут преобразованы. Старые классификации включают "современные классификации сайтов, которые вы настроили, возможно, с помощью Azure AD PowerShell или библиотеки ядра PnP, которые задают определенные `ClassificationList` значения параметра.

Например, в PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Дополнительные сведения о старом методе классификации можно найти в разделе ["современные" классификации сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

В зависимости от текущего развертывания у вас есть два варианта преобразования старых классификаций в новые классификации.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Если вы никогда не использовали метки чувствительности (единой системы меток защиты информации Майкрософт) для файлов и электронной почты

Мы рекомендуем вам:

1. Создайте новые метки конфиденциальности в центре соответствия требованиям Microsoft 365, имена которых совпадают с именами существующих классификаций.
2. Используйте PowerShell, чтобы применить новые метки к существующим группам Office 365 и сайтам SharePoint с помощью сопоставления имен.
3. Удалите старые классификации.

Приложения и службы, которые поддерживают новые метки конфиденциальности, отобразят их. Новые метки создаются в новых командах, группах и сайтах. Пользователи по-прежнему могут создавать группы из приложений и служб, которые не поддерживают новые метки. Однако пользователи не могут применить метку к этим группам. Используйте PowerShell, чтобы применить новые метки конфиденциальности для этих групп.

Вы можете хранить старые классификации; Однако настоятельно рекомендуется использовать PowerShell, чтобы применить новые метки конфиденциальности к этим группам.

Приложения и службы, которые поддерживают новые метки конфиденциальности, будут созданы с новыми метками. Когда пользователи создают группы из приложений и служб, которые не поддерживают новые метки, они могут выбрать классификацию.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Если вы используете метки конфиденциальности (Объединенные метки информационной защиты Майкрософт) для файлов и электронной почты

После включения этого предварительного просмотра перейдите к каждой метке в центре соответствия требованиям Microsoft 365 и примените нужные политики для сайтов и групп. Пользователи начнут просматривать существующие метки, доступные для сайтов и групп.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365

Перед применением новых меток убедитесь, что вы используете последнюю версию командной консоли SharePoint Online. Если у вас уже есть последняя версия, вы можете [переметить группы Office 365 с помощью новых меток конфиденциальности](#relabel-office-365-groups-with-new-sensitivity-labels).

Подготовка командной консоли SharePoint Online для предварительного просмотра:

1. Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удаление "Командная консоль SharePoint Online".

2. В веб-браузере перейдите на страницу центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Выберите язык и нажмите кнопку **скачать**.

4. Выберите файл в формате x64 и x86. msi. Скачайте файл x64, если вы используете 64-разрядную версию Windows или файл x86, если вы запускаете 32-разрядную версию. Если вы не знаете, посмотрите, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. После загрузки файла запустите его и следуйте указаниям мастера установки.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Переразметка групп Office 365 с помощью новых меток конфиденциальности

1. Убедитесь, что вы используете последнюю версию командной консоли SharePoint Online. Инструкции можно найти [в статье Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к консоли управления SharePoint Online. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Выполните следующую команду, чтобы получить список меток конфиденциальности и их идентификаторы GUID.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Запишите GUID для метки, которую требуется перезаписать. Например, метка "Общие".

5. Используйте следующую команду, чтобы получить список групп с классификацией "общий". При выполнении этой команды вы будете подключаться к Exchange Online PowerShell и исполняем командлет Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. Для каждой группы добавьте новый GUID метки чувствительности.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
