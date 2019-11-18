---
title: Управление шифрованием сообщений Office 365
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
description: После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами. Например, вы можете включить одноразовые коды проходов, отобразить кнопку Защита в Outlook в Интернете и многое другое. Задачи, описанные в этой статье, описывают, как.
ms.openlocfilehash: 780be179485fa18f7e0da0fabc7bb5365238da94
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38687381"
---
# <a name="manage-office-365-message-encryption"></a>Управление шифрованием сообщений Office 365

После завершения настройки шифрования сообщений Office 365 (OME) можно настроить конфигурацию развертывания несколькими способами. Например, можно включить одноразовые коды проходов, отобразить кнопку **шифрования** в Outlook в Интернете и т. д. Задачи, описанные в этой статье, описывают, как.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Управление тем, могут ли получатели учетной записи Google, Yahoo и Майкрософт использовать эти учетные записи для входа на портал Office 365 для шифрования сообщений

Когда вы настраиваете новые возможности шифрования сообщений Office 365, пользователи в организации могут отправлять сообщения получателям, находящимся за пресроком вашей организации Office 365. Если получатель использует *социальные идентификаторы* , такие как учетная запись Google, учетная запись Yahoo или учетная запись Майкрософт, получатель может войти на портал OME с помощью социальных идентификаторов. При необходимости вы можете запретить получателям использовать социальные идентификаторы для входа на портал OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Чтобы управлять тем, могут ли получатели использовать социальные идентификаторы для входа на портал OME
  
