---
title: Поддержка azure information Protection для Office 365, выполняемая 21Vianet
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
description: Дополнительные сведения о Azure Information Protection (AIP) для Office 365, выполняемой 21Vianet, и о настройке ее для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418036"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Поддержка azure information Protection для Office 365, выполняемая 21Vianet

В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365, управляемой 21Vianet, и коммерческими предложениями, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Различия между AIP для Office 365, выполняемым 21Vianet, и коммерческими предложениями

Хотя наша цель — предоставить все коммерческие функции и функции клиентам в Китае с помощью AIP для Office 365 с предложением 21Vianet, мы хотели бы выделить некоторые недостающие функции.

В следующем списке содержатся существующие пробелы между AIP для Office 365, выполняемым 21Vianet, и нашими коммерческими предложениями по январю 2021 г.:

- Управление правами на информацию (IRM) поддерживается только для приложений Microsoft 365 для предприятия (сборка 11731.10000 или более). Версии Office 2010, Office 2013 и других версий Office 2016 не поддерживаются.

- Миграция служба управления правами Active Directory (AD RMS) в AIP в настоящее время недоступна.
  
- Поддерживается обмен защищенными электронными письмами с пользователями в коммерческом облаке.
  
- Обмен документами и вложениями электронной почты с пользователями в коммерческом облаке в настоящее время не доступен. Это включает Office 365, управляемый 21-ю пользователямиVianet в коммерческом облаке, не-Office 365, управляемый 21-ю пользователямиVianet в коммерческом облаке, и пользователей с лицензией RMS для физических лиц.
  
- IRM с SharePoint (защищенные IRM-сайты и библиотеки) в настоящее время недоступны.
  
- Расширение мобильного устройства для AD RMS в настоящее время не доступно.

- Мобильный [зритель не](/azure/information-protection/rms-client/mobile-app-faq) поддерживается Azure China 21Vianet.

- Область AIP портала Azure недоступна для клиентов в Китае. Используйте [команды PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) вместо выполнения действий на портале, например установки локального сканера и управления заданиями сканирования контента.

## <a name="configure-aip-for-customers-in-china"></a>Настройка AIP для клиентов в Китае

Настройка AIP для клиентов в Китае:
1. [Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)

2. [Настройка шифрования DNS.](#step-2-configure-dns-encryption)

3. [Установка и настройка клиента единой маркировки AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Настройка приложений AIP в Windows.](#step-4-configure-aip-apps-on-windows)

5. [Установка локального сканера AIP и управление заданиями сканирования контента.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Шаг 1. Включить управление правами для клиента

Чтобы шифрование работало правильно, необходимо включить RMS для клиента.

1. Проверьте, включен ли RMS:

    1. Запустите PowerShell в качестве администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Импорт модуля с помощью `Import-Module AipService` .
    4. Подключение к службе с помощью `Connect-AipService -environmentname azurechinacloud` .
    5. Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте, является ли состояние `Enabled` .

2. Если функциональное состояние , `Disabled` запустите `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Шаг 2. Настройка шифрования DNS

Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к китайскому экземпляру службы и загрузке оттуда. Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись SRV DNS с информацией о URL-адресе Azure RMS. Без записи SRV DNS клиентские приложения по умолчанию попытаются подключиться к общедоступным облачным экземплярам и сбой.

Кроме того, существует предположение, что пользователи будут входить в систему с иным имям пользователя, основанным на домене, владельцем клиента (например, ), а не имям `joe@contoso.cn` `onmschina` пользователя (например, `joe@contoso.onmschina.cn` ). Имя домена из имени пользователя используется для перенаправления DNS в правильный экземпляр службы.

#### <a name="configure-dns-encryption---windows"></a>Настройка шифрования DNS - Windows

1. Получите ID RMS:

    1. Запустите PowerShell в качестве администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Подключение к службе с помощью `Connect-AipService -environmentname azurechinacloud` .
    4. `(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ID RMS.

2. Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

    - Служба = `_rmsredir`
    - Протокол = `_http`
    - Имя = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (где GUID — это ID RMS)
    - Приоритет, вес, секунды, TTL = значения по умолчанию

3. Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Это добавит запись в DNS, для проверки которой может потребоваться несколько минут после добавления значения в параметры DNS.

4. Войдите в центр администрирования Microsoft 365 с соответствующими глобальными учетными данными администратора и добавьте домен (например, `contoso.cn` ) для создания пользователей. В процессе проверки могут потребоваться дополнительные изменения DNS. После проверки можно создать пользователей.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Настройка шифрования DNS - Mac, iOS, Android

Войдите в поставщик DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

- Служба = `_rmsdisco`
- Протокол = `_http`
- Имя = `_tcp`
- Target = `api.aadrm.cn`
- Порт = `80`
- Приоритет, вес, секунды, TTL = значения по умолчанию

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Шаг 3. Установка и настройка клиента единой маркировки AIP

Скачайте клиент единой метки AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)

Дополнительные сведения см. в указанных ниже статьях.

- [Документация по AIP](/azure/information-protection/)
- [История и политика поддержки версий AIP](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Требования к системе AIP](/azure/information-protection/requirements)
- [AIP quickstart: Развертывание клиента AIP](/azure/information-protection/quickstart-deploy-client)
- [Руководство администратора AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Руководство по пользователю AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Узнайте о метки конфиденциальности Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>Шаг 4. Настройка приложений AIP в Windows

Приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать их на правильное суверенное облако для Azure China:

- Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Имя = `CloudEnvType`
- Значение = `6` (по умолчанию = 0)
- Тип = `REG_DWORD`

> [!IMPORTANT]
> Убедитесь, что не удаляйте ключ реестра после удаления. Если ключ пустой, неправильный или несуществующий, функциональность будет вести себя как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака). Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Шаг 5. Установка локального сканера AIP и управление заданиями сканирования контента

Установка локального сканера AIP для сканирования сетевых и контентных акций для конфиденциальных данных, а также применения меток классификации и защиты в зависимости от политики организации.

- При создании и настройке приложений Azure AD для команды [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) в области  разрешений API запросов  показана таблица **API,** которая используется моей организацией вместо вкладки API Microsoft. Выберите **API, которые использует моя организация,** чтобы затем выбрать **службы управления** правами Azure.

- При установке сканера и управлении заданиями сканирования контента используйте следующие cmdlets вместо интерфейса портала Azure, который используется коммерческими предложениями:<br><br>

    | Командлет | Описание |
    |--|--|
    | [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Добавляет новый репозиторий в задание проверки контента. |
    | [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Получает сведения о работе по проверке контента. |
    | [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Получает сведения о репозиториях, определенных для задания сканирования контента. |
    | [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Удаляет задание сканирования контента. |
    | [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Удаляет репозиторий из задания проверки контента. |
    | [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Определяет параметры задания сканирования контента. |
    | [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Определяет параметры существующего репозитория в заданиях проверки контента. |
    | | |

> [!TIP]
> При [установке сканера](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)используйте одно и то же имя кластера в команде [Install-AIPScanner,](/powershell/module/azureinformationprotection/install-aipscanner) чтобы связать несколько узлов сканера с тем же кластером. Использование одного и того же кластера для нескольких узлов сканера позволяет нескольким сканерам работать вместе для выполнения сканирования.
> 
> Чтобы получить сведения о кластере, используйте комлет [Get-AIPScannerConfiguration.](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)
> 
Дополнительные сведения см. в том, что такое сканер единой маркировки [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) и управление заданиями сканирования контента только [с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)