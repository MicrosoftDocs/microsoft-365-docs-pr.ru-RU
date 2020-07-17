---
title: Просмотр отчетов о защите от потери данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Использование отчетов о защите от потери данных в Office 365 для просмотра числа совпадений политики защиты от потери данных, переопределений или ложных срабатываний, а также о том, заменяются ли они на заданный момент времени.
ms.openlocfilehash: 1ddcd60dc9314779ade2f7ceae02d336f902e483
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818999"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="439fc-103">Просмотр отчетов о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="439fc-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="439fc-104">После создания политик защиты от потери данных (DLP) необходимо убедиться, что они работают должным образом и помогают обеспечить соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="439fc-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="439fc-105">С помощью отчетов DLP в центре безопасности &amp; и соответствия требованиям вы можете быстро просмотреть:</span><span class="sxs-lookup"><span data-stu-id="439fc-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="439fc-106">**Соответствия политике защиты от потери** данных В этом отчете показано количество совпадений политики защиты от потери данных с течением времени.</span><span class="sxs-lookup"><span data-stu-id="439fc-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="439fc-107">Вы можете отфильтровать отчет по дате, расположению, политике или действию.</span><span class="sxs-lookup"><span data-stu-id="439fc-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="439fc-108">Этот отчет можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="439fc-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="439fc-109">Настройка и уточнение политик защиты от потери данных во время их запуска в тестовом режиме.</span><span class="sxs-lookup"><span data-stu-id="439fc-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="439fc-110">Вы можете просмотреть конкретное правило, соответствующее содержимому.</span><span class="sxs-lookup"><span data-stu-id="439fc-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="439fc-111">сосредоточиться на определенных периодах времени и определить причины скачков и тенденций;</span><span class="sxs-lookup"><span data-stu-id="439fc-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="439fc-112">выявить бизнес-процессы, которые нарушают политики защиты от потери данных вашей организации;</span><span class="sxs-lookup"><span data-stu-id="439fc-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="439fc-113">Узнайте, какие действия применяются к содержимому, в любом бизнес-влиянии политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="439fc-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="439fc-114">проверить соответствие требованиям конкретной политики защиты от потери данных, отображая все совпадения с правилами этой политики;</span><span class="sxs-lookup"><span data-stu-id="439fc-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="439fc-115">Просмотр списка основных пользователей и повторение пользователей, участвующих в происшествиях в Организации.</span><span class="sxs-lookup"><span data-stu-id="439fc-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="439fc-116">Просмотрите список основных типов конфиденциальной информации в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="439fc-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="439fc-117">**Инциденты DLP** В этом отчете также отображаются соответствия политике с течением времени, например отчет о соответствии политикам.</span><span class="sxs-lookup"><span data-stu-id="439fc-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="439fc-118">Тем не менее, отчет соответствия политике отображает совпадения на уровне правила; Например, если адрес электронной почты соответствует трем различным правилам, в отчете политика соответствия политик отображаются три разные элементы строк.</span><span class="sxs-lookup"><span data-stu-id="439fc-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="439fc-119">В отчете о происшествиях, напротив, отображаются совпадения на уровне элементов; Например, если сообщение, сопоставляемое с тремя различными правилами, в отчете о происшествиях отображается один элемент строки для этого фрагмента контента.</span><span class="sxs-lookup"><span data-stu-id="439fc-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="439fc-120">Так как счетчики отчетов объединяются по-разному, отчет соответствия политике лучше для определения совпадений с определенными правилами и тонкой настройки политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="439fc-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="439fc-121">Отчет о происшествиях лучше определять конкретные фрагменты контента, которые являются проблематичными для политик защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="439fc-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="439fc-122">**Ложные срабатывания и переопределения защиты от потери** данных Если политика защиты от потери данных позволяет пользователям переопределять их или сообщать о ложном срабатывании, в этом отчете отображается количество таких экземпляров с течением времени.</span><span class="sxs-lookup"><span data-stu-id="439fc-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="439fc-123">Вы можете отфильтровать отчет по дате, расположению или политике.</span><span class="sxs-lookup"><span data-stu-id="439fc-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="439fc-124">Этот отчет можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="439fc-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="439fc-125">Настройте или уточните политики защиты от потери данных, указав, какие политики приводят к большому количеству ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="439fc-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="439fc-126">Просмотр обоснований, предоставленных пользователями при разрешении подсказки политики путем переопределения политики.</span><span class="sxs-lookup"><span data-stu-id="439fc-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="439fc-127">Узнайте, где политики защиты от потери данных конфликтуют с допустимыми бизнес-процессами, используя большое количество пользовательских переопределений.</span><span class="sxs-lookup"><span data-stu-id="439fc-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="439fc-128">Все отчеты DLP могут показывать данные из последнего периода времени из четырех месяцев.</span><span class="sxs-lookup"><span data-stu-id="439fc-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="439fc-129">Для отображения последних данных в отчетах может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="439fc-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="439fc-130">Эти отчеты можно найти в &amp; \> **Reports** \> **панели мониторинга "** безопасность отчетов" центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="439fc-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Отчет о соответствии политике защиты от потери данных](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="439fc-132">Просмотр выравнивания, предоставленного пользователем для переопределения</span><span class="sxs-lookup"><span data-stu-id="439fc-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="439fc-133">Если политика защиты от потери данных позволяет пользователям переопределять ее, можно использовать отчет о ложных срабатываниях и переопределении для просмотра текста, отправленного пользователями в подсказке политики.</span><span class="sxs-lookup"><span data-stu-id="439fc-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Поле обоснования в подробностях отчета о положительном и переопределении DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="439fc-135">Выполнение действий с подробностями и рекомендациями</span><span class="sxs-lookup"><span data-stu-id="439fc-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="439fc-136">В отчетах могут отображаться подробные сведения и рекомендации, с помощью которых можно щелкнуть красный значок предупреждения, чтобы просмотреть сведения о возможных проблемах и выполнить действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="439fc-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Щелкните значок Insight (аналитика), чтобы просмотреть сведения и действия, которые необходимо выполнить](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="439fc-138">Разрешения для отчетов о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="439fc-138">Permissions for DLP reports</span></span>

