---
title: Получение сведений об основных управляемых устройствах для мобильных устройств и безопасности
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Используйте Windows PowerShell для получения сведений об основных устройствах для мобильных устройств и безопасности в Организации.
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430283"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Получение сведений об основных управляемых устройствах для мобильных устройств и безопасности

В этой статье показано, как использовать Windows PowerShell для получения сведений об устройствах в Организации, которые вы настроили для обеспечения базовой мобильной работы и безопасности.

Ниже приведена подразделение сведений об устройствах, доступных вам.

|**Detail**|**Что искать в PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Устройство регистрируется в базовой мобильной связи и безопасности. Дополнительные сведения см. в статье [Регистрация мобильного устройства с помощью базовой мобильной работы и безопасности](enroll-your-mobile-device.md)|Параметр "для *управления*"   имеет следующий тип:<br/>**True**= устройство зарегистрировано.<br/>**False**= устройство не зарегистрировано. |
|Устройство соответствует политикам безопасности устройств. Дополнительные сведения см в разделе [Создание политик безопасности устройств](create-device-security-policies.md)|Значение параметра "параметром" *соответствует*   :<br/>**Значение true**   = устройство соответствует политикам.<br/>**False (ложь**   ) = устройство несовместимо с политиками.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Основные параметры PowerShell для обеспечения мобильности и безопасности":::

