---
title: Зачем использовать PowerShell для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: Сводка. Сведения о том, почему для управления Microsoft 365 необходимо использовать PowerShell, в некоторых случаях более эффективно, а в других — по необходимости.
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754110"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="e16b1-103">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="e16b1-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e16b1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e16b1-105">С помощью Центра администрирования Microsoft 365 вы можете управлять учетными записями и лицензиями пользователей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="e16b1-106">Вы также можете управлять своими службами Microsoft 365, такими как Exchange Online, Teams и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e16b1-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="e16b1-107">Если вместо этого вы используете PowerShell для управления этими службами, вы можете использовать среду командной строки и языка сценариев для скорости, автоматизации и дополнительных возможностей.</span><span class="sxs-lookup"><span data-stu-id="e16b1-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="e16b1-108">В этой статье показано, как использовать PowerShell для управления Microsoft 365 для:</span><span class="sxs-lookup"><span data-stu-id="e16b1-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="e16b1-109">Раскрытие дополнительной информации, которую вы не видите в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="e16b1-110">Настройка функций и параметров возможна только с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e16b1-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="e16b1-111">Массовые операции</span><span class="sxs-lookup"><span data-stu-id="e16b1-111">Do bulk operations</span></span>
    
- <span data-ttu-id="e16b1-112">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="e16b1-112">Filter data</span></span>
    
- <span data-ttu-id="e16b1-113">Печать или сохранение данных</span><span class="sxs-lookup"><span data-stu-id="e16b1-113">Print or save data</span></span>
    
- <span data-ttu-id="e16b1-114">Управление службами</span><span class="sxs-lookup"><span data-stu-id="e16b1-114">Manage across services</span></span>
    
