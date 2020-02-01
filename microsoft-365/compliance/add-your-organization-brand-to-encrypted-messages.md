---
title: Добавление фирменной символики Организации в зашифрованные сообщения
f1.keywords:
- NOCSH
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
ms.openlocfilehash: b4712edd86099b1c382ef02ca54520b68a54614e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594030"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Добавление фирменной символики организации в зашифрованные сообщения

Как администратор Exchange Online или Exchange Online Protection, вы можете применить фирменную символику компании, чтобы настроить внешний вид сообщений электронной почты Office 365 для шифрования сообщений в Организации и содержимое портала шифрования. С помощью командлетов Windows PowerShell Get – OMEConfiguration и Set – OMEConfiguration можно настроить следующие аспекты просмотра для получателей зашифрованных сообщений электронной почты:
  
- Вводный текст зашифрованного сообщения электронной почты

- Текст заявления об отказе зашифрованного сообщения электронной почты

- Текст, который отображается на портале OME

- Логотип, который отображается в сообщении электронной почты и на портале OME, а также указывает, следует ли использовать логотип.

- Цвет фона в сообщении электронной почты и на портале OME

Кроме того, в любое время вы можете восстановить интерфейс по умолчанию.

Если вы хотите расширить возможности управления, вы можете использовать расширенное шифрование сообщений Office 365 и создать несколько шаблонов для зашифрованных сообщений электронной почты, исходящих из вашей организации. С помощью этих шаблонов можно управлять не только внешним видом и поведением сообщений электронной почты, но и управлять частями конечного пользователя. Например, можно указать, будут ли Получатели почты, к которым применен этот шаблон, и пользователи, использующие учетные записи Google, Yahoo и Майкрософт, использовать эти учетные записи для входа на портал Office 365 для шифрования сообщений. Вы можете использовать шаблоны для выполнения нескольких вариантов использования, таких как:

- Шаблоны для каждого отдела, такие как финансы, продажи и т. д.

- Шаблоны для разных продуктов

- Шаблоны для различных географических регионов или стран

- Следует ли разрешить отзыв сообщений электронной почты

- Следует ли срок действия сообщений электронной почты, отправляемых внешним получателям, через определенное количество дней.

Создав шаблоны, вы можете применить их к зашифрованным сообщениям электронной почты с помощью правил для почтовых ящиков Exchange. Если вы используете расширенное шифрование сообщений Office 365, вы можете отозвать любое электронное письмо, имеющее фирменную символику, с помощью этих шаблонов.

## <a name="work-with-ome-branding-templates"></a>Работайте с шаблонами фирменной символики OME

В шаблоне фирменной символики можно изменить несколько компонентов. Шаблон по умолчанию можно изменить, но не удалить. При наличии расширенного шифрования сообщений можно также создавать, изменять и удалять настраиваемые шаблоны. Используйте Windows PowerShell для работы с одним шаблоном фирменного стиля за раз. Чтобы использовать эти командлеты, вам потребуется рабочая или учебная учетная запись с правами глобального администратора в организации Office 365.

- [Set — OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-omeconfiguration) — изменить шаблон фирменной символики по умолчанию или созданный пользовательский шаблон фирменной символики.
- [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) — создание нового шаблона фирменного стиля, только расширенного шифрования сообщений.
- [Remove – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration) — удалить настраиваемый шаблон фирменного стиля, только расширенное шифрование сообщения. Шаблон фирменной символики по умолчанию удалить невозможно.
  
## <a name="modify-an-ome-branding-template"></a>Изменение шаблона фирменной символики OME

Используйте Windows PowerShell, чтобы изменить один шаблон фирменного стиля за раз. При наличии расширенного шифрования сообщений можно также создавать, изменять и удалять настраиваемые шаблоны.

1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Измените шаблон с помощью командлета Set – OMEConfiguration, как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) , или используйте приведенную ниже графику и таблицу, чтобы получить рекомендации.

![Настраиваемые части электронной почты](media/ome-template-breakout.png)

|**Настройка этой функции шифрования**|**Используйте эти команды**|
|:-----|:-----|
|Цвет фона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Логотип|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF  <br/> Оптимальный размер файла эмблемы: менее 40 КБ  <br/> Оптимальный размер изображения логотипа: 170x70 пикселей. Если изображение превышает эти размеры, служба изменяет размер логотипа для отображения на портале. Служба не изменяет сам графический файл. Для достижения лучших результатов используйте оптимальный размер.|
|Текст рядом с именем отправителя и адресом электронной почты|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Текст, который отображается на кнопке "чтение сообщения"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Текст, расположенный над кнопкой "чтение сообщения"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Включение или отключение проверки подлинности с помощью кода одноразового этапа для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Примеры:** <br/>Включение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Отключение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Включение или отключение проверки подлинности с помощью удостоверений Microsoft, Google или Yahoo для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Примеры:** <br/>Включение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Отключение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Создание шаблона фирменной символики OME (расширенное шифрование сообщений)

