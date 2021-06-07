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
description: Администраторы могут узнать о встроенных нежелательных, а не нежелательных и фишинговых вариантах сообщений электронной почты в Outlook в Интернете (Outlook Web App) в Exchange Online, а также о том, как отключить эти параметры отчетности для пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788311"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Сообщение нежелательной и фишинговой почты в Outlook в Интернете в Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или на локальном почтовом ящике с использованием гибридной современной проверки подлинности можно отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные негативы (разрешена плохая электронная почта) и фишинговые сообщения в Exchange Online Protection (EOP). [](../../enterprise/hybrid-modern-auth-overview.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

> [!IMPORTANT]
> Мы рекомендуем надстройку Сообщение отчетов или надстройку Report Phishing для отправки пользователей. Дополнительные сведения см. [в добавлении Enable the Report Message или Report Phishing add-ins.](./enable-the-report-message-add-in.md) Мы не рекомендуем встроенный опыт отчетов в Outlook, так как он не может использовать политику отправки [пользователей.](./user-submission.md)

- Если вы администратор в организации с Exchange Online почтовыми ящиками, рекомендуем использовать портал Отправки в Центре & соответствия требованиям. Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)

- Администраторы могут отключить или включить возможность для пользователей сообщать о сообщениях в Корпорацию Майкрософт Outlook в Интернете. Подробные сведения см. в разделе [Отключение](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) или включить нежелательные сообщения электронной почты в Outlook в веб-разделе, опубликованном в этой статье.

- Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан. Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)

- Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете

По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативах и фишинговых сообщениях в Microsoft для анализа Outlook в Интернете. Администраторы могут настраивать Outlook политик почтовых ящиков в Exchange Online PowerShell, чтобы пользователи не сообщали о ложных срабатываемых спама и нежелательных ложных негативах в Microsoft. Нельзя отключить возможность для пользователей сообщать о фишинговых сообщениях в Корпорацию Майкрософт.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Вам необходимо получить разрешения в Exchange Online, прежде чем вы сможете сделать процедуры в этой статье. В частности, вам нужны  роли **политики** получателей или получателей  почты, которые по умолчанию назначены группам ролей управления и управления получателями организации.  Дополнительные сведения о группах ролей в Exchange Online см. в Exchange Online [и](/exchange/permissions-exo/permissions-exo) изменения групп ролей [в Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но можно создавать настраиваемые политики. Пользовательские политики применяются к пользователям с масштабами перед политикой по умолчанию. Дополнительные сведения о Outlook политиках веб-почтовых ящиков см. в Outlook политиках веб-почтовых ящиков [в Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Отключение нежелательной отчетности по электронной почте не удаляет возможность пометить сообщение как нежелательное или нежелательное в Outlook в Интернете. Выбор сообщения в папке нежелательной почты и нажатие кнопки **Не** нежелательной не нежелательной по-прежнему перемещает сообщение обратно \>  в папку "Входящие". Выбор сообщения в любой другой папке  электронной почты и нажатие нежелательной нежелательной почты по-прежнему перемещает сообщение \>  в папку нежелательной почты. Больше нет возможности сообщить об этом сообщении в Корпорацию Майкрософт.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Использование Exchange Online PowerShell для отключения или отключения нежелательной отчетности по электронной почте Outlook в Интернете

1. Чтобы найти существующие Outlook политики веб-почтовых ящиков и состояние нежелательной отчетности по электронной почте, запустите следующую команду:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Чтобы отключить или включить нежелательные сообщения электронной почты Outlook в Интернете, используйте следующий синтаксис:

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

Чтобы убедиться, что вы успешно включили или отключили нежелательные сообщения электронной почты Outlook в Интернете, используйте любой из следующих действий:

- В Exchange Online PowerShell запустите следующую команду и проверьте значение свойства **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Откройте почтовый ящик пострадавшего пользователя Outlook в Интернете, выберите сообщение в почтовом ящике, щелкните нежелательной почты и убедитесь в том, что запрос на сообщение в Корпорацию Майкрософт отображается или не  \>  отображается.<sup>\*</sup>

- Откройте почтовый ящик пострадавшего пользователя Outlook в Интернете, выберите сообщение в папке  нежелательной почты, щелкните нежелательной почты и убедитесь, что сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup>

<sup>\*</sup> Пользователи могут скрыть запрос, чтобы сообщить о сообщении, но при этом сообщить о сообщении. Чтобы проверить этот параметр в Outlook в Интернете:

1. Щелкните **Параметры** ![ Outlook значке ](../../media/owa-settings-icon.png) \> **веб-параметров Просмотреть все** Outlook параметров \> **нежелательной почты**.
2. В разделе **Отчеты** проверьте значение: **Спросите меня перед отправкой отчета**.

   ![Outlook в настройках отчетов по электронной почте нежелательной почты](../../media/owa-junk-email-reporting-options.png)
