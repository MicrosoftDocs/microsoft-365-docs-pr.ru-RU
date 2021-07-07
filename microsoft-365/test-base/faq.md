---
title: Тестовый базовый faq
description: Обзор часто задамые вопросы
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323383"
---
# <a name="test-base-faq"></a><span data-ttu-id="1f2f9-103">Тестовый базовый faq</span><span class="sxs-lookup"><span data-stu-id="1f2f9-103">Test Base FAQ</span></span>

<span data-ttu-id="1f2f9-104">**В. Как отправить пакеты в команду Test Base?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="1f2f9-105">**A:** Отправка пакетов непосредственно в среду тестовой базы с помощью нашего портала самообслуживки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="1f2f9-106">Чтобы отправить пакет приложений, перейдите на портал [Azure и](https://www.aka.ms/testbaseportal "Главная страницы тестовой базы") загрузите папку с молнией, содержащую седаны, зависимости и сценарии тестирования приложения с помощью панели мониторинга тестовой базы самообслуживатель.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="1f2f9-107">Дополнительные сведения см. в руководстве пользователя по бортам или свяжитесь с нашей командой за <testbasepreview@microsoft.com> помощью и дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="1f2f9-108">**В. Какие тесты являются тестами out-of-box (OOB)?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="1f2f9-109">**A:** Стандартные тесты (OOB) стандартизуются, тестовые тесты по умолчанию запускаются, запускаются и закрываются 30 (30) раз, а затем неустановлены.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="1f2f9-110">Пакеты, созданные для тестовой базы, будут иметь следующие тестовые сценарии: установить, запустить, закрыть и необязательно удалить скрипт.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="1f2f9-111">Тесты out-of-box (OOB) предоставляют стандартизированную телеметрию в приложении для сравнения Windows сборки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="1f2f9-112">**В. Можем ли мы отправлять тесты за пределами тестов out-of-box (установка, запуск, закрыть, удалить тестовые скрипты)?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="1f2f9-113">**A:** Да, клиенты также могут загружать пакеты приложений для **функциональных тестов** с помощью панели мониторинга портала самообслуживки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="1f2f9-114">**Функциональные тесты** — это тесты, позволяющие клиентам выполнять сценарии для выполнения настраиваемой функциональности в своем приложении.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="1f2f9-115">Тестирование</span><span class="sxs-lookup"><span data-stu-id="1f2f9-115">Testing</span></span>

<span data-ttu-id="1f2f9-116">**В. Поддерживаете ли вы функциональные тесты?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="1f2f9-117">**A:** Да, тестовая база поддерживает функциональные тесты.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="1f2f9-118">Функциональные тесты — это тесты, которые позволяют нашим клиентам выполнять сценарии для выполнения настраиваемой функциональности в своем приложении.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="1f2f9-119">Чтобы отправить пакет приложений для функционального тестирования, просто загрузите папку с молнией, содержащую седаны, зависимости и тестовые скрипты приложения с помощью панели мониторинга портала самообслуживки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="1f2f9-120">Дополнительные сведения см. в руководстве пользователя по бортам или свяжитесь с нашей командой за <testbasepreview@microsoft.com> помощью и дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="1f2f9-121">**В. Как тестовая база обрабатывает наши тестовые данные?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="1f2f9-122">**A:** Тестовая база надежно собирает и управляет тестными данными в среде Azure.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="1f2f9-123">**В. Может ли тестовая база поддерживать наши автоматизированные тесты?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="1f2f9-124">Да, тестовая база поддерживает автоматизированные тесты, однако в настоящее время мы не поддерживаем ручные тесты из-за возможностей службы.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="1f2f9-125">**В. Какие языки и структуры автоматизированных тестов вы поддерживаете?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="1f2f9-126">**A:** Мы поддерживаем все языки и структуры.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="1f2f9-127">Мы вызываем все скрипты через PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="1f2f9-128">Кроме того, необходимо предоставить (загрузить) зависимые биналоги необходимой структуры.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="1f2f9-129">**В. Как скоро тестовая база предоставит результаты тестирования?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="1f2f9-130">**A:** Каждый тест, который мы запускаем с сборками предварительного выпуска, будет предоставлять результаты в течение 48 часов на панели [мониторинга Azure Portal.](https://www.aka.ms/testbaseportal "Главная страницы тестовой базы")</span><span class="sxs-lookup"><span data-stu-id="1f2f9-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="1f2f9-131">**В. Можно ли перезагрузать после установки?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="1f2f9-132">**A:** Да, наш процесс поддерживает перезагрузку после установки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="1f2f9-133">Не забудьте выбрать этот параметр из списка "Необязательные параметры" при настройке задач **на** портале onboarding.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="1f2f9-134">Для тестов out-of-box (OOB) можно указать, нужна ли перезагрузка для сценария _Install._</span><span class="sxs-lookup"><span data-stu-id="1f2f9-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Снимок перезагрузки](Media/reboot.png)

<span data-ttu-id="1f2f9-136">В то время как для функциональных тестов можно указать, требуется ли перезагрузка для каждого добавленного сценария.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Выбор функциональных тестов](Media/functionalreboot.png)

<span data-ttu-id="1f2f9-138">**В. Какие Windows поддерживаете?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="1f2f9-139">**A:** В настоящее время мы поддерживаем Windows 10, Windows Server 2016, Windows Server 2016 версию Core, Windows Server 2019 и Windows Server 2019 Core.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="1f2f9-140">**В. В чем разница между тестами обновления безопасности и тестами обновления функций?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="1f2f9-141">**A:** Для тестирования обновлений безопасности **<ins></ins>** мы проверяем ежемесячные обновления безопасности перед выпуском в Windows, которые ориентированы на обеспечение безопасности и защиты пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="1f2f9-142">Для тестов обновления функций мы **<ins></ins>** тестировать на основе двухлетки обновлений компонентов предварительного выпуска, которые вводят новые функции и возможности на Windows.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="1f2f9-143">Параметры отладки</span><span class="sxs-lookup"><span data-stu-id="1f2f9-143">Debugging options</span></span>

<span data-ttu-id="1f2f9-144">**В. Получаем ли мы доступ к виртуальным машинам (виртуальным машинам) в случае сбоев? Что такое доля тестовой базы?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="1f2f9-145">**A:** Чтобы служба была совместима, а предзапустимые обновления были безопасными, доступ к VMs имеет только Корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="1f2f9-146">Однако клиенты могут просматривать результаты тестов и другие показатели тестирования на панели мониторинга портала, включая сигналы аварийного сбоя и подвешения, показатели надежности, использование памяти и ЦП и т. д. Мы также генерируем и предоставляем журналы тестовых запусков на панели мониторинга для скачивания и дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="1f2f9-147">Мы также можем предоставить сбросы памяти для отладки сбоя по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="1f2f9-148">**В. Если во время тестирования имеются проблемы, какие дальнейшие действия необходимо предпринять для устранения этих проблем?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="1f2f9-149">**A:** Группа тестовой базы выполнит начальный процесс определения первопричины ошибки, а затем в зависимости от полученных результатов мы переназначим для отладки клиентскую или внутреннюю команды в Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="1f2f9-150">Мы всегда тесно сотрудничаем с нашими клиентами в совместной работе по устранению любых проблем.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="1f2f9-151">**В. Корпорация Майкрософт удерживает выпуск исправлений безопасности до решения проблемы? Какие альтернативные разрешения доступны?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="1f2f9-152">**A:** Целью тестовой базы является обеспечение того, чтобы наши конечные клиенты не сталкивались с любыми вопросами.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="1f2f9-153">Мы будем упорно работать с поставщиками программного обеспечения для решения любых проблем до выпуска, но в случае, если исправление невозможно, у нас есть другие разрешения, такие как прошивки и блоки.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="1f2f9-154">Разное</span><span class="sxs-lookup"><span data-stu-id="1f2f9-154">Miscellaneous</span></span>

<span data-ttu-id="1f2f9-155">**В. Как служба будет работать с сервером на предугодном сервере?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="1f2f9-156">**A:** В настоящее время мы не предоставляем поддержку на предудержке серверов.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="1f2f9-157">Однако если сервер обнажает конечную точку HTTP, мы можем подключиться к ней через Интернет.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="1f2f9-158">**Вопрос: Кто размещены VMs?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="1f2f9-159">**A:** Корпорация Майкрософт предусматривает VM для этой службы, принимая нагрузку на это от клиента.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="1f2f9-160">**В. Поддерживает ли эта служба веб-, мобильные или настольные приложения?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="1f2f9-161">**A:** В настоящее время основное внимание уделяется настольным приложениям, однако в будущем у нас есть планы для бортовых веб-приложений, но в настоящее время мы не поддерживаем мобильные приложения.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="1f2f9-162">**В. В чем разница между тестовой базой и SUVP?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="1f2f9-163">**A:** Самое большое различие между тестовой базой и SUVP состоит в том, что наши партнеры на борту своих приложений в среде Test Base Azure для проверки выполняется в отношении предварительного выпуска обновлений, а не сами тесты.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="1f2f9-164">Помимо предварительного тестирования обновлений безопасности, мы поддерживаем тестирование обновлений функций предварительного выпуска на нашей платформе.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="1f2f9-165">У нас есть много других типов обновлений и тестирования ОС на нашей дорожной карте.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="1f2f9-166">**В. Есть ли затраты, связанные со службой?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="1f2f9-167">**A:** Служба тестовой базы будет бесплатной для пользователей до тех пор, пока не будет обеспечена общая доступность (GA).</span><span class="sxs-lookup"><span data-stu-id="1f2f9-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="1f2f9-168">В это время мы объявим структуру затрат, которая будет действовать для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="1f2f9-169">**В. Как предоставить отзывы о тестовой базе?**</span><span class="sxs-lookup"><span data-stu-id="1f2f9-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="1f2f9-170">**A:** Чтобы поделиться своими отзывами о тестовой базе, выберите значок **Обратной** связи в левом нижнем конце портала.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="1f2f9-171">Включите снимок экрана с отправкой, чтобы помочь Корпорации Майкрософт лучше понять ваши отзывы.</span><span class="sxs-lookup"><span data-stu-id="1f2f9-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="1f2f9-172">Вы также можете отправлять предложения по продукту и высвеить другие идеи по <testbasepreview@microsoft.com> ссылке .</span><span class="sxs-lookup"><span data-stu-id="1f2f9-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