>[!NOTE]
>Команды и сценарии также возвращают сведения обо всех устройствах под управлением [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Прежде чем начать

Для выполнения команд и сценариев, описанных в этой статье, необходимо настроить несколько моментов.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Шаг 1: Скачайте и установите модуль Azure Active Directory для Windows PowerShell

Для получения дополнительных сведений об этих действиях обратитесь к разделу [Подключение к Microsoft 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Перейдите на страницу [Помощник по входу в Microsoft Online Services для ИТ-специалистов ртвл](https://www.microsoft.com/download/details.aspx?id=41950)   и выберите пункт  **Загрузка для помощника по входу в Microsoft Online Services**.   

2. Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:   

    1. Откройте командную строку для уровня администратора PowerShell.  

    2. Выполните команду Install-Module MSOnline.
    
    3. Если отобразится запрос на установку поставщика NuGet, введите Y и нажмите клавишу ВВОД.   

    4. Если отобразится запрос на установку модуля из репозитория PSGallery, введите Y и нажмите клавишу ВВОД.   

    5. После установки закройте командное окно PowerShell.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Шаг 2: подключение к вашей подписке на Microsoft 365

1. В модуле Windows Azure Active Directory для Windows PowerShell выполните следующую команду.  

    $UserCredential = Get-Credential

2. В диалоговом окне Запрос учетных данных Windows PowerShell введите имя пользователя и пароль для учетной записи глобального администратора Microsoft 365, а затем нажмите кнопку **ОК**.
    
3. Выполните следующую команду.
    
    Connect — MsolService — $UserCredential учетных данных

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Шаг 3: Убедитесь, что вы можете запускать сценарии PowerShell.

>[!NOTE]
>Вы можете пропустить этот шаг, если вы уже настроили выполнение сценариев PowerShell.

Чтобы запустить скрипт Get-MsolUserDeviceComplianceStatus.ps1, необходимо включить выполнение сценариев PowerShell.

1. На рабочем столе Windows нажмите кнопку **Пуск**и введите Windows PowerShell. Щелкните правой кнопкой мыши Windows PowerShell, а затем выберите пункт **Запуск от имени администратора**.

2. Выполните следующую команду.
    
    Set — ExecutionPolicy RemoteSigned

3. При появлении соответствующего запроса введите Y и нажмите клавишу ВВОД.
    
**Выполните командлет Get – Мсолдевице, чтобы отобразить сведения для всех устройств в Организации.**

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.  

2. Выполните следующую команду.
    
    Get – Мсолдевице — ALL – Ретурнрегистередовнерс | Where – Object {$ _. RegisteredOwners. Count — gt 0}

Дополнительные примеры приведены в статье  [Get – мсолдевице](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Запуск скрипта для получения сведений об устройстве

Сначала сохраните сценарий на своем компьютере.

1. Скопируйте и вставьте приведенный ниже текст в Блокнот.  

2.  Param
    

3.  [PSObject []] $users = @ (),
    

4.  [Переключатель] $export,
    

5.  [Строка] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-format "yyMMdd_HHMMss") + ". csv",
    

6.  [Строка] $exportPath = [среда]:: Жетфолдерпас ("Рабочий стол")
    

7.  )
    

9.  [System. Collections. IDictionary] $script: schema = @ {
    

11.  DeviceId = ' '
    

12.  Девицеостипе = ' '
    

13.  Девицеосверсион = ' '
    

14.  Девицетрустлевел = ' '
    

15.  DisplayName = ' '
    

16.  Является совместимым = ' '
    

17.  Managed = ' '
    

18.  Аппроксимателастлогонтиместамп = ' '
    

19.  Девицеобжектид = ' '
    

20.  Регистередовнерупн = ' '
    

21.  Регистередовнеробжектид = ' '
    

22.  Регистередовнердисплайнаме = ' '
    

23.  }
    

25.  Функция Креатересултобжект
    

26.  {
    

28.  [PSObject] $resultObject = New – Object: TypeName PSObject — Property $script: schema
    

30.  Возврат $resultObject
    

31.  }
    

33.  Если ($users. Count-EQ 0)
    

34.  {
    

35.  $users = Get MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u в $users)
    

39.  {
    

41.  [PSObject] $devices = Get – мсолдевице — Регистередовнерупн $u. UserPrincipalName
    

42.  foreach ($d в $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = Креатересултобжект
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult. Девицеостипе = $d. Девицеостипе
    

47.  $deviceResult. Девицеосверсион = $d. Девицеосверсион
    

48.  $deviceResult. Девицетрустлевел = $d. Девицетрустлевел
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. с соответствующим = $d. Графдевицеобжект. ALL
    

51.  $deviceResult. Графдевицеобжект. Managed = $d...
    

52.  $deviceResult. Девицеобжектид = $d. ObjectId
    

53.  $deviceResult. Регистередовнерупн = $u. UserPrincipalName
    

54.  $deviceResult. Регистередовнеробжектид = $u. ObjectId
    

55.  $deviceResult. Регистередовнердисплайнаме = $u. DisplayName
    

56.  $deviceResult. Аппроксимателастлогонтиместамп = $d. Аппроксимателастлогонтиместамп
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  Если ($export)
    

64.  {
    

65.  $result | Export-CSV-Path ($exportPath + " \" + $exportFileName) — нотипеинформатион
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Сохраните его как файл сценария Windows PowerShell, используя расширение File. ps1; Например, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Запуск сценария для получения сведений об устройстве для одной учетной записи пользователя

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите к папке, в которой был сохранен сценарий. Например, если вы сохранили его в К:\пс-скриптс, выполните следующую команду.
    
    CD К:\пс-скриптс

3. Выполните следующую команду, чтобы определить пользователя, для которого необходимо получить сведения об устройстве. В этом примере показано получение сведений для bar@example.com.
    
    $u = Get MsolUser — UserPrincipalName bar@example.com

4. Выполните следующую команду, чтобы запустить скрипт.

    .\Get-MsolUserDeviceComplianceStatus.ps1 $u экспорта

Информация экспортируется на Рабочий стол Windows в виде CSV-файла. Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь для CSV-файла.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Запуск скрипта для получения сведений об устройстве для группы пользователей

1. Откройте модуль Microsoft Azure Active Directory для Windows PowerShell.
    
2. Перейдите к папке, в которой был сохранен сценарий. Например, если вы сохранили его в К:\пс-скриптс, выполните следующую команду.   

    CD К:\пс-скриптс

3. Выполните следующую команду, чтобы определить группу, для которой требуется получить сведения об устройстве. В этом примере показано получение сведений для пользователей в группе Финанцестафф. 

    $u = Get – Мсолграупмембер — Сеарчстринг "Финанцестафф" | % {Get – MsolUser – ObjectId $ _. ИД

4. Выполните следующую команду, чтобы запустить скрипт.   

    .\Get-MsolUserDeviceComplianceStatus.ps1 $u экспорта

Информация экспортируется на Рабочий стол Windows в виде CSV-файла. Вы можете использовать дополнительные параметры, чтобы указать имя файла и путь для CSV-файла.

## <a name="related-topics"></a>Статьи по теме

[Microsoft Connect снят](https://docs.microsoft.com/collaborate/connect-redirect)

[Общие сведения о базовом мобильном и системном обеспечении безопасности](overview.md)

[Get — Мсолдевице](https://go.microsoft.com/fwlink/?linkid=841721)