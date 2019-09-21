---
title: Добавление фирменной символики Организации в зашифрованные сообщения
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Как глобальный администратор Office 365 вы можете применить фирменную символику вашей организации к зашифрованным сообщениям электронной почты в Организации и содержимому портала шифрования.
ms.openlocfilehash: dd08ffad4a50cafd90f2306645e93e623b8076cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089963"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Добавление фирменной символики организации в зашифрованные сообщения

Как администратор Exchange Online или Exchange Online Protection, вы можете применить фирменную символику компании, чтобы настроить внешний вид сообщений электронной почты Office 365 для шифрования сообщений в Организации и содержимое портала шифрования. С помощью командлетов Windows PowerShell Get – OMEConfiguration и Set – OMEConfiguration можно настроить следующие аспекты просмотра для получателей зашифрованных сообщений электронной почты:
  
- Вводный текст зашифрованного сообщения электронной почты

- Текст заявления об отказе зашифрованного сообщения электронной почты

- Текст, который отображается на портале OME

- Эмблема, отображаемая в сообщении электронной почты и на портале OME

- Цвет фона в сообщении электронной почты и на портале OME

Кроме того, в любое время вы можете восстановить интерфейс по умолчанию.

 Если вы хотите расширить возможности управления, вы можете использовать расширенное шифрование сообщений Office 365 и создать несколько шаблонов для зашифрованных сообщений электронной почты, исходящих из вашей организации. С помощью этих шаблонов можно управлять не только внешним видом и поведением сообщений электронной почты, но и управлять частями конечного пользователя. Например, вы можете указать, какие получатели почты, к которой применен этот шаблон, и кто использует учетные записи Google, Yahoo и Майкрософт, могут использовать эти учетные записи для входа на портал Office 365 для шифрования сообщений. Вы можете использовать шаблоны для выполнения нескольких вариантов использования, таких как:

- Шаблоны для каждого отдела, такие как финансы, продажи и т. д.

- Шаблоны для разных продуктов

- Шаблоны для различных географических регионов или стран

- Следует ли запретить отзыв сообщений электронной почты

- Указывает, следует ли срок действия сообщений электронной почты, отправляемых внешним получателям, через определенное количество дней.

Создав шаблоны, вы можете применить их к зашифрованным сообщениям электронной почты с помощью правил для почтовых ящиков Exchange. Если вы используете расширенное шифрование сообщений Office 365, вы можете отозвать любое электронное письмо, имеющее фирменную символику, с помощью этих шаблонов.
  
||
|:-----|
|Эта статья входит в набор статей, посвященных шифрованию сообщений Office 365. Эта статья предназначена для администраторов и Итпрос. Если вы просто ищете сведения о том, как отправлять или получать зашифрованные сообщения, ознакомьтесь со статьей, посвященной [шифрованию сообщений Office 365 (OME)](ome.md) , и выберите статью, которая наилучшим образом соответствует вашим потребностям.|
||

## <a name="create-branding-templates"></a>Создание шаблонов фирменного стиля

Шаблоны фирменного стиля для вашей организации создаются в Windows PowerShell с помощью командлета New – OMEConfiguration. После создания шаблона необходимо определить части шаблона с помощью командлета Set – OMEConfiguration. Можно создать несколько шаблонов.

![Настраиваемые части электронной почты](media/ome-template-breakout.png)
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции можно найти [в статье подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет New – OMEConfiguration для создания нового шаблона.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. Определите настройки для шаблона, который вы только что определили с помощью командлета Set – OMEConfiguration, как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) , или используйте приведенную ниже таблицу для указания рекомендаций.

|**Настройка этой функции шифрования**|**Используйте эти команды**|
|:-----|:-----|
|Цвет фона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Логотип|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF  <br/> Оптимальный размер файла логотипа: менее 40 КБ  <br/> Оптимальный размер изображения логотипа: 170 x 70 пикселей|
|Текст рядом с именем отправителя и адресом электронной почты|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Текст, который отображается на кнопке "чтение сообщения"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Текст, расположенный над кнопкой "чтение сообщения"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Включение или отключение проверки подлинности с помощью кода одноразового этапа для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Примеры** <br/>Включение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Отключение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Включение или отключение проверки подлинности с помощью удостоверений Microsoft, Google или Yahoo для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Примеры** <br/>Включение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Отключение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>Удаление настроек фирменного стиля с портала OME и электронных сообщений, зашифрованных с помощью OME
  
