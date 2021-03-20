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
description: После завершения настройки шифрования сообщений Office 365 узнайте, как настроить развертывание несколькими способами.
ms.openlocfilehash: 06e9d22d51c05fe9f7bc4c1a014607feafbf2dba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908189"
---
# <a name="manage-office-365-message-encryption"></a>Управление шифрованием сообщений Office 365

После завершения настройки шифрования сообщений Office 365 можно настроить конфигурацию развертывания несколькими способами. Например, можно настроить, включить ли одно время коды пропусков, отобразить кнопку **Шифровать** в Outlook в Интернете и другие. Задачи в этой статье описывают, как.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Управление, могут ли получатели учетных записей Google, Yahoo и Microsoft Использовать эти учетные записи для входов на портал шифрования сообщений Office 365

При настройках новых возможностей шифрования сообщений Office 365 пользователи в организации могут отправлять сообщения получателям, которые находятся за пределами организации. Если получатель использует социальный *ID,* например учетную запись Google, учетную запись Yahoo или учетную запись Майкрософт, получатель может войти на портал OME с социальным ИД. Если вы хотите, вы можете не разрешать получателям использовать социальные ID для регистрации на портале OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Управление тем, могут ли получатели использовать социальные ID для регистрации на портале OME
  
1. [Подключение к Exchange Online с помощью удаленной powerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните Set-OMEConfiguration с параметром SocialIdSignIn следующим образом:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Например, отключение социальных ID:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Чтобы включить социальные ID:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Управление использованием кодов одновеких пропусков для портала шифрования сообщений Office 365

Если получатель сообщения, зашифрованного OME, не использует Outlook, независимо от учетной записи, используемой получателем, получатель получает ограниченную ссылку веб-просмотра, которая позволяет ему читать сообщение. Эта ссылка включает в себя код пропуска один раз. В качестве администратора вы можете решить, могут ли получатели использовать одно время коды пропусков для регистрации на портале OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Управление созданием кодов одновекового пропуска OME
  
1. Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации и запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-OMEConfiguration с параметром OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Например, отключение одновеких кодов пропусков:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Чтобы включить коды одновеких пропусков:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Управление отображением кнопки Шифрование в Outlook в Интернете

В качестве администратора можно управлять отображением этой кнопки конечным пользователям.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Управление тем, появится ли кнопка Шифровка в Outlook в Интернете
  
1. Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации и запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-IRMConfiguration с параметром -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Например, чтобы отключить кнопку **Шифрование:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Чтобы включить **кнопку Шифровать:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Включить расшифровку сообщений электронной почты на стороне службы для пользователей почтовых приложений iOS

Почтовое приложение iOS не может расшифровать сообщения, защищенные шифрованием сообщений Office 365. Как администратор Microsoft 365 вы можете применить расшифровку на стороне службы для сообщений, доставленных в почтовое приложение iOS. При использовании расшифровки на стороне службы служба отправляет расшифрованную копию сообщения на устройство iOS. Устройство клиента хранит расшифровку сообщения. В сообщении также сохраняются сведения о правах на использование, несмотря на то, что почтовое приложение iOS не применяет к пользователю права на использование с клиентской стороны. Пользователь может копировать или печатать сообщение, даже если у него изначально не было прав на это. Однако если пользователь пытается выполнить действие, которое требует почтового сервера Microsoft 365, например пересылать сообщение, сервер не разрешит действие, если пользователь изначально не имеет права на использование. Тем не менее конечные пользователи могут обойти ограничение использования "Не перенадвигать", пересылая сообщение из другой учетной записи в почтовом приложении iOS. Независимо от того, настроена ли расшифровка почты на стороне службы, вложения в зашифрованную и защищенную правами почту нельзя просматривать в приложении для почты iOS.
  
Если вы не разрешаете отправлять расшифрованные сообщения пользователям почтовых приложений iOS, пользователи получают сообщение о том, что у них нет прав на просмотр сообщения. По умолчанию расшифровка сообщений электронной почты на стороне службы не включена.
  
Дополнительные сведения и сведения о клиентских впечатлениях см. в обзоре зашифрованных сообщений на [iPhone или iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Управление тем, могут ли пользователи почтовых приложений iOS просматривать сообщения, защищенные шифрованием сообщений Office 365
  
1. Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации и запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-ActiveSyncOrganizations с параметром AllowRMSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Например, настроить службу для расшифровки сообщений перед их отправлением в незасвеченные приложения, например в почтовое приложение iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Или, чтобы настроить службу, чтобы не отправлять расшифрованные сообщения в незасвеченные приложения:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Отдельные политики почтовых ящиков (OWA/ActiveSync) переопределяют эти параметры (например, если в соответствующей политике почтовых ящиков OWA или ActiveSync эти конфигурации не применяются).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Включить расшифровку вложений электронной почты на стороне службы для почтовых клиентов веб-браузера

Обычно при использовании шифрования сообщений Office 365 вложения автоматически шифруются. В качестве администратора можно применять расшифровку на стороне службы для вложений электронной почты, скачиваемых пользователями из веб-браузера.
  
При использовании расшифровки на стороне службы служба отправляет расшифрованную копию файла на устройство. Сообщение по-прежнему шифруется. Вложение электронной почты также хранит сведения о правах на использование, даже если браузер не применяет к пользователю права использования на стороне клиента. Пользователь может копировать или печатать вложение электронной почты, даже если у него изначально не было прав на это. Однако если пользователь попытается выполнить действие, которое требует почтового сервера Microsoft 365, например пересылание вложения, сервер не разрешит действие, если пользователь изначально не имеет права на использование.
  
Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения для зашифрованной и защищенной правами почты в почтовом приложении iOS.
  
Если вы не разрешаете расшифровывать вложения электронной почты, то по умолчанию пользователи получают сообщение, в котором говорится, что у них нет прав на просмотр вложения.
  
Дополнительные сведения о том, как Microsoft 365 реализует шифрование для электронных писем и вложений электронной почты с помощью Encrypt-Only, см. в варианте [Encrypt-Only для электронных писем.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Управление расшифровкой вложений электронной почты при загрузке из веб-браузера
  
1. Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации и запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите Set-IRMConfiguration с параметром DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь скачивает их из веб-браузера:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Чтобы настроить службу, чтобы оставить зашифрованные вложения электронной почты по мере их загрузки:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Убедитесь, что все внешние получатели используют портал OME для чтения зашифрованной почты

Вы можете использовать настраиваемые шаблоны брендинга, чтобы заставить получателей получать почту-оболочку, которая направляет их на чтение зашифрованной электронной почты на портале OME вместо использования Outlook или Outlook в Интернете. Это может потребоваться, если вы используете более полный контроль над тем, как получатели используют получаемую почту. Например, если внешние получатели просматривают электронную почту на веб-портале, можно установить дату истечения срока действия электронной почты и отоискить ее. Эти функции поддерживаются только через портал OME. При создании правил потока почты можно использовать параметр Шифровать и не переададовать.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Используйте настраиваемый шаблон, чтобы заставить всех внешних получателей использовать портал OME и зашифрованную электронную почту.

1. Используйте учетную запись для работы или школы с глобальными разрешениями администратора в организации и запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    где:

   - `mail flow rule name` это имя, которое необходимо использовать для нового правила потока почты.

   - `option name` является либо `Encrypt` `Do Not Forward` или .

   - `template name` это имя, которое вы дали пользовательский шаблон брендинга, например `OME Configuration` .

   Чтобы шифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить Encrypt-Only:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Чтобы шифровать все внешние сообщения электронной почты с помощью шаблона "Конфигурация OME" и применить параметр "Не переадружайте":

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Настройка внешнего вида сообщений электронной почты и портала OME

Подробные сведения о том, как настроить OME для организации, см. в статью Добавление бренда организации в [зашифрованные сообщения.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей для OME

Мы надеемся, что до этого не доймет, но если потребуется, отключить новые возможности для OME очень просто. Сначала необходимо удалить все созданные правила потока почты, которые используют новые возможности OME. Сведения об удалении правил потока почты см. в сообщении [Управление правилами потока почты.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) Затем выполните эти действия в Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей для OME
  
1. С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Если вы включили кнопку **Шифровать** в Outlook в Интернете, отключим ее, заработав Set-IRMConfiguration с параметром SimplifiedClientAccessEnabled. В противном случае пропустите этот шаг.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Отключение новых возможностей для OME путем запуска Set-IRMConfiguration с параметром AzureRMSLicensingEnabled, заданным как false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```