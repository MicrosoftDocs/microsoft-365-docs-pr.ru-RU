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
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692978"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="932e1-103">Зачем использовать PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="932e1-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="932e1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="932e1-105">С помощью центра администрирования Microsoft 365 вы можете не только управлять своими учетными записями пользователей и лицензиями Microsoft 365, но также можете управлять службами Microsoft 365, такими как Exchange Online, Teams и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="932e1-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="932e1-106">Тем не менее, вы также можете управлять этими элементами с помощью команд PowerShell, используя преимущества командной строки и языковых сценариев среды для ускорения, автоматизации и дополнительной возможности.</span><span class="sxs-lookup"><span data-stu-id="932e1-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="932e1-107">В этой статье мы покажем вам, как использовать PowerShell для управления Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="932e1-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="932e1-108">Показать дополнительные сведения, которые не отображаются в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="932e1-109">Настройка функций и параметров, доступных только в PowerShell</span><span class="sxs-lookup"><span data-stu-id="932e1-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="932e1-110">Выполнение массовых операций</span><span class="sxs-lookup"><span data-stu-id="932e1-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="932e1-111">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="932e1-111">Filtering data</span></span>
    
- <span data-ttu-id="932e1-112">Печать или сохранение данных</span><span class="sxs-lookup"><span data-stu-id="932e1-112">Print or save data</span></span>
    
- <span data-ttu-id="932e1-113">Управление между службами</span><span class="sxs-lookup"><span data-stu-id="932e1-113">Manage across services</span></span>
    
