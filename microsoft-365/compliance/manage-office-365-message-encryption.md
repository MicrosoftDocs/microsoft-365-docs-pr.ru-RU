---
title: Управление шифрованием сообщений Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: После завершения настройки шифрования сообщений Office 365 (OME) узнайте, как настроить развертывание несколькими способами.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815436"
---
# <a name="manage-office-365-message-encryption"></a>Управление шифрованием сообщений Office 365

После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами. Например, можно настроить, следует ли включить одноветные  коды прохода, отобразить кнопку "Зашифровать" в Outlook в Интернете и многого другого. В этой статье описано, как это сделать.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Управляйте тем, могут ли получатели учетных записей Google, Yahoo и Microsoft использовать эти учетные записи для входов на портал шифрования сообщений Office 365

При настройках новых возможностей шифрования сообщений Office 365 пользователи в организации могут отправлять сообщения получателям, которые находятся за пределами организации. Если получатель  использует социальный ИД, например учетную запись Google, учетную запись Yahoo или учетную запись Майкрософт, получатель может войти на портал OME с помощью социального ИД. При этом можно разрешить получателям использовать социальные ID для входов на портал OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Управление возможностью получателей использовать социальные ID для входов на портал OME
  
1. [Подключение к Exchange Online с помощью удаленной powerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Выполните Set-OMEConfiguration с параметром SocialIdSignIn следующим образом:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Например, чтобы отключить социальные ИД:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Чтобы включить социальные ИД:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Управление использованием разных кодов прохода для портала шифрования сообщений Office 365

Если получатель сообщения, зашифрованного с помощью OME, не использует Outlook, независимо от учетной записи, используемой получателем, получатель получает ограниченную ссылку на веб-представление, которая позволяет ему прочитать сообщение. Эта ссылка включает одноветный код прохода. Как администратор вы можете решить, могут ли получатели использовать однонаправленные коды для входов на портал OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Управление созданием OME одновейных кодов прохода
  
1. Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите Set-OMEConfiguration с параметром OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Например, чтобы отключить разовые коды проходов:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Чтобы включить разовые коды прохода:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Управление отображением кнопки "Зашифровать" в Outlook в Интернете

Администратор может управлять отображением этой кнопки для конечных пользователей.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Управление тем, отображается ли кнопка "Зашифровать" в Outlook в Интернете
  
1. Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите Set-IRMConfiguration с параметром -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Например, чтобы отключить кнопку **"Зашифровать":**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Чтобы включить **кнопку "Зашифровать":**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Включить расшифровку сообщений электронной почты на стороне службы для пользователей почтовых приложений iOS

Почтовое приложение iOS не может расшифровывать сообщения, защищенные с помощью шифрования сообщений Office 365. Как администратор Microsoft 365 вы можете применять расшифровку на стороне службы для сообщений, доставленных в почтовое приложение iOS. При использовании расшифровки на стороне службы служба отправляет расшифрованную копию сообщения на устройство iOS. На клиентских устройствах хранится расшифрованная копия сообщения. В сообщении также сохраняются сведения о правах на использование, даже если почтовое приложение iOS не применяет клиентские права на использование к пользователю. Пользователь может копировать или печатать сообщение, даже если у него изначально нет прав на это. Однако если пользователь по пытается выполнить действие, которое требует на сервере почты Microsoft 365, например пересылать сообщение, сервер не позволит выполнить это действие, если пользователь изначально не имеет права на использование. Тем не менее конечные пользователи могут обойти ограничение использования "Не пересылать", перена пересылая сообщение из другой учетной записи в почтовом приложении iOS. Независимо от того, настроена ли расшифровка почты на стороне службы, вложения для зашифрованной и защищенной правами почты не могут просматриваться в почтовом приложении iOS.
  
Если вы не разрешаете отправлять расшифрованные сообщения пользователям почтового приложения iOS, пользователи получают сообщение о том, что у них нет прав на просмотр сообщения. По умолчанию расшифровка сообщений электронной почты на стороне службы не включена.
  
Дополнительные сведения и сведения о клиенте см. в сообщении, зашифрованном на [iPhone или iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Управление возможностью просмотра сообщений, защищенных с помощью шифрования сообщений Office 365, для пользователей почтового приложения iOS
  
1. Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите Set-ActiveSyncOrganizations с параметром AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Например, чтобы настроить службу для расшифровки сообщений, прежде чем они будут отправлены неподтвершенным приложениям, например почтовому приложению iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Или, чтобы служба не отправлять расшифрованные сообщения в неподслужимые приложения:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Отдельные политики почтовых ящиков (OWA/ActiveSync) переопрепреют эти параметры (т. е. если для параметра -IRMEnabled задано false в соответствующей политике почтовых ящиков OWA или политике почтовых ящиков ActiveSync, эти конфигурации не будут применяться).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Включить расшифровку вложений электронной почты на стороне службы для почтовых клиентов веб-браузера

Обычно при использовании шифрования сообщений Office 365 вложения шифруются автоматически. Как администратор вы можете применять расшифровку на стороне службы к вложениям электронной почты, скачиваемых пользователями из веб-браузера.
  
При использовании расшифровки на стороне службы служба отправляет расшифрованную копию файла на устройство. Сообщение по-прежнему зашифровано. Вложение электронной почты также хранит сведения о правах на использование, даже если браузер не применяет к пользователю права на использование на стороне клиента. Пользователь может копировать или печатать вложение электронной почты, даже если у него изначально нет прав на это. Однако если пользователь попытается выполнить действие, которое требует от почтового сервера Microsoft 365, например пересылать вложение, сервер не позволит выполнить это действие, если пользователь изначально не имеет права на использование.
  
Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения для зашифрованной и защищенной правами почты в почтовом приложении iOS.
  
Если вы не разрешаете расшифровывать вложения электронной почты (это значение по умолчанию), пользователи получают сообщение о том, что у них нет прав на просмотр вложения.
  
Дополнительные сведения о том, как Microsoft 365 реализует шифрование для сообщений электронной почты и вложений с помощью параметра Encrypt-Only, см. в параметре "Только шифрование" для сообщений [электронной почты.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Управление расшифровкой вложений электронной почты при загрузке из веб-браузера
  
1. Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите Set-IRMConfiguration с параметром DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь загружает их из веб-браузера:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Чтобы настроить службу на то, чтобы оставить зашифрованные вложения электронной почты после загрузки:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Убедитесь, что все внешние получатели используют портал OME для чтения зашифрованной почты

Вы можете использовать настраиваемые шаблоны фирменения, чтобы заставить получателей получать сообщения-оболочки, которые поосят их на чтение зашифрованной электронной почты на портале OME, а не с помощью Outlook или Outlook в Интернете. Это может потребоваться, если вы хотите больше контролировать, как получатели используют почту, которая они получают. Например, если внешние получатели просматривают электронную почту на веб-портале, вы можете установить дату окончания срока действия сообщения и отоискить сообщение. Эти функции поддерживаются только на портале OME. При создании правил потока почты можно использовать параметры "Шифровать" и "Не пересылать".

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Использование пользовательского шаблона для принудительного использования всеми внешними получателями портала OME и зашифрованной электронной почты

1. Используйте учетную запись для работы или учебного заведения, которая имеет разрешения глобального администратора в вашей организации, и запустите сеанс Windows PowerShell подключения к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите New-TransportRule управления:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    где:

   - `mail flow rule name` это имя, которое вы хотите использовать для нового правила потока почты.

   - `option name` is either `Encrypt` or `Do Not Forward` .

   - `template name` это имя, которое вы предоставили пользовательскому шаблону фирменой настройки, например `OME Configuration` .

   Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить Encrypt-Only параметр:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Чтобы зашифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить параметр "Не переадружайте":

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Настройка внешнего вида сообщений электронной почты и портала OME

Дополнительные сведения о настройке OME для организации см. в описании добавления фирменного параметра организации в [зашифрованные сообщения.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей OME

Надеемся, что это не так, но при необходимости отключить новые возможности для OME очень просто. Сначала необходимо удалить все созданные правила потока почты, которые используют новые возможности OME. Сведения об удалении правил потока почты см. в под [управлением правил потока почты.](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx) Затем выполните эти действия в Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей OME
  
1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Если вы  включили кнопку "Зашифровать" в Outlook в Интернете, отключили ее, задав Set-IRMConfiguration с параметром SimplifiedClientAccessEnabled. В противном случае пропустите этот шаг.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Отключив новые возможности OME, задав для параметра AzureRMSLicensingEnabled Set-IRMConfiguration параметру false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
