---
title: Добавление бренда организации в зашифрованные сообщения
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
- seo-marvel-jun2020
description: Узнайте, Office 365 глобальные администраторы могут применять брендинг организации к зашифрованным сообщениям электронной почты & контенту портала шифрования.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394717"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Добавление бренда организации в вашу Microsoft 365 для зашифрованных сообщений шифрования бизнес-сообщений

Вы можете применить брендинг компании, чтобы настроить внешний вид сообщений электронной почты организации и портала шифрования. Чтобы начать работу, необходимо применить глобальные разрешения администратора к своей учетной записи или учебной учетной записи. После получения этих разрешений используйте Get-OMEConfiguration и Set-OMEConfiguration Windows PowerShell для настройки этих частей зашифрованных сообщений электронной почты:
  
- Вводный текст

- Disclaimer text

- URL-адрес для заявления о конфиденциальности вашей организации

- Текст на портале OME

- Логотип, который отображается в сообщении электронной почты и портале OME, или же использовать логотип вообще

- Цвет фона в сообщении электронной почты и портале OME

Кроме того, в любое время вы можете восстановить интерфейс по умолчанию.

Если вы хотите больше контроля, Расширенное шифрование сообщений Office 365 создать несколько шаблонов для зашифрованных сообщений электронной почты, исходя из вашей организации. Эти шаблоны используются для управления частями интерфейса конечного пользователя. Например, укажите, могут ли получатели использовать учетные записи Google, Yahoo и Microsoft для входов на портал шифрования. Используйте шаблоны для выполнения нескольких случаев использования, таких как:

- Отдельные отделы, такие как Финансы, Продажи и так далее.

- Различные продукты

- Различные географические регионы или страны

- Хотите ли вы разрешить отмену электронных писем

- Хотите ли вы, чтобы срок действия электронной почты, отправленной внешним получателям, истекал по истечении определенного числа дней.

После создания шаблонов можно применить их к зашифрованным электронным письмам с помощью Exchange правил потока почты. Если у вас Расширенное шифрование сообщений Office 365, вы можете отоискить любую электронную почту, которую вы завяли, используя эти шаблоны.

## <a name="work-with-ome-branding-templates"></a>Работа с шаблонами брендинга OME

Вы можете изменить несколько функций в шаблоне брендинга. Шаблон по умолчанию можно изменить, но не удалить. Если у вас есть расширенный шифрование сообщений, вы также можете создавать, изменять и удалять настраиваемые шаблоны. Используйте Windows PowerShell для работы с одним шаблоном брендинга одновременно.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) — изменение шаблона брендинга по умолчанию или созданного вами пользовательского шаблона брендинга.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) — создание нового шаблона фирменности, только для предварительного шифрования сообщений.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) — удалите настраиваемый шаблон брендинга, только расширенный шифрование сообщений. Вы не можете удалить шаблон брендинга по умолчанию.
  
## <a name="modify-an-ome-branding-template"></a>Изменение шаблона брендинга OME

Используйте Windows PowerShell для изменения одного шаблона брендинга одновременно. Если у вас есть расширенный шифрование сообщений, вы также можете создавать, изменять и удалять настраиваемые шаблоны.

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Используйте Set-OMEConfiguration, как описано в [set-OMEConfiguration,](/powershell/module/exchange/Set-OMEConfiguration) или используйте следующие графические и таблицы для руководства.

![Настраиваемые части электронной почты](../media/ome-template-breakout.png)

