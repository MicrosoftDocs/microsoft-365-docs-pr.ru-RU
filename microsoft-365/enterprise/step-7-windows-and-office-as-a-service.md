---
title: Этап 7. Windows и Office как услуга
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
description: Узнайте, как подготовиться к использованию модели "Windows и Office как услуга" в вашей среде.
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870833"
---
# <a name="step-7-windows-and-office-as-a-service"></a><span data-ttu-id="e41b9-103">Этап 7. Windows и Office как услуга</span><span class="sxs-lookup"><span data-stu-id="e41b9-103">Step 7: Windows and Office as a Service</span></span>

<span data-ttu-id="e41b9-104">Подготовьтесь к обновлениям Semi-Annual Channel с новыми компонентами и возможностями в Windows 10 и Office 365 профессиональный плюс, а также соответствующими обновлениями средств управления в System Center Configuration Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="e41b9-104">Prepare for semi-annual channel updates with new features and capabilities in Windows 10 and Office 365 ProPlus along with corresponding updates to management tools with System Center Configuration Manager Current Branch.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="e41b9-105"><strong>Этап 7. Подготовка к модели "Windows и Office как услуга"</strong></span><span class="sxs-lookup"><span data-stu-id="e41b9-105"><strong>Step 7: Preparing for Windows and Office as a Service</strong></span></span></p>
<p><span data-ttu-id="e41b9-p101">В Windows 10 и Office 365 профессиональный плюс постоянно добавляются новые функции, чтобы развивать пользовательский интерфейс и средства безопасности в соответствии с новейшими инновациями. Узнайте, как обеспечивать актуальность с помощью полугодичных и ежемесячных обновлений, как работают новые модели обслуживания и какие у вас есть инструменты и возможности.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p101">Both Windows 10 and Office 365 ProPlus continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="e41b9-p102">Модель "Windows и Office как услуга" указана в описании седьмого этапа из рекомендуемой серии статей о процессе развертывания, который охватывает аспекты планирования полугодичных обновлений компонентов. Чтобы просмотреть полный процесс развертывания на компьютере, посетите [центр развертывания на современных компьютерах](https://aka.ms/HowToShift).</span><span class="sxs-lookup"><span data-stu-id="e41b9-p102">Windows and Office as a Service is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="e41b9-p103">Как в Windows 10, так и в Office 365 профессиональный плюс представлены новые варианты обслуживания, модели поддержки и расписания обновления. Эти изменения помогают своевременно устанавливать новые функции. Вместе с этими обновлениями предоставляются новые параметры конфигурации, позволяющие использовать подходящие вам планы обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p103">Both Windows 10 and Office 365 ProPlus introduce new servicing options, support models and update timelines. These changes simplify the process for staying current on the latest features. Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span>

