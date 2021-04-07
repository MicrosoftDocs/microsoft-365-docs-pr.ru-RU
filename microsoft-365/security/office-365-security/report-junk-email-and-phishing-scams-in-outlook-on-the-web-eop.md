---
title: Сообщение нежелательной и фишинговой почты в Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о встроенных нежелательных, а не нежелательных и фишинговых вариантах сообщений электронной почты в Outlook в Интернете (Outlook Web App) в Exchange Online и о том, как отключить эти параметры отчетности для пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615217"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Сообщение нежелательной и фишинговой почты в Outlook в Интернете в Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В microsoft 365 организациях с почтовыми ящиками в Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные негативы (разрешена плохая электронная почта) и фишинговые сообщения в Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Для наилучшего использования пользовательской отправки рекомендуется использовать надстройки Report Message и Report Phishing. Дополнительные [сведения см.](./enable-the-report-message-add-in.md) в [](./enable-the-report-phish-add-in.md) дополнительных сведениях.

- Если вы администратор в организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям. Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)

- Администраторы могут отключить или включить возможность для пользователей сообщать о сообщениях в Microsoft в Outlook в Интернете. Подробные сведения см. в разделе Отключение или включить нежелательные сообщения электронной почты в [Outlook в веб-разделе](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) в этой статье.

- Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)

- Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете

По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативах и фишинговых сообщениях в Microsoft для анализа в Outlook в Интернете. Администраторы могут настраивать Outlook для политик веб-почтовых ящиков в Exchange Online PowerShell, чтобы пользователи не сообщали о ложных срабатываваемых спама и нежелательных ложных негативах в Microsoft. Нельзя отключить возможность для пользователей сообщать о фишинговых сообщениях в Корпорацию Майкрософт.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Вам необходимо получить разрешения в Exchange Online, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам нужны  роли **политики** получателей или получателей  почты, которые по умолчанию назначены группам ролей управления и управления получателями организации.  Дополнительные сведения о группах ролей в Exchange Online см. в рублях [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) и [Modify role groups in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)

- Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но можно создавать настраиваемые политики. Пользовательские политики применяются к пользователям с масштабами перед политикой по умолчанию. Дополнительные сведения о политиках Outlook для веб-почтовых ящиков см. в странице Outlook в политиках веб-почтовых [ящиков в Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Отключение нежелательной отчетности по электронной почте не удаляет возможность пометить сообщение как нежелательное или нежелательное в Outlook в Интернете. Выбор сообщения в папке нежелательной почты и нажатие кнопки **Не** нежелательной не нежелательной по-прежнему перемещает сообщение обратно \>  в папку "Входящие". Выбор сообщения в любой другой папке  электронной почты и нажатие нежелательной нежелательной почты по-прежнему перемещает сообщение \>  в папку нежелательной почты. Больше нет возможности сообщить об этом сообщении в Корпорацию Майкрософт.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Использование Exchange Online PowerShell для отключения или отключения нежелательной отчетности по электронной почте в Outlook в Интернете

1. Чтобы найти существующий Outlook в политиках веб-почтовых ящиков и состоянии нежелательной отчетности по электронной почте, запустите следующую команду:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Чтобы отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующий синтаксис:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   В этом примере отключает нежелательные сообщения электронной почты в политике по умолчанию.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   В этом примере включается нежелательное сообщение электронной почты в настраиваемой политике под названием Contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) и [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Чтобы убедиться, что вы успешно включили или отключили нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующие действия:

- В Exchange Online PowerShell запустите следующую команду и проверьте значение **свойства ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите  сообщение в почтовом ящике, нажмите нежелательной почты и убедитесь, что сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup>

- Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите сообщение  в папке нежелательной почты, щелкните нежелательной почты и убедитесь, что запрос на сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup>

<sup>\*</sup> Пользователи могут скрыть запрос, чтобы сообщить о сообщении, но при этом сообщить о сообщении. Чтобы проверить этот параметр в Outlook в Интернете:

1. Щелкните **Параметры** ![ Outlook на значке веб-параметров Просмотр всех ](../../media/owa-settings-icon.png) \> **параметров Outlook** \> **нежелательной почты**.
2. В разделе **Отчеты** проверьте значение: **Спросите меня перед отправкой отчета**.

   ![Outlook для параметров отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)