Если вы используете расширенное шифрование сообщений Office 365, вы можете создать настраиваемые шаблоны фирменного стиля для своей организации с помощью командлета [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) . После создания шаблона измените шаблон с помощью командлета Set – OMEConfiguration, как описано в статье [изменение шаблона фирменной символики OME](#modify-an-ome-branding-template). Можно создать несколько шаблонов.

Чтобы создать новый настраиваемый шаблон фирменной символики:

1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) для создания нового шаблона.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Возврат к исходным значениям шаблона фирменной символики по умолчанию

Чтобы удалить все изменения из шаблона по умолчанию, включая настройки фирменного стиля и т. д., выполните указанные ниже действия.
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет **Set – OMEConfiguration** , как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Чтобы удалить настройки фирменной символики Организации из значений DisclaimerText, EmailText и PortalText, установите для этого параметра пустую строку `""`. Для всех значений изображений, например Logo, установите значение `"$null"`.

   В следующей таблице описываются параметры настройки шифрования по умолчанию.

   **Сброс функции шифрования к тексту и изображению по умолчанию**|**Используйте эти команды**|
   |:-----|:-----|
   |Текст по умолчанию, сопровождающий зашифрованные сообщения электронной почты.  <br/> Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Логотип|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Цвет фона|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Пример возврата к значению по умолчанию:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Удаление настраиваемого шаблона фирменного стиля (расширенного шифрования сообщений)

Вы можете удалять и удалять только созданные вами шаблоны фирменного стиля. Шаблон фирменной символики по умолчанию удалить невозможно.

Чтобы удалить настраиваемый шаблон фирменной символики:
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в организации Office 365 запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет **Remove – OMEConfiguration** следующим образом:

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Дополнительные сведения см. в разделе [Remove – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Создание правила для процесса обработки почты Exchange, которое применяет настраиваемую фирменную символику к зашифрованным сообщениям электронной почты

После того как вы изменяли шаблон по умолчанию или создали новые шаблоны фирменного стиля, вы можете создать правила для почтовых ящиков Exchange, чтобы применить собственную фирменную символику на основе определенных условий. Такое правило будет применять настраиваемую фирменную символику в следующих сценариях:

- Если пользователь вручную зашифровал сообщение из Outlook или Outlook в Интернете (прежнее название — Outlook Web App)

- Если сообщение было автоматически зашифровано правилом для почтовых ящиков Exchange или политикой защиты от потери данных в Office 365

Сведения о том, как создать правило для процесса обработки почты Exchange, которое применяет шифрование, можно узнать в статье [Определение правил обработки почтового процесса для шифрования сообщений электронной почты в Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. В веб-браузере с помощью рабочей или учебной учетной записи, которой предоставлены разрешения глобального администратора, [Войдите в Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Выберите плитку **Администратор** .

3. В центре администрирования Microsoft 365 выберите \> **Exchange** **центры администрирования** .

4. В центре администрирования Exchange перейдите к разделу **правила** обработки **почтового процесса** \> и](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> выберите **Новый** ![новый значок **создать новое правило**. Дополнительные сведения об использовании [центра администрирования Exchange можно найти в центре администрирования Exchange в Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. В поле **имя**введите имя правила, например фирменный стиль для отдела продаж.

6. В поле **Применить это правило, если**выберите условие, **которое отправитель находится в Организации** , а также другие необходимые условия из списка доступных условий. Например, может потребоваться применить определенный шаблон фирменной символики к:

   - Все зашифрованные сообщения электронной почты, отправленные участниками отдела финансов
   - Зашифрованные сообщения электронной почты, отправленные с определенным ключевым словом, например "External" или "Partner"
   - Зашифрованные сообщения электронной почты, отправленные на определенный домен

7. В **разделе выполните следующие действия**выберите **изменить безопасность** > сообщений**применение настраиваемой фирменной символики к сообщениям OME**. Затем в раскрывающемся списке выберите шаблон фирменной символики из созданного или измененного.

8. Необязательно Если вы хотите, чтобы правило обработки почтового ящика применяло шифрование в дополнение к настраиваемой фирменной символике, **выполните следующие действия**, выберите **изменить безопасность сообщений**, а затем нажмите **применить шифрование и защиту сообщений Office 365**. Выберите шаблон RMS в списке и нажмите кнопку **сохранить**, а затем нажмите кнопку **ОК**.
  
   Список шаблонов включает все шаблоны и параметры по умолчанию, а также пользовательские шаблоны, созданные для использования в Office 365. Если список пуст, убедитесь, что вы настроили шифрование сообщений Office 365 с помощью новых возможностей, как описано в статье [Настройка новых возможностей шифрования сообщений office 365](set-up-new-message-encryption-capabilities.md). Сведения о шаблонах по умолчанию можно узнать в статье [Настройка шаблонов для Azure Information Protection и управление ими](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Сведения о параметре "не **пересылать** " можно узнать в статье не [пересылать сообщения](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Для получения дополнительных сведений о параметре " **только шифрование** " в разделе [шифрование только для сообщений электронной почты](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Выберите команду **Добавить действие** , если хотите указать другое действие.
