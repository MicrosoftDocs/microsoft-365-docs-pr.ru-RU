---
title: Поддержка Azure Information Protection для Office 365 под управлением 21Vianet
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
description: Узнайте больше об Azure Information Protection (AIP) для Office 365 под управлением 21Vianet и ее настройке для клиентов в Китае.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099682"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Поддержка Azure Information Protection для Office 365 под управлением 21Vianet

В этой статье освещаются различия между поддержкой Azure Information Protection (AIP) для Office 365 под управлением 21Vianet и коммерческих предложений, а также конкретные инструкции по настройке AIP для клиентов в Китае, включая установку локального сканера AIP и управление заданиями сканирования &mdash; контента.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Различия между AIP для Office 365 под управлением 21Vianet и коммерческими предложениями

Хотя наша цель — предоставить все коммерческие функции клиентам в Китае с нашим предложением AIP для Office 365 под управлением 21Vianet, мы хотим выделить некоторые отсутствующие функции.

Следующий список содержит существующие пробелы между AIP для Office 365 под управлением 21Vianet и нашими коммерческими предложениями с января 2021 г.:

- Управление правами на управление правами на данные (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731.10000 или выше). Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.

- Миграция служба управления правами Active Directory (AD RMS) на AIP в настоящее время недоступна.
  
- Совместное использование защищенных сообщений электронной почты с пользователями в коммерческом облаке поддерживается.
  
- Общий доступ к документам и вложениям электронной почты пользователям в коммерческом облаке в настоящее время не доступен. К ним относятся пользователи Office 365 под управлением 21Vianet в коммерческом облаке, пользователи не из Office 365, управляемые пользователями 21Vianet в коммерческом облаке, а также пользователи с лицензией RMS для физических лиц.
  
- IRM с SharePoint (сайты и библиотеки, защищенные с помощью IRM) в настоящее время не доступен.
  
- Расширение мобильного устройства для AD RMS в настоящее время не доступно.

- Приложение ["Просмотр мобильных устройств"](/azure/information-protection/rms-client/mobile-app-faq) не поддерживается azure China 21Vianet.

- Область AIP портала Azure недоступна для пользователей в Китае. Вместо выполнения действий на портале, таких как установка локального сканера и управление заданиями сканирования контента, используйте команды [PowerShell.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)

## <a name="configure-aip-for-customers-in-china"></a>Настройка AIP для клиентов в Китае

Настройка AIP для клиентов в Китае:
1. [Включить управление правами для клиента.](#step-1-enable-rights-management-for-the-tenant)

2. [Настройка шифрования DNS.](#step-2-configure-dns-encryption)

3. [Установите и настройте клиент унифицированных меток AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Настройка приложений AIP в Windows.](#step-4-configure-aip-apps-on-windows)

5. [Установка локального сканера AIP и управление](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)заданиями сканирования контента. 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Шаг 1. Включить управление правами для клиента

Чтобы шифрование работало правильно, необходимо включить для клиента RMS.

1. Проверьте, включена ли RMS:

    1. Запустите PowerShell от учетной записи администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Импортировать модуль с помощью `Import-Module AipService` .
    4. Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .
    5. Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте `Enabled` состояние.

2. Если это функциональное `Disabled` состояние, запустите `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Шаг 2. Настройка шифрования DNS

Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы в Китае и из нее подключаться к первой загрузке. Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись DNS SRV с информацией об URL-адресе Azure RMS. Без DNS-записи SRV клиентские приложения по умолчанию попытаются подключиться к экземпляру общего облака и не будут работать.

Кроме того, предположим, что пользователи будут входить в систему с помощью имени пользователя, основанного на домене, владельцем клиента (например, ), а не ином пользователем `joe@contoso.cn` `onmschina` (например). `joe@contoso.onmschina.cn` Доменное имя из имени пользователя используется для перенаправления DNS на правильный экземпляр службы.

#### <a name="configure-dns-encryption---windows"></a>Настройка шифрования DNS — Windows

1. Получите ИД RMS:

    1. Запустите PowerShell от учетной записи администратора.
    2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
    3. Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .
    4. `(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ИД RMS.

2. Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

    - Служба = `_rmsredir`
    - Протокол = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (где GUID — это ИД RMS)
    - Приоритет, вес, секунды, TTL = значения по умолчанию

3. Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) При этом в DNS будет добавлена запись, проверка которой может занять несколько минут после добавления значения в параметры DNS.

4. Войдите в Центр администрирования Microsoft 365 с соответствующими учетными данными глобального администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя. В процессе проверки могут потребоваться дополнительные изменения DNS. После проверки пользователи могут быть созданы.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Настройка шифрования DNS — Mac, iOS, Android

Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

- Служба = `_rmsdisco`
- Протокол = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Порт = `80`
- Приоритет, вес, секунды, TTL = значения по умолчанию

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Шаг 3. Установка и настройка клиента унифицированных меток AIP

Скачайте клиент унифицированных меток AIP из [Центра загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)

Дополнительные сведения см. в указанных ниже статьях.

- [Документация по AIP](/azure/information-protection/)
- [История версий AIP и политика поддержки](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Требования к системе AIP](/azure/information-protection/requirements)
- [Краткое развертывание клиента AIP](/azure/information-protection/quickstart-deploy-client)
- [Руководство администратора AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Руководство пользователя по AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Узнайте о метах конфиденциальности Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Шаг 4. Настройка приложений AIP в Windows

Приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать им правильное независимое облако для Azure в Китае:

- Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Значение = `6` (по умолчанию = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Убедитесь, что не удаляйте ключ реестра после удаления. Если ключ пустой, неправильный или несуществующий, функция будет действовать как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака). Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Шаг 5. Установка локального сканера AIP и управление заданиями сканирования контента

Установите локального сканерА AIP, чтобы проверить сетевые и контентные пакеты на конфиденциальные данные, а также применить метки классификации и защиты, настроенные в политике организации.

При установке сканера и управлении заданиями проверки содержимого используйте следующие cmdlets вместо интерфейса портала Azure, который используется коммерческими предложениями:<br><br>

| Командлет | Описание |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Добавляет новый репозиторий в задание проверки содержимого. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Получает сведения о заданиях проверки содержимого. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Получает сведения о репозиториях, определенных для задания сканирования содержимого. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Удаляет задание проверки содержимого. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Удаляет репозиторий из задания сканирования содержимого. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Определяет параметры задания проверки содержимого. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Определяет параметры существующего репозитория в заданиях сканирования содержимого. |

Дополнительные сведения см. в том, что такое унифицированный сканер меток [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) И управление заданиями проверки содержимого [с помощью только PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