[<span data-ttu-id="e41b9-113">Содействие переходу пользователей на современные компьютеры</span><span class="sxs-lookup"><span data-stu-id="e41b9-113">Helping customers shift to a modern desktop</span></span>](https://www.microsoft.com/ru-RU/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a><span data-ttu-id="e41b9-114">Типы обновлений</span><span class="sxs-lookup"><span data-stu-id="e41b9-114">Update Types</span></span>

<span data-ttu-id="e41b9-p104">Обновления делятся на две основные категории: обновления компонентов и исправления с обновлениями для системы безопасности, содержащие накопительные пакеты исправлений ошибок, а также улучшений безопасности и надежности. Что касается частоты, для Windows и Office доступен канал Semi-Annual Channel, доставляющий новые функции дважды в год (в марте и сентябре), в то время как исправления и обновления для системы безопасности выпускаются ежемесячно. Кроме того, исключительно для приложений Office 365 мы предоставляем обновления на канале Monthly Channel, которые полностью поддерживаются и содержат как новые функции, так и исправления.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p104">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes. In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while Quality and Security Updates occur Monthly. Additionally, unique to Office 365 Apps, we deliver Monthly Channel updates that are fully-supported and contain both new features and quality updates.</span></span>

<span data-ttu-id="e41b9-118">Если вы привыкли более продолжительному циклу обновления ОС и приложений, вы можете спросить:</span><span class="sxs-lookup"><span data-stu-id="e41b9-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="e41b9-119">Будут ли обновления совместимыми?</span><span class="sxs-lookup"><span data-stu-id="e41b9-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="e41b9-120">Потребуется ли постоянная переподготовка пользователей?</span><span class="sxs-lookup"><span data-stu-id="e41b9-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="e41b9-121">Каковы риски?</span><span class="sxs-lookup"><span data-stu-id="e41b9-121">And what are the risks?</span></span>

<span data-ttu-id="e41b9-122">Чтобы ответить на эти вопросы и объяснить преимущества более частой доставки новых возможностей, мы рассмотрим некоторые особенности этого подхода.</span><span class="sxs-lookup"><span data-stu-id="e41b9-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="e41b9-123">Преимущества обновлений компонентов</span><span class="sxs-lookup"><span data-stu-id="e41b9-123">Feature Update Benefits</span></span>

<span data-ttu-id="e41b9-p105">Во-первых, мы отказались от старой модели, которая создавала огромные волны перемен примерно каждые три года, в пользу небольших добавочных изменений с выпуском обновлений компонентов дважды в год. Почему? Технологии, как и угрозы безопасности, стремительно развиваются, поэтому возможности и защиту требуется поддерживать в актуальном состоянии. Например, некоторые обновления, связанные с безопасностью, невозможно просто доставлять в ежемесячных обновлениях для системы безопасности или файлах сигнатур антивируса. Это могут быть низкоуровневые изменения платформы, например защиты на основе виртуализации.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p105">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

[<span data-ttu-id="e41b9-128">Краткое руководство по модели "Windows как услуга"</span><span class="sxs-lookup"><span data-stu-id="e41b9-128">Quick guide to Windows as a service</span></span>](https://docs.microsoft.com/ru-RU/windows/deployment/update/waas-quick-start)

[<span data-ttu-id="e41b9-129">Устранение угроз с помощью функций безопасности Windows 10</span><span class="sxs-lookup"><span data-stu-id="e41b9-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/ru-RU/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="e41b9-130">Преимущества модели накопительных пакетов обновления</span><span class="sxs-lookup"><span data-stu-id="e41b9-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="e41b9-p106">Доставка исправлений и обновлений для системы безопасности в виде накопительного пакета обновления исправляет множество возникавших ранее проблем. Раньше каждый месяц приходилось выбирать нужные компоненты из десятков доступных обновлений для Windows и Office. Как вы можете представить, это делает поддержку тестовых матриц практически невозможной. Кроме того, если установить версию Windows или Office, вышедшую более года назад, то применение всех обновлений, выпущенных с момента выхода этой версии, может занять часы или даже дни.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p106">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="e41b9-p107">С накопительной моделью от актуальной версии вас всегда отделяет лишь одно обновление, поэтому необходимое количество ежемесячных обновлений снижается. Каждое обновление дополняет выпуски за предыдущие месяцы и содержит все исправления, необходимые для обеспечения актуальности. Накопительные пакеты обновления особенно полезны для тех компьютеров, которые были отключены в течение нескольких месяцев, так как находились на складе, ожидая переназначения другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p107">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

[<span data-ttu-id="e41b9-138">Обзор модели "Windows как услуга"</span><span class="sxs-lookup"><span data-stu-id="e41b9-138">Overivew of Windows as a service</span></span>](https://docs.microsoft.com/ru-RU/windows/deployment/update/waas-overview)

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="e41b9-139">Расширенная проверка обновлений</span><span class="sxs-lookup"><span data-stu-id="e41b9-139">Expanded Validation of Updates</span></span>

<span data-ttu-id="e41b9-p108">Еще одно преимущество заключается в том, что перед широким развертыванием обновлений мы сначала выпускаем сборки через программы предварительной оценки [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) и [Windows](https://insider.windows.com/ru-RU/), что позволяет нам собирать данные телеметрии и отзывы до выпуска общедоступной версии. В настоящее время программы предварительной оценки открыты для всех, поэтому вы можете заранее осваивать новые обновления. К моменту выпуска мы собираем данные телеметрии с миллионов конфигураций, поэтому можем быть уверены в качестве общедоступных обновлений.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p108">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/ru-RU/), and this allows us to gather telemetry and feedback ahead of us releasing updates broadly. Now the Insider programs are open to everyone so that you can get ahead of understanding the updates. By the time we release updates we will have received telemetry from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="e41b9-143">И еще: сборки для участников программы предварительной оценки Office 365 профессиональный плюс основаны на обновлениях Monthly Channel, поэтому если вы используете Semi-Annual Channel для Office, чтобы доставлять обновления компонентов дважды в год, как и для Windows, то вы можете проверять эти сборки заранее, а также использовать выпуски для Semi-Annual Channel.</span><span class="sxs-lookup"><span data-stu-id="e41b9-143">AND one more thing, because Office 365 ProPlus Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the semi-annual channel targeted releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="e41b9-144">Вспомогательные средства управления</span><span class="sxs-lookup"><span data-stu-id="e41b9-144">Supporting Management Tools</span></span>

<span data-ttu-id="e41b9-p109">Мы также продумали удобное развертывание обновлений. System Center Configuration Manager (Current Branch) часто обновляется для поддержки новых возможностей и развертывания этих обновлений в Windows и Office.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p109">We've also thought through how to make the deployment of updates seamless to you. System Center Configuration Manager Current Branch is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

[<span data-ttu-id="e41b9-147">Развертывание обновлений Windows 10 с помощью System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e41b9-147">Deploy Windows 10 updates using System Center Configuration Manager</span></span>](https://docs.microsoft.com/ru-RU/windows/deployment/update/waas-manage-updates-configuration-manager)

[<span data-ttu-id="e41b9-148">Управление Office 365 профессиональный плюс с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e41b9-148">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/ru-RU/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="e41b9-149">Поэтапное развертывание обновлений</span><span class="sxs-lookup"><span data-stu-id="e41b9-149">Phased Deployment of Updates</span></span>

<span data-ttu-id="e41b9-p110">Теперь переключим внимание на то, как вы будете развертывать эти обновления. Для любого выпуска рекомендуем выполнять развертывание как минимум в три этапа: проверку, пилотное тестирование и широкое развертывание в рабочей среде. Когда Windows 10 и Office 365 профессиональный плюс будут готовы к работе, вы будете использовать ежемесячное обслуживание, чтобы поддерживать их актуальность с помощью обновлений для системы безопасности и исправлений, а новые функции будут добавляться в рамках полугодичного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p110">Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Office 365 ProPlus, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="e41b9-153">Ежемесячное обновление</span><span class="sxs-lookup"><span data-stu-id="e41b9-153">Monthly Updating</span></span>

<span data-ttu-id="e41b9-p111">Эта модель обслуживания устроена так, чтобы вы могли сократить частоту развертывания новых функций до двух раз в год, а при необходимости даже пропускать полугодичные обновления и продолжать получать исправления и обновления для системы безопасности. Как уже упоминалось, накопительный характер ежемесячных обновлений означает, что их размер будет увеличиваться каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p111">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="e41b9-156">Экспресс-обновления</span><span class="sxs-lookup"><span data-stu-id="e41b9-156">Express Updates</span></span>

<span data-ttu-id="e41b9-p112">С помощью технологии "экспресс-обновлений" в Windows и двоичного разностного сжатия в Office мы можем значительно уменьшать размер скачиваемых файлов. В обоих случаях системы обновления проверяют версию, установленную на компьютере, и находят отличия, которые требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p112">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="e41b9-159">Описание исправлений Windows 10 и сведения об окончании выпуска разностных обновлений</span><span class="sxs-lookup"><span data-stu-id="e41b9-159">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="e41b9-160">Центр обновления Windows для бизнеса и Windows Server Update Services уже давно поддерживают экспресс-обновления, но теперь мы добавили их поддержку в System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e41b9-160">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to System Center Configuration Manager so that it can also use Express Updates.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="e41b9-161">Двоичное разностное сжатие</span><span class="sxs-lookup"><span data-stu-id="e41b9-161">Binary Delta Compression</span></span>

<span data-ttu-id="e41b9-162">Двоичное разностное сжатие в Office используется, только если вы обновляете последнюю версию Office 365 профессиональный плюс, поэтому для его использования необходимо выполнять обновление с предыдущей сборки и не пропускать обновления.</span><span class="sxs-lookup"><span data-stu-id="e41b9-162">Binary Delta Compression in Office is only used if you're updating from the most recent version of Office 365 ProPlus-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="e41b9-p113">Каналами обновления Windows и Office можно управлять с помощью диспетчера конфигураций, используя стандартный процесс утверждения и таргетинга. Кроме того, вы можете использовать параметры политики в Office и Windows, чтобы принудительно применять определенные каналы обновления, а также связанные с ними параметры.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p113">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="e41b9-165">Полугодичные обновления</span><span class="sxs-lookup"><span data-stu-id="e41b9-165">Semi-Annual Updates</span></span>

<span data-ttu-id="e41b9-166">Итак, мы рассмотрели ежемесячные обновления. Теперь перейдем к более масштабным полугодичным обновлениям.</span><span class="sxs-lookup"><span data-stu-id="e41b9-166">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="e41b9-167">Как упоминалось в статье "Готовность устройств и приложений", подготовку к этим крупным обновлениям следует начать с помощью тех же средств обеспечения готовности, которые мы настроили на 1-м этапе развертывания.</span><span class="sxs-lookup"><span data-stu-id="e41b9-167">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="e41b9-p114">Что касается инструментария, вы можете использовать параметры политики в центре обновления Windows для бизнеса, средства управления обновлениями ПО в System Center Configuration Manager, Windows Server Update Services (WSUS) или политики обновления, заданные в Microsoft Intune. Если вас беспокоит пропускная способность сети, см. статью "Этап 2. Готовность каталогов и сети", чтобы узнать, как вы можете уменьшить сетевой трафик с помощью оптимизации доставки и других технологий однорангового кэширования.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p114">As for tooling, you can use policy settings with Windows Update for Business, software update management via System Center Configuration Manager, Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="e41b9-170">Windows Semi-Annual Channel</span><span class="sxs-lookup"><span data-stu-id="e41b9-170">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/ru-RU/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="e41b9-171">Semi-Annual Channel для Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="e41b9-171">Semi-Annual Channel for Office 365 ProPlus</span></span>](https://docs.microsoft.com/ru-RU/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="e41b9-172">Последовательности задач обновления</span><span class="sxs-lookup"><span data-stu-id="e41b9-172">Upgrade Task Sequences</span></span>

<span data-ttu-id="e41b9-173">Установка крупных обновлений компонентов с помощью стандартных методик управления обновлениями ПО поддерживается, но многие организации выбирают последовательность задач обновления в System Center Configuration Manager или Microsoft Deployment Toolkit.</span><span class="sxs-lookup"><span data-stu-id="e41b9-173">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with System Center Configuration Manager or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="e41b9-174">Последовательность задач позволяет создавать собственные проверки или задачи ДО установки обновления компонентов, а также выполнять пользовательские задачи ПОСЛЕ установки самого обновления. Задачи после обновления могут включать временную остановку служб, если это требуется во время обновления, установку и замену драйверов, обновления приложений, а также параметры персонализации панели задач или меню "Пуск" в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e41b9-174">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="e41b9-p115">Если вы уже используете последовательности задач для переноса компьютеров с Windows 7 на Windows 10 и хорошо владеете этими инструментами, то это отличная отправная точка, предоставляющая полный контроль. Вы можете использовать одну последовательность задач для всего обновления, но во многих организациях используется две последовательности. Одна гарантирует, что компьютеры готовы к обновлению, незаметно подготавливая все необходимые установочные файлы на целевых компьютерах, а другая выполняет само обновление. Этот подход обеспечивает меньшее воздействие на продуктивность пользователей.</span><span class="sxs-lookup"><span data-stu-id="e41b9-p115">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.</span></span>

[<span data-ttu-id="e41b9-179">Создание последовательности задач для обновления операционной системы в Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e41b9-179">Create a task sequence to upgrade an OS in Configuration Manager</span></span>](https://docs.microsoft.com/ru-RU/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="e41b9-180">Поддержка обновлений компонентов в полугодовом канале</span><span class="sxs-lookup"><span data-stu-id="e41b9-180">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="e41b9-181">[Как было объявлено в сентябре 2018 г.](https://www.microsoft.com/ru-RU/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), сроки поддержки обновлений Semi-Annual Channel будут основаны на описанной ниже модели.</span><span class="sxs-lookup"><span data-stu-id="e41b9-181">[As announced in September 2018](https://www.microsoft.com/ru-RU/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="e41b9-182">Все поддерживаемые в данный момент обновления компонентов Windows 10 Корпоративная и Windows 10 для образовательных учреждений, начиная с версии 1607, будут поддерживаться в течение 30 месяцев со дня их первоначального выпуска.</span><span class="sxs-lookup"><span data-stu-id="e41b9-182">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="e41b9-183">Все последующие обновления компонентов, начиная с версии 1809, выпущенные в сентябре, будут поддерживаться в течение 30 месяцев со дня их выпуска.</span><span class="sxs-lookup"><span data-stu-id="e41b9-183">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="e41b9-184">Будущие обновления компонентов, выпущенные в марте, начиная с версии 1903, будут поддерживаться в течение 18 месяцев со дня их выпуска.</span><span class="sxs-lookup"><span data-stu-id="e41b9-184">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="e41b9-185">Полугодичные обновления Office 365 профессиональный плюс продолжат поддерживаться в течение 18 месяцев.</span><span class="sxs-lookup"><span data-stu-id="e41b9-185">Office 365 ProPlus semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="e41b9-186">Дополнительные варианты автоматизации установки помимо последовательностей задач</span><span class="sxs-lookup"><span data-stu-id="e41b9-186">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="e41b9-187">Если вы не используете последовательности задач обновления, то теперь вы можете выполнять дополнительные действия или применять файлы драйверов во время обновления компонентов до установки (до того, как программа установки выполнит проверки совместимости) или до фиксации (применения обновления).</span><span class="sxs-lookup"><span data-stu-id="e41b9-187">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="e41b9-188">Что нового в программе установки Windows 10 версии 1803</span><span class="sxs-lookup"><span data-stu-id="e41b9-188">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/ru-RU/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="e41b9-189">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e41b9-189">Next Step</span></span> 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[<span data-ttu-id="e41b9-190">Этап 8. Информирование и обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="e41b9-190">Step 8: User Communications and Training</span></span>](https://aka.ms/mdd8)

## <a name="previous-step"></a><span data-ttu-id="e41b9-191">Предыдущий этап</span><span class="sxs-lookup"><span data-stu-id="e41b9-191">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[<span data-ttu-id="e41b9-192">Этап 6. Развертывание ОС и обновление компонентов</span><span class="sxs-lookup"><span data-stu-id="e41b9-192">Step 6 OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)