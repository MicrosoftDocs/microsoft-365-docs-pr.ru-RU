---
title: Обновление Office 2010 до Microsoft 365 — администрирование Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Узнайте, как обновить Microsoft Office до последнего клиента Office для пользователей в организации.
ms.openlocfilehash: 14be8d63b2acb3e4838640dc399595c0ba3f97f5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913998"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="2b8d2-103">Обновление Microsoft 365 для бизнес-пользователей до последнего клиента Office</span><span class="sxs-lookup"><span data-stu-id="2b8d2-103">Upgrade your Microsoft 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="2b8d2-104">Office 2010 достигает конечной поддержки</span><span class="sxs-lookup"><span data-stu-id="2b8d2-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="2b8d2-105">Office 2010 вышел на конец поддержки 13 октября 2020 г.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-105">Office 2010 reached its end of support on October 13, 2020.</span></span> <span data-ttu-id="2b8d2-106">Корпорация Майкрософт больше не будет предоставлять следующие:</span><span class="sxs-lookup"><span data-stu-id="2b8d2-106">Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="2b8d2-107">Техническая поддержка проблем</span><span class="sxs-lookup"><span data-stu-id="2b8d2-107">Technical support for issues</span></span>

- <span data-ttu-id="2b8d2-108">Исправление ошибок для обнаруженных проблем</span><span class="sxs-lookup"><span data-stu-id="2b8d2-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="2b8d2-109">Исправления безопасности для обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="2b8d2-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="2b8d2-110">Дополнительные сведения см. в конце плана [поддержки Office 2010.](/deployoffice/endofsupport/office-2010-end-support-roadmap)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-110">See [Office 2010 end of support roadmap](/deployoffice/endofsupport/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="2b8d2-111">**Это правильный раздел для вас?**</span><span class="sxs-lookup"><span data-stu-id="2b8d2-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="2b8d2-112">Если вы администратор, ответственный за подписку microsoft 365 для бизнеса в вашей организации, вы в правильном месте.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-112">If you're the admin responsible for the Microsoft 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="2b8d2-113">Администраторы обычно отвечают за такие задачи, как управление пользователями, сброс паролей, управление установками Office и добавление или удаление лицензий.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="2b8d2-114">Если вы не администратор и у вас есть продукт [Семейства Microsoft 365,](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) см. статью Как обновить [Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) для получения сведений об обновлении старой, домашней версии Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-114">If you're not an admin and you have a [Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) for information about upgrading your older, home use version of Office.</span></span>

## <a name="get-ready-to-upgrade-to-microsoft-365"></a><span data-ttu-id="2b8d2-115">Готовьтесь к обновлению до Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8d2-115">Get ready to upgrade to Microsoft 365</span></span>

<span data-ttu-id="2b8d2-116">В качестве администратора вы контролируете, какую версию могут установить люди Office в организации.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="2b8d2-117">Мы настоятельно рекомендуем пользователям в организации запускать более старые версии Office, такие как Office 2010, Office 2013 или Office 2016, обновление до последней версии, чтобы воспользоваться преимуществами повышения безопасности и производительности.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="2b8d2-118">Действия по обновлению</span><span class="sxs-lookup"><span data-stu-id="2b8d2-118">Upgrade steps</span></span>

<span data-ttu-id="2b8d2-p104">Ниже приведены пошаговые инструкции, которые помогут вам обновить программное обеспечение пользователей до последней версии классического клиента Office. Рекомендуем ознакомиться с этими шагами до начала обновления.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-p104">The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="2b8d2-121">Шаг 1. Проверка требований к системе</span><span class="sxs-lookup"><span data-stu-id="2b8d2-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="2b8d2-122">[Проверьте системные требования](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) к Office, чтобы убедиться, что устройства совместимы с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-122">[Check the system requirements](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="2b8d2-123">Например, более новые версии Office не могут быть установлены на компьютерах с Windows XP или Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="2b8d2-124">Если в вашей организации пользователи запускают более старые версии Windows на компьютерах или ноутбуках, рекомендуется обновление до Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="2b8d2-125">Windows 7 достигла конца поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="2b8d2-126">Дополнительные сведения можно получить в службе поддержки Windows 7, которая заканчивается в январе [2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) г.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="2b8d2-127">Ознакомьтесь с [требованиями к системе Windows 10,](https://www.microsoft.com/windows/windows-10-specifications) чтобы узнать, можно ли обновить их операционные системы.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="2b8d2-128">Проверка совместимости приложений</span><span class="sxs-lookup"><span data-stu-id="2b8d2-128">Check application compatibility</span></span>