<span data-ttu-id="e16b1-115">Помните, что PowerShell для Microsoft 365 — это набор модулей для Windows PowerShell, которая является средой командной строки для служб и платформ windows.</span><span class="sxs-lookup"><span data-stu-id="e16b1-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="e16b1-116">В этой среде создается язык командной оболочки, который можно расширить с помощью дополнительных модулей.</span><span class="sxs-lookup"><span data-stu-id="e16b1-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="e16b1-117">Он предоставляет способ выполнения простых или сложных команд или сценариев.</span><span class="sxs-lookup"><span data-stu-id="e16b1-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="e16b1-118">Например, после установки модулей PowerShell для Microsoft 365 и подключения к подписке на Microsoft 365 можно выполнить следующую команду, чтобы получить список всех почтовых ящиков пользователей для Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e16b1-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="e16b1-119">Вы также можете получить список почтовых ящиков с помощью Центра администрирования Microsoft 365, но подсчет элементов во всех списках для всех сайтов для всех веб-приложений будет непростой задачей.</span><span class="sxs-lookup"><span data-stu-id="e16b1-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="e16b1-120">PowerShell для Microsoft 365 предназначен для управления Microsoft 365, а не для замены Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="e16b1-121">Администраторы должны иметь возможность использовать PowerShell для Microsoft 365, так как существуют некоторые процедуры настройки, которые можно сделать только с помощью PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="e16b1-122">В таких случаях необходимо знать, как:</span><span class="sxs-lookup"><span data-stu-id="e16b1-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="e16b1-123">Установите PowerShell для модулей Microsoft 365 (только один раз для каждого компьютера администратора).</span><span class="sxs-lookup"><span data-stu-id="e16b1-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="e16b1-124">Подключите свою подписку на Microsoft 365 (один раз для каждого сеанса PowerShell).</span><span class="sxs-lookup"><span data-stu-id="e16b1-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="e16b1-125">Соберите сведения, необходимые для запуска необходимых команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="e16b1-126">Запустите PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="e16b1-127">После того как вы изучите эти базовые навыки, вам не придется перечислять пользователей почтовых ящиков с помощью команды **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="e16b1-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="e16b1-128">Вам также не нужно понимать, как создать команду, например указанную ранее, чтобы подсчитать все элементы во всех списках для всех сайтов для всех веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="e16b1-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="e16b1-129">Майкрософт и сообщество администраторов могут помочь вам с такими задачами при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e16b1-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="e16b1-130">PowerShell для Microsoft 365 может раскрывать информацию, которую вы не видите в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="e16b1-131">В Центре администрирования Microsoft 365 отображается много полезной информации.</span><span class="sxs-lookup"><span data-stu-id="e16b1-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="e16b1-132">Однако в нем не отображаются все возможные сведения, которые Microsoft 365 хранит о пользователях, лицензиях, почтовых ящиках и сайтах.</span><span class="sxs-lookup"><span data-stu-id="e16b1-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="e16b1-133">Вот пример для пользователей и *групп в* Центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e16b1-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Пример отображения пользователей и групп в Центре администрирования Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="e16b1-135">Это представление предоставляет необходимую информацию во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="e16b1-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="e16b1-136">Однако иногда требуется больше.</span><span class="sxs-lookup"><span data-stu-id="e16b1-136">However, there are times when you need more.</span></span> <span data-ttu-id="e16b1-137">Например, лицензирование Microsoft 365 (и доступные пользователю функции Microsoft 365) частично зависит от географического расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="e16b1-138">Политики и функции, которые можно распространить на пользователя, который является пользователем в США, могут быть не теми, которые можно распространить на пользователя в Индии или Бельгии.</span><span class="sxs-lookup"><span data-stu-id="e16b1-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="e16b1-139">Чтобы определить географическое положение пользователя, выполните следующие действия в Центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e16b1-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="e16b1-140">Дважды щелкните **отображаемое имя** пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="e16b1-141">В области отображения свойств пользователя выберите **сведения.**</span><span class="sxs-lookup"><span data-stu-id="e16b1-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="e16b1-142">На экране сведений выберите **дополнительные сведения.**</span><span class="sxs-lookup"><span data-stu-id="e16b1-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="e16b1-143">Прокрутите страницу до тех пор, пока не найдете заголовок **"Страна или регион":**</span><span class="sxs-lookup"><span data-stu-id="e16b1-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Пример сведений о регионе для пользователя в Центре администрирования Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="e16b1-145">Запишите отображаемое имя и местонахождение пользователя на лист бумаги или скопируйте и вставьте их в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="e16b1-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="e16b1-146">Эту процедуру необходимо повторить для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="e16b1-147">Если у вас много пользователей, этот процесс может быть утомительным.</span><span class="sxs-lookup"><span data-stu-id="e16b1-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="e16b1-148">С помощью PowerShell для Microsoft 365 вы можете отобразить эти сведения для всех пользователей с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e16b1-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="e16b1-149">PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты *с Msol* в их имени.</span><span class="sxs-lookup"><span data-stu-id="e16b1-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="e16b1-150">Эти cmdlets необходимо запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e16b1-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="e16b1-151">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="e16b1-152">Эта команда PowerShell получает всех пользователей в текущей подписке Microsoft 365 (**Get-AzureADUser),** но отображает только имя и расположение каждого пользователя (**Select DisplayName, UsageLocation).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="e16b1-153">Так как PowerShell для Microsoft 365 поддерживает язык командной оболочки, вы можете дополнительно управлять информацией, полученной командой **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="e16b1-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="e16b1-154">Например, вы хотите отсортировать этих пользователей по их расположению, сгруппировать всех пользователей из Бразилии, всех пользователей ИЗ США и так далее.</span><span class="sxs-lookup"><span data-stu-id="e16b1-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="e16b1-155">Вот команда:</span><span class="sxs-lookup"><span data-stu-id="e16b1-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="e16b1-156">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="e16b1-157">Эта команда PowerShell получает всех пользователей в текущей подписке Microsoft 365, но отображает только имя и расположение каждого пользователя и сортировать их сначала по его расположению, а затем по имени **(Sort UsageLocation, DisplayName).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="e16b1-158">Можно также использовать дополнительную фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="e16b1-158">You can also use additional filtering.</span></span> <span data-ttu-id="e16b1-159">Например, если нужно просмотреть сведения о пользователях, находящихся в Бразилии, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e16b1-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="e16b1-160">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="e16b1-161">Эта команда PowerShell интер интерпретации: получить всех пользователей в текущей подписке Microsoft 365, чьи расположения в Бразилии (**Где {$ \_ . UsageLocation -eq "BR"}**) и отображение имени и расположения для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="e16b1-162">**Примечание о больших доменах**</span><span class="sxs-lookup"><span data-stu-id="e16b1-162">**A note about large domains**</span></span>
  
