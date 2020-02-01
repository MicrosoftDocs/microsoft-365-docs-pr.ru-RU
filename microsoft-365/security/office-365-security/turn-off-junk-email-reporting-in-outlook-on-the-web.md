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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="8bd80-103">Отключение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="8bd80-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="8bd80-104">Вы можете отправлять нежелательные, фишинговые и нежелательные сообщения в корпорацию Майкрософт для анализа с помощью Outlook в Интернете (прежнее название Outlook Web App) для отчетов о нежелательной почте, как описано в статье [Report спам и фишинговые мошенничества в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="8bd80-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="8bd80-105">Если вы не хотите использовать эти параметры, администраторы могут отключить их с помощью командлета [Set – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) .</span><span class="sxs-lookup"><span data-stu-id="8bd80-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8bd80-106">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="8bd80-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="8bd80-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd80-107"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="8bd80-108">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="8bd80-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="8bd80-109">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="8bd80-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8bd80-110">Чтобы просмотреть необходимые разрешения, обратитесь к разделу "политики почтовых ящиков Outlook в Интернете" в разделе [разрешения Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span><span class="sxs-lookup"><span data-stu-id="8bd80-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="8bd80-111">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8bd80-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="8bd80-112">Отключение нежелательных сообщений, фишинговых и нежелательных отчетов в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8bd80-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="8bd80-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd80-113"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="8bd80-114">Сначала выполните следующую команду, чтобы получить имена доступных в Outlook политик веб-почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="8bd80-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="8bd80-115">Затем используйте следующий синтаксис для включения или отключения нежелательных отчетов в Майкрософт в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="8bd80-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="8bd80-116">В этом примере отключаются отчеты в политике почтовых ящиков Outlook Web App по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="8bd80-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="8bd80-117">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) и [Set/OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="8bd80-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8bd80-118">Как проверить, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="8bd80-118">How do you know this worked?</span></span>
<span data-ttu-id="8bd80-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd80-119"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="8bd80-120">Выполните командлет **Get-OWAMailboxPolicy** , чтобы проверить значения параметров, а затем откройте Outlook в Интернете для соответствующего пользователя (у которого к ним применена политика почтовых ящиков Outlook), и убедитесь, что параметры отчета о нежелательных, фишинговых и нежелательных элементов недоступны.</span><span class="sxs-lookup"><span data-stu-id="8bd80-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="8bd80-121">Вы по-прежнему можете помечать сообщения как нежелательные, фишинговые и нежелательные, но не можете их сообщать.</span><span class="sxs-lookup"><span data-stu-id="8bd80-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
