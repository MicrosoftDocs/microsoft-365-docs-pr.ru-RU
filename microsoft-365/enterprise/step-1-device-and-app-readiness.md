---
title: Этап 1. Проверка готовности устройств и приложений
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как оценить готовность устройств и приложений в среде.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871087"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="2f9b6-103">Этап 1. Проверка готовности устройств и приложений</span><span class="sxs-lookup"><span data-stu-id="2f9b6-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="2f9b6-104">Начните свой проект по развертыванию на настольных ПК с инвентаризации имеющихся устройств и приложений, расставьте приоритеты и определите, что вы хотите использовать дальше, протестируйте отобранные приложения и устройства, а затем внесите исправления, необходимые для подготовки к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="2f9b6-105"><strong>Этап 1. Проверка готовности устройств и приложений</strong></span><span class="sxs-lookup"><span data-stu-id="2f9b6-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="2f9b6-106">Начните свой проект по развертыванию на настольных ПК с инвентаризации имеющихся устройств и приложений, расставьте приоритеты и определите, что вы хотите использовать дальше, протестируйте отобранные приложения и устройства, а затем внесите исправления, необходимые для подготовки к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="2f9b6-p101">Проверка готовности устройств и приложений — это первый этап рекомендуемого нами процесса развертывания, при выполнении которого необходимо проверить аспекты целостности в части совместимости приложений и оборудования. Весь процесс развертывания для настольных ПК см. в [центре Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="2f9b6-p102">В прошлом основным препятствием при обновлении настольных ПК пользователей были вопросы совместимости приложений и оборудования. Если вы планируете перейти на Windows 10 и Office 365 профессиональный плюс, хорошая новость заключается в том, что в Windows 10 будут работать почти все приложения, написанные в течение 10 последних лет. Любые надстройки COM и макросы VBA, которые ваша организация использовала, начиная с Office 2010, будут по-прежнему работать в последних версиях Office без какой-либо модернизации.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="2f9b6-111">Таким образом, в зависимости от размера и возраста вашей организации проверка совместимости приложений и оборудования, вероятно, по-прежнему будет важным первоначальным этапом рекомендуемого нами восьмиэтапного процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="2f9b6-112">В этой статье мы рассказываем о первом этапе — проверке готовности устройств и приложений с помощью нового средства "Проверка готовности к обновлению" в Windows Analytics. Это интеллектуальное облачное решение, доступное при наличии лицензии на ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="2f9b6-113">Если в данный момент в вашей среде нет Windows Analytics либо вы хотите зарегистрироваться, чтобы использовать пробную версию, перейдите на [страницу Windows Analytics](http://www.aka.ms/windowsanalytics) и начните работу.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="2f9b6-114">Рекомендуемое средство: "Проверка готовности к обновлению" в Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="2f9b6-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="2f9b6-p103">Рекомендуемое нами средство "Проверка готовности к обновлению" в Windows Analytics имеет много преимуществ перед традиционными системами управления для настольных ПК. Для его использования не нужен агент. С помощью этого средства вы выполните все необходимые действия. И, наконец, на основании сведений о совместимости приложений и драйверов, собранных при обновлении сотен миллионов потребительских ПК, это средство способно выполнить подробную оценку и выявить проблемы совместимости, из-за которых, возможно, не удастся выполнить обновление, а также предоставить ссылки на рекомендуемые исправления, известные Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="2f9b6-p104">Чтобы настроить средство "Проверка готовности к обновлению" в Windows Analytics, вам прежде всего потребуется настроить подписку на Azure и включить в нее рабочую область Azure Log Analytics. После запуска этого средства вы можете зарегистрировать любое подключенное к Интернету устройство под управлением Windows 7 с пакетом обновления 1 (SP1) или более поздней версии через параметры групповой политики. Это просто. Не нужно развертывать агенты, а с помощью визуального рабочего процесса средства "Проверка готовности к обновлению" в Windows Analytics вы пройдете от пилотной версии до развертывания в рабочей среде. При желании вы можете экспортировать данные из этого средства в средства развертывания программного обеспечения (например, в System Center Configuration Manager), чтобы выполнить настройку для компьютеров и создавать коллекции по мере их готовности к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="2f9b6-122">Процесс проверки готовности устройств и приложений</span><span class="sxs-lookup"><span data-stu-id="2f9b6-122">Device and App Readiness Process</span></span>

