---
title: Добавление фирменой марки организации в зашифрованные сообщения
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
description: Узнайте, как глобальные администраторы Office 365 могут применять фирменую марку организации к зашифрованным электронным & содержимому портала шифрования.
ms.openlocfilehash: 56b948fc941da4fb221d929ecd59c5300b135e39
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709501"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Добавление торговой марки организации в зашифрованные сообщения шифрования сообщений Microsoft 365 для бизнеса

Вы можете применить фирменую марку компании, чтобы настроить внешний вид сообщений электронной почты организации и портала шифрования. Перед началом работы необходимо применить разрешения глобального администратора к своей учетной записи работы или учебного заведения. После получения этих разрешений используйте Get-OMEConfiguration и Set-OMEConfiguration Windows PowerShell для настройки этих частей зашифрованных сообщений электронной почты:
  
- Вводный текст

- Disclaimer text

- URL-адрес заявления о конфиденциальности вашей организации

- Текст на портале OME

- Логотип, который отображается в сообщении электронной почты и на портале OME или используется ли логотип вообще

- Цвет фона в сообщении электронной почты и на портале OME

Кроме того, в любое время вы можете восстановить интерфейс по умолчанию.

Если вы хотите больше контроля, используйте office 365 Advanced Message Encryption, чтобы создать несколько шаблонов для зашифрованных сообщений электронной почты из вашей организации. Используйте эти шаблоны для управления частями пользовательского интерфейса. Например, укажите, могут ли получатели использовать учетные записи Google, Yahoo и Microsoft для входов на портал шифрования. Используйте шаблоны для выполнения нескольких вариантов использования, например:

- Отдельные отделы, такие как "Финансы", "Продажи" и так далее.

- Различные продукты

- Различные географические регионы или страны

- Хотите ли вы разрешить отзыв сообщений электронной почты

- Указывает, следует ли отправлять сообщения электронной почты внешним получателям по истечении указанного количества дней.

После создания шаблонов их можно применять к зашифрованным электронным письмам с помощью правил потока почты Exchange. Если у вас есть Office 365 Advanced Message Encryption, вы можете отоискить все сообщения электронной почты, которые вы добавили в фирменую марку, используя эти шаблоны.

## <a name="work-with-ome-branding-templates"></a>Работа с шаблонами фирменного оформления OME

В шаблоне фирменой марки можно изменить несколько функций. Шаблон по умолчанию можно изменять, но не удалять. Если у вас есть advanced Message Encryption, вы также можете создавать, изменять и удалять настраиваемые шаблоны. Используйте Windows PowerShell для одновременной работы с одним шаблоном фирменой марки.

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) — изменение шаблона фирменения по умолчанию или созданного вами настраиваемого шаблона фирменения.
- [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) : создание нового шаблона фирменности, только advanced Message Encryption.
- [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) — удаление настраиваемого шаблона фирменности, только advanced Message Encryption. Шаблон фирменой настройки по умолчанию удалить нельзя.
  
## <a name="modify-an-ome-branding-template"></a>Изменение шаблона фирменного оформления OME

Используйте Windows PowerShell для одновременного изменения одного шаблона фирменой марки. Если у вас есть advanced Message Encryption, вы также можете создавать, изменять и удалять настраиваемые шаблоны.

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте Set-OMEConfiguration, как описано в [set-OMEConfiguration,](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) или воспользуйтесь следующей графикой и таблицей для указания.

![Настраиваемые части электронной почты](../media/ome-template-breakout.png)

