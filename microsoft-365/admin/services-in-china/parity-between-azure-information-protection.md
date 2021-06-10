---
title: Поддержка azure information Protection для Office 365 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Дополнительные сведения о Azure Information Protection (AIP) для Office 365 21Vianet и настройке ее для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535846"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Поддержка azure information Protection для Office 365 21Vianet

В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365 21Vianet и коммерческими предложениями, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Различия между AIP для Office 365 21Vianet и коммерческими предложениями

Хотя наша цель заключается в том, чтобы предоставить все коммерческие функции и функции клиентам в Китае с нашим AIP для Office 365 21Vianet предложение, есть некоторые отсутствующие функции, которые мы хотели бы выделить.

Следующий список включает существующие пробелы между AIP для Office 365 21Vianet и нашими коммерческими предложениями по январь 2021 г.:

- Управление правами на информацию (IRM) поддерживается только для Приложения Microsoft 365 для предприятий (сборка 11731.10000 или выше). Office 2010, Office 2013 г. и другие версии Office 2016 г. не поддерживаются.

- Миграция службы Active Directory Rights Management (AD RMS) в AIP в настоящее время недоступна.
  
- Поддерживается обмен защищенными электронными письмами с пользователями в коммерческом облаке.
  
- Обмен документами и вложениями электронной почты с пользователями в коммерческом облаке в настоящее время не доступен. Это включает Office 365 21Vianet пользователей в коммерческом облаке, не Office 365 управляемых пользователями 21Vianet в коммерческом облаке, и пользователей с лицензией RMS для физических лиц.
  
- IRM с SharePoint (защищенные IRM-сайты и библиотеки) в настоящее время недоступны.
  
- Расширение мобильного устройства для AD RMS в настоящее время не доступно.

- Мобильный [зритель не](/azure/information-protection/rms-client/mobile-app-faq) поддерживается Azure China 21Vianet.

- Область AIP портала Azure недоступна для клиентов в Китае. Используйте [команды PowerShell вместо](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) выполнения действий на портале, таких как управление заданиями сканирования контента и выполнение их.

## <a name="configure-aip-for-customers-in-china"></a>Настройка AIP для клиентов в Китае

Настройка AIP для клиентов в Китае:
1. [Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)

