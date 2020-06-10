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
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Примените фирменную символику вашей организации к зашифрованным сообщениям электронной почты в Организации и содержимому портала шифрования.
ms.openlocfilehash: 86636b319151a96e9ec827f85cc943282c30f63c
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679113"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Добавление фирменной символики организации в зашифрованные сообщения

Как администратор Exchange Online или Exchange Online Protection, вы можете применить фирменную символику компании, чтобы настроить внешний вид сообщений электронной почты в службе шифрования сообщений Microsoft 365 для бизнеса, а также содержимое портала шифрования. С помощью командлетов Windows PowerShell Get – OMEConfiguration и Set – OMEConfiguration можно настроить следующие аспекты просмотра для получателей зашифрованных сообщений электронной почты:
  
- Вводный текст зашифрованного сообщения электронной почты

- Текст заявления об отказе зашифрованного сообщения электронной почты

- URL-адрес заявления о конфиденциальности для Организации

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

В шаблоне фирменной символики можно изменить несколько компонентов. Шаблон по умолчанию можно изменить, но не удалить. При наличии расширенного шифрования сообщений можно также создавать, изменять и удалять настраиваемые шаблоны. Используйте Windows PowerShell для работы с одним шаблоном фирменного стиля за раз. Чтобы использовать эти командлеты, вам потребуется рабочая или учебная учетная запись с разрешениями глобального администратора в Организации.

- [Set — OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) — изменить шаблон фирменной символики по умолчанию или созданный пользовательский шаблон фирменной символики.
- [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) — создание нового шаблона фирменного стиля, только расширенного шифрования сообщений.
- [Remove – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) — удалить настраиваемый шаблон фирменного стиля, только расширенное шифрование сообщения. Шаблон фирменной символики по умолчанию удалить невозможно.
  
## <a name="modify-an-ome-branding-template"></a>Изменение шаблона фирменной символики OME

Используйте Windows PowerShell, чтобы изменить один шаблон фирменного стиля за раз. При наличии расширенного шифрования сообщений можно также создавать, изменять и удалять настраиваемые шаблоны.

1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Измените шаблон с помощью командлета Set – OMEConfiguration, как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) , или используйте приведенную ниже графику и таблицу, чтобы получить рекомендации.

![Настраиваемые части электронной почты](../media/ome-template-breakout.png)