1. [Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Выполните командлет Set – OMEConfiguration с параметром СоЦиалидсигнин следующим образом:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Например, чтобы отключить социальные идентификаторы:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Чтобы включить социальные идентификаторы:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Управление использованием кодов одноразовых проходов для портала шифрования сообщений Office 365

Если получатель сообщения, зашифрованного с помощью OME, не использует Outlook независимо от учетной записи, используемой получателем, получатель получает ссылку на веб-просмотр в ограниченном времени, которая позволяет читать сообщение. Эта ссылка включает однократный код этапа. Как администратор вы можете определить, могут ли получатели использовать коды одноразовых проходов для входа на портал OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Управление созданием одноразовых кодов этапа OME
  
1. Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Выполните командлет Set – OMEConfiguration с параметром Отпенаблед:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Например, чтобы отключить однократные коды прохода:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Чтобы включить однократные коды прохода:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Управление отображением кнопки шифрования в Outlook в Интернете

Как администратор, вы можете управлять тем, отображается ли эта кнопка для конечных пользователей.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Управление отображением кнопки "шифровать" в Outlook в Интернете
  
1. Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Выполните командлет Set – IRMConfiguration с параметром – Симплифиедклиентакцессенаблед:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Например, чтобы отключить кнопку " **шифровать** ":

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Чтобы включить кнопку " **шифровать** ":

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Включение расшифровки сообщений электронной почты на стороне службы для пользователей почтового приложения для iOS

Почтовое приложение iOS не может расшифровывать сообщения, защищенные с помощью шифрования сообщений Office 365. Как администратор Office 365, вы можете применять расшифровку на стороне службы для сообщений, доставляемых в почтовое приложение iOS. Если вы решили использовать расшифровку на стороне службы, служба отправляет расшифрованную копию сообщения на устройство iOS. Клиентское устройство сохраняет расшифрованную копию сообщения. Кроме того, в сообщении хранятся сведения о правах на использование, даже если почтовое приложение iOS не применяет к пользователю права на использование на стороне клиента. Пользователь может скопировать или напечатать сообщение, даже если у них изначально нет прав на это. Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Office 365, например переслать сообщение, сервер не разрешил действие, если пользователь изначально не имел право на использование. Тем не менее, конечные пользователи могут обойти ограничение использования "не пересылать", пересылая сообщение из другой учетной записи в почтовом приложении iOS. Независимо от того, настроена ли расшифровка почты на стороне службы, вложения в зашифрованные и защищенные правами сообщения не могут быть просмотрены в почтовом приложении iOS.
  
Если вы решили не разрешать отправку расшифрованных сообщений пользователям почтовых приложений iOS, пользователи получат сообщение о том, что у них нет прав на просмотр сообщения. По умолчанию Расшифровка сообщений электронной почты на стороне службы не включена.
  
Более подробную информацию и представление интерфейса взаимодействия с клиентом можно узнать в статье [Просмотр зашифрованных сообщений на iPhone или iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Управление тем, могут ли пользователи почтового приложения iOS просматривать сообщения, защищенные с помощью шифрования сообщений Office 365
  
1. Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Выполните командлет Set – Активесинкорганизатионс с параметром Алловрмссуппортфоруненлигхтенедаппс:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Например, чтобы настроить службу для расшифровки сообщений перед их отправкой в приложения уненлигхтенед, такие как почтовое приложение для iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Или, чтобы настроить службу так, чтобы она не отправляла расшифрованные сообщения в приложения уненлигхтенед:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Индивидуальные политики почтовых ящиков (OWA/ActiveSync) переопределяют эти параметры (например, если для параметра-IRMEnabled задано значение false в соответствующей политике почтовых ящиков OWA или политика почтовых ящиков ActiveSync, то эти конфигурации не применяются).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Включение расшифровки вложений электронной почты на стороне службы для почтовых клиентов веб-браузеров

Как правило, при использовании шифрования сообщений Office 365 вложения автоматически шифруются. Как администратор Office 365, вы можете применять расшифровку на стороне службы для вложений электронной почты, которые пользователи скачивают из веб-браузера.
  
При использовании расшифровки на стороне службы Служба отправляет расшифрованную копию файла на устройство. Сообщение все еще зашифровано. Вложение электронной почты также хранит сведения о правах на использование, несмотря на то, что браузер не применяет к пользователю права на использование на стороне клиента. Пользователь может копировать или печатать вложение электронной почты, даже если у них изначально нет прав на это. Тем не менее, если пользователь попытается выполнить действие, требующее наличия почтового сервера Office 365, например переслать вложение, сервер не разрешил действие, если пользователь изначально не имел право на использование.
  
Независимо от того, настроена ли расшифровка вложений на стороне службы, пользователи не могут просматривать вложения в зашифрованные сообщения и сообщения, защищенные правами, в почтовом приложении iOS.
  
Если вы не разрешите расшифровывать вложенные сообщения электронной почты (по умолчанию), пользователи получат сообщение о том, что у них нет прав на просмотр вложения.
  
Для получения дополнительных сведений о том, как Office 365 внедряет шифрование для сообщений электронной почты и вложений электронной почты с помощью параметра только шифрование, в разделе только [шифрование для сообщений](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) электронной почты.
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Чтобы управлять расшифровкой вложений электронной почты при загрузке из веб-браузера
  
1. Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Выполните командлет Set – IRMConfiguration с параметром Декриптаттачментфромпортал:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   Например, чтобы настроить службу для расшифровки вложений электронной почты, когда пользователь загрузит их из веб-браузера, выполните следующие действия:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   Чтобы настроить службу для выхода из зашифрованных вложений электронной почты во время загрузки, выполните указанные ниже действия.

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>Убедитесь, что все внешние получатели используют портал OME для чтения шифрованной почты — только расширенное шифрование сообщений в Office 365

Если вы используете расширенное шифрование сообщений Office 365, вы можете использовать настраиваемые шаблоны фирменной символики, чтобы заставить получателей получать почтовую почту, которая направляет им возможность читать зашифрованную электронную почту на портале OME, а не использовать Outlook или Outlook в Интернете. Это может потребоваться, если вы хотите лучше контролировать, как получатели используют полученные сообщения. Например, если внешние получатели просматривают электронную почту на веб-портале, вы можете задать дату истечения срока действия для электронной почты и отозвать электронную почту. Эти функции поддерживаются только на портале OME. При создании правил для почтового процесса можно использовать параметр шифрования и параметр "не пересылать".

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>Создание настраиваемого шаблона для принудительного использования портала OME всеми внешними получателями, а для шифрования электронной почты — ревокабле и истечения срока действия в течение 7 дней

1. Используйте рабочую или учебную учетную запись с разрешениями глобального администратора в организации Office 365 и запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Запустите командлет New – OMEConfiguration:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   где `template name` — это имя, которое вы хотите использовать для шаблона настраиваемого фирменного стиля Office 365. For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. Запустите командлет New – TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    где:

   - `mail flow rule name`— Это имя, которое вы хотите использовать для нового правила для почтового процесса.

   - `option name`может иметь `Encrypt` значение `Do Not Forward`или.

   - `template name`— Это имя, которое вы присвоили настраиваемому шаблону фирменной символики, например `One week expiration`.

   Чтобы зашифровать все внешние сообщения с помощью шаблона "срок действия одной недели" и применить параметр только шифрование:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   Чтобы зашифровать все внешние сообщения с помощью шаблона "срок действия одной недели" и применить параметр "не пересылать":

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Настройка внешнего вида сообщений электронной почты и портала OME

Подробные сведения о том, как настроить OME для вашей организации, можно найти [в статье Добавление фирменной символики вашей организации в зашифрованные сообщения](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей для OME

Мы надеемся, что она не поступила, но если вам необходимо отключить новые возможности для OME, очень просто. Сначала необходимо удалить все созданные вами правила для процесса обработки почты, в которых используются новые возможности OME. Сведения об удалении правил для процесса обработки почты приведены в разделе [Управление правилами](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)обработки почты. Затем выполните указанные ниже действия в Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Отключение новых возможностей для OME
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Если вы включили кнопку **шифровать** в Outlook в Интернете, отключите ее, выполнив командлет Set-IRMConfiguration с параметром симплифиедклиентакцессенаблед. В противном случае пропустите этот шаг.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Отключите новые возможности для OME, выполнив командлет Set – IRMConfiguration с параметром Азурермслиценсинженаблед, равным false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
