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
description: Сводка. сведения о том, почему необходимо использовать PowerShell для управления Microsoft 365, в некоторых случаях, более эффективно и в других случаях.
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754110"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="8328a-103">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="8328a-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8328a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8328a-105">С помощью центра администрирования Microsoft 365 вы можете управлять пользовательскими учетными записями и лицензиями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="8328a-106">Вы также можете управлять службами Microsoft 365, такими как Exchange Online, Teams и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8328a-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="8328a-107">Если вместо этого вы используете PowerShell для управления этими службами, вы можете использовать преимущества командной строки и язык сценариев для ускорения, автоматизации и дополнительных возможностей.</span><span class="sxs-lookup"><span data-stu-id="8328a-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="8328a-108">В этой статье показано, как использовать PowerShell для управления Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8328a-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="8328a-109">Отображение дополнительной информации, которая не отображается в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="8328a-110">Настройка функций и параметров, доступных только в PowerShell</span><span class="sxs-lookup"><span data-stu-id="8328a-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="8328a-111">Выполнение массовых операций</span><span class="sxs-lookup"><span data-stu-id="8328a-111">Do bulk operations</span></span>
    
- <span data-ttu-id="8328a-112">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="8328a-112">Filter data</span></span>
    
- <span data-ttu-id="8328a-113">Печать или сохранение данных</span><span class="sxs-lookup"><span data-stu-id="8328a-113">Print or save data</span></span>
    
- <span data-ttu-id="8328a-114">Управление между службами</span><span class="sxs-lookup"><span data-stu-id="8328a-114">Manage across services</span></span>
    
