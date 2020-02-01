---
title: Отключение отчетов о нежелательной почте в Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Как администратор Office 365, вы можете отключить возможность отправки отчетов о нежелательной почте для пользователей.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598126"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Отключение отчетов о нежелательной почте в Outlook в Интернете

Вы можете отправлять нежелательные, фишинговые и нежелательные сообщения в корпорацию Майкрософт для анализа с помощью Outlook в Интернете (прежнее название Outlook Web App) для отчетов о нежелательной почте, как описано в статье [Report спам и фишинговые мошенничества в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Если вы не хотите использовать эти параметры, администраторы могут отключить их с помощью командлета [Set – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?
<a name="sectionSection0"> </a>

- Предполагаемое время для завершения: 5 минут.

- Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Чтобы просмотреть необходимые разрешения, обратитесь к разделу "политики почтовых ящиков Outlook в Интернете" в разделе [разрешения Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

- Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Отключение нежелательных сообщений, фишинговых и нежелательных отчетов в Майкрософт
<a name="sectionSection1"> </a>

Сначала выполните следующую команду, чтобы получить имена доступных в Outlook политик веб-почтовых ящиков:

```
Get-OwaMailboxPolicy | Format-Table Name
```

Затем используйте следующий синтаксис для включения или отключения нежелательных отчетов в Майкрософт в Outlook в Интернете:

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

В этом примере отключаются отчеты в политике почтовых ящиков Outlook Web App по умолчанию:

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) и [Set/OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

## <a name="how-do-you-know-this-worked"></a>Как проверить, что все получилось?
<a name="sectionSection2"> </a>

Выполните командлет **Get-OWAMailboxPolicy** , чтобы проверить значения параметров, а затем откройте Outlook в Интернете для соответствующего пользователя (у которого к ним применена политика почтовых ящиков Outlook), и убедитесь, что параметры отчета о нежелательных, фишинговых и нежелательных элементов недоступны. Вы по-прежнему можете помечать сообщения как нежелательные, фишинговые и нежелательные, но не можете их сообщать.
