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
ms.openlocfilehash: a2a8c2f9120ff4b1d2efab4d7ae63294ce7f923b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091463"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="04e77-103">Отключение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="04e77-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="04e77-104">Вы можете отправлять нежелательные, фишинговые и нежелательные сообщения в корпорацию Майкрософт для анализа с помощью Outlook в Интернете (прежнее название Outlook Web App) для отчетов о нежелательной почте, как описано в статье [Report спам и фишинговые мошенничества в Outlook в Интернете ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="04e77-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="04e77-105">Если вы не хотите использовать эти параметры, администраторы могут отключить их с помощью командлета [Set – OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="04e77-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04e77-106">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="04e77-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="04e77-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="04e77-107"></span></span>

- <span data-ttu-id="04e77-108">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="04e77-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="04e77-109">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="04e77-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="04e77-110">Чтобы просмотреть необходимые разрешения, обратитесь к разделу "политики почтовых ящиков Outlook в Интернете" в разделе [Outlook в Интернете](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) .</span><span class="sxs-lookup"><span data-stu-id="04e77-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="04e77-111">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="04e77-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="04e77-112">Отключение нежелательных сообщений, фишинговых и нежелательных отчетов в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="04e77-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="04e77-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="04e77-113"></span></span>

<span data-ttu-id="04e77-114">Сначала выполните следующую команду, чтобы получить имена доступных в Outlook политик веб-почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="04e77-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="04e77-115">Затем используйте следующий синтаксис для включения или отключения нежелательных отчетов в Майкрософт в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="04e77-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="04e77-116">В этом примере отключаются отчеты в политике почтовых ящиков Outlook Web App по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="04e77-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="04e77-117">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) и [Set/OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span><span class="sxs-lookup"><span data-stu-id="04e77-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="04e77-118">Как проверить, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="04e77-118">How do you know this worked?</span></span>
<span data-ttu-id="04e77-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="04e77-119"></span></span>

<span data-ttu-id="04e77-120">Выполните командлет **Get-OWAMailboxPolicy** , чтобы проверить значения параметров, а затем откройте Outlook в Интернете для соответствующего пользователя (у которого к ним применена политика почтовых ящиков Outlook), и убедитесь, что параметры отчета о нежелательных, фишинговых и нежелательных элементов недоступны.</span><span class="sxs-lookup"><span data-stu-id="04e77-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="04e77-121">Вы по-прежнему можете помечать сообщения как нежелательные, фишинговые и нежелательные, но не можете их сообщать.</span><span class="sxs-lookup"><span data-stu-id="04e77-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
