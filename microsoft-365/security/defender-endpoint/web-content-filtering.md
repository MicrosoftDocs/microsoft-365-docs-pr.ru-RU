---
title: Фильтрация веб-содержимого
description: Использование фильтрации веб-контента в Microsoft Defender для конечной точки для отслеживания и регулирования доступа к веб-сайтам в зависимости от их категорий контента.
keywords: веб-защита, защита от веб-угроз, просмотр веб-сайтов, мониторинг, отчеты, карты, список доменов, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47211e187d1f9f883745f008c6d94d04ee762e98
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302068"
---
# <a name="web-content-filtering"></a><span data-ttu-id="741d6-104">Фильтрация веб-содержимого</span><span class="sxs-lookup"><span data-stu-id="741d6-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="741d6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="741d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="741d6-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="741d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="741d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="741d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="741d6-108">**Фильтрация веб-контента в настоящее время является общедоступным предварительным просмотром**</span><span class="sxs-lookup"><span data-stu-id="741d6-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="741d6-109">Эта версия предварительного просмотра предоставляется без соглашения об уровне обслуживания и не рекомендуется для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="741d6-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="741d6-110">Некоторые функции могут не поддерживаться или иметь ограниченные возможности.</span><span class="sxs-lookup"><span data-stu-id="741d6-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="741d6-111">Дополнительные сведения см. в [веб-сайте Microsoft Defender для функций предварительного просмотра конечных точек.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="741d6-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="741d6-112">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="741d6-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="741d6-113">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="741d6-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="741d6-114">Фильтрация веб-контента является частью возможностей [веб-защиты](web-protection-overview.md) в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="741d6-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="741d6-115">Это позволяет организации отслеживать и регулировать доступ к веб-сайтам в зависимости от их категорий контента.</span><span class="sxs-lookup"><span data-stu-id="741d6-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="741d6-116">Многие из этих веб-сайтов, хотя и не являются вредоносными, могут быть проблематичными из-за правил соответствия требованиям, использования пропускной способности или других проблем.</span><span class="sxs-lookup"><span data-stu-id="741d6-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="741d6-117">Настройка политик в группах устройств для блокировки определенных категорий.</span><span class="sxs-lookup"><span data-stu-id="741d6-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="741d6-118">Блокировка категории не позволяет пользователям в определенных группах устройств получать доступ к URL-адресам, связанным с этой категорией.</span><span class="sxs-lookup"><span data-stu-id="741d6-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="741d6-119">Для любой категории, которая не заблокирована, URL-адреса проверяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="741d6-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="741d6-120">Пользователи могут получать доступ к URL-адресам без сбоев, и вы соберите статистику доступа для создания более настраиваемого решения по политике.</span><span class="sxs-lookup"><span data-stu-id="741d6-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="741d6-121">Пользователи увидят блок-уведомление, если элемент на просматриваемой странице вызывает заблокированный ресурс.</span><span class="sxs-lookup"><span data-stu-id="741d6-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="741d6-122">Фильтрация веб-контента доступна в основных веб-браузерах с блоками, выполняемыми Защитник Windows SmartScreen (Microsoft Edge) и Network Protection (Chrome, Firefox, Brave и Opera).</span><span class="sxs-lookup"><span data-stu-id="741d6-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="741d6-123">Дополнительные сведения о поддержке браузера см. в разделе Предварительные условия.</span><span class="sxs-lookup"><span data-stu-id="741d6-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="741d6-124">Обобщение преимуществ:</span><span class="sxs-lookup"><span data-stu-id="741d6-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="741d6-125">Пользователям не позволяется получать доступ к веб-сайтам в заблокированных категориях, независимо от того, просматривают ли они веб-сайты на локальном сайте или в</span><span class="sxs-lookup"><span data-stu-id="741d6-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="741d6-126">Группа безопасности может удобно развертывать политики для групп пользователей с помощью групп устройств, определенных в настройках управления доступом на основе ролей [в Microsoft Defender для конечных точек.](/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="741d6-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="741d6-127">Ваша группа безопасности может получать доступ к веб-отчетам в том же центральном расположении, с видимостью над фактическими блоками и веб-использованием</span><span class="sxs-lookup"><span data-stu-id="741d6-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="741d6-128">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="741d6-128">User experience</span></span>