1. [Подключитесь к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет **Set – OMEConfiguration** , как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Чтобы удалить настройки фирменной символики Организации из значений DisclaimerText, EmailText и PortalText, установите для этого параметра пустую строку `""`. Для всех значений изображений, например Logo, установите значение `"$null"`.

**Параметры настройки шифрования**

**Сброс функции шифрования к тексту и изображению по умолчанию**|**Используйте эти команды**|
|:-----|:-----|
|Текст по умолчанию, сопровождающий зашифрованные сообщения электронной почты.  <br/> Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|Логотип|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|Цвет фона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Создание правила для процесса обработки почты Exchange, которое применяет пользовательскую фирменную символику к зашифрованным сообщениям

Создав шаблон фирменной символики, вы можете создать правила для обработки почтовых ящиков Exchange, которые будут применяться в соответствии с определенными условиями. Такое правило будет применять настраиваемую фирменную символику в следующих сценариях:

- Если сообщение было вручную зашифровано конечным пользователем из Outlook или Outlook в Интернете (прежнее название — Outlook Web App)

- Если сообщение было автоматически зашифровано правилом для почтовых ящиков Exchange или политикой защиты от потери данных в Office 365

Сведения о том, как создать правило для процесса обработки почты Exchange, которое применяет шифрование, можно узнать в статье [Определение правил обработки почтового процесса для шифрования сообщений электронной почты в Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. В веб-браузере с помощью рабочей или учебной учетной записи, которой предоставлены разрешения глобального администратора, [Войдите в Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Выберите плитку **Администратор** .

3. В центре администрирования Microsoft 365 выберите \> **Exchange** **центры администрирования** .

4. В центре администрирования Exchange перейдите к разделу **правила** обработки **почтового процесса** \> и](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> выберите **Новый** ![новый значок **создать новое правило**. Дополнительные сведения об использовании [центра администрирования Exchange можно найти в центре администрирования Exchange в Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. В поле **имя**введите имя правила, например фирменный стиль для отдела продаж.

6. В поле **Применить это правило, если** выберите условие, выберите условие, **которое отправитель находится в Организации** , а также другие необходимые условия из списка доступных условий. Например, может потребоваться применить определенный шаблон фирменной символики к:

     - Все зашифрованные сообщения электронной почты, отправленные участниками отдела финансов
     - Зашифрованные сообщения электронной почты, отправленные с определенным ключевым словом, например "External" или "Partner"
     - Зашифрованные сообщения электронной почты, отправленные на определенный домен

7. В **разделе выполните следующие действия**выберите **изменить безопасность** > сообщений**применение настраиваемой фирменной символики к сообщениям OME**. Затем в раскрывающемся списке выберите шаблон фирменной символики из созданных вами.

8. Необязательно Если вы хотите, чтобы правило обработки почтового ящика также применяло шифрование в дополнение к настраиваемой фирменной символике, **выполните следующие действия**, выберите **изменить безопасность сообщений** , а затем нажмите **применить шифрование и защиту сообщений Office 365**. Выберите шаблон RMS в списке и нажмите кнопку **сохранить**, а затем нажмите кнопку **ОК**.
  
     Список шаблонов включает все шаблоны и параметры по умолчанию, а также пользовательские шаблоны, созданные для использования в Office 365. Если список пуст, убедитесь, что вы настроили шифрование сообщений Office 365 с помощью новых возможностей, как описано в статье [Настройка новых возможностей шифрования сообщений office 365](set-up-new-message-encryption-capabilities.md). Сведения о шаблонах по умолчанию можно узнать в статье [Настройка шаблонов для Azure Information Protection и управление ими](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Сведения о параметре "не **пересылать** " можно узнать в статье не [пересылать сообщения](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Для получения дополнительных сведений о параметре " **только шифрование** " в разделе [шифрование только для сообщений электронной почты](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

     Вы можете выбрать **действие Добавить действие** , если хотите указать другое действие.