1. [Добавьте главу службы синхронизации защиты информации Майкрософт.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [Настройка шифрования DNS.](#step-3-configure-dns-encryption)

1. [Установка и настройка клиента единой маркировки AIP.](#step-4-install-and-configure-the-aip-unified-labeling-client)

1. [Настройка приложений AIP на Windows](#step-5-configure-aip-apps-on-windows).

1. [Установка локального сканера AIP и управление заданиями сканирования контента.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Шаг 1. Включить управление правами для клиента

Чтобы шифрование работало правильно, необходимо включить RMS для клиента.

1. Проверьте, включен ли RMS:

    1. Запустите PowerShell в качестве администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Импорт модуля с помощью `Import-Module AipService` .
    4. Подключение службе с помощью `Connect-AipService -environmentname azurechinacloud` .
    5. Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте, является ли состояние `Enabled` .

2. Если функциональное состояние , `Disabled` запустите `Enable-AipService` .

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Шаг 2. Добавление основного директора службы синхронизации microsoft Information Protection Service

Руководитель **службы синхронизации** защиты информации Майкрософт по умолчанию не доступен в клиентах Azure China и необходим для azure Information Protection.

1. Создайте эту главу службы вручную с помощью [командалета New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) и ID приложения для службы синхронизации защиты информации `870c4f2e-85b6-4d43-bdda-6ed9a579b725` Майкрософт. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. После добавления основного владельца службы добавьте соответствующие разрешения, необходимые для службы.

### <a name="step-3-configure-dns-encryption"></a>Шаг 3. Настройка шифрования DNS

Чтобы шифрование работало правильно, Office клиентские приложения должны подключиться к китайскому экземпляру службы и загрузчику оттуда. Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись SRV DNS с информацией о URL-адресе Azure RMS. Без записи SRV DNS клиентские приложения по умолчанию попытаются подключиться к общедоступным облачным экземплярам и сбой.

Кроме того, существует предположение, что пользователи будут входить в систему с иным имям пользователя, основанным на домене, владельцем клиента (например, ), а не имям `joe@contoso.cn` `onmschina` пользователя (например, `joe@contoso.onmschina.cn` ). Имя домена из имени пользователя используется для перенаправления DNS в правильный экземпляр службы.

#### <a name="configure-dns-encryption---windows"></a>Настройка шифрования DNS - Windows

1. Получите ID RMS:

    1. Запустите PowerShell в качестве администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Подключение службе с помощью `Connect-AipService -environmentname azurechinacloud` .
    4. `(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ID RMS.

2. Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

    - Служба = `_rmsredir`
    - Протокол = `_http`
    - Имя = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (где GUID — это ID RMS)
    - Приоритет, вес, секунды, TTL = значения по умолчанию

3. Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Это добавит запись в DNS, для проверки которой может потребоваться несколько минут после добавления значения в параметры DNS.

4. Войдите в центр администрирования Microsoft 365 с соответствующими глобальными учетными данными администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя. В процессе проверки могут потребоваться дополнительные изменения DNS. После проверки можно создать пользователей.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Настройка шифрования DNS - Mac, iOS, Android

Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

- Служба = `_rmsdisco`
- Протокол = `_http`
- Имя = `_tcp`
- Target = `api.aadrm.cn`
- Порт = `80`
- Приоритет, вес, секунды, TTL = значения по умолчанию


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Шаг 4. Установка и настройка клиента единой маркировки AIP

Скачайте и установите клиент единой метки AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)

Дополнительные сведения см. в указанных ниже статьях.

- [Документация по AIP](/azure/information-protection/)
- [История и политика поддержки версий AIP](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Требования к системе AIP](/azure/information-protection/requirements)
- [AIP quickstart: Развертывание клиента AIP](/azure/information-protection/quickstart-deploy-client)
- [Руководство администратора AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Руководство по пользователю AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Узнайте о Microsoft 365 меток конфиденциальности](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Шаг 5. Настройка приложений AIP на Windows

Приложениям AIP на Windows нужен следующий ключ реестра, чтобы указать их на правильное суверенное облако для Azure China:

- Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Имя = `CloudEnvType`
- Значение = `6` (по умолчанию = 0)
- Тип = `REG_DWORD`

> [!IMPORTANT]
> Убедитесь, что не удаляйте ключ реестра после удаления. Если ключ пустой, неправильный или несуществующий, функциональность будет вести себя как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака). Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Шаг 6. Установка локального сканера AIP и управление заданиями сканирования контента

Установка локального сканера AIP для сканирования сетевых и контентных акций для конфиденциальных данных, а также применения меток классификации и защиты в зависимости от политики организации.

При настройке и управлении заданиями проверки контента используйте следующую процедуру вместо интерфейса портала [Azure,](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) который используется коммерческими предложениями.

Дополнительные сведения см. в том, что такое сканер единой маркировки [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) и управление заданиями сканирования контента только [с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)

**Установка и настройка сканера:**

1. Вопишитесь на компьютер Windows Server, который будет запускать сканер. Используйте учетную запись с правами локального администратора и с разрешениями на запись в SQL Server базу данных.

1. Начните с закрытия PowerShell. Если вы ранее установили клиент AIP и сканер, убедитесь, что служба **AIPScanner** остановлена.

1. Откройте сеанс Windows PowerShell с помощью **параметра Run в качестве администратора.**

1. Запустите комлет [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) указав SQL Server экземпляр, на котором можно создать базу данных для сканера защиты информации Azure, а также значимое имя кластера сканера.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Одно и то же имя кластера можно использовать в команде [Install-AIPScanner,](/powershell/module/azureinformationprotection/install-aipscanner) чтобы связать несколько узлов сканера с тем же кластером. Использование одного и того же кластера для нескольких узлов сканера позволяет нескольким сканерам работать вместе для выполнения сканирования.
    > 

1. Убедитесь, что служба теперь установлена с помощью **служб**  >  **административных инструментов.**

    Установленная служба называется **сканером защиты информации Azure** и настроена на запуск с помощью созданной учетной записи службы сканера.

1. Получите маркер Azure для использования с помощью сканера. Маркер Azure AD позволяет сканеру выполнить проверку подлинности в службе защиты информации Azure, что позволяет сканеру работать без интерактивной работы. 

    1. Откройте портал Azure и создайте приложение Azure AD, чтобы указать маркер доступа для проверки подлинности. Дополнительные сведения см. в [материалах How to label files non-interactively for Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)
    
        > [!TIP]
        > При создании и настройке приложений Azure AD для команды [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) в области  разрешений API запросов  показана таблица **API,** которая используется моей организацией вместо вкладки API Microsoft. Выберите **API, которые использует моя организация,** чтобы затем выбрать **службы управления** правами Azure. 
        >

    1. С компьютера Windows Server, если учетной записи службы  сканера был предоставлен журнал на локальном праве для установки, войдите в эту учетную запись и запустите сеанс PowerShell. 
    
        Если учетная запись службы  сканера не может быть предоставлена журналу локально правильно для установки, используйте параметр *OnBehalfOf* с [помощью Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication)как описано в описании Как метить файлы неавтериализно для [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)

    1. Запустите [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication)указав значения, скопированные из приложения Azure AD:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Пример.

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    Теперь у сканера есть маркер для проверки подлинности в Azure AD. Этот маркер действителен в течение одного года, двух лет или никогда в соответствии с конфигурацией секрета клиента веб-приложения **и API** в Azure AD. По истечении срока действия маркера необходимо повторить эту процедуру.

1. Запустите [комлет Set-AIPScannerConfiguration,](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) чтобы настроить работу сканера в автономном режиме. Запуск:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Запустите [комлет Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) для создания задания проверки контента по умолчанию.

    Единственным требуемого параметра в **комлете Set-AIPScannerContentScanJob** является **Enforce**. Однако в настоящее время может потребоваться определить другие параметры для задания проверки контента. Пример.

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    Синтаксис выше настраивает следующие параметры при продолжении настройки:

    - Сохраняет планирование запуска сканера в *ручном режиме*
    - Задает типы сведений, которые будут обнаружены на основе политики маркировки конфиденциальности
    - Не *применяет* политику маркировки конфиденциальности
    - Автоматически маркируется файлы на основе контента с помощью метки по умолчанию, определенной для политики маркировки конфиденциальности.
    - Не *допускается* повторное перенаверение файлов
    - Сохраняет сведения о файлах при сканировании и автоматической маркировке, включая изменение даты, последние изменения *и* *изменение значений*
    - Задает сканер, чтобы исключить файлы .msg и .tmp при запуске
    - Устанавливает владельца по умолчанию для учетной записи, используемой при запуске сканера

1. Чтобы определить репозитории, которые необходимо сканировать в заданиях проверки контента, используйте код [Add-AIPScannerRepository.](/powershell/module/azureinformationprotection/add-aipscannerrepository) Например, выполните команду:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Используйте один из следующих синтаксисов в зависимости от типа репозитория, который вы добавляете:

    - Для сетевой доли используйте `\\Server\Folder` .
    - Для библиотеки SharePoint используйте `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Для локального пути: `C:\Folder`
    - Для пути UNC: `\\Server\Folder`

    > [!NOTE]
    > Поддиадры не поддерживаются, а расположения WebDav не поддерживаются.
    >
    > Чтобы изменить репозиторий позже, используйте вместо него кодлет [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository) 


Продолжить следующие действия по мере необходимости:

- [Запуск цикла обнаружения и просмотр отчетов для сканера](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Использование PowerShell для настройки сканера для применения классификации и защиты](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Используйте PowerShell для настройки политики DLP с помощью сканера](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

В следующей таблице перечислены cmdlets PowerShell, которые необходимы для установки сканера и управления заданиями сканирования контента:

| Командлет | Описание |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Добавляет новый репозиторий в задание проверки контента. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Возвращает сведения о кластере. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Получает сведения о работе по проверке контента. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Получает сведения о репозиториях, определенных для задания сканирования контента. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Удаляет задание сканирования контента. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Удаляет репозиторий из задания проверки контента. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Определяет параметры задания сканирования контента. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Определяет параметры существующего репозитория в заданиях проверки контента. |
| | |

Дополнительные сведения см. в указанных ниже статьях.

- [Что такое сканер единой маркировки Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Настройка и установка единого сканера маркировки Azure Information Protection (AIP)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Управление заданиями сканирования контента только с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
