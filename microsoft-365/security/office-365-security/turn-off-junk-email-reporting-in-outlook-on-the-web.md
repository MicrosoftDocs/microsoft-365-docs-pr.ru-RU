---
title: Отключение отчетов о нежелательной почте в Outlook в Интернете
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
ms.openlocfilehash: de0e5d1aa51ececafc0d344b9907f6751a613370
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441176"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Отключение отчетов о нежелательной почте в Outlook в Интернете

Вы можете отправлять нежелательные, фишинговые и нежелательные сообщения в корпорацию Майкрософт для анализа с помощью Outlook в Интернете (прежнее название Outlook Web App) для отчетов о нежелательной почте, как описано в статье [Report спам и фишинговые мошенничества в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Если вы не хотите использовать эти параметры, администраторы могут отключить их с помощью командлета [Set – OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?
<a name="sectionSection0"> </a>

- Предполагаемое время для завершения: 5 минут.
    
- Для выполнения этих процедур необходимы соответствующие разрешения. Чтобы просмотреть необходимые разрешения, обратитесь к разделу "политики почтовых ящиков Outlook в Интернете" в разделе [Outlook в Интернете](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) . 

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

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) и [Set/OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).

## <a name="how-do-you-know-this-worked"></a>Как проверить, что все получилось?
<a name="sectionSection2"> </a>

Выполните командлет **Get-OWAMailboxPolicy** , чтобы проверить значения параметров, а затем откройте Outlook в Интернете для соответствующего пользователя (у которого к ним применена политика почтовых ящиков Outlook), и убедитесь, что параметры отчета о нежелательных, фишинговых и нежелательных элементов недоступны. Вы по-прежнему можете помечать сообщения как нежелательные, фишинговые и нежелательные, но не можете их сообщать. 
