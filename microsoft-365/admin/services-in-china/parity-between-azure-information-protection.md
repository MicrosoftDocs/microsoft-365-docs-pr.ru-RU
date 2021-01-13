---
title: Четность между Azure Information Protection для Office 365 под управлением 21Vianet и коммерческими предложениями
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840305"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Четность между Azure Information Protection для Office 365 под управлением 21Vianet и коммерческими предложениями

Хотя наша цель — предоставить все коммерческие функции клиентам в Китае с помощью нашей службы Azure Information Protection (AIP) для Office 365 под управлением 21Vianet, мы хотим выделить некоторые отсутствующие функции.

В следующем списке содержатся существующие пробелы между Azure Information Protection для Office 365 под управлением 21Vianet и нашими коммерческими предложениями с января 2021 г.:

- Управление правами на управление правами на данные (IRM) поддерживается только для приложений Microsoft 365 для предприятий (сборка 11731.10000 или выше). Office 2010, Office 2013 и другие версии Office 2016 не поддерживаются.

- Миграция служба управления правами Active Directory (AD RMS) в Azure Information Protection в настоящее время недоступна.
  
- Общий доступ к защищенным электронным письмам пользователям в коммерческом облаке поддерживается.
  
- Общий доступ к документам и вложениям электронной почты пользователям в коммерческом облаке в настоящее время не доступен. К ним относятся пользователи Office 365 под управлением 21Vianet в коммерческом облаке, пользователи не из Office 365, управляемые пользователями 21Vianet в коммерческом облаке, а также пользователи с лицензией RMS для физических лиц.
  
- IRM с SharePoint (сайты и библиотеки, защищенные с помощью IRM) в настоящее время не доступен.
  
- Расширение мобильного устройства для AD RMS в настоящее время не доступно.

- Приложение ["Просмотр мобильных устройств"](/azure/information-protection/rms-client/mobile-app-faq) не поддерживается azure China 21Vianet.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Настройка Azure Information Protection для клиентов в Китае

### <a name="enable-rights-management-for-the-tenant"></a>Включить управление правами для клиента

Чтобы шифрование работало правильно, необходимо включить для клиента RMS.

- Проверьте, включена ли RMS:
  1. Запустите PowerShell от учетной записи администратора.
  2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
  3. Импорт модуля с помощью `Import-Module AipService` .
  4. Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .
  5. Запустите `(Get-AipServiceConfiguration).FunctionalState` и проверьте `Enabled` состояние.

- Если это функциональное `Disabled` состояние, запустите `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>Конфигурация DNS для шифрования (Windows)

Чтобы шифрование работало правильно, клиентские приложения Office должны подключаться к экземпляру службы в Китае и из нее подключаться к первой загрузке. Чтобы перенаправить клиентские приложения в нужный экземпляр службы, администратор клиента должен настроить запись DNS SRV с информацией об URL-адресе Azure RMS. Без DNS-записи SRV клиентские приложения по умолчанию попытаются подключиться к экземпляру общего облака и не будут работать.

Кроме того, предположим, что пользователи будут входить с помощью имени пользователя, основанного на домене, владельцем клиента (например, ), а не ином пользователем `joe@contoso.cn` `onmschina` (например). `joe@contoso.onmschina.cn` Доменное имя из имени пользователя используется для перенаправления DNS на правильный экземпляр службы.

- Получите ИД RMS:
  1. Запустите PowerShell от учетной записи администратора.
  2. Если модуль AIPService не установлен, запустите `Install-Module AipService` .
  3. Подключите службу с помощью `Connect-AipService -environmentname azurechinacloud` .
  4. `(Get-AipServiceConfiguration).RightsManagementServiceId`Запустите, чтобы получить ИД RMS.

- Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.
  - Служба = `_rmsredir`
  - Протокол = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (где GUID — это ИД RMS)
  - Приоритет, вес, секунды, TTL = значения по умолчанию

- Связать пользовательский домен с клиентом на [портале Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Это добавит запись в DNS, проверка которой может занять несколько минут после добавления значения в параметры DNS.

- Войдите в Центр администрирования Microsoft 365 с соответствующими учетными данными глобального администратора и добавьте домен (например, `contoso.cn` ) для создания пользователя. В процессе проверки могут потребоваться дополнительные изменения DNS. После проверки пользователи могут быть созданы.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Конфигурация DNS для шифрования (Mac, iOS, Android)

Войдите к поставщику DNS, перейдите к настройкам DNS для домена и добавьте новую запись SRV.

- Служба = `_rmsdisco`
- Протокол = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Порт = `80`
- Приоритет, вес, секунды, TTL = значения по умолчанию

### <a name="aip-client-configuration"></a>Конфигурация клиента AIP

Унифицированный клиент AIP можно скачать в [Центре загрузки Майкрософт.](https://www.microsoft.com/download/details.aspx?id=53018)

Дополнительные сведения см. в указанных ниже статьях.

- [Документация по Azure Information Protection](/azure/information-protection/)
- [История версий AIP и политика поддержки](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Требования к системе AIP](/azure/information-protection/requirements)
- [Краткое развертывание клиента AIP](/azure/information-protection/quickstart-deploy-client)
- [Руководство администратора AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Руководство пользователя по AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Узнайте о метах конфиденциальности Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>Конфигурация приложений AIP (только для клиента унифицированных меток)

Для решения унифицированных меток приложениям AIP в Windows необходим следующий ключ реестра, чтобы указать им правильное независимое облако для Azure в Китае:

- Узел реестра = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Значение = `6` (по умолчанию = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Убедитесь, что не удаляйте ключ реестра после удаления. Если ключ пустой, неправильный или несуществующий, функция будет действовать как значение по умолчанию (значение по умолчанию = 0 для коммерческого облака). Если ключ пустой или неправильный, в журнал также добавляется ошибка печати.

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Управление заданиями проверки контента Azure Information Protection

Чтобы управлять заданиями сканирования контента Azure Information Protection на сервере сканера Azure в Китае, используйте вместо портала Azure следующие cmdlets:<br><br>

| Командлет | Описание |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Добавляет новый репозиторий в задание проверки содержимого. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Получает сведения о вашем задание проверки содержимого. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Получает сведения о репозиториях, определенных для задания сканирования содержимого. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Удаляет задание проверки содержимого. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Удаляет репозиторий из задания сканирования содержимого. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Определяет параметры задания проверки содержимого. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Определяет параметры существующего репозитория в заданиях сканирования содержимого. |

Дополнительные сведения см. в под [управление заданиями проверки содержимого только с помощью PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)