<span data-ttu-id="2f9b6-p105">Проверка готовности устройств и приложений включает четыре этапа: 1) инвентаризация; 2) определение приоритетов; 3) тестирование; 4) исправление. Давайте рассмотрим эти этапы по очереди.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="2f9b6-p106">1.\. Инвентаризация</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p106">1\. Inventory</span></span>

<span data-ttu-id="2f9b6-131">Для службы "Проверка готовности к обновлению" в Windows Analytics используется процесс инвентаризации компьютеров, приложений и надстроек Office на настольных ПК в организации, в котором не используются агенты.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="2f9b6-132">Кроме того, это средство формирует отчеты по самым посещаемым сайтам в Интернете, приложениям и расположениям в интрасети. Эти отчеты упростят для вас проверку совместимости в будущем.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="2f9b6-p107">2.\. Определение приоритетов</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p107">2\. Prioritize</span></span>

<span data-ttu-id="2f9b6-135">После инвентаризации с помощью средства "Проверка готовности к обновлению" в Windows Analytics можно обнаружить распространенные приложения и оборудование вашей организации, определить для них приоритеты, а также аспекты, на которых необходимо сконцентрироваться, чтобы подготовить как можно больше ПК к развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="2f9b6-136">Кроме того, в этом средстве имеются рекомендации по оценке обновлений, необходимых для решения проблем на следующем этапе — этапе тестирования.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="2f9b6-p108">3.\. Тестирование</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p108">3\. Testing</span></span>

<span data-ttu-id="2f9b6-p109">Вы обнаружите, что большая часть прошедших инвентаризацию приложений, драйверов и надстроек работает, как и прежде. Если средство "Проверка готовности к обновлению" в Windows Analytics обнаружит проблемы для каких-либо элементов, оно предоставит известную ему информацию, включая сведения о том, где найти обновления версий для устранения проблем, связанных с совместимостью. Вместо того чтобы тратить время и ресурсы на решение сложных проблем, связанных с второстепенными редко развертываемыми приложениями и старыми устройствами, вы можете проработать с пользователями возможность вывода этих элементов из эксплуатации или их замены.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="2f9b6-p110">С помощью средства "Проверка готовности к обновлению" в Windows Analytics вы также можете обнаружить проблемы совместимости при использовании браузеров, выявив веб-сайты и веб-приложения, к которым обращаются пользователи и в которых по-прежнему используются элементы ActiveX, вспомогательные объекты браузера, VBScript и другие устаревшие технологии, не поддерживаемые в браузере Microsoft Edge. Для работы с такими сайтами пользователям придется по-прежнему использовать браузер Internet Explorer 11. Вы можете добавить такие сайты в [список сайтов режима предприятия](https://docs.microsoft.com/ru-RU/microsoft-edge/deploy/emie-to-improve-compatibility) с помощью средства Enterprise Mode Site List Manager.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/ru-RU/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="2f9b6-144">Кроме того, чтобы упростить переход на Office 365 профессиональный плюс, вам может потребоваться использовать средство [Readiness Toolkit for Office](https://docs.microsoft.com/ru-RU/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) для проверки совместимости ваших надстроек и макросов Microsoft Visual Basic для приложений (VBA).</span><span class="sxs-lookup"><span data-stu-id="2f9b6-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/ru-RU/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="2f9b6-p111">4.\. Исправление</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p111">4\. Remediation</span></span>

<span data-ttu-id="2f9b6-p112">Последний этап проверки совместимости устройств и приложений — исправление. На этом этапе вам потребуется собрать необходимые пакеты программного обеспечения и драйверов. С их помощью вы замените или обновите устройства и приложения старых версий в процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="2f9b6-p113">При проработке списка проблем, которые необходимо исправить, вы обнаружите, что все больше и больше ПК переходит в состояние "Готов к развертыванию". Это означает, что драйверы и приложения на ПК признаны совместимыми с версией ОС Windows 10, для которой вы хотите выполнить развертывание.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="2f9b6-151">Непрерывное использование средств телеметрии</span><span class="sxs-lookup"><span data-stu-id="2f9b6-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="2f9b6-p114">"Проверка готовности к обновлению" в Windows Analytics — это не только средство, с помощью которого вы можете перейти на Windows 10 и Office 365 профессиональный плюс. После перевода настольных компьютеров на Windows 10 и Office 365 вы можете использовать это средство для обслуживания развертывания полугодовых обновлений компонентов и управления ими, чтобы поддерживать компьютеры в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f9b6-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="2f9b6-154">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="2f9b6-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="2f9b6-155">Этап 2. Проверка готовности каталогов и сети</span><span class="sxs-lookup"><span data-stu-id="2f9b6-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)