<span data-ttu-id="8328a-115">Помните, что PowerShell для Microsoft 365 — это набор модулей для Windows PowerShell, который представляет собой среду командной строки для служб и платформ на основе Windows.</span><span class="sxs-lookup"><span data-stu-id="8328a-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="8328a-116">Эта среда создает язык командной консоли, который можно расширить с помощью дополнительных модулей.</span><span class="sxs-lookup"><span data-stu-id="8328a-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="8328a-117">Он предоставляет способ выполнения простых или сложных команд или сценариев.</span><span class="sxs-lookup"><span data-stu-id="8328a-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="8328a-118">Например, после установки модулей PowerShell для Microsoft 365 и подключения к вашей подписке Microsoft 365 можно выполнить следующую команду, чтобы получить список всех почтовых ящиков пользователей для Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8328a-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="8328a-119">Вы также можете получить список почтовых ящиков с помощью центра администрирования Microsoft 365, но подсчитать элементы во всех списках всех сайтов для всех веб-приложений непросто.</span><span class="sxs-lookup"><span data-stu-id="8328a-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="8328a-120">PowerShell для Microsoft 365 предназначен для управления Microsoft 365, а не для замены центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="8328a-121">Администраторы должны иметь возможность использовать PowerShell для Microsoft 365, так как некоторые процедуры настройки можно выполнить только с помощью команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="8328a-122">В таких случаях необходимо знать, как:</span><span class="sxs-lookup"><span data-stu-id="8328a-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="8328a-123">Установите PowerShell для модулей Microsoft 365 (выполнить только один раз для каждого компьютера администратора).</span><span class="sxs-lookup"><span data-stu-id="8328a-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="8328a-124">Подключаться к вашей подписке Microsoft 365 (один раз для каждого сеанса PowerShell);</span><span class="sxs-lookup"><span data-stu-id="8328a-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="8328a-125">Соберите информацию, необходимую для запуска необходимых команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="8328a-126">Запустите PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="8328a-127">Изучите эти основные навыки, вам не нужно перечислить пользователей почтовых ящиков с помощью команды **Get/Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="8328a-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="8328a-128">Кроме того, вам не нужно знать, как создать новую команду, например команду, указанную ранее, чтобы подсчитать все элементы во всех списках всех сайтов для всех веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="8328a-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="8328a-129">Корпорация Майкрософт и сообщество администраторов могут помочь вам с такими задачами.</span><span class="sxs-lookup"><span data-stu-id="8328a-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="8328a-130">В PowerShell для Microsoft 365 может отображаться информация, которая не отображается в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="8328a-131">Центр администрирования Microsoft 365 содержит много полезной информации.</span><span class="sxs-lookup"><span data-stu-id="8328a-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="8328a-132">Но в нем не отображаются все возможные сведения о пользователях, лицензиях, почтовых ящиках и сайтах, которые хранятся в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="8328a-133">Ниже приведен пример для *пользователей и групп* в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8328a-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Пример отображения пользователей и групп в центре администрирования Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="8328a-135">Это представление предоставляет сведения, необходимые для многих случаев.</span><span class="sxs-lookup"><span data-stu-id="8328a-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="8328a-136">Однако бывают случаи, когда вам требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="8328a-136">However, there are times when you need more.</span></span> <span data-ttu-id="8328a-137">Например, лицензирование Microsoft 365 (и функции Microsoft 365, доступные пользователю) зависят от географического расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="8328a-138">Политики и функции, которые можно расширить для пользователя, который живет в США, могут отличаться от тех, которые можно расширить для пользователя в Индии или Бельгии.</span><span class="sxs-lookup"><span data-stu-id="8328a-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="8328a-139">Чтобы определить географическое расположение пользователя, выполните следующие действия в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8328a-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="8328a-140">Дважды щелкните **отображаемое имя** пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="8328a-141">В области Отображение свойств пользователя выберите **сведения**.</span><span class="sxs-lookup"><span data-stu-id="8328a-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="8328a-142">В отображении сведений выберите **Дополнительные сведения**.</span><span class="sxs-lookup"><span data-stu-id="8328a-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="8328a-143">Прокрутите страницу, пока не найдете **название страны или региона**:</span><span class="sxs-lookup"><span data-stu-id="8328a-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Пример сведений о регионе для пользователя в центре администрирования Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="8328a-145">Запишите отображаемое имя и местонахождение пользователя на лист бумаги или скопируйте и вставьте их в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="8328a-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="8328a-146">Эту процедуру необходимо повторить для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="8328a-147">Если у вас много пользователей, этот процесс может быть утомительным.</span><span class="sxs-lookup"><span data-stu-id="8328a-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="8328a-148">С помощью PowerShell для Microsoft 365 вы можете отобразить эту информацию для всех пользователей с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8328a-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="8328a-149">PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модулей Windows PowerShell и командлетов, в именах которых *MSOL* .</span><span class="sxs-lookup"><span data-stu-id="8328a-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="8328a-150">Эти командлеты необходимо запускать в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8328a-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="8328a-151">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="8328a-152">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 (**Get-AzureADUser**), но отображение только имени и расположения каждого пользователя (**выберите DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="8328a-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="8328a-153">Так как PowerShell для Microsoft 365 поддерживает язык командной консоли, вы можете дополнительно манипулировать сведениями, полученными с помощью команды **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="8328a-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="8328a-154">Например, вы хотели бы сортировать этих пользователей по их расположению, объединяя всех пользователей Бразилии, всех пользователей США и т. д.</span><span class="sxs-lookup"><span data-stu-id="8328a-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="8328a-155">Вот эта команда:</span><span class="sxs-lookup"><span data-stu-id="8328a-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="8328a-156">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="8328a-157">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365, но отображение имени и расположения каждого пользователя и сортировка их по их расположению, а затем по имени (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="8328a-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="8328a-158">Кроме того, можно использовать дополнительную фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="8328a-158">You can also use additional filtering.</span></span> <span data-ttu-id="8328a-159">Например, если нужно просмотреть сведения о пользователях, находящихся в Бразилии, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8328a-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="8328a-160">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="8328a-161">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365, чье расположение — Бразилия (**где {$ \_ . UsageLocation-EQ "BR"}**), а затем отобразите имя и местоположение каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="8328a-162">**Примечание о больших доменах**</span><span class="sxs-lookup"><span data-stu-id="8328a-162">**A note about large domains**</span></span>
  