|**Настройка этой функции шифрования**|**Используйте эти команды**|
|:-----|:-----|
|Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Дополнительные сведения о цветах фона см. в разделе [Фоновые](#background-color-reference) цвета в этой статье.|
|Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF  <br/> Оптимальный размер файла эмблемы: менее 40 КБ  <br/> Оптимальный размер изображения логотипа: 170x70 пикселей. Если ваше изображение превышает эти размеры, служба повторно размеры вашего логотипа для отображения на портале. Служба не изменит сам графический файл. Для получения наилучших результатов используйте оптимальный размер.|
|Текст рядом с именем и адресом электронной почты отправитель|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Текст, который отображается на кнопке "Чтение сообщения"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Текст, который отображается ниже кнопки "Чтение сообщения"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL-адрес ссылки "Заявление о конфиденциальности"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Включить или отключить проверку подлинности с помощью разового кода прохода для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Примеры.** <br/>Включить одновековые коды паролей для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Отключение одновекового пароля для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Чтобы включить или отключить проверку подлинности с помощью удостоверений Microsoft, Google или Yahoo для этого пользовательского шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Примеры.** <br/>Чтобы включить социальные ID для этого пользовательского шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Отключение социальных ID для этого пользовательского шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Создание шаблона брендинга OME (предварительное шифрование сообщений)

Если у вас Расширенное шифрование сообщений Office 365, вы можете создать настраиваемые шаблоны брендинга для своей организации с помощью комлета [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration) После создания шаблона вы измените шаблон с помощью Set-OMEConfiguration, как описано в шаблоне модифицировать шаблон [брендинга OME.](#modify-an-ome-branding-template) Можно создать несколько шаблонов.

Создание нового пользовательского шаблона брендинга:

1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Для создания нового шаблона используйте комлет [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Пример.

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Возврат шаблона брендинга по умолчанию к исходным значениям

Чтобы удалить все изменения из шаблона по умолчанию, включая настройки бренда и т. ч., выполните следующие действия:
  
1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Используйте **комлет Set-OMEConfiguration,** как описано в [Set-OMEConfiguration.](/powershell/module/exchange/Set-OMEConfiguration) Чтобы удалить фирменные настройки организации из значений DisclaimerText, EmailText и PortalText, установите значение пустой `""` строки. Для всех значений изображений, таких как Logo, установите значение  `"$null"` .

   В следующей таблице описываются параметры настройки шифрования по умолчанию.

   |Сброс функции шифрования к тексту и изображению по умолчанию|Используйте эти команды|
   |:-----|:-----|
   |Текст по умолчанию, который поставляется с зашифрованными сообщениями электронной почты.  Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Пример, возвращающийся к умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Пример, возвращающийся к умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Пример, возвращающийся к умолчанию:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Удаление пользовательского шаблона брендинга (предварительное шифрование сообщений)

Вы можете удалить или удалить только шаблоны брендинга, которые вы сделали. Вы не можете удалить шаблон брендинга по умолчанию.

Чтобы удалить настраиваемый шаблон брендинга:
  
1. С помощью учетной записи работы или школы, которая имеет глобальные разрешения администратора в организации, запустите сеанс Windows PowerShell и подключите к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Используйте **комлет Remove-OMEConfiguration** следующим образом:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Пример.

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Дополнительные сведения см. [в дополнительных сведениях Remove-OMEConfiguration.](/powershell/module/exchange/remove-omeconfiguration)

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Создание правила Exchange потока почты, которое применяет настраиваемый брендинг к зашифрованным электронным письмам

После изменения шаблона по умолчанию или создания новых шаблонов брендинга можно создать правила потока Exchange для применения настраиваемой фирменности на основе определенных условий. Такое правило будет применять настраиваемый брендинг в следующих сценариях:

- Если электронная почта была зашифрована вручную конечным пользователем с помощью Outlook или Outlook в Интернете, Outlook Web App

- Если электронная почта была автоматически зашифрована правилом потока Exchange или политикой предотвращения потери данных

Сведения о создании правила потока Exchange, применяемой для шифрования, см. в статью Определение правил потока почты для шифрования сообщений электронной почты [в Office 365.](define-mail-flow-rules-to-encrypt-email.md)

1. В веб-браузере, используя учетную запись для работы или [](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)школы, которая получила разрешения глобального администратора, вопишитесь в Office 365 .

2. Выберите **плитку администрирования.**

3. В центре Microsoft 365 выберите **центры** администрирования \> Exchange.

4. В EAC перейдите к **правилам потока** \> **почты** и выберите **новый** ![ значок Создание нового ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **правила**. Дополнительные сведения об использовании центра администрирования см. в Exchange центре администрирования [в Exchange Online.](/exchange/exchange-admin-center)

5. В **Name** введите имя правила, например Branding для отдела продаж.

6. В **Примени** это правило, если выберите условие, которое отправителю находится внутри организации, и другие условия, которые вам нужны из списка доступных условий.  Например, может потребоваться применить определенный шаблон брендинга для:

   - Все зашифрованные сообщения электронной почты, отправленные от сотрудников финансового отдела
   - Зашифрованные сообщения электронной почты, отправленные с определенным ключевым словом, таким как "Внешний" или "Партнер"
   - Зашифрованные сообщения электронной почты, отправленные в определенный домен

7. Далее **выберите** **Изменение** безопасности сообщений \> **Применение настраиваемой фирменности для сообщений OME.** Далее из выпадаемой страницы выберите шаблон брендинга.

8. (Необязательный) Вы можете настроить правило потока почты, чтобы применить шифрование и настраиваемый брендинг. Из **Делайте следующее,** выберите Изменение безопасности **сообщения,** а затем выберите Применение шифрование сообщений Office 365 **и защиты прав**. Выберите шаблон RMS из списка, выберите **Сохранить**, а затем выберите **ОК**.
  
   Список шаблонов включает шаблоны и параметры по умолчанию, а также созданные пользовательские шаблоны. Если список пуст, убедитесь, что вы шифрование сообщений Office 365 с новыми возможностями. Инструкции см. в [инструкции Настройка новых шифрование сообщений Office 365 возможностей.](set-up-new-message-encryption-capabilities.md) Сведения о шаблонах по умолчанию см. в меню Настройка и управление шаблонами [для Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Сведения о параметре **"Не переададку"** см. в варианте [Не переададка электронной почты.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Сведения о только **варианте шифрования** см. в [параметре Шифровать только для электронных писем.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Выберите **действие добавить,** если нужно указать другое действие.

## <a name="background-color-reference"></a>Справочная ссылка цвета фона

Имена цветов, которые можно использовать для фонового цвета, ограничены. Вместо цветного имени можно использовать значение кода hex (#RRGGBB). Вы можете использовать значение кода hex, соответствующее цвету имени, или вы можете использовать пользовательское значение кода hex. Обязательно заключив значение кода hex в кавычках (например, `"#f0f8ff"` ).

Доступные имена фоновых цветов и соответствующие значения кода гекса описаны в следующей таблице.

|**Название цвета**|**Цветовой код**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|