|**Настройка этой функции шифрования**|**Используйте эти команды**|
|:-----|:-----|
|Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Дополнительные сведения о цветах фона см. в разделе ["Цвета](#background-color-reference) фона" далее в этой статье.|
|Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF  <br/> Оптимальный размер файла эмблемы: менее 40 КБ  <br/> Оптимальный размер изображения логотипа: 170x70 пикселей. Если изображение превышает эти размеры, служба меняет размер логотипа для отображения на портале. Служба не изменяет сам графический файл. Для наилучших результатов используйте оптимальный размер.|
|Текст рядом с именем и адресом электронной почты отправитель|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Текст, который отображается на кнопке "Прочитать сообщение"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Текст, который отображается под кнопкой "Прочитать сообщение"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL-адрес ссылки на заявление о конфиденциальности|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Чтобы включить или отключить проверку подлинности с помощью разового кода прохода для этого настраиваемого шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Примеры.** <br/>Чтобы включить одновейные парольные коды для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Отключение одновейных паролей для этого настраиваемого шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Чтобы включить или отключить проверку подлинности с помощью удостоверений Майкрософт, Google или Yahoo для этого пользовательского шаблона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Примеры.** <br/>Чтобы включить социальные ID для этого пользовательского шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Отключение социальных ИД для этого пользовательского шаблона <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Создание шаблона фирменной марки OME (advanced Message Encryption)

Если у вас есть Office 365 Advanced Message Encryption, вы можете создать настраиваемые шаблоны фирменой настройки для своей организации с помощью [cmdlet New-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) После создания шаблона его можно изменить с помощью Set-OMEConfiguration, как описано в описании изменения шаблона [фирменного оформления OME.](#modify-an-ome-branding-template) Можно создать несколько шаблонов.

Чтобы создать новый настраиваемый шаблон фирменой настройки:

1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте для создания нового шаблона с помощью [cmdlet New-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration)

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Пример.

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Возврат шаблона фирменки по умолчанию к исходным значениям

Чтобы удалить все изменения из шаблона по умолчанию, включая настройки торговой марки и т. с., выполните следующие действия:
  
1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте **cmdlet Set-OMEConfiguration,** как описано в [set-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) Чтобы удалить фирменные настройки организации из значений DisclaimerText, EmailText и PortalText, запишите в качестве значения пустую `""` строку. Для всех значений изображений, таких как логотип, установите значение  `"$null"` .

   В следующей таблице описываются параметры настройки шифрования по умолчанию.

   **Сброс функции шифрования к тексту и изображению по умолчанию**|**Используйте эти команды**|
   |:-----|:-----|
   |Текст по умолчанию, который поставляется с зашифрованными сообщениями электронной почты  <br/> Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Заявление об отказе в зашифрованном сообщении электронной почты.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Пример:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Пример обратного обратного значения по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Логотип|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Пример обратного обратного значения по умолчанию:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Цвет фона|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Пример обратного обратного значения по умолчанию:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Удаление пользовательского шаблона фирменой настройки (advanced Message Encryption)

Вы можете удалять только шаблоны фирменой марки, которые вы сделали. Шаблон фирменой настройки по умолчанию удалить нельзя.

Удаление пользовательского шаблона фирменой настройки:
  
1. Используя учетную запись для работы или учебного заведения с разрешениями глобального администратора в организации, Windows PowerShell сеанс и подключите его к Exchange Online. Инструкции см. в статье [Подключение к Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Используйте **cmdlet Remove-OMEConfiguration** следующим образом:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Пример.

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Дополнительные сведения см. в [подстройки Remove-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Создание правила потока почты Exchange, которое применяет настраиваемую фирмовую марку к зашифрованным электронным письмам

После изменения шаблона по умолчанию или создания новых шаблонов фирменности можно создать правила потока почты Exchange, чтобы применить настраиваемую фирменную марку на основе определенных условий. Такое правило будет применять настраиваемую фирменую марку в следующих сценариях:

- Если сообщение было зашифровано пользователем вручную с помощью Outlook или Outlook в Интернете, ранее Outlook Web App

- Если сообщение было автоматически зашифровано правилом потока обработки почты Exchange или политикой защиты от потери данных

Сведения о том, как создать правило потока почты Exchange, которое применяет шифрование, см. в подмене правил потока почты для шифрования сообщений электронной почты [в Office 365.](define-mail-flow-rules-to-encrypt-email.md)

1. В веб-браузере, используя учетную запись для работы или учебного заведения, которая получила разрешения глобального администратора, во sign [in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Выберите **плитку** "Администратор".

3. В Центре администрирования Microsoft 365 выберите **"Центры администрирования** \> **Exchange".**

4. В EAC перейдите в **"Правила потока** почты" и выберите \>  **"Создать** новый ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **значок" "Создать новое правило".** Дополнительные сведения об использовании Центра администрирования Exchange см. в [Центре администрирования Exchange в Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)

5. **Введите** имя правила, например Branding for sales department.

6. **Применив это правило,** выберите условие, которое отправитель находится внутри организации, и другие условия, которые необходимо в списке доступных условий.  Например, можно применить определенный шаблон фирменой марки к:

   - Все зашифрованные сообщения от сотрудников финансового отдела
   - Зашифрованные сообщения электронной почты, отправленные с помощью определенного ключевого слова, например "Внешний" или "Партнер"
   - Зашифрованные сообщения электронной почты, отправленные в определенный домен

7. From **Do the following**, select Modify the message **security** Apply \> **custom branding to OME messages**. Затем в выпадаемом меню выберите шаблон фирменой марки.

8. (Необязательно) Вы можете настроить правило потока почты для применения шифрования и пользовательской фирменой настройки. From **Do the following**, select Modify the message **security**, and then choose Apply **Office 365 Message Encryption and rights protection**. Выберите шаблон RMS из списка, выберите **"Сохранить"** и "ОК". 
  
   Список шаблонов включает шаблоны и параметры по умолчанию, а также все созданные вами настраиваемые шаблоны. Если список пуст, убедитесь, что вы настроили шифрование сообщений Office 365 с новыми возможностями. Инструкции см. в настройках новых возможностей шифрования [сообщений Office 365.](set-up-new-message-encryption-capabilities.md) Сведения о шаблонах по умолчанию см. в сведениях о настройке и управлении [шаблонами для Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates) Сведения о параметре **"Не переад вперед"** см. в параметре ["Не переададантов" для сообщений электронной почты.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Сведения о параметре **"Только шифрование"** см. в параметре ["Только шифрование" для сообщений электронной почты.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Выберите **действие "Добавить",** если нужно указать другое действие.

## <a name="background-color-reference"></a>Справочные данные по цвету фона

Имена цветов, которые можно использовать для фонового цвета, ограничены. Вместо имени цвета можно использовать значение 6-го кода (#RRGGBB). Вы можете использовать значение кодов в hex, соответствующее имени цвета, или пользовательское значение кода. Не забудьте заключить значение кода в кавычках (например, `"#f0f8ff"` ).

Доступные имена цветов фона и соответствующие им значения кодов описаны в следующей таблице.

|**Название цвета**|**Код цвета**|
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
