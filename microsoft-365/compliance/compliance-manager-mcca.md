---
title: Анализатор конфигурации соответствия требованиям (Майкрософт) для диспетчера соответствия требованиям
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
description: В этой теме вы знаете, как использовать анализатор конфигурации соответствия требованиям (Майкрософт) для быстрого запуска с помощью диспетчера соответствия требованиям (Майкрософт).
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122399"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="08fce-103">Анализатор конфигурации соответствия требованиям (Майкрософт) для диспетчера соответствия требованиям (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="08fce-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="08fce-104">**В этой статье:** Узнайте, как установить и запустить анализатор соответствия требованиям (Майкрософт), чтобы быстро начать работу с Microsoft Compliance Manger.</span><span class="sxs-lookup"><span data-stu-id="08fce-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="08fce-105">Обзор анализатора конфигурации соответствия (MCCA) (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="08fce-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="08fce-106">Анализатор конфигурации соответствия требованиям (Майкрософт) (MCCA) — это средство предварительной версии, которое поможет вам начать работу с [диспетчером соответствия требованиям Майкрософт.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="08fce-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="08fce-107">MCCA — это программа на основе PowerShell, которая извлекет текущие конфигурации вашей организации и проверяет их на основе рекомендуемых microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08fce-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="08fce-108">Эти практические методики основаны на наборе средств контроля, которые включают ключевые нормативы и стандарты для защиты данных и управления данными.</span><span class="sxs-lookup"><span data-stu-id="08fce-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="08fce-109">MCCA поможет вам быстро узнать, какие действия по улучшению в Службе соответствия требованиям применяются к текущей среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08fce-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="08fce-110">Каждое действие, которое определено MCCA, дает рекомендации по реализации с прямыми ссылками на диспетчер соответствия требованиям и применимым решением для принятия коррективных мер.</span><span class="sxs-lookup"><span data-stu-id="08fce-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="08fce-111">Дополнительный ресурс для понимания MCCA — ознакомиться с инструкциями [README на GitHub.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="08fce-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="08fce-112">На этой странице приводится подробная информация о предварительных условиях и инструкции по полной установке.</span><span class="sxs-lookup"><span data-stu-id="08fce-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="08fce-113">Для доступа к этой странице не требуется учетная запись GitHub.</span><span class="sxs-lookup"><span data-stu-id="08fce-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="08fce-114">**Доступность:** MCCA доступна всем организациям с лицензиями на Office 365 и Microsoft 365, а также клиентам среднего уровня сообщества государственных организаций США (GCC). В настоящее время планируется расширить возможности обслуживания до клиентов GCC High.</span><span class="sxs-lookup"><span data-stu-id="08fce-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate customers, with plans underway to expand service to to GCC High customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="08fce-115">Установка MCCA и запуск отчета</span><span class="sxs-lookup"><span data-stu-id="08fce-115">Install MCCA and run a report</span></span>

<span data-ttu-id="08fce-116">Средство MCCA можно установить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08fce-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="08fce-117">Скачав и установив средство, вам не нужно повторять эти действия, чтобы запускать отчеты.</span><span class="sxs-lookup"><span data-stu-id="08fce-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="08fce-118">Каждый раз, когда вы открываете MCCA, вам будут запросить учетные данные для входа, и будет создаваться новый обновленный отчет.</span><span class="sxs-lookup"><span data-stu-id="08fce-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="08fce-119">Шаг 1. Установка Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08fce-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="08fce-120">Для начала вам потребуется модуль Exchange Online PowerShell (2.0.3 или выше), доступный в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08fce-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="08fce-121">[Получите инструкции по установке.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="08fce-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="08fce-122">Шаг 2. Установка MCCA</span><span class="sxs-lookup"><span data-stu-id="08fce-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="08fce-123">Чтобы установить MCCA, начните с использования PowerShell в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="08fce-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="08fce-124">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="08fce-124">Follow the steps below:</span></span>

1. <span data-ttu-id="08fce-125">Выберите кнопку **"Начните"** в Windows.</span><span class="sxs-lookup"><span data-stu-id="08fce-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="08fce-126">Введите **PowerShell,** щелкните правой кнопкой **мыши** Windows PowerShell выберите "Запуск **от администратора".**</span><span class="sxs-lookup"><span data-stu-id="08fce-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="08fce-127">В командной строке введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="08fce-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="08fce-128">Шаг 3. Запуск отчета</span><span class="sxs-lookup"><span data-stu-id="08fce-128">Step 3: Run a report</span></span>

<span data-ttu-id="08fce-129">После установки MCCA можно запустить MCCA и создать отчет.</span><span class="sxs-lookup"><span data-stu-id="08fce-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="08fce-130">Чтобы запустить отчет:</span><span class="sxs-lookup"><span data-stu-id="08fce-130">To run a report:</span></span>

1. <span data-ttu-id="08fce-131">Откройте PowerShell</span><span class="sxs-lookup"><span data-stu-id="08fce-131">Open PowerShell</span></span>
2. <span data-ttu-id="08fce-132">Запустите этот cmdlet:</span><span class="sxs-lookup"><span data-stu-id="08fce-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="08fce-133">После того как MCCA выполняется, он выполняет первоначальную проверку версии и запросит учетные данные.</span><span class="sxs-lookup"><span data-stu-id="08fce-133">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="08fce-134">Во входе запроса имени пользователя во sign in with your Microsoft 365 account email address[(view the roles eligible to create reports).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="08fce-134">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="08fce-135">Затем введите пароль в запросе пароля.</span><span class="sxs-lookup"><span data-stu-id="08fce-135">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="08fce-136">После этого создание отчета займет около 2-5 минут.</span><span class="sxs-lookup"><span data-stu-id="08fce-136">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="08fce-137">После этого откроется окно браузера и отобразит htmL-отчет.</span><span class="sxs-lookup"><span data-stu-id="08fce-137">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="08fce-138">При каждом запуске средства оно будет запросить ваши учетные данные и создать новый отчет.</span><span class="sxs-lookup"><span data-stu-id="08fce-138">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="08fce-139">Этот отчет хранится локально в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="08fce-139">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="08fce-140">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="08fce-140">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="08fce-141">Вы можете получить доступ к ранее созданным отчетам из этого каталога.</span><span class="sxs-lookup"><span data-stu-id="08fce-141">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="08fce-142">Понимание отчета</span><span class="sxs-lookup"><span data-stu-id="08fce-142">Understanding your report</span></span>

<span data-ttu-id="08fce-143">Отчет отражает данные на основе даты и времени, в которое он был создан.</span><span class="sxs-lookup"><span data-stu-id="08fce-143">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="08fce-144">В верхнем разделе приводится информация о том, когда он был создан, название организации и ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="08fce-144">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="08fce-145">Отчеты на основе географического местонахождения</span><span class="sxs-lookup"><span data-stu-id="08fce-145">Geolocation-based reporting</span></span>

<span data-ttu-id="08fce-146">В **разделе** "Примечание" показано, что отчет настраивается в зависимости от географического расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="08fce-146">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="08fce-147">Рекомендации, перечисленные в средстве, будут перечислены в конкретной стране или регионе.</span><span class="sxs-lookup"><span data-stu-id="08fce-147">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="08fce-148">Выбор географического местонахождения используется для оценки типов конфиденциальной информации, соответствующих этому географическому местонахождению, и создания отчета, соответствующего вашей стране или региону.</span><span class="sxs-lookup"><span data-stu-id="08fce-148">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="08fce-149">Выберите географическое местонахождение на основе данных, которые у вас есть в клиенте.</span><span class="sxs-lookup"><span data-stu-id="08fce-149">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="08fce-150">Чтобы изменить сведения о расположении отчета, необходимо предоставить входной параметр географического расположения (-Geo).</span><span class="sxs-lookup"><span data-stu-id="08fce-150">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="08fce-151">Вы можете выбрать одно или несколько географических местонахождений, применимых к вашему арендатору.</span><span class="sxs-lookup"><span data-stu-id="08fce-151">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="08fce-152">Выполните эти инструкции, чтобы запустить отчет на основе определенного расположения:</span><span class="sxs-lookup"><span data-stu-id="08fce-152">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="08fce-153">Откройте PowerShell</span><span class="sxs-lookup"><span data-stu-id="08fce-153">Open PowerShell</span></span>
2. <span data-ttu-id="08fce-154">Чтобы указать определенный регион, необходимо выполнить его с помощью номеров из таблицы ниже, соответствующих стране или региону.</span><span class="sxs-lookup"><span data-stu-id="08fce-154">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="08fce-155">Введите несколько цифр, разделив их запятой.</span><span class="sxs-lookup"><span data-stu-id="08fce-155">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="08fce-156">Например, в приведенной ниже таблице будет запускаться настраиваемый отчет для Asia-Pacific и Японии:</span><span class="sxs-lookup"><span data-stu-id="08fce-156">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="08fce-157">Input</span><span class="sxs-lookup"><span data-stu-id="08fce-157">Input</span></span> |  <span data-ttu-id="08fce-158">Страна</span><span class="sxs-lookup"><span data-stu-id="08fce-158">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="08fce-159">1 </span><span class="sxs-lookup"><span data-stu-id="08fce-159">1</span></span> | <span data-ttu-id="08fce-160">Азиатско-Тихоокеанский регион</span><span class="sxs-lookup"><span data-stu-id="08fce-160">Asia-Pacific</span></span> |
  | <span data-ttu-id="08fce-161">2 </span><span class="sxs-lookup"><span data-stu-id="08fce-161">2</span></span> | <span data-ttu-id="08fce-162">Австралия</span><span class="sxs-lookup"><span data-stu-id="08fce-162">Australia</span></span> |
  | <span data-ttu-id="08fce-163">3 </span><span class="sxs-lookup"><span data-stu-id="08fce-163">3</span></span> | <span data-ttu-id="08fce-164">Канада</span><span class="sxs-lookup"><span data-stu-id="08fce-164">Canada</span></span> |
  | <span data-ttu-id="08fce-165">4 </span><span class="sxs-lookup"><span data-stu-id="08fce-165">4</span></span> | <span data-ttu-id="08fce-166">Европа (за исключением Франции), Ближний Восток и Африка</span><span class="sxs-lookup"><span data-stu-id="08fce-166">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="08fce-167">5 </span><span class="sxs-lookup"><span data-stu-id="08fce-167">5</span></span> | <span data-ttu-id="08fce-168">Франция</span><span class="sxs-lookup"><span data-stu-id="08fce-168">France</span></span> |
  | <span data-ttu-id="08fce-169">6 </span><span class="sxs-lookup"><span data-stu-id="08fce-169">6</span></span> | <span data-ttu-id="08fce-170">Индия</span><span class="sxs-lookup"><span data-stu-id="08fce-170">India</span></span> |
  | <span data-ttu-id="08fce-171">7 </span><span class="sxs-lookup"><span data-stu-id="08fce-171">7</span></span> | <span data-ttu-id="08fce-172">Япония</span><span class="sxs-lookup"><span data-stu-id="08fce-172">Japan</span></span> |
  | <span data-ttu-id="08fce-173">8 </span><span class="sxs-lookup"><span data-stu-id="08fce-173">8</span></span> | <span data-ttu-id="08fce-174">Республика Корея</span><span class="sxs-lookup"><span data-stu-id="08fce-174">Korea</span></span> |
  | <span data-ttu-id="08fce-175">9 </span><span class="sxs-lookup"><span data-stu-id="08fce-175">9</span></span> | <span data-ttu-id="08fce-176">Северная Америка (за исключением Канады)</span><span class="sxs-lookup"><span data-stu-id="08fce-176">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="08fce-177">10 </span><span class="sxs-lookup"><span data-stu-id="08fce-177">10</span></span> | <span data-ttu-id="08fce-178">Южная Америка</span><span class="sxs-lookup"><span data-stu-id="08fce-178">South America</span></span> |
  | <span data-ttu-id="08fce-179">11 </span><span class="sxs-lookup"><span data-stu-id="08fce-179">11</span></span> | <span data-ttu-id="08fce-180">Южная Африка</span><span class="sxs-lookup"><span data-stu-id="08fce-180">South Africa</span></span> |
  | <span data-ttu-id="08fce-181">12 </span><span class="sxs-lookup"><span data-stu-id="08fce-181">12</span></span> | <span data-ttu-id="08fce-182">Швейцария</span><span class="sxs-lookup"><span data-stu-id="08fce-182">Switzerland</span></span> |
  | <span data-ttu-id="08fce-183">13 </span><span class="sxs-lookup"><span data-stu-id="08fce-183">13</span></span> | <span data-ttu-id="08fce-184">Объединенные Арабские Эмираты</span><span class="sxs-lookup"><span data-stu-id="08fce-184">United Arab Emirates</span></span> |
  | <span data-ttu-id="08fce-185">14 </span><span class="sxs-lookup"><span data-stu-id="08fce-185">14</span></span> | <span data-ttu-id="08fce-186">Великобритания</span><span class="sxs-lookup"><span data-stu-id="08fce-186">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="08fce-187">Отчет всегда будет включать поддерживаемые MCCA международные типы конфиденциальной информации, такие как код SWIFT, номер кредитной карты и т. д.</span><span class="sxs-lookup"><span data-stu-id="08fce-187">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="08fce-188">Отчеты на основе ролей</span><span class="sxs-lookup"><span data-stu-id="08fce-188">Role-based reporting</span></span>

<span data-ttu-id="08fce-189">Отчет также будет настраиваться в зависимости от вашей роли.</span><span class="sxs-lookup"><span data-stu-id="08fce-189">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="08fce-190">В приведенной ниже таблице показано, какие роли имеют доступ к разделам отчета.</span><span class="sxs-lookup"><span data-stu-id="08fce-190">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="08fce-191">Другие роли в организации (не перечисленные в таблице ниже) могут не иметь возможности запускать средство или запускать средство и иметь ограниченный доступ к информации в итоговом отчете.</span><span class="sxs-lookup"><span data-stu-id="08fce-191">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="08fce-192">![MCCA — роли](../media/compliance-manager-mcca-roles.png "Роли MCCA")</span><span class="sxs-lookup"><span data-stu-id="08fce-192">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="08fce-193">Ниже перечислены исключения для этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="08fce-193">Exceptions:</span></span>
1. <span data-ttu-id="08fce-194">Пользователь не сможет создавать отчет для IP-адресов отдельно от раздела "Использование IRM для Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="08fce-194">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="08fce-195">Пользователь сможет создавать отчет для IP-адресов отдельно от раздела "Использование IRM для Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="08fce-195">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="08fce-196">Пользователь сможет создавать отчет для IP-адресов отдельно от раздела "Enable Communication Compliance in O365".</span><span class="sxs-lookup"><span data-stu-id="08fce-196">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="08fce-197">Пользователь не сможет создавать отчет для IP-адресов отдельно от раздела "Включить аудит в Office 365".</span><span class="sxs-lookup"><span data-stu-id="08fce-197">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="08fce-198">Пользователь сможет создавать отчет для IP-адресов отдельно от раздела "Включить аудит в Office 365".</span><span class="sxs-lookup"><span data-stu-id="08fce-198">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="08fce-199">Раздел "Сводка по решениям"</span><span class="sxs-lookup"><span data-stu-id="08fce-199">Solutions Summary section</span></span>

<span data-ttu-id="08fce-200">В **разделе "Сводка** решений" отчета приводится обзор действий по улучшению, которые ваша организация может принять в диспетчере соответствия требованиям, чтобы повысить уровень соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08fce-200">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="08fce-201">![MCCA — сводка по решениям](../media/compliance-manager-mcca-solutions.png "Экран сводки по решениям MCCA")</span><span class="sxs-lookup"><span data-stu-id="08fce-201">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="08fce-202">MCCA оценивает текущие конфигурации с соответствием рекомендуемых действий по улучшению в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08fce-202">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="08fce-203">Все действия по улучшению, которые средство MCCA определило как необходимые для внимания, будут перечислены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="08fce-203">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="08fce-204">Рядом с каждым решением Майкрософт находятся цветные поля, указывающие количество элементов, соответствующих действиям по улучшению в диспетчере соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08fce-204">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="08fce-205">Действия разбиты на три состояния:</span><span class="sxs-lookup"><span data-stu-id="08fce-205">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="08fce-206">**OK**: действия, которые соответствуют рекомендуемые условия и не требуют внимания в настоящее время</span><span class="sxs-lookup"><span data-stu-id="08fce-206">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="08fce-207">**Улучшение**: действия, которые требуют внимания</span><span class="sxs-lookup"><span data-stu-id="08fce-207">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="08fce-208">**Рекомендация**: действия, которые не требуют внимания, но для которых мы рекомендуем рекомендации</span><span class="sxs-lookup"><span data-stu-id="08fce-208">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="08fce-209">Выберите поле для просмотра улучшений и рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="08fce-209">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="08fce-210">**Элементы с состоянием улучшения**</span><span class="sxs-lookup"><span data-stu-id="08fce-210">**Items with the Improvement status**</span></span>

<span data-ttu-id="08fce-211">Выберите выпадание рядом с меткой **"Улучшение"** справа от действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="08fce-211">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="08fce-212">Вы увидите краткую сводку и подробные сведения о текущих параметрах и рекомендуемых действиях по улучшению.</span><span class="sxs-lookup"><span data-stu-id="08fce-212">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="08fce-213">Сводка содержит прямые ссылки на диспетчер соответствия требованиям, соответствующее решение в Центре соответствия требованиям Microsoft 365 и соответствующую документацию.</span><span class="sxs-lookup"><span data-stu-id="08fce-213">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="08fce-214">Щелкнув ссылку "Диспетчер соответствия требованиям", вы отфильтрованное представление всех действий по улучшению в этом решении, которые еще не реализованы.</span><span class="sxs-lookup"><span data-stu-id="08fce-214">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="08fce-215">Здесь можно увидеть количество баллов, которые можно достичь для повышения оценки соответствия [требованиям,](compliance-score-calculation.md)а также применяемые ими оценки, а также применимые нормативы и сертификации.</span><span class="sxs-lookup"><span data-stu-id="08fce-215">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="08fce-216">Для DLP есть кнопка "Скрипт устранения", которая предоставляет готовый сценарий PowerShell, основанный на рекомендуемых рекомендациях. </span><span class="sxs-lookup"><span data-stu-id="08fce-216">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="08fce-217">Вы можете скопировать и вкопировать его непосредственно в консоль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08fce-217">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="08fce-218">Она создаст политику DLP в тестовом режиме</span><span class="sxs-lookup"><span data-stu-id="08fce-218">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="08fce-219">**Элементы с состоянием "Рекомендации"**</span><span class="sxs-lookup"><span data-stu-id="08fce-219">**Items with Recommendation status**</span></span>

<span data-ttu-id="08fce-220">Выберите выпадание рядом с меткой **"Рекомендация"** справа от действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="08fce-220">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="08fce-221">Вы увидите сводку текущей среды Microsoft 365 вашей организации, связанную с действием по улучшению, а также рекомендуемые рекомендации.</span><span class="sxs-lookup"><span data-stu-id="08fce-221">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="08fce-222">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="08fce-222">Resources</span></span>

<span data-ttu-id="08fce-223">Дополнительные сведения об установке, настройке и использовании MCCA см. в инструкциях README на [GitHub](https://github.com/OfficeDev/MCCA#overview) (учетная запись GitHub не требуется).</span><span class="sxs-lookup"><span data-stu-id="08fce-223">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="08fce-224">Дополнительные сведения о Windows PowerShell, начните с использования документации [по PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="08fce-224">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="08fce-225">См. также [начальный Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="08fce-225">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