<span data-ttu-id="e16b1-163">Если у вас большой домен с десятками тысяч пользователей, некоторые примеры, которые мы покажем в этой статье, могут привести к регулированием.</span><span class="sxs-lookup"><span data-stu-id="e16b1-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="e16b1-164">В зависимости от таких факторов, как вычислительная мощность и доступная пропускная способность сети, вы можете пытаться сделать слишком много одновременно.</span><span class="sxs-lookup"><span data-stu-id="e16b1-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="e16b1-165">Крупным организациям может потребоваться разделить некоторые из этих операций PowerShell на две команды.</span><span class="sxs-lookup"><span data-stu-id="e16b1-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="e16b1-166">Например, следующая команда возвращает все учетные записи пользователей и отображает имя и расположение для каждой из них:</span><span class="sxs-lookup"><span data-stu-id="e16b1-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="e16b1-167">Она отлично подходит для небольших доменов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-167">That works great for smaller domains.</span></span> <span data-ttu-id="e16b1-168">Но в крупной организации может потребоваться разделить эту операцию на две команды: одну команду для хранения сведений об учетной записи пользователя в переменной, а другую для отображения необходимых сведений.</span><span class="sxs-lookup"><span data-stu-id="e16b1-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="e16b1-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="e16b1-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="e16b1-170">Этот набор команд PowerShell интер интерпретации:</span><span class="sxs-lookup"><span data-stu-id="e16b1-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="e16b1-171">Получите всех пользователей в текущей подписке Microsoft 365 и храните сведения в переменной $x (**$x = Get-AzureADUser).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="e16b1-172">Отображение содержимого переменной *$x,* но только имя и расположение для каждого пользователя (**$x | Выберите DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="e16b1-173">В Microsoft 365 есть функции, которые можно настроить только с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="e16b1-174">Центр администрирования Microsoft 365 предназначен для предоставления доступа к распространенным, полезным задачам администрирования, которые применяются к большинству сред.</span><span class="sxs-lookup"><span data-stu-id="e16b1-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="e16b1-175">Другими словами, Центр администрирования Microsoft 365 был разработан таким образом, чтобы типичный администратор может выполнять наиболее распространенные задачи управления.</span><span class="sxs-lookup"><span data-stu-id="e16b1-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="e16b1-176">Однако некоторые задачи нельзя выполнять в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="e16b1-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="e16b1-177">Например, в Центре администрирования Skype для бизнеса Online есть несколько вариантов создания настраиваемого приглашения на собрания:</span><span class="sxs-lookup"><span data-stu-id="e16b1-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Пример отображения настраиваемых приглашений на собрание в Центре администрирования Skype для бизнеса Online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="e16b1-179">С помощью указанных ниже параметров приглашения на собрания можно сделать более персонализированными и профессиональными.</span><span class="sxs-lookup"><span data-stu-id="e16b1-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="e16b1-180">Но параметры конфигурации собраний — это не просто создание настраиваемого приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="e16b1-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="e16b1-181">Например, по умолчанию собрания позволяют:</span><span class="sxs-lookup"><span data-stu-id="e16b1-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="e16b1-182">анонимным пользователям автоматически присоединяться к каждому собранию;</span><span class="sxs-lookup"><span data-stu-id="e16b1-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="e16b1-183">участникам записывать собрание;</span><span class="sxs-lookup"><span data-stu-id="e16b1-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="e16b1-184">обозначать всех пользователей из вашей организации докладчиками при их присоединении к собранию.</span><span class="sxs-lookup"><span data-stu-id="e16b1-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="e16b1-185">Эти параметры недоступны в Центре администрирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e16b1-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="e16b1-186">Вы можете управлять ими в PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="e16b1-187">Вот команда, которая отключает эти три параметра:</span><span class="sxs-lookup"><span data-stu-id="e16b1-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="e16b1-188">Чтобы выполнить эту команду, необходимо установить модуль [PowerShell Skype для бизнеса Online. ](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="e16b1-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="e16b1-189">Эта команда PowerShell интер интерпретация:</span><span class="sxs-lookup"><span data-stu-id="e16b1-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="e16b1-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="e16b1-191">Отключает возможность записи собраний участниками (**-AllowConferenceRecording $False).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="e16b1-192">Не назначайте всех пользователей из вашей организации в качестве presenters (**-DesignateAsPresenter "None"**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="e16b1-193">Чтобы восстановить эти параметры по умолчанию (включить параметры), запустите команду:</span><span class="sxs-lookup"><span data-stu-id="e16b1-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="e16b1-194">Существуют и другие аналогичные сценарии, поэтому администраторам следует знать, как запускать PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="e16b1-195">PowerShell для Microsoft 365 отлично подходит для массовых операций</span><span class="sxs-lookup"><span data-stu-id="e16b1-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="e16b1-196">Визуальные интерфейсы, такие как Центр администрирования Microsoft 365, являются наиболее ценными при одной операции.</span><span class="sxs-lookup"><span data-stu-id="e16b1-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="e16b1-197">Например, если необходимо отключить одну учетную запись пользователя, вы можете быстро найти и очистить этот контрольный ящик с помощью Центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="e16b1-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="e16b1-198">Это может быть проще, чем выполнение аналогичной операции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e16b1-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="e16b1-199">Но если вам нужно изменить множество вещей или некоторые выбранные в рамках большого набора других вещей, Центр администрирования Microsoft 365 может оказаться не лучшим средством.</span><span class="sxs-lookup"><span data-stu-id="e16b1-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="e16b1-200">Например, вы должны изменить префикс для тысяч номеров телефонов или удалить определенного пользователя *Ken Myer* со всех сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e16b1-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="e16b1-201">Как это сделать в Центре администрирования Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e16b1-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="e16b1-202">В последнем примере допустим, что у вас несколько сотен сайтов SharePoint Online, и вы не знаете, к каков из них входит Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="e16b1-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="e16b1-203">Сначала необходимо запустить Центр администрирования Microsoft 365, а затем выполнить эту процедуру для каждого сайта:</span><span class="sxs-lookup"><span data-stu-id="e16b1-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="e16b1-204">Выберите **URL-адрес** сайта.</span><span class="sxs-lookup"><span data-stu-id="e16b1-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="e16b1-205">В поле **свойств коллекции сайтов** выберите ссылку **"Адрес** веб-сайта", чтобы открыть сайт.</span><span class="sxs-lookup"><span data-stu-id="e16b1-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="e16b1-206">На сайте выберите **"Поделиться".**</span><span class="sxs-lookup"><span data-stu-id="e16b1-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="e16b1-207">В **диалоговом** окне "Поделиться" выберите ссылку, где будут показаны все пользователи с разрешениями на доступ к сайту:</span><span class="sxs-lookup"><span data-stu-id="e16b1-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Пример просмотра участников сайта SharePoint Online в Центре администрирования SharePoint Online](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="e16b1-209">В **диалоговом окне "Общий** доступ" выберите **"Дополнительные".**</span><span class="sxs-lookup"><span data-stu-id="e16b1-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="e16b1-210">Прокрутите список пользователей вниз, найдите и выберите Ken Myer (при условии, что у него есть разрешения на доступ к сайту), а затем выберите "Удалить **разрешения пользователя".**</span><span class="sxs-lookup"><span data-stu-id="e16b1-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="e16b1-211">Это займет много *времени* для нескольких сотен сайтов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="e16b1-212">Альтернативой является запуск следующей команды в PowerShell для Microsoft 365, чтобы удалить Кена Myer со всех сайтов:</span><span class="sxs-lookup"><span data-stu-id="e16b1-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="e16b1-213">Для этой команды необходимо установить модуль [SharePoint Online PowerShell.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="e16b1-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="e16b1-214">Эта команда PowerShell может получить все сайты SharePoint в текущей подписке Microsoft 365 (**Get-SPOSite),** а для каждого сайта удалить Кена Мейера из списка пользователей, которые могут получить к нему доступ (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="e16b1-215">Мы сообщите Microsoft 365, чтобы удалить Кена Мейера с каждого сайта, включая те, к кому у него нет доступа.</span><span class="sxs-lookup"><span data-stu-id="e16b1-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="e16b1-216">Таким образом, в результатах покажутся ошибки для тех сайтов, к которые у него нет доступа.</span><span class="sxs-lookup"><span data-stu-id="e16b1-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="e16b1-217">Мы можем использовать дополнительное условие для этой команды, чтобы удалить Кена Мейера только с сайтов, на которые он входит в список входа.</span><span class="sxs-lookup"><span data-stu-id="e16b1-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="e16b1-218">Но возвращаемая ошибка не причинит вреда самим сайтам.</span><span class="sxs-lookup"><span data-stu-id="e16b1-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="e16b1-219">На запуск этой команды для сотен сайтов может потребоваться несколько минут, а не часы работы в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="e16b1-220">Вот еще один пример массовой операции.</span><span class="sxs-lookup"><span data-stu-id="e16b1-220">Here's another bulk operation example.</span></span> <span data-ttu-id="e16b1-221">Используйте эту команду, чтобы добавить Нового администратора SharePoint Ленни *Киарни* на все сайты в организации:</span><span class="sxs-lookup"><span data-stu-id="e16b1-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="e16b1-222">Эта команда PowerShell выполняет конечную точку: получите все сайты SharePoint в текущей подписке Microsoft 365 и для каждого сайта разрешите доступ к Этому сайту, добавив имя для входа в группу "Участники" сайта (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="e16b1-223">PowerShell для Microsoft 365 отлично подходит для фильтрации данных</span><span class="sxs-lookup"><span data-stu-id="e16b1-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="e16b1-224">Центр администрирования Microsoft 365 предоставляет несколько способов фильтрации данных, чтобы легко найти целевое подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="e16b1-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="e16b1-225">Например, Exchange упрощает фильтрацию практически по любому свойству почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="e16b1-226">Например, вот список почтовых ящиков для всех пользователей, которые являются пользователями города Блумингтон:</span><span class="sxs-lookup"><span data-stu-id="e16b1-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Пример расширенных поисков в Центре администрирования Microsoft 365 для списка почтовых ящиков для всех пользователей, которые являются пользователями города Блумингтон.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="e16b1-228">Центр администрирования Exchange также позволяет объединять критерии фильтрации.</span><span class="sxs-lookup"><span data-stu-id="e16b1-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="e16b1-229">Например, можно найти почтовые ящики всех людей, которые работают в Блумингтоне и работают в финансовом отделе.</span><span class="sxs-lookup"><span data-stu-id="e16b1-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="e16b1-230">Однако существуют ограничения на действия, которые можно сделать в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="e16b1-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="e16b1-231">Например, вам не так просто найти почтовые ящики людей,  которые находятся в Блумингтоне или Сан-Орто, или почтовые ящики для всех людей, которые не находятся в г. Блумингтон.</span><span class="sxs-lookup"><span data-stu-id="e16b1-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="e16b1-232">Вы можете использовать следующую команду PowerShell для Microsoft 365, чтобы получить список почтовых ящиков для всех людей, которые живу в Блумингтоне или Сан-Кике:</span><span class="sxs-lookup"><span data-stu-id="e16b1-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="e16b1-233">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="e16b1-234">Эта команда PowerShell выполняется так: получите всех пользователей в текущей подписке На Microsoft 365, у которых есть почтовый ящик в городе Сан-Орт или Блумингтон (**где {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Дейс" -or $ \_ . City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="e16b1-235">А вот команда для списка всех почтовых ящиков людей, которые где-либо, кроме Блумингтона:</span><span class="sxs-lookup"><span data-stu-id="e16b1-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="e16b1-236">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="e16b1-237">Эта команда PowerShell выполняется так: получите всех пользователей в текущей подписке Microsoft 365, почтовый ящик которых не находится в г. Блумингтон **(где {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**), а затем отобразить имя и город для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="e16b1-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="e16b1-238">Использование поддиаными знаками</span><span class="sxs-lookup"><span data-stu-id="e16b1-238">Use wildcards</span></span>

<span data-ttu-id="e16b1-239">Для совпадения части имени в фильтрах PowerShell также можно использовать поддиаными знаками.</span><span class="sxs-lookup"><span data-stu-id="e16b1-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="e16b1-240">Например, предположим, что вы ищете учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="e16b1-241">Вы можете только запомнить, что фамилией пользователя был *Есенков* или, возможно, *Хельсон* или *Йоргенсон.*</span><span class="sxs-lookup"><span data-stu-id="e16b1-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="e16b1-242">Вы можете найти этого пользователя в Центре администрирования Microsoft 365 с помощью средства поиска и проведения трех различных поисковых запросов:</span><span class="sxs-lookup"><span data-stu-id="e16b1-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="e16b1-243">*Андерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="e16b1-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="e16b1-244">*Хендерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="e16b1-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="e16b1-245">*Йоргенсон*  .</span><span class="sxs-lookup"><span data-stu-id="e16b1-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="e16b1-246">Так как все три из этих имен заканчиваются на "son", вы можете сообщить PowerShell, чтобы отображались все пользователи, имена которых заканчиваются на "son".</span><span class="sxs-lookup"><span data-stu-id="e16b1-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="e16b1-247">Вот команда:</span><span class="sxs-lookup"><span data-stu-id="e16b1-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="e16b1-248">Эта команда PowerShell интер интерпретации: получить всех пользователей в текущей подписке Microsoft 365, но использовать фильтр, который перечисляет только пользователей, фамилии которых заканчиваются на "son" (**-Filter '{LastName -like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="e16b1-249">Означает любой набор символов, которые являются буквами в фамилии \* пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16b1-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="e16b1-250">PowerShell для Microsoft 365 упрощает печать и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="e16b1-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="e16b1-251">Центр администрирования Microsoft 365 позволяет просматривать списки данных.</span><span class="sxs-lookup"><span data-stu-id="e16b1-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="e16b1-252">Вот пример центра администрирования Skype для бизнеса Online, отображающий список пользователей, которым был включен Доступ к Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="e16b1-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Пример Центра администрирования Skype для бизнеса Online со списком пользователей, для которых включен Skype для бизнеса Online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="e16b1-254">Чтобы сохранить эти сведения в файл, необходимо в paste it into a document or Microsoft Excel worksheet.</span><span class="sxs-lookup"><span data-stu-id="e16b1-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="e16b1-255">В любом случае может потребоваться дополнительное форматирование.</span><span class="sxs-lookup"><span data-stu-id="e16b1-255">Either case might require additional formatting.</span></span> <span data-ttu-id="e16b1-256">Кроме того, Центр администрирования Microsoft 365 не предоставляет способ непосредственной печати отображаемого списка.</span><span class="sxs-lookup"><span data-stu-id="e16b1-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="e16b1-257">К счастью, с помощью PowerShell можно не только отобразить список, но и сохранить его в файл, который можно легко импортировать в Excel.</span><span class="sxs-lookup"><span data-stu-id="e16b1-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="e16b1-258">Вот пример команды для сохранения пользовательских данных Skype для бизнеса Online в CSV-файл, который можно легко импортировать в качестве таблицы на листах Excel:</span><span class="sxs-lookup"><span data-stu-id="e16b1-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="e16b1-259">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-259">Here's an example of the results:</span></span>
  
![Пример таблицы, импортируемой в таблицу Excel для пользовательских данных Skype для бизнеса Online, сохраненных в файле значений, разделенных запятой.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="e16b1-261">Эта команда PowerShell интер интерпретации: получить всех пользователей Skype для бизнеса Online в текущей подписке Microsoft 365 (**Get-CsOnlineUser**); получение только имени пользователя, имени пользователя и расположения (**Select DisplayName, UserPrincipalName, UsageLocation);** затем сохраните эти сведения в CSV-файле C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="e16b1-262">Вы также можете использовать параметры для сохранения этого списка в формате XML-файла или HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="e16b1-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="e16b1-263">На самом деле с помощью дополнительных команд PowerShell вы можете сохранить его непосредственно в виде файла Excel с любым пользовательским форматированием.</span><span class="sxs-lookup"><span data-stu-id="e16b1-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="e16b1-264">Вы также можете отправить выходные данные команды PowerShell, которая отображает список непосредственно на принтере по умолчанию в Windows.</span><span class="sxs-lookup"><span data-stu-id="e16b1-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="e16b1-265">Вот пример команды:</span><span class="sxs-lookup"><span data-stu-id="e16b1-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="e16b1-266">Ниже показано, как будет выглядеть напечатанный документ.</span><span class="sxs-lookup"><span data-stu-id="e16b1-266">Here's what your printed document will look like:</span></span>
  
![Пример распечатанных документов, которые были выходными данными команды PowerShell, отправленной непосредственно на принтер по умолчанию в Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="e16b1-268">Эта команда PowerShell интер интерпретация: получить всех пользователей Skype для бизнеса Online в текущей подписке Microsoft 365; получение только имени пользователя, имени пользователя и расположения; а затем отправьте эти сведения на принтер Windows по умолчанию (**Out-Printer).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="e16b1-269">Печатный документ имеет такое же простое форматирование, как и отображение в командном окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e16b1-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="e16b1-270">Чтобы получить твердую копию, просто добавьте | **Вне принтера** до конца команды.</span><span class="sxs-lookup"><span data-stu-id="e16b1-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="e16b1-271">PowerShell для Microsoft 365 позволяет управлять серверным продуктом</span><span class="sxs-lookup"><span data-stu-id="e16b1-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="e16b1-272">Компоненты, составляющие Microsoft 365, предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="e16b1-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="e16b1-273">Например, предположим, что вы добавили нового пользователя в Microsoft 365 и указали такие сведения, как его отдел и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="e16b1-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="e16b1-274">Эти сведения будут доступны при доступе к сведениям пользователя в любой из служб Microsoft 365: Skype для бизнеса Online, Exchange или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e16b1-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="e16b1-275">Это общие сведения, распространяющиеся на набор продуктов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="e16b1-276">Информация о продукте, например сведения о почтовом ящике Exchange пользователя, обычно недоступна в наборе.</span><span class="sxs-lookup"><span data-stu-id="e16b1-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="e16b1-277">Например, сведения о том, включен ли почтовый ящик пользователя, доступны только в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="e16b1-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="e16b1-278">Предположим, вы хотите создать отчет со следующим сведениями обо всех пользователях:</span><span class="sxs-lookup"><span data-stu-id="e16b1-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="e16b1-279">краткое имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="e16b1-279">The user's display name</span></span>
    
- <span data-ttu-id="e16b1-280">Имеет ли пользователь лицензию на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="e16b1-281">включен ли почтовый ящик Exchange пользователя;</span><span class="sxs-lookup"><span data-stu-id="e16b1-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="e16b1-282">включено ли для пользователя приложение Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e16b1-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="e16b1-283">Вы не можете легко создать такой отчет в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e16b1-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e16b1-284">Вместо этого необходимо создать отдельный документ для хранения информации, например листа Excel.</span><span class="sxs-lookup"><span data-stu-id="e16b1-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="e16b1-285">Затем получите все имена пользователей и сведения о лицензировании в Центре администрирования Microsoft 365, получите сведения о почтовом ящике из Центра администрирования Exchange, получите сведения о Skype для бизнеса Online из Центра администрирования Skype для бизнеса Online, а затем объединяйте эти сведения.</span><span class="sxs-lookup"><span data-stu-id="e16b1-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="e16b1-286">Альтернативой является использование скрипта PowerShell для компиляции отчета.</span><span class="sxs-lookup"><span data-stu-id="e16b1-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="e16b1-287">В следующем примере сценарий сложнее, чем команды, которые вы уже видели в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e16b1-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="e16b1-288">Однако он показывает возможность использования PowerShell для создания представлений информации, которые сложно получить в противном случае.</span><span class="sxs-lookup"><span data-stu-id="e16b1-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="e16b1-289">Вот сценарий для компиляции и отображения нужного списка:</span><span class="sxs-lookup"><span data-stu-id="e16b1-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="e16b1-290">Ниже приводится пример результатов.</span><span class="sxs-lookup"><span data-stu-id="e16b1-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="e16b1-291">Этот сценарий PowerShell интер интерпретации:</span><span class="sxs-lookup"><span data-stu-id="e16b1-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="e16b1-292">Получите всех пользователей в текущей подписке Microsoft 365 и храните сведения в переменной с именем *$x* (**$x = Get-AzureADUser).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="e16b1-293">Запустите цикл, который выполняется над всеми пользователями в переменной $x (**foreach ($i в $x).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="e16b1-294">Определите переменную *с именем $y* и храните в ней сведения о почтовом ящике пользователя (**$y = Get-Mailbox -Identity $i.UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="e16b1-295">Добавьте новое свойство к сведениям о пользователе с именем *IsMailBoxEnabled.*</span><span class="sxs-lookup"><span data-stu-id="e16b1-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="e16b1-296">Установите для него значение свойства IsMailBoxEnabled почтового ящика пользователя (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="e16b1-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="e16b1-297">Определите переменную *с именем $y* и храните в ней сведения о Skype для бизнеса Online пользователя (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="e16b1-298">Добавьте новое свойство к сведениям о пользователе с именем *EnabledForSfB.*</span><span class="sxs-lookup"><span data-stu-id="e16b1-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="e16b1-299">Установите для него значение свойства Enabled сведений о Skype для бизнеса Online пользователя (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="e16b1-300">Отображает список пользователей, но включает только их имя, лицензируются ли они, и два новых свойства, которые указывают, включен ли их почтовый ящик и включена ли для них Skype для бизнеса Online **($x | Выберите DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB).**</span><span class="sxs-lookup"><span data-stu-id="e16b1-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e16b1-301">См. также</span><span class="sxs-lookup"><span data-stu-id="e16b1-301">See also</span></span>

[<span data-ttu-id="e16b1-302">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e16b1-303">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e16b1-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e16b1-304">Использование Windows PowerShell для создания отчетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e16b1-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