|**Настройка этой функции шифрования**|**Используйте эти команды**|
|:-----|:-----|
|Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Более подробную информацию о цветах фона можно узнать в разделе [цвета фона](#background-color-reference) далее в этом разделе.|
|Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF  <br/> Оптимальный размер файла эмблемы: менее 40 КБ  <br/> Оптимальный размер изображения логотипа: 170x70 пикселей. Если изображение превышает эти размеры, служба изменяет размер логотипа для отображения на портале. Служба не изменяет сам графический файл. Для достижения лучших результатов используйте оптимальный размер.|
|Текст рядом с именем отправителя и адресом электронной почты|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Текст, который отображается на кнопке "чтение сообщения"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Текст, который отображается под кнопкой "прочитать сообщение"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL-адрес для ссылки на заявление о конфиденциальности|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Включение или отключение проверки подлинности с помощью кода одноразового этапа для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Примеры:** <br/>Включение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Отключение одноразовых секретных кодов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Включение или отключение проверки подлинности с помощью удостоверений Microsoft, Google или Yahoo для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Примеры:** <br/>Включение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Отключение социальных идентификаторов для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Создание шаблона фирменной символики OME (расширенное шифрование сообщений)

Если вы используете расширенное шифрование сообщений Office 365, вы можете создать настраиваемые шаблоны фирменного стиля для своей организации с помощью командлета [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) . После создания шаблона измените шаблон с помощью командлета Set – OMEConfiguration, как описано в статье [изменение шаблона фирменной символики OME](#modify-an-ome-branding-template). Можно создать несколько шаблонов.

Чтобы создать новый настраиваемый шаблон фирменной символики:

1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет [New – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) для создания нового шаблона.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Возврат к исходным значениям шаблона фирменной символики по умолчанию

Чтобы удалить все изменения из шаблона по умолчанию, включая настройки фирменного стиля и т. д., выполните указанные ниже действия.
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет **Set – OMEConfiguration** , как описано в командлете [Set – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration). Чтобы удалить настройки фирменной символики Организации из значений DisclaimerText, EmailText и PortalText, установите для этого параметра пустую строку `""` . Для всех значений изображений, например Logo, установите значение `"$null"` .

   В следующей таблице описываются параметры настройки шифрования по умолчанию.

   **Сброс функции шифрования к тексту и изображению по умолчанию**|**Используйте эти команды**|
   |:-----|:-----|
   |Текст по умолчанию, сопровождающий зашифрованные сообщения электронной почты.  <br/> Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Пример возврата к значению по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Пример возврата к значению по умолчанию:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Удаление настраиваемого шаблона фирменного стиля (расширенного шифрования сообщений)

Вы можете удалять и удалять только созданные вами шаблоны фирменного стиля. Шаблон фирменной символики по умолчанию удалить невозможно.

Чтобы удалить настраиваемый шаблон фирменной символики:
  
1. С помощью рабочей или учебной учетной записи с разрешениями глобального администратора в Организации запустите сеанс Windows PowerShell и подключитесь к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте командлет **Remove – OMEConfiguration** следующим образом:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Дополнительные сведения см. в разделе [Remove – OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Создание правила для процесса обработки почты Exchange, которое применяет настраиваемую фирменную символику к зашифрованным сообщениям электронной почты

После того как вы изменяли шаблон по умолчанию или создали новые шаблоны фирменного стиля, вы можете создать правила для почтовых ящиков Exchange, чтобы применить собственную фирменную символику на основе определенных условий. Такое правило будет применять настраиваемую фирменную символику в следующих сценариях:

- Если пользователь вручную зашифровал сообщение из Outlook или Outlook в Интернете (прежнее название — Outlook Web App)

- Если сообщение было автоматически зашифровано правилом для обработки почтового ящика Exchange или политикой защиты от потери данных

Сведения о том, как создать правило для процесса обработки почты Exchange, которое применяет шифрование, можно узнать в статье [Определение правил обработки почтового процесса для шифрования сообщений электронной почты в Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. В веб-браузере с помощью рабочей или учебной учетной записи, которой предоставлены разрешения глобального администратора, [Войдите в Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Выберите плитку **Администратор** .

3. В центре администрирования Microsoft 365 выберите Exchange **центры администрирования** \> **Exchange**.

4. В центре администрирования Exchange перейдите к разделу правила обработки **почтового процесса** \> **Rules** и выберите **Новый** ![ новый значок ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **создать новое правило**. Дополнительные сведения об использовании [центра администрирования Exchange можно найти в центре администрирования Exchange в Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. В поле **имя**введите имя правила, например фирменный стиль для отдела продаж.

6. В поле **Применить это правило, если**выберите условие, **которое отправитель находится в Организации** , а также другие необходимые условия из списка доступных условий. Например, может потребоваться применить определенный шаблон фирменной символики к:

   - Все зашифрованные сообщения электронной почты, отправленные участниками отдела финансов
   - Зашифрованные сообщения электронной почты, отправленные с определенным ключевым словом, например "External" или "Partner"
   - Зашифрованные сообщения электронной почты, отправленные на определенный домен

7. В **разделе выполните следующие действия**выберите **изменить безопасность сообщений**  >  **применение настраиваемой фирменной символики к сообщениям OME**. Затем в раскрывающемся списке выберите шаблон фирменной символики из созданного или измененного.

8. Необязательно Если вы хотите, чтобы правило обработки почтового ящика применяло шифрование в дополнение к настраиваемой фирменной символике, **выполните следующие действия**, выберите **изменить безопасность сообщений**, а затем нажмите **применить шифрование и защиту сообщений Office 365**. Выберите шаблон RMS в списке и нажмите кнопку **сохранить**, а затем нажмите кнопку **ОК**.
  
   Список шаблонов включает все шаблоны и параметры по умолчанию, а также пользовательские шаблоны, созданные для использования в Office 365. Если список пуст, убедитесь, что вы настроили шифрование сообщений Office 365 с помощью новых возможностей, как описано в статье [Настройка новых возможностей шифрования сообщений office 365](set-up-new-message-encryption-capabilities.md). Сведения о шаблонах по умолчанию можно узнать в статье [Настройка шаблонов для Azure Information Protection и управление ими](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Сведения о параметре "не **пересылать** " можно узнать в статье не [пересылать сообщения](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Для получения дополнительных сведений о параметре " **только шифрование** " в разделе [шифрование только для сообщений электронной почты](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Выберите команду **Добавить действие** , если хотите указать другое действие.

## <a name="background-color-reference"></a>Справочник по цвету фона

Имена цветов, которые можно использовать для фонового цвета, ограничены. Вместо имени цвета можно использовать шестнадцатеричное значение кода (#RRGGBB). Можно использовать шестнадцатеричное значение кода, которое соответствует имени цвета, или можно использовать собственное значение шестнадцатеричного кода. Обязательно заключите шестнадцатеричное значение кода в кавычки (например, `"#f0f8ff"` ).

В приведенной ниже таблице описаны имена доступных фоновых цветов и соответствующие им шестнадцатеричные значения кода.

|||
|---|---|
|**Название цвета**|**Код цвета**|
|алицеблуе|#f0f8ff|
|антикуевхите|#faebd7|
|волны|#00ffff|
|акуамарине|#7fffd4|
|службу|#f0ffff|
|цвет|#f5f5dc|
|бискуе|#ffe4c4|
|black|#000000|
|бланчедалмонд|#ffebcd|
|blue|#0000ff|
|блуевиолет|#8a2be2|
|Иванов|#a52a2a|
|бурливуд|#deb887|
|кадетблуе|#5f9ea0|
|чартреусе|#7fff00|
|рецепт|#d2691e|
|Территория|#ff7f50|
|корнфловерблуе|#6495ed|
|корнсилк|#fff8dc|
|Crimson|#dc143c|
|цвет|#00ffff|
|даркблуе|#00008b|
|даркциан|#008b8b|
|даркголденрод|#b8860b|
|даркграй|#a9a9a9|
|даркгрин|#006400|
|дарккхаки|#bdb76b|
|даркмажента|#8b008b|
|дарколивегрин|#556b2f|
|darkorange|#ff8c00|
|даркорчид|#9932cc|
|даркред|#8b0000|
|дарксалмон|#e9967a|
|дарксеагрин|#8fbc8f|
|даркслатеблуе|#483d8b|
|даркслатеграй|#2f4f4f|
|дарктуркуоисе|#00ced1|
|дарквиолет|#9400d3|
|диппинк|#ff1493|
|дипскиблуе|#00bfff|
|димграй|#696969|
|доджерблуе|#1e90ff|
|фиребрикк|#b22222|
|флоралвхите|#fffaf0|
|форестгрин|#228b22|
|фучсиа|#ff00ff|
|гаинсборо|#dcdcdc|
|гхоствхите|#f8f8ff|
|цвет|#ffd700|
|голденрод|#daa520|
|участка|#808080|
|green|#008000|
|гринеллов|#adff2f|
|хонэйдев|#f0fff0|
|хотпинк|#ff69b4|
|индианред|#cd5c5c|
|Индиго|#4b0082|
|ивори|#fffff0|
|кхаки|#f0e68c|
|лавендер|#e6e6fa|
|лавендерблуш|#fff0f5|
|лавнгрин|#7cfc00|
|лемончиффон|#fffacd|
|lightblue|#add8e6|
|лигхткорал|#f08080|
|лигхтциан|#e0ffff|
|лигхтголденроделлов|#fafad2|
|лигхтграй|#d3d3d3|
|лигхтгрэй|#d3d3d3|
|lightgreen|#90ee90|
|лигхтпинк|#ffb6c1|
|лигхтсалмон|#ffa07a|
|лигхтсеагрин|#20b2aa|
|лигхтскиблуе|#87cefa|
|лигхтслатеграй|#778899|
|лигхтстилблуе|#b0c4de|
|лигхтеллов|#ffffe0|
|желт|#00ff00|
|лимегрин|#32cd32|
|линен|#faf0e6|
|фиолетовый|#ff00ff|
|марун|#800000|
|медиумакуамарине|#66cdaa|
|медиумблуе|#0000cd|
|медиуморчид|#ba55d3|
|медиумпурпле|#9370db|
|медиумсеагрин|#3cb371|
|медиумслатеблуе|#7b68ee|
|медиумспринггрин|#00fa9a|
|медиумтуркуоисе|#48d1cc|
|медиумвиолетред|#c71585|
|миднигхтблуе|#191970|
|минткреам|#f5fffa|
|мистиросе|#ffe4e1|
|моккасин|#ffe4b5|
|наважовхите|#ffdead|
|нави|#000080|
|олдлаце|#fdf5e6|
|темно|#808000|
|оливедраб|#6b8e23|
|orange|#ffa500|
|оранжеред|#ff4500|
|орчид|#da70d6|
|палеголденрод|#eee8aa|
|палегрин|#98fb98|
|палетуркуоисе|#afeeee|
|палевиолетред|#db7093|
|папайавхип|#ffefd5|
|пеачпуфф|#ffdab9|
|Перу|#cd853f|
|pink|#ffc0cb|
|сливовая|#dda0dd|
|повдерблуе|#b0e0e6|
|purple|#800080|
|red|#ff0000|
|росибровн|#bc8f8f|
|ройалблуе|#4169e1|
|саддлебровн|#8b4513|
|салмон|#fa8072|
|сандибровн|#f4a460|
|сеагрин|
|сеашелл|#fff5ee|
|сиенна|#a0522d|
|носят|#c0c0c0|
|скиблуе|#87ceeb|
|слатеблуе|#6a5acd|
|слатеграй|#708090|
|Snow|#fffafa|
|спринггрин|#00ff7f|
|стилблуе|#4682b4|
|Tan|#d2b48c|
|teal|#008080|
|систле|#d8bfd8|
|томато|#ff6347|
|Turquoise|#40e0d0|
|красн|#ee82ee|
|вхеат|#f5deb3|
|white|#ffffff|
|вхитесмоке|#f5f5f5|
|yellow|#ffff00|
|елловгрин|#9acd32|