<span data-ttu-id="741d6-129">Возможность блокировки для браузеров, поддерживаемых третьей стороной, предоставляется сетевой защитой, которая предоставляет тост на уровне системы, уведомляющий пользователя о заблокированном подключении.</span><span class="sxs-lookup"><span data-stu-id="741d6-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="741d6-130">Для более удобной работы в браузере рассмотрите возможность использования Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="741d6-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="741d6-131">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="741d6-131">Prerequisites</span></span>

<span data-ttu-id="741d6-132">Перед тем как попробовать эту функцию, убедитесь, что у вас есть следующие требования:</span><span class="sxs-lookup"><span data-stu-id="741d6-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="741d6-133">Windows 10 Корпоративная E5, Microsoft 365 E5, Безопасность Microsoft 365 E5, Microsoft 365 E3 + Безопасность Microsoft 365 E5 надстройки или автономные лицензии Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="741d6-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="741d6-134">Доступ к Центр безопасности в Microsoft Defender порталу ( https://securitycenter.windows.com) . .</span><span class="sxs-lookup"><span data-stu-id="741d6-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="741d6-135">Устройства, Windows 10 юбилейные обновления (версия 1607) или более поздние версии с последним обновлением MoCAMP.</span><span class="sxs-lookup"><span data-stu-id="741d6-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

## <a name="data-handling"></a><span data-ttu-id="741d6-136">Обработка данных</span><span class="sxs-lookup"><span data-stu-id="741d6-136">Data handling</span></span>

<span data-ttu-id="741d6-137">Мы будем следить за тем регионом, который вы выбрали для использования в качестве части параметров обработки данных [в Microsoft Defender для конечных точек.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="741d6-137">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="741d6-138">Ваши данные не покидают центр обработки данных в этом регионе.</span><span class="sxs-lookup"><span data-stu-id="741d6-138">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="741d6-139">Кроме того, ваши данные не будут делиться с любыми сторонними сторонами, в том числе с нашими поставщиками данных.</span><span class="sxs-lookup"><span data-stu-id="741d6-139">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="741d6-140">Включив фильтрацию веб-контента</span><span class="sxs-lookup"><span data-stu-id="741d6-140">Turn on web content filtering</span></span>

<span data-ttu-id="741d6-141">В левом меню навигации выберите **Параметры**  >  **общие**  >  **расширенные функции.**</span><span class="sxs-lookup"><span data-stu-id="741d6-141">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="741d6-142">Прокрутите вниз, пока не увидите запись для **фильтрации веб-контента.**</span><span class="sxs-lookup"><span data-stu-id="741d6-142">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="741d6-143">Переключение переключателя на **параметры "Включен"** **и "Сохранение".**</span><span class="sxs-lookup"><span data-stu-id="741d6-143">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="741d6-144">Настройка политик фильтрации веб-контента</span><span class="sxs-lookup"><span data-stu-id="741d6-144">Configure web content filtering policies</span></span>

<span data-ttu-id="741d6-145">Политики фильтрации веб-контента указывают, какие категории сайтов заблокированы, на каких группах устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-145">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="741d6-146">Чтобы управлять политиками, перейдите **Параметры**  >  **правила фильтрации** веб-контента  >  .</span><span class="sxs-lookup"><span data-stu-id="741d6-146">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="741d6-147">С помощью фильтра можно найти политики, содержащие определенные заблокированные категории или применяемые к определенным группам устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-147">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="741d6-148">Создание политики</span><span class="sxs-lookup"><span data-stu-id="741d6-148">Create a policy</span></span>

<span data-ttu-id="741d6-149">Чтобы добавить новую политику:</span><span class="sxs-lookup"><span data-stu-id="741d6-149">To add a new policy:</span></span>

1. <span data-ttu-id="741d6-150">Выберите **добавить политику** на странице **фильтрации** веб-контента **в Параметры.**</span><span class="sxs-lookup"><span data-stu-id="741d6-150">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="741d6-151">Укажите имя.</span><span class="sxs-lookup"><span data-stu-id="741d6-151">Specify a name.</span></span>

3. <span data-ttu-id="741d6-152">Выберите категории для блокировки.</span><span class="sxs-lookup"><span data-stu-id="741d6-152">Select the categories to block.</span></span> <span data-ttu-id="741d6-153">Используйте значок расширения, чтобы полностью расширить каждую родительную категорию и выбрать определенные категории веб-контента.</span><span class="sxs-lookup"><span data-stu-id="741d6-153">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="741d6-154">Укажите область политики.</span><span class="sxs-lookup"><span data-stu-id="741d6-154">Specify the policy scope.</span></span> <span data-ttu-id="741d6-155">Выберите группы устройств, чтобы указать, где применять политику.</span><span class="sxs-lookup"><span data-stu-id="741d6-155">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="741d6-156">Доступ к веб-сайтам в выбранных категориях будет препятствовать только устройствам в выбранных группах устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-156">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="741d6-157">Просмотрите сводку и сохраните политику.</span><span class="sxs-lookup"><span data-stu-id="741d6-157">Review the summary and save the policy.</span></span> <span data-ttu-id="741d6-158">Обновление политики может занять до 2 часов для применения к выбранным устройствам.</span><span class="sxs-lookup"><span data-stu-id="741d6-158">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!TIP]
> <span data-ttu-id="741d6-159">Можно развернуть политику без выбора какой-либо категории в группе устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-159">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="741d6-160">Это действие создаст политику только аудита, которая поможет вам понять поведение пользователей перед созданием политики блокировки.</span><span class="sxs-lookup"><span data-stu-id="741d6-160">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="741d6-161">При одновременном удалении политики или изменении групп устройств это может привести к задержке развертывания политики.</span><span class="sxs-lookup"><span data-stu-id="741d6-161">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="741d6-162">Блокировка категории "Uncategorized" может привести к неожиданным и нежелательным результатам.</span><span class="sxs-lookup"><span data-stu-id="741d6-162">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="741d6-163">Разрешить определенные веб-сайты</span><span class="sxs-lookup"><span data-stu-id="741d6-163">Allow specific websites</span></span>

<span data-ttu-id="741d6-164">Можно переопредить заблокированную категорию в фильтрации веб-контента, чтобы разрешить один сайт, создав настраиваемую политику индикатора.</span><span class="sxs-lookup"><span data-stu-id="741d6-164">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="741d6-165">Настраиваемая политика индикатора вытемеет политику фильтрации веб-контента, если она применяется к группе устройств, о чем идет речь.</span><span class="sxs-lookup"><span data-stu-id="741d6-165">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="741d6-166">Создайте настраиваемый индикатор в Центр безопасности в Microsoft Defender, Параметры  >  **индикаторы**  >  **URL-адрес и элемент добавления**  >  **домена.**</span><span class="sxs-lookup"><span data-stu-id="741d6-166">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="741d6-167">Введите домен сайта.</span><span class="sxs-lookup"><span data-stu-id="741d6-167">Enter the domain of the site.</span></span>

3. <span data-ttu-id="741d6-168">Установите действие политики, чтобы **разрешить**.</span><span class="sxs-lookup"><span data-stu-id="741d6-168">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="741d6-169">Неточности отчетности</span><span class="sxs-lookup"><span data-stu-id="741d6-169">Reporting inaccuracies</span></span>

<span data-ttu-id="741d6-170">Если вы столкнулись с доменом, который был неправильно классифицированы, вы можете сообщить о неточности непосредственно нам со страницы отчетов о фильтрации веб-контента.</span><span class="sxs-lookup"><span data-stu-id="741d6-170">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="741d6-171">Эта функция доступна только в новом центре Microsoft 365 безопасности (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="741d6-171">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="741d6-172">Чтобы сообщить о неточности, перейдите к **доменам сведений** о фильтрации веб-контента Reports  >  **Web**  >  **Protection.**  >  </span><span class="sxs-lookup"><span data-stu-id="741d6-172">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="741d6-173">На вкладке доменов отчетов о фильтрации веб-контента вы увидите эллипсис рядом с каждым из доменов.</span><span class="sxs-lookup"><span data-stu-id="741d6-173">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="741d6-174">Наведите курсор над этим эллипсисом и выберите **отчет о неточности**.</span><span class="sxs-lookup"><span data-stu-id="741d6-174">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="741d6-175">Откроется панель, на которой можно выбрать приоритет и добавить дополнительные сведения, такие как предлагаемая категория для повторной классификации.</span><span class="sxs-lookup"><span data-stu-id="741d6-175">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="741d6-176">После завершения формы выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="741d6-176">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="741d6-177">Наша команда рассмотрит запрос в течение одного делового дня.</span><span class="sxs-lookup"><span data-stu-id="741d6-177">Our team will review the request within one business day.</span></span> <span data-ttu-id="741d6-178">Для немедленной разблокировки создайте [настраиваемый индикатор допуска.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="741d6-178">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="741d6-179">Карточки фильтрации веб-контента и сведения</span><span class="sxs-lookup"><span data-stu-id="741d6-179">Web content filtering cards and details</span></span>

<span data-ttu-id="741d6-180">Выберите **Отчеты > для** просмотра карт с информацией о фильтрации веб-контента и защите веб-угроз.</span><span class="sxs-lookup"><span data-stu-id="741d6-180">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="741d6-181">В следующих карточках приводится сводная информация о фильтрации веб-контента.</span><span class="sxs-lookup"><span data-stu-id="741d6-181">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="741d6-182">Веб-активность по категориям</span><span class="sxs-lookup"><span data-stu-id="741d6-182">Web activity by category</span></span>

<span data-ttu-id="741d6-183">На этой карте перечислены родительские категории веб-контента с наибольшим увеличением или уменьшением числа попыток доступа.</span><span class="sxs-lookup"><span data-stu-id="741d6-183">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="741d6-184">Понимание резких изменений шаблонов веб-активности в организации за последние 30 дней, 3 месяца или 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="741d6-184">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="741d6-185">Выберите имя категории, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="741d6-185">Select a category name to view more information.</span></span>

<span data-ttu-id="741d6-186">В первые 30 дней использования этой функции у организации может не хватить данных для отображения этих сведений.</span><span class="sxs-lookup"><span data-stu-id="741d6-186">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Изображение веб-активности по карте категории](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="741d6-188">Сводная карта фильтрации веб-контента</span><span class="sxs-lookup"><span data-stu-id="741d6-188">Web content filtering  summary card</span></span>

<span data-ttu-id="741d6-189">Эта карта отображает распределение попыток заблокированного доступа по различным родительским категориям веб-контента.</span><span class="sxs-lookup"><span data-stu-id="741d6-189">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="741d6-190">Выберите один из цветных баров, чтобы просмотреть дополнительные сведения о определенной родительской веб-категории.</span><span class="sxs-lookup"><span data-stu-id="741d6-190">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Изображение сводной карты фильтрации веб-контента](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="741d6-192">Сводная карта веб-действий</span><span class="sxs-lookup"><span data-stu-id="741d6-192">Web activity summary card</span></span>

<span data-ttu-id="741d6-193">Эта карта отображает общее количество запросов на веб-контент во всех URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="741d6-193">This card displays the total number of requests for web content in all URLs.</span></span>

![Изображение сводной карты веб-активности](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="741d6-195">Просмотр сведений о карточке</span><span class="sxs-lookup"><span data-stu-id="741d6-195">View card details</span></span>

<span data-ttu-id="741d6-196">Вы можете получить доступ к данным **Отчета** для каждой карты, выбрав строку таблицы или цветную планку из диаграммы на карте.</span><span class="sxs-lookup"><span data-stu-id="741d6-196">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="741d6-197">Страница отчетов для каждой карты содержит обширные статистические данные о категориях веб-контента, доменах веб-сайтов и группах устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-197">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Изображение сведений о отчете о защите веб-сайтов](images/web-protection-report-details.png)

- <span data-ttu-id="741d6-199">**Веб-категории:** Списки категорий веб-контента, у них были попытки доступа в организации.</span><span class="sxs-lookup"><span data-stu-id="741d6-199">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="741d6-200">Выберите определенную категорию, чтобы открыть сводную вылетную информацию.</span><span class="sxs-lookup"><span data-stu-id="741d6-200">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="741d6-201">**Домены**. Списки веб-доменов, которые были доступны или заблокированы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="741d6-201">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="741d6-202">Выберите определенный домен, чтобы просмотреть подробные сведения об этом домене.</span><span class="sxs-lookup"><span data-stu-id="741d6-202">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="741d6-203">**Группы устройств:** списки всех групп устройств, которые создали веб-активность в организации</span><span class="sxs-lookup"><span data-stu-id="741d6-203">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="741d6-204">Чтобы выбрать период времени, используйте фильтр диапазона времени в верхней части слева от страницы.</span><span class="sxs-lookup"><span data-stu-id="741d6-204">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="741d6-205">Вы также можете фильтровать сведения или настраивать столбцы.</span><span class="sxs-lookup"><span data-stu-id="741d6-205">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="741d6-206">Выберите строку, чтобы открыть флайер с дополнительными сведениями о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="741d6-206">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="741d6-207">Ошибки и проблемы</span><span class="sxs-lookup"><span data-stu-id="741d6-207">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="741d6-208">Ограничения и известные проблемы в этом предварительном просмотре</span><span class="sxs-lookup"><span data-stu-id="741d6-208">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="741d6-209">Поддерживается Microsoft Edge только в том случае, если конфигурация ОС вашего устройства — Server **(cmd**  >  **Systeminfo**  >  **OS Configuration).**</span><span class="sxs-lookup"><span data-stu-id="741d6-209">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="741d6-210">Защита сети поддерживается только в режиме Inspect на устройствах Server, который отвечает за безопасность трафика в поддерживаемых браузерах сторон.</span><span class="sxs-lookup"><span data-stu-id="741d6-210">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="741d6-211">Ненаверенные устройства будут иметь неправильные данные, показанные в отчете.</span><span class="sxs-lookup"><span data-stu-id="741d6-211">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="741d6-212">В **окантовке отчетов** о группах устройств может появиться строка  >   с пустым полем группы устройств.</span><span class="sxs-lookup"><span data-stu-id="741d6-212">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="741d6-213">Эта группа содержит ненаписаные устройства перед их вложением в указанную группу.</span><span class="sxs-lookup"><span data-stu-id="741d6-213">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="741d6-214">В отчете для этой строки может не содержаться точное количество устройств или количество доступа.</span><span class="sxs-lookup"><span data-stu-id="741d6-214">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="741d6-215">Отчеты по фильтрации веб-контента в настоящее время ограничены отображением 5000 записей.</span><span class="sxs-lookup"><span data-stu-id="741d6-215">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="741d6-216">Например, в отчете Домены будет показываться максимум 5000 доменов для данного запроса фильтра, если это применимо.</span><span class="sxs-lookup"><span data-stu-id="741d6-216">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="741d6-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="741d6-217">Related topics</span></span>

- [<span data-ttu-id="741d6-218">Обзор веб-защиты</span><span class="sxs-lookup"><span data-stu-id="741d6-218">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="741d6-219">Защита от веб-угроз</span><span class="sxs-lookup"><span data-stu-id="741d6-219">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="741d6-220">Мониторинг безопасности в Интернете</span><span class="sxs-lookup"><span data-stu-id="741d6-220">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="741d6-221">Реагирование на веб-угрозы</span><span class="sxs-lookup"><span data-stu-id="741d6-221">Respond to web threats</span></span>](web-protection-response.md)