<span data-ttu-id="932e1-114">Прежде чем приступать к работе, ознакомьтесь с оболочкой PowerShell для Microsoft 365 — набором модулей командной строки для служб и платформ на основе Windows для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="932e1-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="932e1-115">Эта среда создает язык командной консоли, который можно расширить с помощью дополнительных модулей и предоставляет способ выполнения простых или сложных команд или сценариев.</span><span class="sxs-lookup"><span data-stu-id="932e1-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="932e1-116">Например, после установки модулей PowerShell для Microsoft 365 и подключения к вашей подписке Microsoft 365 можно выполнить эту команду, чтобы получить список всех почтовых ящиков пользователей для Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="932e1-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="932e1-117">Вы также можете легко выполнить список почтовых ящиков с помощью центра администрирования Microsoft 365, но подсчитать количество элементов во всех списках всех сайтов для всех веб-приложений нелегко.</span><span class="sxs-lookup"><span data-stu-id="932e1-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="932e1-118">Обратите внимание, что PowerShell для Microsoft 365 предназначен для расширения возможностей управления Microsoft 365, а не для замены центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="932e1-119">Как администратор, вам необходимо по крайней мере быть знакомым с использованием PowerShell для Microsoft 365, поскольку существуют некоторые процедуры настройки, которые можно выполнить только с помощью команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="932e1-120">В таких случаях вы должны уметь:</span><span class="sxs-lookup"><span data-stu-id="932e1-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="932e1-121">Установите PowerShell для модулей Microsoft 365 (выполнить только один раз для каждого компьютера администратора).</span><span class="sxs-lookup"><span data-stu-id="932e1-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="932e1-122">Подключение к вашей подписке Microsoft 365 (выполняется один раз для каждого сеанса PowerShell).</span><span class="sxs-lookup"><span data-stu-id="932e1-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="932e1-123">Соберите информацию, необходимую для запуска необходимых команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="932e1-124">Успешное выполнение команд PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="932e1-125">Овладев этими основными навыками, вам не обязательно отображать список пользователей почтовых ящиков с помощью команды **Get-Mailbox** или учиться создавать команду, подобную предыдущей, для подсчета всех элементов во всех списках для всех сайтов всех веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="932e1-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="932e1-126">Корпорация Майкрософт и сообщество администраторов могут помочь вам при необходимости.</span><span class="sxs-lookup"><span data-stu-id="932e1-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="932e1-127">PowerShell для Microsoft 365 может открыть дополнительные сведения, которые не отображаются в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="932e1-128">В центре администрирования Microsoft 365 отображается большое количество полезной информации, но это не означает, что на ней отображаются все возможные сведения, которые хранятся в Microsoft 365 для пользователей, лицензий, почтовых ящиков и сайтов.</span><span class="sxs-lookup"><span data-stu-id="932e1-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="932e1-129">Ниже приведен пример для **пользователей и групп** в центре администрирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="932e1-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Пример отображения пользователей и групп в центре администрирования Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="932e1-131">Для многих целей отображаются сведения, которые необходимо знать.</span><span class="sxs-lookup"><span data-stu-id="932e1-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="932e1-132">Однако бывают случаи, когда вам требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="932e1-132">However, there are times when you need more.</span></span> <span data-ttu-id="932e1-133">Например, лицензирование Microsoft 365 (и функции Microsoft 365, доступные пользователю) зависят от географического расположения этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="932e1-134">Политики и функции, которые вы можете расширить для пользователя, который живет в США, могут отличаться от политик и функций, которые можно расширить для пользователя, который живет в Индии или в Бельгии.</span><span class="sxs-lookup"><span data-stu-id="932e1-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="932e1-135">С помощью центра администрирования Microsoft 365 вы можете определить географическое расположение пользователя, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="932e1-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="932e1-136">Дважды щелкните **отображаемое имя** пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="932e1-137">На панели отображения свойств пользователя щелкните **сведения**.</span><span class="sxs-lookup"><span data-stu-id="932e1-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="932e1-138">В окне сведений щелкните **дополнительные сведения**.</span><span class="sxs-lookup"><span data-stu-id="932e1-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="932e1-139">Прокрутите окно вниз до заголовка **Страна или регион**.</span><span class="sxs-lookup"><span data-stu-id="932e1-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Пример сведений о регионе для пользователя в центре администрирования Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="932e1-141">Запишите отображаемое имя и местонахождение пользователя на лист бумаги или скопируйте и вставьте их в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="932e1-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="932e1-142">Эту процедуру необходимо повторить для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="932e1-143">Если пользователей очень много, эта задача может показаться утомительной.</span><span class="sxs-lookup"><span data-stu-id="932e1-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="932e1-144">С помощью PowerShell для Microsoft 365 вы можете отобразить эту информацию для всех пользователей с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="932e1-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="932e1-145">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="932e1-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="932e1-146">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="932e1-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="932e1-147">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-147">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="932e1-148">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 ( **Get-AzureADUser** ), но отображение только имени и расположения каждого пользователя ( **выберите DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="932e1-149">Так как PowerShell для Microsoft 365 поддерживает язык командной консоли, вы можете продолжить работать с данными, полученными из команды **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="932e1-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="932e1-150">Например, вы хотели бы сортировать этих пользователей по их расположению, объединяя всех пользователей Бразилии, всех пользователей США и т. д. Ниже приведена команда.</span><span class="sxs-lookup"><span data-stu-id="932e1-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="932e1-151">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-151">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="932e1-152">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365, но отображение имени и расположения каждого пользователя и сортировка их по их расположению, а затем их имена ( **Sort UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="932e1-p110">Можно также использовать дополнительные фильтры. Например, если нужно просмотреть сведения о пользователях, находящихся в Бразилии, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="932e1-p110">You can also employ additional filtering. For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="932e1-155">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="932e1-156">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365 с расположением в Бразилии ( **где {$ \_ . UsageLocation-EQ "BR"}** ), а затем отобразите имя и местоположение каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="932e1-157">**Небольшое примечание относительно более крупных доменов**</span><span class="sxs-lookup"><span data-stu-id="932e1-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="932e1-158">Если у вас очень большой домен, включающий десятки тысяч пользователей, то использование некоторых сценариев, описанных в этой статье, может привести к так называемому "регулированию".</span><span class="sxs-lookup"><span data-stu-id="932e1-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="932e1-159">Это будет означать, что вы одновременно выполняете слишком большое количество задач, для чего недостаточно мощности компьютера и пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="932e1-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="932e1-160">Из-за этого, более крупные организации могут попытаться разделить некоторые из этих команд PowerShell для Microsoft 365 на две команды.</span><span class="sxs-lookup"><span data-stu-id="932e1-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="932e1-161">Например, указанная ниже команда возвращает все учетные записи пользователей и отображает для каждой из них имя и расположение.</span><span class="sxs-lookup"><span data-stu-id="932e1-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="932e1-p112">Она отлично подходит для небольших доменов. Тем не менее крупной организации может понадобиться разделить ее на две команды: одна команда будет использоваться для сохранения сведений об учетных записях пользователей в переменной, а другая  для отображения необходимой информации. Вот пример:</span><span class="sxs-lookup"><span data-stu-id="932e1-p112">That works great for smaller domains. In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information. Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="932e1-165">Ниже приведена интерпретация этого набора команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="932e1-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="932e1-166">Получите всех пользователей в текущей подписке на Microsoft 365 и сохраните их в переменной с именем $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="932e1-167">Отображается содержимое переменной $x, которое включает в себя только имя и местонахождение каждого пользователя (**$x | Select DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="932e1-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="932e1-168">Microsoft 365 содержит функции, которые можно настроить только с помощью PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="932e1-169">Центр администрирования Microsoft 365 предназначен для обеспечения доступа к наиболее распространенным или осмысленным задачам администрирования, которые применяются к большинству пользователей.</span><span class="sxs-lookup"><span data-stu-id="932e1-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="932e1-170">Другими словами, центр администрирования Microsoft 365 был разработан таким образом, что стандартный администратор может использовать это средство для выполнения самых распространенных задач управления.</span><span class="sxs-lookup"><span data-stu-id="932e1-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="932e1-171">Это определение означает, что существует несколько задач, которые невозможно выполнить с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="932e1-172">Например, в Центр администрирования Skype для бизнеса Online используется несколько параметров для создания настраиваемых приглашений на собрания:</span><span class="sxs-lookup"><span data-stu-id="932e1-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Пример отображения настраиваемых приглашений на собрание в Центре администрирования Skype для бизнеса Online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="932e1-p114">С помощью указанных ниже параметров приглашения на собрания можно сделать более персонализированными и профессиональными. Тем не менее, настройки собраний позволяют сделать больше, чем просто создать пользовательские приглашения. Например, по умолчанию собрания позволяют:</span><span class="sxs-lookup"><span data-stu-id="932e1-p114">With these settings, you can add a touch of personalization and professionalism to meeting invitations. However, there's more to meeting configuration settings than simply creating custom meeting invitations. For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="932e1-177">анонимным пользователям автоматически присоединяться к каждому собранию;</span><span class="sxs-lookup"><span data-stu-id="932e1-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="932e1-178">участникам записывать собрание;</span><span class="sxs-lookup"><span data-stu-id="932e1-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="932e1-179">обозначать всех пользователей из вашей организации докладчиками при их присоединении к собранию.</span><span class="sxs-lookup"><span data-stu-id="932e1-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="932e1-180">Эти параметры недоступны в Центре администрирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="932e1-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="932e1-181">Тем не менее, вы можете управлять ими из PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="932e1-182">Указанная ниже команда отключает эти три параметра.</span><span class="sxs-lookup"><span data-stu-id="932e1-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="932e1-183">Для использования этой команды необходимо установить [модуль PowerShell для Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="932e1-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="932e1-184">Интерпретация этой команды PowerShell: параметры для новых собраний Skype для бизнеса Online ( **Set-CsMeetingConfiguration** ), запретить анонимным пользователям получать автоматический вход в собрания ( **-адмитанонимаусусерсбидефаулт $false** ), отключить возможность записи собраний ( **-AllowConferenceRecording $false** ) и не определять всех пользователей в Организации как выступающих ( **-десигнатеаспресентер "нет"** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="932e1-185">Если вы передумали и хотите восстановить эти настройки по умолчанию (т. е. включить их все), выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="932e1-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="932e1-186">Это только один пример.</span><span class="sxs-lookup"><span data-stu-id="932e1-186">This is just one example.</span></span> <span data-ttu-id="932e1-187">Существуют другие пользователи, которые, по этой причине, должны иметь опыт работы с PowerShell для команд Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="932e1-188">PowerShell для Microsoft 365 отлично работает при выполнении массовых операций</span><span class="sxs-lookup"><span data-stu-id="932e1-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="932e1-189">Историческось, что визуальные интерфейсы, такие как центр администрирования Microsoft 365, наиболее полезны, если вы выполняете одну операцию.</span><span class="sxs-lookup"><span data-stu-id="932e1-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="932e1-190">Например, если необходимо отключить одну учетную запись пользователя, вы можете использовать центр администрирования Microsoft 365 для быстрого обнаружения и снятия флажка.</span><span class="sxs-lookup"><span data-stu-id="932e1-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="932e1-191">Это может быть проще, чем выполнение аналогичной операции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="932e1-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="932e1-192">Но если вам нужно изменить множество вещей или некоторые из выбранных элементов в большом наборе других элементов, центр администрирования Microsoft 365 может оказаться неоптимальным.</span><span class="sxs-lookup"><span data-stu-id="932e1-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="932e1-193">Например, если необходимо изменить префикс для тысяч телефонных номеров или удалить определенного пользователя, Ken Myer со всех сайтов SharePoint Online, как это сделать в центре администрирования Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="932e1-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="932e1-194">Допустим, в последнем примере у вас есть несколько сотен сайтов SharePoint Online и вы даже не знаете, на каком из них зарегистрирован пользователь Ken Meyer.</span><span class="sxs-lookup"><span data-stu-id="932e1-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="932e1-195">Это означает, что вам потребуется начать с центра администрирования Microsoft 365, а затем выполнить эту процедуру для каждого сайта:</span><span class="sxs-lookup"><span data-stu-id="932e1-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="932e1-196">Щелкнуть **URL-адрес** сайта.</span><span class="sxs-lookup"><span data-stu-id="932e1-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="932e1-197">В поле **свойств семейства веб-сайтов** щелкнуть ссылку **Адрес веб-сайта**, чтобы открыть сайт.</span><span class="sxs-lookup"><span data-stu-id="932e1-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="932e1-198">На сайте нажать кнопку **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="932e1-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="932e1-199">В диалоговом окне **Общий доступ** щелкнуть ссылку, чтобы показать всех пользователей с разрешениями для сайта:</span><span class="sxs-lookup"><span data-stu-id="932e1-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Пример просмотра участников сайта SharePoint Online в Центре администрирования SharePoint Online](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="932e1-201">В диалоговом окне **Общий доступ предоставлен** нажать кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="932e1-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="932e1-202">Прокрутить список пользователей, найти и выбрать Кена Майера (если у него есть разрешения для сайта) и нажать кнопку **Удалить разрешения пользователя**.</span><span class="sxs-lookup"><span data-stu-id="932e1-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="932e1-203">Для нескольких сотен сайтов это может занять очень много времени.</span><span class="sxs-lookup"><span data-stu-id="932e1-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="932e1-204">Кроме того, можно использовать PowerShell для Microsoft 365 и следующую команду, чтобы удалить Ken Myer со всех сайтов:</span><span class="sxs-lookup"><span data-stu-id="932e1-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="932e1-205">Для этой команды необходимо установить [модуль PowerShell для SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="932e1-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="932e1-206">Интерпретация этой команды PowerShell: получение всех сайтов SharePoint в текущей подписке на Microsoft 365 ( **Get-SPOSite** ) и для каждого сайта удалите Ken Крюкова из списка пользователей, имеющих доступ к нему ( **foreach {Remove-супруг-site $) \_ . URL-адрес LoginName "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="932e1-207">Так как мы сообщаем Microsoft 365 удалить Ken Крюкова со всех сайтов, включая те, в которых у него нет доступа, при отображении этой команды будут отображаться ошибки для тех сайтов, к которым у него в данный момент нет доступа.</span><span class="sxs-lookup"><span data-stu-id="932e1-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="932e1-208">В этой команде можно использовать дополнительное условие, чтобы пользователь Ken Meyer был удален только с тех сайтов, в списке учетных записей которых он содержится, но чтобы указанные ошибки не влияли на сами сайты.</span><span class="sxs-lookup"><span data-stu-id="932e1-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="932e1-209">Выполнение этой команды может занять несколько минут, а не часов работы с сотнями сайтов в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="932e1-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="932e1-p121">Вот еще один пример массовой операции. Чтобы добавить пользователя Бонни Керни (Bonnie Kearney) — нового администратора SharePoint — на все сайты в организации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="932e1-p121">Here is another bulk operation example. Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="932e1-212">Интерпретация этой команды PowerShell: получение всех сайтов SharePoint в текущей подписке на Microsoft 365 и для каждого сайта, разрешение доступа к Бонние Кеарнэй путем добавления имени для входа в группу "участники" сайта ( **foreach {Add-супруг-site $) \_ . URL-адрес: LoginName "bkearney@litwareinc.com"-Group "Members"}** .</span><span class="sxs-lookup"><span data-stu-id="932e1-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="932e1-213">PowerShell для Microsoft 365 отлично подходит для фильтрации данных</span><span class="sxs-lookup"><span data-stu-id="932e1-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="932e1-214">Центр администрирования Microsoft 365 предоставляет несколько различных способов фильтрации данных, чтобы быстро и легко находить целевое подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="932e1-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="932e1-215">Например, Exchange упрощает фильтрацию практически любого свойства почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="932e1-216">Например, ниже приведен список почтовых ящиков всех пользователей, проживающих в городе Блумингтон:</span><span class="sxs-lookup"><span data-stu-id="932e1-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Пример расширенного поиска в центре администрирования Microsoft 365 для списка почтовых ящиков всех пользователей, проживающих в городе Блумингтон.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="932e1-p123">Кроме того, Центр администрирования Exchange позволяет сочетать различные условия фильтра. Например, можно найти почтовые ящики всех пользователей, проживающих в г. Блумингтон и работающих в отделе финансов.</span><span class="sxs-lookup"><span data-stu-id="932e1-p123">The Exchange Admin center also lets you combine filter criteria. For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="932e1-p124">Но возможности фильтрации в Центре администрирования Exchange ограничены. Например, вам может понадобиться найти почтовые ящики пользователей, проживающих в городах Блумингтон (Bloomington) или Сан-Диего (San Diego), или почтовые ящики всех пользователей, которые не проживают в городе Блумингтон.</span><span class="sxs-lookup"><span data-stu-id="932e1-p124">However, there are limitations to what you can do in the Exchange Admin center. For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="932e1-222">С помощью PowerShell для Microsoft 365 вы можете получить список почтовых ящиков для всех пользователей, проживающих в городах Блумингтон или Сан Диего, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="932e1-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="932e1-223">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="932e1-224">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 с почтовым ящиком в городах в городах Сан-Диего или Блумингтон ( **где {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-and ($ \_ . City – Eq "Сан Диего" (или $) \_ . City-Eq "Блумингтон")}** ), а затем отображаются имя и город для каждого из них ( **выберите DisplayName, City** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="932e1-225">Чтобы отобразить список всех почтовых ящиков пользователей, проживающих в любом месте за исключением г. Блумингтон, используйте такую команду:</span><span class="sxs-lookup"><span data-stu-id="932e1-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="932e1-226">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-226">Here is an example of the display:</span></span>
  
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

> [!TIP]
>  <span data-ttu-id="932e1-227">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке Microsoft 365 с почтовым ящиком, не расположенным в городе Блумингтон ( **где {$ \_ . RecipientTypeDetails — EQ "UserMailbox" и $ \_ . City-NE "Блумингтон"}** ), а затем отображает имя и город для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="932e1-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="932e1-228">Кроме того, можно использовать подстановочные знаки в фильтрах PowerShell для сопоставления части имени.</span><span class="sxs-lookup"><span data-stu-id="932e1-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="932e1-229">Предположим, вы ищете учетную запись пользователя, но помните только, что его фамилия или Андерсон, или Хендерсон, или, может быть, Йоргенсон.</span><span class="sxs-lookup"><span data-stu-id="932e1-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="932e1-230">Вы можете проследить этого пользователя в центре администрирования Microsoft 365 с помощью средства поиска и выполнить три различных поиска:</span><span class="sxs-lookup"><span data-stu-id="932e1-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="932e1-231">*Андерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="932e1-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="932e1-232">*Хендерсон*  ;</span><span class="sxs-lookup"><span data-stu-id="932e1-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="932e1-233">*Йоргенсон*  .</span><span class="sxs-lookup"><span data-stu-id="932e1-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="932e1-234">Так как все три из этих имен заканчиваются на ""] ", вы можете указать PowerShell, чтобы отобразить всех пользователей, чье имя оканчивается на" "]".</span><span class="sxs-lookup"><span data-stu-id="932e1-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="932e1-235">Вот как это делается:</span><span class="sxs-lookup"><span data-stu-id="932e1-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="932e1-236">Интерпретация этой команды PowerShell: получение всех пользователей в текущей подписке на Microsoft 365, но использование фильтра, в котором указаны только те пользователи, чьи фамилии заканчиваются на "E3" ( **-Filter "{LastName-Like" "] \* "** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="932e1-237">Это \* означает любой набор символов, которые являются буквами в случае фамилии пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="932e1-238">Оболочка PowerShell для Microsoft 365 упрощает печать и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="932e1-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="932e1-239">Центр администрирования Microsoft 365 позволяет просматривать списки данных.</span><span class="sxs-lookup"><span data-stu-id="932e1-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="932e1-240">Ниже приведен пример, где в Центре администрирования Skype для бизнеса Online отображается список пользователей, для которых включено приложение Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="932e1-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Пример Центра администрирования Skype для бизнеса Online со списком пользователей, для которых включен Skype для бизнеса Online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="932e1-242">Чтобы сохранить эти данные в файл, необходимо их скопировать и вставить в документ или лист Excel.</span><span class="sxs-lookup"><span data-stu-id="932e1-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="932e1-243">В любом случае может потребоваться дополнительное форматирование копии.</span><span class="sxs-lookup"><span data-stu-id="932e1-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="932e1-244">Кроме того, центр администрирования Microsoft 365 не предоставляет возможности непосредственного вывода списка.</span><span class="sxs-lookup"><span data-stu-id="932e1-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="932e1-245">К счастью, вы можете использовать PowerShell, чтобы не только отображать список, но и сохранить его в файл, который можно легко импортировать в Excel.</span><span class="sxs-lookup"><span data-stu-id="932e1-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="932e1-246">Ниже приведен пример команды, позволяющей сохранить пользовательские данные Skype для бизнеса Online в файл с разделителями-запятыми (CSV-файл), который легко импортировать в виде таблицы в лист Excel.</span><span class="sxs-lookup"><span data-stu-id="932e1-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="932e1-247">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-247">Here is an example of the display:</span></span>
  
![Пример таблицы с данными пользователей Skype для бизнеса, импортированной на лист Excel и сохраненной в формате файла данных с разделителями-запятыми (CSV).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="932e1-249">Интерпретация этой команды PowerShell: получение всех пользователей Skype для бизнеса Online в текущей подписке на Microsoft 365 ( **Get-CsOnlineUser** ), получение только имени пользователя, имени участника-пользователя и расположения ( **выберите DisplayName, userPrincipalName, UsageLocation** ), а затем сохраните эту информацию в CSV-файле с именем c: \\ logs \\SfBUsers.csv ( **Export-CSV-Path "c: \\ logs \\SfBUsers.csv"-нотипеинформатион** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="932e1-p131">PowerShell также позволяет сохранить этот список в виде XML-файла или HTML-страницы. Кроме того, с помощью дополнительных команд PowerShell вы можете сохранить данные непосредственно в файл Excel, используя необходимое форматирование.</span><span class="sxs-lookup"><span data-stu-id="932e1-p131">You can also use options to save this list as an XML file or as an HTML page. In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="932e1-252">Кроме того, можно отправить выходные данные команды PowerShell, которая отображает список непосредственно на принтере по умолчанию в Windows.</span><span class="sxs-lookup"><span data-stu-id="932e1-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="932e1-253">Вот пример необходимой команды:</span><span class="sxs-lookup"><span data-stu-id="932e1-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="932e1-254">Ниже показано, как будет выглядеть напечатанный документ.</span><span class="sxs-lookup"><span data-stu-id="932e1-254">Here's what your printed document will look like:</span></span>
  
![Пример напечатанного документа, который был выведен с помощью команды PowerShell, указанной непосредственно на принтере по умолчанию в Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="932e1-256">Интерпретация этой команды PowerShell: получение всех пользователей Skype для бизнеса Online в текущей подписке на Microsoft 365, получение только имени пользователя, имени участника-пользователя и расположения, а затем отправка этих сведений на принтер Windows по умолчанию ( **Out-Printer** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="932e1-257">Для напечатанного документа используется то же простое форматирование, что и при отображении в командном окне PowerShell, но после того как вы создали команду PowerShell, чтобы отобразить то, что вам нужно, просто добавьте **| Out – Printer** до конца команды, чтобы получить окончательную копию для работы.</span><span class="sxs-lookup"><span data-stu-id="932e1-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="932e1-258">PowerShell для Microsoft 365 позволяет управлять различными серверными продуктами</span><span class="sxs-lookup"><span data-stu-id="932e1-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="932e1-259">Различные компоненты, составляющие Microsoft 365, рассчитаны на совместную работу.</span><span class="sxs-lookup"><span data-stu-id="932e1-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="932e1-260">Например, предположим, что вы добавляете нового пользователя в Microsoft 365 и задаете такую информацию, как отдел и номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="932e1-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="932e1-261">Эта информация будет доступна при доступе к сведениям о пользователе с помощью любой из служб Microsoft 365: Skype для бизнеса Online, Exchange или SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="932e1-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="932e1-p134">Это общие сведения, распространяющиеся на набор продуктов. Сведения о конкретных продуктах, например информация о почтовом ящике Exchange пользователя, обычно недоступны во всех продуктах набора. Например, если вы хотите знать, включен ли почтовый ящик пользователя, то эти сведения доступны только в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="932e1-p134">But that's for common information that spans the suite of products. Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite. For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="932e1-265">Предположим, вы хотите создать отчет со следующим сведениями обо всех пользователях:</span><span class="sxs-lookup"><span data-stu-id="932e1-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="932e1-266">краткое имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="932e1-266">The user's display name</span></span>
    
- <span data-ttu-id="932e1-267">Является ли пользователь лицензированным для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="932e1-268">включен ли почтовый ящик Exchange пользователя;</span><span class="sxs-lookup"><span data-stu-id="932e1-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="932e1-269">включено ли для пользователя приложение Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="932e1-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="932e1-270">В настоящее время вы не можете использовать центр администрирования Microsoft 365 для простого создания такого отчета.</span><span class="sxs-lookup"><span data-stu-id="932e1-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="932e1-271">Вместо этого необходимо создать отдельный документ для хранения информации, например листа Excel, и получить все имена пользователей и сведения о лицензировании из центра администрирования Microsoft 365, получить сведения о почтовом ящике из центра администрирования Exchange, получить сведения о Skype для бизнеса Online из центра администрирования Skype для бизнеса Online, а затем выполнить разбор и объединение этих данных.</span><span class="sxs-lookup"><span data-stu-id="932e1-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="932e1-272">Альтернативой является использование скрипта PowerShell для компиляции этого отчета.</span><span class="sxs-lookup"><span data-stu-id="932e1-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="932e1-273">Следующий пример сценария сложнее приведенных выше команд.</span><span class="sxs-lookup"><span data-stu-id="932e1-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="932e1-274">Кроме того, в ней показано, как использовать PowerShell для создания представлений данных, которые в противном случае очень трудно выполнить.</span><span class="sxs-lookup"><span data-stu-id="932e1-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="932e1-275">Вот сценарий, с помощью которого можно составить и отобразить необходимый список:</span><span class="sxs-lookup"><span data-stu-id="932e1-275">Here is the script that can compile and display the needed list:</span></span>
  
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

<span data-ttu-id="932e1-276">Ниже приведен пример отображения.</span><span class="sxs-lookup"><span data-stu-id="932e1-276">Here is an example of the display:</span></span>
  
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

<span data-ttu-id="932e1-277">Этот сценарий PowerShell интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="932e1-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="932e1-278">Получите всех пользователей в текущей подписке на Microsoft 365 и сохраните их в переменной с именем $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="932e1-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="932e1-279">Запускается цикл для всех пользователей в переменной $x (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="932e1-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="932e1-280">Определяется переменная $y, в которой сохраняются сведения о почтовом ящике пользователя (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="932e1-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="932e1-281">К сведениям о пользователе добавляется новое свойство IsMailBoxEnabled, которое задается как значение свойства IsMailBoxEnabled почтового ящика пользователя (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="932e1-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="932e1-282">Определяется переменная $y, в которой сохраняются данные Skype для бизнеса Online пользователя (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="932e1-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="932e1-283">К сведениям о пользователе добавляется новое свойство EnabledForSfB, которое задается как значение свойства Enabled для данных Skype для бизнеса Online пользователя (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="932e1-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="932e1-284">Отображается список пользователей, в котором указаны только их имена, наличие лицензии и два новых свойства, которые указывают, включен ли почтовый ящик пользователей и могут ли они использовать Skype для бизнеса Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span><span class="sxs-lookup"><span data-stu-id="932e1-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="932e1-285">См. также</span><span class="sxs-lookup"><span data-stu-id="932e1-285">See also</span></span>

[<span data-ttu-id="932e1-286">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="932e1-287">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="932e1-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="932e1-288">Использование Windows PowerShell для создания отчетов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="932e1-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

