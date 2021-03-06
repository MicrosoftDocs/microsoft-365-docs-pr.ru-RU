---
title: Настройка функции управления правами на доступ к данным для использования локального сервера служб Active Directory Rights Management
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Узнайте, как настроить управление правами на информацию (IRM) в Exchange Online использовать сервер службы управления правами active Directory (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227239"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Настройка функции управления правами на доступ к данным для использования локального сервера служб AD RMS

Для использования в локальном развертывании управление правами на информацию в Exchange Online использует службы Active Directory Rights Management (AD RMS), технологию защиты информации в Windows Server 2008 и более поздней. К сообщению электронной почты применяется шаблон политики прав AD RMS. Права прикрепляются к сообщению, поэтому защита обеспечивается как в сети, так и вне ее, за пределами брандмауэра организации и внутри него.

В этом разделе показано, как настроить управление правами на доступ к данным для использования сервера службы управления правами Active Directory. Сведения об использовании новых возможностей для шифрование сообщений Office 365 с Azure Active Directory и Управление правами Azure см. в шифрование сообщений Office 365 [FAQ](./ome-faq.yml).

Дополнительные сведения об управлении правами на доступ к данным в Exchange Online см. в разделе [Управление правами на доступ к данным в Exchange Online](information-rights-management-in-exchange-online.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Предполагаемое время выполнения задачи: 30 минут.

- Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье "Управление правами на доступ к данным" в статье [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions).

- Сервер службы управления правами Active Directory должен работать под управлением ОС Windows Server 2008 или более поздней версии. Сведения о развертывании службы управления правами Active Directory см. в разделе [Установка кластера службы управления правами Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Сведения об установке и настройке Windows PowerShell и подключении к службе см. в разделе [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Сведения о ярлыках клавиатуры, которые могут применяться к процедурам в этом разделе, см. в разделе [Клавишные](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)ярлыки для центра администрирования Exchange в Exchange Online .

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к участникам форумов, посвященных Exchange. Посетите форумы по таким продуктам: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) или [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="how-do-you-do-this"></a>Как это сделать
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Действие 1. Использование консоли службы управления правами Active Directory для экспорта доверенного домена публикации (TPD) из сервера службы управления правами Active Directory

Первый шаг — это экспорт доверенного домена публикации (TPD) с локального сервера AD RMS в XML-файл. Доверенный домен публикации (TPD) содержит следующие параметры, необходимые для использования функции службы управления правами:

- серверный сертификат лицензиара (SLC), который используется для подписания и шифрования сертификатов и лицензий;

- URL-адреса, используемые для лицензирования и публикации;

- шаблоны политики прав службы управления правами Active Directory, созданные с помощью конкретного серверного сертификата лицензиара (SLC) для данного доверенного домена публикации (TPD).

При импорте доверенного домена публикации он сохраняется и защищается в Exchange Online.

1. Откройте консоль службы управления правами Active Directory и разверните кластер AD RMS.

2. В дереве консоли раскройте узел **Политики доверия**, а затем выберите пункт **Доверенные домены публикации**.

3. В области результатов выберите сертификат домена, который необходимо экспортировать.

4. На панели **Действия** выберите команду **Экспортировать доверенный домен публикации**.

5. В окне **Файл домена публикации** нажмите кнопку **Сохранить как**, чтобы сохранить файл в известном расположении на локальном компьютере. Введите имя файла и обязательно укажите расширение имени файла  `.xml`, а затем нажмите кнопку **Сохранить**.

6. В полях **Пароль** и **Подтверждение пароля** введите надежный пароль, используемый для шифрования файла доверенного домена публикации. Этот пароль потребуется указать при импорте доверенного домена публикации в облачную почтовую организацию.

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Действие 2. Импортируйте TPD в службу Exchange Online с помощью командной консоли Exchange

После экспорта TPD в XML-файл следует импортировать его в Exchange Online. При импорте TPD также импортируются шаблоны службы управления правами Active Directory вашей организации. При импорте первого TPD он становится TPD по умолчанию для вашей организации на основе облака. При импорте другого TPD можно использовать параметр **Default**, чтобы использовать его по умолчанию.

Для импорта TPD выполните в среде Windows PowerShell следующую команду:

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Значения параметров  _ExtranetLicensingUrl_ и  _IntranetLicensingUrl_ можно получить в консоли службы управления правами Active Directory. В дереве консоли выберите кластер AD RMS. В области результатов отобразятся URL-адреса лицензирования. Эти URL-адреса используются почтовыми клиентами при необходимости расшифровки контента и в случае, если Exchange Online требуется определить используемый TPD.

При запуске данной команды потребуется ввести пароль. Введите пароль, указанный при экспорте TPD с сервера AD RMS.

Например, при выполнении следующей команды импортируется TPD с именем "Exported TPD" с помощью XML-файла, экспортированного с сервера службы управления правами Active Directory и сохраненного на рабочем столе учетной записи администратора. Параметр Name используется для указания имени TPD.

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Подробные сведения о синтаксисе и параметрах см. в разделе [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).

#### <a name="how-do-you-know-this-step-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно импортировали TPD, выполните командлет **Get-RMSTrustedPublishingDomain** для извлечения доверенных доменов публикации в вашей организации Exchange Online. Для получения дополнительных сведений см. примеры в разделе [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Действие 3. Распространите шаблон политики прав AD RMS с помощью командной консоли Exchange

После импорта TPD необходимо распространить шаблон политики прав службы управления правами Active Directory. Распределенный шаблон виден Outlook в Интернете (ранее Outlook Web App) пользователям, которые могут применить шаблоны к сообщению электронной почты.

Чтобы получить список всех шаблонов в TPD по умолчанию, выполните следующую команду.

```powershell
Get-RMSTemplate -Type All | fl
```

Если значение параметра  _Type_ равно  `Archived`, шаблон будет недоступен пользователям. Только распределенные шаблоны в TPD по умолчанию доступны в Outlook в Интернете.

Чтобы распространить шаблон, выполните следующую команду.

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Например, при выполнении следующей команды импортируется шаблон "Company Confidential".

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Дополнительные сведения о синтаксисе и параметрах см. в разделах [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) и [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).

**Шаблон «"Не пересылать"»**

При импорте TPD по умолчанию из локальной организации в Exchange Online импортируется один шаблон политики прав службы управления правами Active Directory с именем **Не пересылать**. Этот шаблон автоматически распространяется при импорте TPD по умолчанию. Изменить шаблон **Не пересылать** с помощью командлета **Set-RMSTemplate** нельзя.

Когда к сообщению применяется шаблон **Не пересылать**, прочитать это сообщение смогут только получатели, являющиеся его адресатами. Кроме того, получатели не смогут:

- пересылать сообщение другому пользователю;

- копировать содержимое сообщения.

- и печатать его.

> [!IMPORTANT]
> Шаблон **Не пересылать** не сможет защитить информацию из сообщения от копирования с помощью сторонних программ или камер, а также от простого переписывания.

Можно также создать дополнительные шаблоны политики прав службы управления правами Active Directory на сервере службы управления правами Active Directory в локальной организации в соответствии с требованиями защиты IRM. При создании дополнительных шаблонов политики прав службы управления правами Active Directory следует снова экспортировать TPD с локального сервера службы управления правами Active Directory и обновить TPD в облачной почтовой организации.

#### <a name="how-do-you-know-this-step-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно распространили шаблон политики прав службы управления правами Active Directory, выполните командлет **Get-RMSTemplate** для проверки свойств шаблона. Для получения дополнительных сведений см. примеры в разделе [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Действие 4. Включите управление правами на доступ к данным с помощью командной консоли Exchange

После импорта TPD и распространения шаблона политики прав службы управления правами Active Directory выполните следующую команду, чтобы включить управление правами на доступ к данным для своей облачной почтовой организации.

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Подробные сведения о синтаксисе и параметрах см. в разделе [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).

#### <a name="how-do-you-know-this-step-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно включили управление правами на доступ к данным (IRM), выполните командлет [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) для проверки конфигурации IRM в организации Exchange Online.

## <a name="how-do-you-know-this-task-worked"></a>Как убедиться, что это сработало?
<a name="sectionSection2"> </a>

Чтобы убедиться, что вы успешно импортировали TPD и включили IRM, выполните приведенные ниже действия.

- С помощью командлета **Test-IRMConfiguration** проверьте функциональные возможности IRM. Подробные сведения см. в примере 1 в разделе [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Соберите новое сообщение в Outlook в Интернете iRM-защиты, выбрав параметр **Set permissions** из расширенного меню ![ (Значок Дополнительные ](../media/ITPro-EAC-MoreOptionsIcon.gif) параметры).