<span data-ttu-id="2b8d2-129">Чтобы обеспечить успешное обновление, рекомендуем определить все приложения Office, включая сценарии VBA, макросы, надстройки сторонних разработчиков, а также сложные документы и электронные таблицы, и оценить их совместимость с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="2b8d2-130">Например, если в текущей версии Office вы используете надстройки сторонних разработчиков, обратитесь к поставщику, чтобы узнать, совместимы ли они с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="2b8d2-131">Шаг 2. Проверка существующего плана подписки</span><span class="sxs-lookup"><span data-stu-id="2b8d2-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="2b8d2-132">Некоторые планы Microsoft 365 не включают полные настольные версии Office, а действия по обновлению отличаются, если в план не входит Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-132">Some Microsoft 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="2b8d2-133">Не знаете, какой у вас есть план подписки?</span><span class="sxs-lookup"><span data-stu-id="2b8d2-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="2b8d2-134">Узнайте, что у меня есть для подписки на Microsoft [365 для бизнеса?](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-134">See [What Microsoft 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="2b8d2-135">Если ваш текущий план включает в себя Office, перейдите к разделу [Шаг 3. Удаление Office](#step-3---uninstall-office).</span><span class="sxs-lookup"><span data-stu-id="2b8d2-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="2b8d2-136">В противном случае выберите один из вариантов ниже.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="2b8d2-137">Варианты обновления для планов, не включающих в себя Office</span><span class="sxs-lookup"><span data-stu-id="2b8d2-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="2b8d2-138">**Вариант 1. Переключение подписки на Office**</span><span class="sxs-lookup"><span data-stu-id="2b8d2-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="2b8d2-139">Переключение на подписку, включаемую Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="2b8d2-140">См. [переход на другой Microsoft 365 для бизнес-плана.](../../commerce/subscriptions/switch-to-a-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-140">See [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="2b8d2-141">**Вариант 2. Покупка отдельных, разовые покупки Office или покупка Office с помощью лицензии на объем**</span><span class="sxs-lookup"><span data-stu-id="2b8d2-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="2b8d2-142">Купите индивидуальную, разовую покупку Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="2b8d2-143">См. [в деле Office Home &amp; Business](https://products.office.com/home-and-business) или [Office Professional](https://products.office.com/professional)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="2b8d2-144">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="2b8d2-144">OR</span></span>

 - <span data-ttu-id="2b8d2-145">Приобретай несколько копий Office с помощью лицензии на объем.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="2b8d2-146">См. [в руб. Сравнение пакетов, доступных с помощью лицензирования объемов.](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="2b8d2-147">Шаг 3. Удаление Office</span><span class="sxs-lookup"><span data-stu-id="2b8d2-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="2b8d2-148">Перед установкой последней версии Office рекомендуется удалить все старые версии Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="2b8d2-149">Однако, если вы измените свое решение о обновлении Office, обратите внимание на следующие случаи, когда после его стирки не удастся переустановить Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="2b8d2-150">Если у вас есть сторонние надстройки, обратитесь к производителю, чтобы узнать, есть ли обновление, которое будет работать с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

> [!TIP]
> <span data-ttu-id="2b8d2-151">Если при устранении проблем с Office вы можете использовать средство помощника по поддержке и восстановлению Майкрософт, чтобы помочь удалить Office: [Скачайте](https://go.microsoft.com/fwlink/?LinkID=2155008)и запустите помощник по поддержке и восстановлению Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-151">If you run into issues while uninstalling Office, you can use the Microsoft Support and Recovery Assistant tool to help you remove Office: [Download and run the Microsoft Support and Recovery Assistant](https://go.microsoft.com/fwlink/?LinkID=2155008).</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="2b8d2-152">Выберите версию Office, которая необходимо удалить</span><span class="sxs-lookup"><span data-stu-id="2b8d2-152">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="2b8d2-153">С компьютера</span><span class="sxs-lookup"><span data-stu-id="2b8d2-153">From a PC</span></span>](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [<span data-ttu-id="2b8d2-154">С Mac</span><span class="sxs-lookup"><span data-stu-id="2b8d2-154">From a Mac</span></span>](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="2b8d2-155">Известные проблемы при попытке переустановить предыдущие версии Office после удаления</span><span class="sxs-lookup"><span data-stu-id="2b8d2-155">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="2b8d2-156">**Office через лицензию тома** Если у вас больше нет доступа к исходным файлам этих версий томной лицензии Office, переустановить его не удастся.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-156">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="2b8d2-157">**Office, предварительно установленный на компьютере** Если у вас больше нет диска или ключа продукта (если Office пришел с ним), переустановить его не удастся.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-157">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="2b8d2-158">**Подписки, не поддерживаемые** Если копия Office была получена с помощью прекращенных подписок, таких как Office 365 Small Business Premium или Office 365 Среднего размера, вы не сможете установить старую версию Office, если у вас нет ключа продукта, который пришел с подпиской.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-158">**Non-supported subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="2b8d2-p112">Если вы хотите установить старую версию Office параллельно с новой, просмотрите список версий, для которых поддерживается эта возможность, в статье [Установка и использование разных версий Office на одном компьютере](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). Параллельная установка может быть хорошим выбором, например, если вы используете в текущей версии Office надстройки сторонних разработчиков и не уверены в их совместимости с новой версией.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-p112">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="2b8d2-161">Шаг 4. Назначение лицензий на Office пользователям</span><span class="sxs-lookup"><span data-stu-id="2b8d2-161">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="2b8d2-162">Если вы еще этого не сделали, назначьте лицензии любым пользователям в организации, которым необходимо установить Office, см. в рублях Назначение лицензий пользователям [в Microsoft 365 для бизнеса.](../manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-162">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="2b8d2-163">Шаг 5. Установка Office</span><span class="sxs-lookup"><span data-stu-id="2b8d2-163">Step 5 - Install Office</span></span>

<span data-ttu-id="2b8d2-164">После проверки пользователей, у которых необходимо обновить все лицензии, последний шаг — установить Office, скачать и установить или переустановить Office на компьютере или [Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-164">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span>
  
> [!TIP]
> <span data-ttu-id="2b8d2-165">Если вы не хотите, чтобы пользователи сами устанавливали Office, см. в рублях Управление настройками загрузки программного обеспечения [в Office 365.](/DeployOffice/manage-software-download-settings-office-365)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-165">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="2b8d2-166">С помощью [средства развертывания Office](/DeployOffice/overview-office-deployment-tool) можно скачать программное обеспечение Office в локализованную сеть, а затем развернуть Office с помощью обычно используемого метода развертывания программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-166">You can use the [Office Deployment Tool](/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>