<span data-ttu-id="439fc-139">Для просмотра отчетов о защите от потери данных в центре безопасности & соответствия требованиям необходимо назначить:</span><span class="sxs-lookup"><span data-stu-id="439fc-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="439fc-140">Роль **читателя безопасности** в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="439fc-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="439fc-141">По умолчанию эта роль назначается группам ролей "Управление организацией" и "читатель безопасности" в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="439fc-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="439fc-142">Роль **управления соблюдением защиты от потери** данных в центре безопасности &.</span><span class="sxs-lookup"><span data-stu-id="439fc-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="439fc-143">По умолчанию эта роль назначается группам ролей "Администратор соответствия требованиям", "Управление организацией", "администратор безопасности" и "читатель безопасности" в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="439fc-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="439fc-144">Роль **получателей только для просмотра** в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="439fc-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="439fc-145">По умолчанию эта роль назначается группам ролей "Управление соответствием", "Управление организацией" и "Управление организацией" только для просмотра в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="439fc-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="439fc-146">Поиск командлетов для отчетов о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="439fc-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="439fc-147">Чтобы можно было использовать большинство командлетов в Центре безопасности и соответствия требованиям, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="439fc-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="439fc-148">Подключение к центру безопасности и &amp; соответствия требованиям с помощью удаленной оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="439fc-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="439fc-149">Используйте любой из этих [ &amp; командлетов центра соответствия требованиям безопасности](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="439fc-149">Use any of these [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="439fc-150">При этом, чтобы создавать отчеты со сведениями о защите от потери данных, системе потребуется получать данные из Office 365, в том числе из Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="439fc-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="439fc-151">По этой причине командлеты для отчетов DLP доступны в Exchange Online PowerShell, а не в интерфейсе &amp; PowerShell центра соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="439fc-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="439fc-152">Поэтому, чтобы можно было использовать эти командлеты для отчетов со сведениями о защите от потери данных, необходимо выполнить указанные действия.</span><span class="sxs-lookup"><span data-stu-id="439fc-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="439fc-153">[Подключитесь к Exchange Online с помощью удаленного сеанса PowerShell](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="439fc-153">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)</span></span>
    
2. <span data-ttu-id="439fc-154">Используйте следующие командлеты для отчетов со сведениями о защите от потери данных:</span><span class="sxs-lookup"><span data-stu-id="439fc-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="439fc-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="439fc-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="439fc-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="439fc-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