<span data-ttu-id="8328a-163">Если у вас большой домен с десятками тысяч пользователей, попробуйте в некоторых примерах, приведенных в этой статье, привести к регулированию.</span><span class="sxs-lookup"><span data-stu-id="8328a-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="8328a-164">На основе таких факторов, как вычислительная мощность и доступная пропускная способность сети, вы можете попробовать слишком много времени.</span><span class="sxs-lookup"><span data-stu-id="8328a-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="8328a-165">В крупных организациях может потребоваться разделить некоторые операции PowerShell на две команды.</span><span class="sxs-lookup"><span data-stu-id="8328a-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="8328a-166">Например, следующая команда возвращает все учетные записи пользователей и отображает имя и расположение каждого из них:</span><span class="sxs-lookup"><span data-stu-id="8328a-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="8328a-167">Она отлично подходит для небольших доменов.</span><span class="sxs-lookup"><span data-stu-id="8328a-167">That works great for smaller domains.</span></span> <span data-ttu-id="8328a-168">Но в большой организации может потребоваться разделить эту операцию на две команды: одна команда для хранения данных учетной записи пользователя в переменной, а другая — для отображения необходимой информации.</span><span class="sxs-lookup"><span data-stu-id="8328a-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="8328a-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="8328a-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="8328a-170">Ниже приведена интерпретация этого набора команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8328a-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="8328a-171">Получите всех пользователей в текущей подписке на Microsoft 365 и сохраните их в переменной с именем $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="8328a-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="8328a-172">Отображение содержимого переменной *$x*, но включать только имя и местоположение каждого пользователя (**$x | Выберите DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="8328a-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="8328a-173">Microsoft 365 содержит функции, которые можно настроить только с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="8328a-174">Центр администрирования Microsoft 365 предназначен для обеспечения доступа к общим и удобным административным задачам, которые применимы к большинству сред.</span><span class="sxs-lookup"><span data-stu-id="8328a-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="8328a-175">Другими словами, центр администрирования Microsoft 365 разработан, чтобы обычный администратор мог выполнять наиболее распространенные задачи управления.</span><span class="sxs-lookup"><span data-stu-id="8328a-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="8328a-176">Но в центре администрирования можно выполнить некоторые задачи.</span><span class="sxs-lookup"><span data-stu-id="8328a-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="8328a-177">Например, центр администрирования Skype для бизнеса Online предоставляет несколько вариантов для создания настраиваемых приглашений на собрания:</span><span class="sxs-lookup"><span data-stu-id="8328a-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Пример отображения настраиваемых приглашений на собрание в Центре администрирования Skype для бизнеса Online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="8328a-179">С помощью указанных ниже параметров приглашения на собрания можно сделать более персонализированными и профессиональными.</span><span class="sxs-lookup"><span data-stu-id="8328a-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="8328a-180">Но параметры настройки собраний больше, чем простое создание настраиваемых приглашений на собрания.</span><span class="sxs-lookup"><span data-stu-id="8328a-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="8328a-181">Например, по умолчанию собрания позволяют:</span><span class="sxs-lookup"><span data-stu-id="8328a-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="8328a-182">анонимным пользователям автоматически присоединяться к каждому собранию;</span><span class="sxs-lookup"><span data-stu-id="8328a-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="8328a-183">участникам записывать собрание;</span><span class="sxs-lookup"><span data-stu-id="8328a-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="8328a-184">обозначать всех пользователей из вашей организации докладчиками при их присоединении к собранию.</span><span class="sxs-lookup"><span data-stu-id="8328a-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="8328a-185">Эти параметры недоступны в центре администрирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8328a-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="8328a-186">Вы можете управлять ими в PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="8328a-187">Вот команда, с помощью которой отключаются эти три параметра:</span><span class="sxs-lookup"><span data-stu-id="8328a-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="8328a-188">Для выполнения этой команды необходимо установить [модуль PowerShell для Skype для бизнеса Online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="8328a-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="8328a-189">Эта команда PowerShell интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8328a-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="8328a-190">В разделе Параметры новых собраний Skype для бизнеса Online (**Set-CsMeetingConfiguration**) отключите разрешение анонимным пользователям получать автоматический вход в собрания (**-адмитанонимаусусерсбидефаулт $false**).</span><span class="sxs-lookup"><span data-stu-id="8328a-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="8328a-191">Отключение возможности записи собраний участниками (**-AllowConferenceRecording $false**).</span><span class="sxs-lookup"><span data-stu-id="8328a-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="8328a-192">Не указывайте всех пользователей в Организации как выступающих (**-десигнатеаспресентер "нет"**).</span><span class="sxs-lookup"><span data-stu-id="8328a-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="8328a-193">Чтобы восстановить эти параметры по умолчанию (включите параметры), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8328a-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="8328a-194">Существуют и другие схожие сценарии, поэтому администраторы должны знать, как запускать PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="8328a-195">PowerShell для Microsoft 365 отлично подходит для массовых операций</span><span class="sxs-lookup"><span data-stu-id="8328a-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="8328a-196">Визуальные интерфейсы, такие как центр администрирования Microsoft 365, наиболее полезны, если у вас есть одна операция.</span><span class="sxs-lookup"><span data-stu-id="8328a-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="8328a-197">Например, если необходимо отключить одну учетную запись пользователя, вы можете использовать центр администрирования для быстрого обнаружения и снятия флажка.</span><span class="sxs-lookup"><span data-stu-id="8328a-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="8328a-198">Это может быть проще, чем выполнение аналогичной операции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8328a-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="8328a-199">Но если вам нужно изменить множество вещей или некоторые из выбранных элементов в большом наборе других элементов, центр администрирования Microsoft 365 может быть не лучшим средством.</span><span class="sxs-lookup"><span data-stu-id="8328a-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="8328a-200">Например, предположим, что необходимо изменить префикс для тысяч телефонных номеров или удалить определенного пользователя *Ken Myer* со всех сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8328a-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="8328a-201">Как это можно сделать в центре администрирования Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="8328a-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="8328a-202">В последнем примере предположим, что у вас есть несколько сотен сайтов SharePoint Online, и вы не знаете, в каких из них Кен Крюкова входит.</span><span class="sxs-lookup"><span data-stu-id="8328a-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="8328a-203">Необходимо запустить центр администрирования Microsoft 365, а затем выполнить эту процедуру для каждого сайта:</span><span class="sxs-lookup"><span data-stu-id="8328a-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="8328a-204">Выберите **URL-адрес** сайта.</span><span class="sxs-lookup"><span data-stu-id="8328a-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="8328a-205">В поле **Свойства семейства веб-сайтов** выберите ссылку **адрес веб-сайта** , чтобы открыть сайт.</span><span class="sxs-lookup"><span data-stu-id="8328a-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="8328a-206">На сайте выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="8328a-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="8328a-207">В диалоговом окне **общий доступ** выберите ссылку, в которой отображаются все пользователи с разрешениями для сайта:</span><span class="sxs-lookup"><span data-stu-id="8328a-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Пример просмотра участников сайта SharePoint Online в Центре администрирования SharePoint Online](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="8328a-209">В диалоговом окне **общий доступ** выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="8328a-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="8328a-210">Прокрутите список пользователей, найдите и выберите Кен Myer (предполагая, что у него есть разрешения для сайта), а затем выберите **удалить разрешения пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8328a-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="8328a-211">Это займет *много* времени для нескольких сотен сайтов.</span><span class="sxs-lookup"><span data-stu-id="8328a-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="8328a-212">Кроме того, можно выполнить следующую команду в PowerShell для Microsoft 365, чтобы удалить Ken Myer со всех сайтов:</span><span class="sxs-lookup"><span data-stu-id="8328a-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="8328a-213">Для этой команды необходимо установить [модуль PowerShell для SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="8328a-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="8328a-214">Интерпретация этой команды PowerShell: получение всех сайтов SharePoint в текущей подписке на Microsoft 365 (**Get-SPOSite**) и для каждого сайта. Удалите Ken Крюкова из списка пользователей, имеющих доступ к нему (**foreach {Remove-супруг-site $) \_ . URL-адрес LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="8328a-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="8328a-215">Мы говорим корпорации Майкрософт 365 удалить Ken Крюкова со всех сайтов, в том числе к тем, у которых у него нет доступа.</span><span class="sxs-lookup"><span data-stu-id="8328a-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="8328a-216">Таким образом, результаты будут показывать ошибки для тех сайтов, к которым у них нет доступа.</span><span class="sxs-lookup"><span data-stu-id="8328a-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="8328a-217">В этой команде можно использовать дополнительное условие, чтобы удалить Ken Крюкова только с сайтов, на которых они находятся в списке входа.</span><span class="sxs-lookup"><span data-stu-id="8328a-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="8328a-218">Однако возвращенные ошибки не дают вред сайтам.</span><span class="sxs-lookup"><span data-stu-id="8328a-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="8328a-219">Выполнение этой команды может занять несколько минут, а не часов работы с сотнями сайтов в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="8328a-220">Вот еще один пример массовой операции.</span><span class="sxs-lookup"><span data-stu-id="8328a-220">Here's another bulk operation example.</span></span> <span data-ttu-id="8328a-221">Используйте эту команду, чтобы добавить *Бонние кеарнэй*, новый администратор SharePoint для всех сайтов в Организации:</span><span class="sxs-lookup"><span data-stu-id="8328a-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="8328a-222">Интерпретация этой команды PowerShell: получение всех сайтов SharePoint в текущей подписке на Microsoft 365 и для каждого сайта разрешить доступ к Бонние Кеарнэй, добавив имя для входа в группу "участники" сайта (**foreach {Add-супруг-site $) \_ . URL-адрес LoginName "бкеарнэй \@ litwareinc.com"-Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="8328a-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="8328a-223">PowerShell для Microsoft 365 отлично подходит для фильтрации данных</span><span class="sxs-lookup"><span data-stu-id="8328a-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="8328a-224">Центр администрирования Microsoft 365 предоставляет несколько способов фильтрации данных, чтобы легко находить целевое подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="8328a-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="8328a-225">Например, Exchange упрощает фильтрацию практически любого свойства почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="8328a-226">Например, ниже приведен список почтовых ящиков для всех пользователей, проживающих в городе Блумингтон:</span><span class="sxs-lookup"><span data-stu-id="8328a-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Пример расширенного поиска в центре администрирования Microsoft 365 для списка почтовых ящиков всех пользователей, проживающих в городе Блумингтон.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="8328a-228">В центре администрирования Exchange также можно объединять условия фильтрации.</span><span class="sxs-lookup"><span data-stu-id="8328a-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="8328a-229">Например, вы можете найти почтовые ящики всех пользователей, проживающих в Блумингтон, и работать в отделе финансов.</span><span class="sxs-lookup"><span data-stu-id="8328a-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="8328a-230">Но в центре администрирования Exchange есть ограничения.</span><span class="sxs-lookup"><span data-stu-id="8328a-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="8328a-231">Например, невозможно легко найти почтовые ящики людей, проживающих в Блумингтон *или* Сан Диего, или почтовые ящики для всех пользователей, которые не работают в Блумингтон.</span><span class="sxs-lookup"><span data-stu-id="8328a-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="8328a-232">Вы можете использовать следующую команду PowerShell для Microsoft 365, чтобы получить список почтовых ящиков для всех пользователей, проживающих в Блумингтон или Сан Диего:</span><span class="sxs-lookup"><span data-stu-id="8328a-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="8328a-233">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="8328a-234">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 с почтовым ящиком в городе Сан-Диего или Блумингтон (**где {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City – Eq "Сан Диего" (или $) \_ . City-Eq "Блумингтон")}**), а затем отобразить имя и город для каждого из них (**выберите DisplayName, City**).</span><span class="sxs-lookup"><span data-stu-id="8328a-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="8328a-235">Ниже приведена команда для перечисления всех почтовых ящиков пользователей, которые живут в любом месте за исключением Блумингтон:</span><span class="sxs-lookup"><span data-stu-id="8328a-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="8328a-236">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="8328a-237">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 с почтовым ящиком, не расположенным в городе Блумингтон (**где {$ \_ . RecipientTypeDetails — EQ "UserMailbox" и $ \_ . City-NE "Блумингтон"}**), а затем отображает имя и город для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="8328a-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="8328a-238">Использование подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="8328a-238">Use wildcards</span></span>

<span data-ttu-id="8328a-239">Кроме того, можно использовать подстановочные знаки в фильтрах PowerShell для сопоставления части имени.</span><span class="sxs-lookup"><span data-stu-id="8328a-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="8328a-240">Например, предположим, что вы ищете учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="8328a-241">Вы можете запомнить, что фамилия пользователя — *Андерсон;* или, возможно, *Хендерсон;* или *Йоргенсон*.</span><span class="sxs-lookup"><span data-stu-id="8328a-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="8328a-242">Вы можете проследить этого пользователя в центре администрирования Microsoft 365 с помощью средства поиска и выполнить три различных поиска:</span><span class="sxs-lookup"><span data-stu-id="8328a-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="8328a-243">*Андерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="8328a-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="8328a-244">*Хендерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="8328a-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="8328a-245">*Йоргенсон*  .</span><span class="sxs-lookup"><span data-stu-id="8328a-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="8328a-246">Так как все три из этих имен заканчиваются на ""] ", вы можете указать PowerShell, чтобы отобразить всех пользователей, чье имя оканчивается на" "]".</span><span class="sxs-lookup"><span data-stu-id="8328a-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="8328a-247">Вот эта команда:</span><span class="sxs-lookup"><span data-stu-id="8328a-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="8328a-248">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365, но использование фильтра, в котором указаны только те пользователи, чьи фамилии заканчиваются на "E3" (**-Filter "{LastName-Like" "] \* "**).</span><span class="sxs-lookup"><span data-stu-id="8328a-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="8328a-249">Это \* означает любой набор символов, которые являются буквами фамилии пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="8328a-250">Оболочка PowerShell для Microsoft 365 упрощает печать и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="8328a-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="8328a-251">Центр администрирования Microsoft 365 позволяет просматривать списки данных.</span><span class="sxs-lookup"><span data-stu-id="8328a-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="8328a-252">Ниже приведен пример центра администрирования Skype для бизнеса Online, в котором отображается список пользователей, которым разрешено использовать Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="8328a-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Пример Центра администрирования Skype для бизнеса Online со списком пользователей, для которых включен Skype для бизнеса Online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="8328a-254">Чтобы сохранить эти сведения в файл, необходимо вставить его в документ или лист Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="8328a-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="8328a-255">В любом случае может потребоваться дополнительное форматирование.</span><span class="sxs-lookup"><span data-stu-id="8328a-255">Either case might require additional formatting.</span></span> <span data-ttu-id="8328a-256">Кроме того, центр администрирования Microsoft 365 не предоставляет возможности непосредственного вывода списка.</span><span class="sxs-lookup"><span data-stu-id="8328a-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="8328a-257">К счастью, вы можете использовать PowerShell, чтобы не только отображать список, но и сохранить его в файл, который можно легко импортировать в Excel.</span><span class="sxs-lookup"><span data-stu-id="8328a-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="8328a-258">Ниже приведен пример команды для сохранения данных пользователя Skype для бизнеса Online в CSV-файл, который можно легко импортировать в виде таблицы на листе Excel.</span><span class="sxs-lookup"><span data-stu-id="8328a-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="8328a-259">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-259">Here's an example of the results:</span></span>
  
![Пример таблицы, импортированной на лист Excel для данных пользователя Skype для бизнеса Online, сохраненного в файле с разделителями-запятыми.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="8328a-261">Интерпретация этой команды PowerShell: получение всех пользователей Skype для бизнеса Online в текущей подписке на Microsoft 365 (**Get-CsOnlineUser**); получите только имя пользователя, имя участника-пользователя и расположение (**выберите DisplayName, userPrincipalName, UsageLocation**); затем сохраните эти сведения в CSV-файле с именем C: \\ logs \\SfBUsers.csv (**Export-CSV-Path "C: \\ logs \\SfBUsers.csv"-нотипеинформатион**).</span><span class="sxs-lookup"><span data-stu-id="8328a-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="8328a-262">Вы также можете использовать параметры для сохранения этого списка в виде XML-файла или HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="8328a-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="8328a-263">Кроме того, с помощью дополнительных команд PowerShell вы можете сохранить его непосредственно в виде файла Excel, используя любое пользовательское форматирование.</span><span class="sxs-lookup"><span data-stu-id="8328a-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="8328a-264">Кроме того, можно отправить выходные данные команды PowerShell, которая отображает список непосредственно на принтере по умолчанию в Windows.</span><span class="sxs-lookup"><span data-stu-id="8328a-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="8328a-265">Вот пример команды:</span><span class="sxs-lookup"><span data-stu-id="8328a-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="8328a-266">Ниже показано, как будет выглядеть напечатанный документ.</span><span class="sxs-lookup"><span data-stu-id="8328a-266">Here's what your printed document will look like:</span></span>
  
![Пример напечатанного документа, который был выведен с помощью команды PowerShell, отправленной непосредственно на принтер, используемый по умолчанию в Windows.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="8328a-268">Интерпретация этой команды PowerShell: получение всех пользователей Skype для бизнеса Online в текущей подписке на Microsoft 365; получите только имя пользователя, имя участника-пользователя и расположение; а затем отправить эти сведения на принтер Windows по умолчанию (**Out-Printer**).</span><span class="sxs-lookup"><span data-stu-id="8328a-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="8328a-269">Форматирование документа аналогично простому форматированию, которое отображается в командном окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8328a-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="8328a-270">Чтобы получить твердую копию, просто добавьте **| Out – Printer** в конце команды.</span><span class="sxs-lookup"><span data-stu-id="8328a-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="8328a-271">PowerShell для Microsoft 365 позволяет управлять различными серверными продуктами</span><span class="sxs-lookup"><span data-stu-id="8328a-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="8328a-272">Компоненты, составляющие Microsoft 365, предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="8328a-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="8328a-273">Например, предположим, что вы добавляете нового пользователя в Microsoft 365, а также указываете такие сведения, как отдел и номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="8328a-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="8328a-274">Эта информация будет доступна при доступе к сведениям о пользователе в любой из служб Microsoft 365: Skype для бизнеса Online, Exchange или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8328a-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="8328a-275">Это общие сведения, распространяющиеся на набор продуктов.</span><span class="sxs-lookup"><span data-stu-id="8328a-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="8328a-276">Сведения о конкретном продукте, такие как сведения о почтовом ящике Exchange пользователя, обычно не доступны в наборе.</span><span class="sxs-lookup"><span data-stu-id="8328a-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="8328a-277">Например, сведения о включении или отключении почтового ящика пользователя доступны только в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="8328a-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="8328a-278">Предположим, вы хотите создать отчет со следующим сведениями обо всех пользователях:</span><span class="sxs-lookup"><span data-stu-id="8328a-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="8328a-279">краткое имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="8328a-279">The user's display name</span></span>
    
- <span data-ttu-id="8328a-280">Является ли пользователь лицензированным для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="8328a-281">включен ли почтовый ящик Exchange пользователя;</span><span class="sxs-lookup"><span data-stu-id="8328a-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="8328a-282">включено ли для пользователя приложение Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8328a-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="8328a-283">Такой отчет невозможно легко создать в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8328a-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8328a-284">Вместо этого необходимо создать отдельный документ для хранения данных, например листа Excel.</span><span class="sxs-lookup"><span data-stu-id="8328a-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="8328a-285">Затем получите все имена пользователей и сведения о лицензировании из центра администрирования Microsoft 365, получите сведения о почтовом ящике из центра администрирования Exchange, получите сведения о Skype для бизнеса Online в центре администрирования Skype для бизнеса Online, а затем объедините эти сведения.</span><span class="sxs-lookup"><span data-stu-id="8328a-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="8328a-286">Альтернативой является использование скрипта PowerShell для компиляции отчета.</span><span class="sxs-lookup"><span data-stu-id="8328a-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="8328a-287">Следующий пример скрипта более сложный, чем команды, показанные ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8328a-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="8328a-288">Кроме того, в ней показано, как использовать PowerShell для создания информационных представлений, которые трудно возникать в ином случае.</span><span class="sxs-lookup"><span data-stu-id="8328a-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="8328a-289">Ниже приведен скрипт для компиляции и отображения необходимого списка.</span><span class="sxs-lookup"><span data-stu-id="8328a-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="8328a-290">Вот пример результатов:</span><span class="sxs-lookup"><span data-stu-id="8328a-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="8328a-291">Этот сценарий PowerShell интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8328a-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="8328a-292">Получите всех пользователей в текущей подписке на Microsoft 365 и сохраните их в переменной с именем *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="8328a-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="8328a-293">Запустите цикл, который будет выполняться для всех пользователей в переменной $x (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="8328a-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="8328a-294">Определите переменную с именем *$y* и сохраните сведения о почтовом ящике пользователя (**$y = Get-Mailbox-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="8328a-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="8328a-295">Добавьте новое свойство к сведениям о пользователях с именем *исмаилбоксенаблед*.</span><span class="sxs-lookup"><span data-stu-id="8328a-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="8328a-296">Задайте для него значение свойства Исмаилбоксенаблед почтового ящика пользователя (**$i | Add-Member-Мембертипе нотепроперти-Name исмаилбоксенаблед-value $y. исмаилбоксенаблед**).</span><span class="sxs-lookup"><span data-stu-id="8328a-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="8328a-297">Определите переменную с именем *$y*и сохраните информацию пользователя Skype для бизнеса Online в ней (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="8328a-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="8328a-298">Добавьте новое свойство к сведениям о пользователях с именем *енабледфорсфб*.</span><span class="sxs-lookup"><span data-stu-id="8328a-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="8328a-299">Задайте для него значение свойства Enabled для сведений о Skype для бизнеса Online (**$i | Add-Member-Мембертипе нотепроперти-Name енабледфорсфб-value $y. Enabled**).</span><span class="sxs-lookup"><span data-stu-id="8328a-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="8328a-300">Отображение списка пользователей, но включение только их имени (при наличии лицензии), а также двух новых свойств, указывающих на то, включен ли их почтовый ящик и включены ли они в Skype для бизнеса Online (**$x | Выберите DisplayName, лицензировать, Исмаилбоксенаблед, Енабледфорсфб**).</span><span class="sxs-lookup"><span data-stu-id="8328a-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8328a-301">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="8328a-301">See also</span></span>

[<span data-ttu-id="8328a-302">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8328a-303">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8328a-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8328a-304">Использование Windows PowerShell для создания отчетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8328a-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
