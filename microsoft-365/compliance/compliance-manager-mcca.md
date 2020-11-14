---
title: Анализатор соответствия настройкам Майкрософт для диспетчера соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как с помощью анализатора соответствия требованиям корпорации Майкрософт быстро приступить к работе с диспетчером соответствия Майкрософт.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072020"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a><span data-ttu-id="c85ee-103">Анализатор соответствия настройкам Майкрософт для диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="c85ee-103">Microsoft Compliance Configuration Analyzer for Compliance Manager</span></span>

<span data-ttu-id="c85ee-104">**В этой статье:** Узнайте, как установить и запустить средство анализатора соответствия требованиям Майкрософт, чтобы быстро начать работу с диспетчером соответствия Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c85ee-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a><span data-ttu-id="c85ee-105">Обзор анализатора соответствия требованиям Майкрософт (МККА)</span><span class="sxs-lookup"><span data-stu-id="c85ee-105">Microsoft Compliance Configuration Analyzer (MCCA) overview</span></span>

<span data-ttu-id="c85ee-106">Анализатор соответствия требованиям Майкрософт (МККА) — это средство, с помощью которого можно начать работу с [диспетчером соответствия требованиям Майкрософт](compliance-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c85ee-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="c85ee-107">МККА — это средство на основе PowerShell, которое выдает текущие конфигурации вашей организации и проверяет их на соответствие рекомендациям Microsoft 365, рекомендуемым.</span><span class="sxs-lookup"><span data-stu-id="c85ee-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="c85ee-108">Эти рекомендации основаны на наборе элементов управления, включающих ключевые нормативные требования и стандарты для защиты данных и управления данными.</span><span class="sxs-lookup"><span data-stu-id="c85ee-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="c85ee-109">МККА поможет быстро узнать, какие действия по улучшению в диспетчере соответствия относятся к текущей среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c85ee-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="c85ee-110">Каждое действие, определенное с помощью МККА, предоставит рекомендации по реализации, с прямыми ссылками на диспетчер соответствия требованиям и соответствующим решением, чтобы начать делать корректирующие действия.</span><span class="sxs-lookup"><span data-stu-id="c85ee-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="c85ee-111">Дополнительный ресурс для понимания МККА заключается в [статье readme на сайте GitHub](https://github.com/OfficeDev/MCCA#overview).</span><span class="sxs-lookup"><span data-stu-id="c85ee-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="c85ee-112">На этой странице представлены подробные сведения о необходимых компонентах и инструкции по полной установке.</span><span class="sxs-lookup"><span data-stu-id="c85ee-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="c85ee-113">Для доступа к этой странице не требуется учетная запись GitHub.</span><span class="sxs-lookup"><span data-stu-id="c85ee-113">You don’t need a GitHub account to access this page.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="c85ee-114">Установка МККА и запуск отчета</span><span class="sxs-lookup"><span data-stu-id="c85ee-114">Install MCCA and run a report</span></span>

<span data-ttu-id="c85ee-115">Средство МККА можно установить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c85ee-115">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="c85ee-116">После загрузки и установки средства нет необходимости повторять эти действия для запуска отчетов.</span><span class="sxs-lookup"><span data-stu-id="c85ee-116">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="c85ee-117">При каждом открытии МККА запрашиваются учетные данные для входа и создается новый, обновленный отчет.</span><span class="sxs-lookup"><span data-stu-id="c85ee-117">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="c85ee-118">Шаг 1: Установка Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c85ee-118">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="c85ee-119">Для начала вам потребуется модуль PowerShell Exchange Online (v 2.0.3 или более поздней версии), доступный в галерее PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c85ee-119">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="c85ee-120">[Получение инструкций по установке](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="c85ee-120">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="c85ee-121">Шаг 2: Установка МККА</span><span class="sxs-lookup"><span data-stu-id="c85ee-121">Step 2: Install MCCA</span></span>

<span data-ttu-id="c85ee-122">Чтобы установить МККА, запустите PowerShell с помощью PowerShell в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="c85ee-122">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="c85ee-123">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c85ee-123">Follow the steps below:</span></span>

1. <span data-ttu-id="c85ee-124">Нажмите кнопку **Пуск** Windows.</span><span class="sxs-lookup"><span data-stu-id="c85ee-124">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="c85ee-125">Введите **PowerShell** , щелкните правой кнопкой мыши **Windows PowerShell** , а затем выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="c85ee-125">Type **PowerShell** , right-click on **Windows PowerShell** , then select **Run as administrator**.</span></span>
1. <span data-ttu-id="c85ee-126">В командной строке введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="c85ee-126">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="c85ee-127">Шаг 3: Запуск отчета</span><span class="sxs-lookup"><span data-stu-id="c85ee-127">Step 3: Run a report</span></span>

<span data-ttu-id="c85ee-128">После установки МККА можно запустить МККА и создать отчет.</span><span class="sxs-lookup"><span data-stu-id="c85ee-128">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="c85ee-129">Чтобы запустить отчет, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c85ee-129">To run a report:</span></span>

1. <span data-ttu-id="c85ee-130">Открытие PowerShell</span><span class="sxs-lookup"><span data-stu-id="c85ee-130">Open PowerShell</span></span>
2. <span data-ttu-id="c85ee-131">Выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="c85ee-131">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="c85ee-132">После запуска МККА выполняет проверку начальной версии и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c85ee-132">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="c85ee-133">В поле введите запрос имени пользователя Войдите с помощью электронного адреса учетной записи Microsoft 365 ([Просмотрите роли, доступные для создания отчетов](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="c85ee-133">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="c85ee-134">Затем введите пароль в запросе пароля.</span><span class="sxs-lookup"><span data-stu-id="c85ee-134">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="c85ee-135">Создание отчета займет около 2-5 минут.</span><span class="sxs-lookup"><span data-stu-id="c85ee-135">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="c85ee-136">После этого откроется окно браузера, в котором будет отображаться HTML-отчет.</span><span class="sxs-lookup"><span data-stu-id="c85ee-136">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="c85ee-137">При каждом запуске средства будет запрашивать учетные данные и создавать новый отчет.</span><span class="sxs-lookup"><span data-stu-id="c85ee-137">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="c85ee-138">Этот отчет хранится локально в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="c85ee-138">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="c85ee-139">C:\Users \<username> \аппдата\локал\микрософт\мкка.</span><span class="sxs-lookup"><span data-stu-id="c85ee-139">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="c85ee-140">Вы можете получать доступ к ранее созданным отчетам из этого каталога.</span><span class="sxs-lookup"><span data-stu-id="c85ee-140">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="c85ee-141">Общие сведения об отчете</span><span class="sxs-lookup"><span data-stu-id="c85ee-141">Understanding your report</span></span>

<span data-ttu-id="c85ee-142">Отчет отражает данные в соответствии с датой и временем его создания.</span><span class="sxs-lookup"><span data-stu-id="c85ee-142">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="c85ee-143">В верхней части представлены сведения о процессе создания, имени Организации и идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="c85ee-143">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="c85ee-144">Отчетность на основе географического расположения</span><span class="sxs-lookup"><span data-stu-id="c85ee-144">Geolocation-based reporting</span></span>

<span data-ttu-id="c85ee-145">В разделе **Note (Примечание** ) показано, что отчет настроен в соответствии с географическим расположением клиента.</span><span class="sxs-lookup"><span data-stu-id="c85ee-145">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="c85ee-146">Рекомендации, приведенные в этом средстве, относятся к вашей стране или региону.</span><span class="sxs-lookup"><span data-stu-id="c85ee-146">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="c85ee-147">Ваш выбор географического расположения используется для оценки типов конфиденциальной информации (налево), которые относятся к этому географическому положению, и создания отчета, который соответствует вашей стране или региону.</span><span class="sxs-lookup"><span data-stu-id="c85ee-147">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="c85ee-148">Выберите пункт географические расположения на основе данных, содержащихся в клиенте.</span><span class="sxs-lookup"><span data-stu-id="c85ee-148">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="c85ee-149">Чтобы изменить сведения о расположении отчета, необходимо указать входной параметр географического расположения (-GEO).</span><span class="sxs-lookup"><span data-stu-id="c85ee-149">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="c85ee-150">Вы можете выбрать одно или несколько географов, доступных для клиента.</span><span class="sxs-lookup"><span data-stu-id="c85ee-150">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="c85ee-151">Выполните следующие инструкции, чтобы запустить отчет, основанный на определенном расположении:</span><span class="sxs-lookup"><span data-stu-id="c85ee-151">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="c85ee-152">Открытие PowerShell</span><span class="sxs-lookup"><span data-stu-id="c85ee-152">Open PowerShell</span></span>
2. <span data-ttu-id="c85ee-153">Чтобы указать определенный регион, выполните командлет, используя номера из приведенной ниже таблицы, которые соответствуют стране или региону.</span><span class="sxs-lookup"><span data-stu-id="c85ee-153">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="c85ee-154">Введите несколько чисел, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="c85ee-154">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="c85ee-155">Например, приведенный ниже командлет запустит настраиваемый отчет для Asia-Pacific и Японии:</span><span class="sxs-lookup"><span data-stu-id="c85ee-155">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="c85ee-156">Input</span><span class="sxs-lookup"><span data-stu-id="c85ee-156">Input</span></span> |  <span data-ttu-id="c85ee-157">Страна</span><span class="sxs-lookup"><span data-stu-id="c85ee-157">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="c85ee-158">1,1</span><span class="sxs-lookup"><span data-stu-id="c85ee-158">1</span></span> | <span data-ttu-id="c85ee-159">Азиатско-Тихоокеанский регион</span><span class="sxs-lookup"><span data-stu-id="c85ee-159">Asia-Pacific</span></span> |
  | <span data-ttu-id="c85ee-160">2</span><span class="sxs-lookup"><span data-stu-id="c85ee-160">2</span></span> | <span data-ttu-id="c85ee-161">Австралия</span><span class="sxs-lookup"><span data-stu-id="c85ee-161">Australia</span></span> |
  | <span data-ttu-id="c85ee-162">4</span><span class="sxs-lookup"><span data-stu-id="c85ee-162">3</span></span> | <span data-ttu-id="c85ee-163">Канада</span><span class="sxs-lookup"><span data-stu-id="c85ee-163">Canada</span></span> |
  | <span data-ttu-id="c85ee-164">4 </span><span class="sxs-lookup"><span data-stu-id="c85ee-164">4</span></span> | <span data-ttu-id="c85ee-165">Европа (без Франции)/Ближнего Востока и Африки</span><span class="sxs-lookup"><span data-stu-id="c85ee-165">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="c85ee-166">5 </span><span class="sxs-lookup"><span data-stu-id="c85ee-166">5</span></span> | <span data-ttu-id="c85ee-167">Франция</span><span class="sxs-lookup"><span data-stu-id="c85ee-167">France</span></span> |
  | <span data-ttu-id="c85ee-168">6 </span><span class="sxs-lookup"><span data-stu-id="c85ee-168">6</span></span> | <span data-ttu-id="c85ee-169">Индия</span><span class="sxs-lookup"><span data-stu-id="c85ee-169">India</span></span> |
  | <span data-ttu-id="c85ee-170">7 </span><span class="sxs-lookup"><span data-stu-id="c85ee-170">7</span></span> | <span data-ttu-id="c85ee-171">Япония</span><span class="sxs-lookup"><span data-stu-id="c85ee-171">Japan</span></span> |
  | <span data-ttu-id="c85ee-172">8 </span><span class="sxs-lookup"><span data-stu-id="c85ee-172">8</span></span> | <span data-ttu-id="c85ee-173">Республика Корея</span><span class="sxs-lookup"><span data-stu-id="c85ee-173">Korea</span></span> |
  | <span data-ttu-id="c85ee-174">9 </span><span class="sxs-lookup"><span data-stu-id="c85ee-174">9</span></span> | <span data-ttu-id="c85ee-175">Северная Америка (за исключением Канады)</span><span class="sxs-lookup"><span data-stu-id="c85ee-175">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="c85ee-176">10 </span><span class="sxs-lookup"><span data-stu-id="c85ee-176">10</span></span> | <span data-ttu-id="c85ee-177">Южная Америка</span><span class="sxs-lookup"><span data-stu-id="c85ee-177">South America</span></span> |
  | <span data-ttu-id="c85ee-178">11 </span><span class="sxs-lookup"><span data-stu-id="c85ee-178">11</span></span> | <span data-ttu-id="c85ee-179">Южная Африка</span><span class="sxs-lookup"><span data-stu-id="c85ee-179">South Africa</span></span> |
  | <span data-ttu-id="c85ee-180">12 </span><span class="sxs-lookup"><span data-stu-id="c85ee-180">12</span></span> | <span data-ttu-id="c85ee-181">Швейцария</span><span class="sxs-lookup"><span data-stu-id="c85ee-181">Switzerland</span></span> |
  | <span data-ttu-id="c85ee-182">13 </span><span class="sxs-lookup"><span data-stu-id="c85ee-182">13</span></span> | <span data-ttu-id="c85ee-183">Объединенные Арабские Эмираты</span><span class="sxs-lookup"><span data-stu-id="c85ee-183">United Arab Emirates</span></span> |
  | <span data-ttu-id="c85ee-184">14 </span><span class="sxs-lookup"><span data-stu-id="c85ee-184">14</span></span> | <span data-ttu-id="c85ee-185">Соединенное Королевство</span><span class="sxs-lookup"><span data-stu-id="c85ee-185">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="c85ee-186">Отчет всегда будет включать поддерживаемые международные типы конфиденциальной информации, например код SWIFT, номер кредитной карты и т. д.</span><span class="sxs-lookup"><span data-stu-id="c85ee-186">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="c85ee-187">Создание отчетов на основе ролей</span><span class="sxs-lookup"><span data-stu-id="c85ee-187">Role-based reporting</span></span>

<span data-ttu-id="c85ee-188">Отчет также будет настраиваемым в зависимости от вашей роли.</span><span class="sxs-lookup"><span data-stu-id="c85ee-188">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="c85ee-189">В приведенной ниже таблице показано, какие роли имеют доступ к разделам отчета.</span><span class="sxs-lookup"><span data-stu-id="c85ee-189">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="c85ee-190">Другие роли в Организации (не перечисленные в приведенной ниже таблице) могут не иметь функции запустить средство или запустить средство и иметь ограниченный доступ к данным в итоговом отчете.</span><span class="sxs-lookup"><span data-stu-id="c85ee-190">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="c85ee-191">![МККА — роли](../media/compliance-manager-mcca-roles.png "Роли МККА")</span><span class="sxs-lookup"><span data-stu-id="c85ee-191">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="c85ee-192">Ниже перечислены исключения для этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="c85ee-192">Exceptions:</span></span>
1. <span data-ttu-id="c85ee-193">Пользователь не сможет создавать отчет об IP-адресах отдельно от раздела "использование IRM для Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c85ee-193">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="c85ee-194">Пользователь сможет создавать отчет об IP-адресе отдельно от раздела "использование IRM для Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="c85ee-194">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="c85ee-195">Пользователь сможет создавать отчет об IP-адресе отдельно от раздела "Включение соответствия требованиям в O365".</span><span class="sxs-lookup"><span data-stu-id="c85ee-195">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="c85ee-196">Пользователь не сможет создавать отчет об IP-адресах отдельно от раздела "Включение аудита в Office 365".</span><span class="sxs-lookup"><span data-stu-id="c85ee-196">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="c85ee-197">Пользователь может формировать отчет об IP-адресах, отличных от раздела "Включение аудита в Office 365".</span><span class="sxs-lookup"><span data-stu-id="c85ee-197">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="c85ee-198">Раздел "Сводка по решениям"</span><span class="sxs-lookup"><span data-stu-id="c85ee-198">Solutions Summary section</span></span>

<span data-ttu-id="c85ee-199">В разделе " **Сводка по решениям** " этого отчета приводится обзор действий по улучшению, которые Организация может принять в диспетчере соответствия требованиям, чтобы повысить уровень соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c85ee-199">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="c85ee-200">![МККА — сводка по решениям](../media/compliance-manager-mcca-solutions.png "Экран сводки решений МККА")</span><span class="sxs-lookup"><span data-stu-id="c85ee-200">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="c85ee-201">МККА оценивает текущие конфигурации в соответствии с рекомендуемыми действиями по улучшению в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c85ee-201">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c85ee-202">В этом разделе приводится любое действие по улучшению, определенное средством МККА.</span><span class="sxs-lookup"><span data-stu-id="c85ee-202">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="c85ee-203">Рядом с каждым решением Майкрософт отображаются штриховые флажки, указывающие количество элементов, соответствующих действиям по улучшению в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c85ee-203">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c85ee-204">Действия разбиваются на три состояния:</span><span class="sxs-lookup"><span data-stu-id="c85ee-204">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="c85ee-205">**ОК** : действия, которые удовлетворяют рекомендуемым условиям и не требуют внимания в настоящее время</span><span class="sxs-lookup"><span data-stu-id="c85ee-205">**OK** : the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="c85ee-206">**Улучшение** : действия, требующие внимания</span><span class="sxs-lookup"><span data-stu-id="c85ee-206">**Improvement** : actions that need attention</span></span>
- <span data-ttu-id="c85ee-207">**Рекомендация** : действия, которые не требуют внимания, но мы рекомендуем использовать рекомендации</span><span class="sxs-lookup"><span data-stu-id="c85ee-207">**Recommendation** : actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="c85ee-208">Выберите поле, чтобы просмотреть улучшения и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c85ee-208">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="c85ee-209">**Элементы с состоянием улучшения**</span><span class="sxs-lookup"><span data-stu-id="c85ee-209">**Items with the Improvement status**</span></span>

<span data-ttu-id="c85ee-210">Выберите раскрывающийся список рядом с меткой **улучшения** справа от действия улучшения.</span><span class="sxs-lookup"><span data-stu-id="c85ee-210">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="c85ee-211">Вы увидите краткие сводки и подробные сведения о текущих параметрах и рекомендуемых действиях по улучшению.</span><span class="sxs-lookup"><span data-stu-id="c85ee-211">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="c85ee-212">Сводка включает прямые ссылки в Диспетчер соответствия требованиям, применимое решение в центре соответствия требованиям Microsoft 365 и релевантную документацию.</span><span class="sxs-lookup"><span data-stu-id="c85ee-212">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="c85ee-213">Если щелкнуть ссылку диспетчер соответствия требованиям, вы получите отфильтрованное представление всех действий по улучшению, которые еще не реализованы в этом решении.</span><span class="sxs-lookup"><span data-stu-id="c85ee-213">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="c85ee-214">В этой статье вы можете увидеть количество баллов, которые можно достигнуть, чтобы повысить уровень [соответствия требованиям](compliance-score-calculation.md), оценить их, а также соответствующие нормативные требования и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="c85ee-214">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="c85ee-215">Для защиты от потери данных существует кнопка **сценария исправления** , предоставляющая предварительно созданный сценарий PowerShell в зависимости от рекомендуемых действий.</span><span class="sxs-lookup"><span data-stu-id="c85ee-215">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="c85ee-216">Вы можете скопировать и вставить его непосредственно в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c85ee-216">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="c85ee-217">В тестовом режиме будет создана политика защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="c85ee-217">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="c85ee-218">**Элементы с состоянием рекомендации**</span><span class="sxs-lookup"><span data-stu-id="c85ee-218">**Items with Recommendation status**</span></span>

<span data-ttu-id="c85ee-219">Выберите раскрывающийся список рядом с меткой **Рекомендация** справа от действия улучшения.</span><span class="sxs-lookup"><span data-stu-id="c85ee-219">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="c85ee-220">Вы увидите сводную информацию о текущей среде Microsoft 365, которая связана с действием по улучшению, а также рекомендуем рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="c85ee-220">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="c85ee-221">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="c85ee-221">Resources</span></span>

<span data-ttu-id="c85ee-222">Более подробную информацию об установке, настройке и использовании МККА можно найти в [статье readme на сайте GitHub](https://github.com/OfficeDev/MCCA#overview) (нет учетной записи GitHub не нужно).</span><span class="sxs-lookup"><span data-stu-id="c85ee-222">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="c85ee-223">Для получения дополнительных сведений о Windows PowerShell Начните с [использования документации по PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="c85ee-223">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="c85ee-224">См. также [Запуск Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="c85ee-224">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
