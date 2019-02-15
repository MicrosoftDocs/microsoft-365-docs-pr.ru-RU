---
title: Справочник по настраиваемым параметрам для наСтольных компьютеров, управляемых корпорацией Майкрософт
description: Настройка категорий для настраиваемых параметров на наСтольном компьютере, управляемом Майкрософт
keywords: НаСтольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051100"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="1c943-104">Справочные сведения о настраиваемых параметрах — управляемый Майкрософт Настольный компьютер</span><span class="sxs-lookup"><span data-stu-id="1c943-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="1c943-p101">В этом разделе перечислены категории параметров, которые пользователи могут настроить с помощью управляемого рабочего стола Майкрософт. Каждая категория параметров включает сведения о требованиях, рекомендациях и способах настройки категории параметров.</span><span class="sxs-lookup"><span data-stu-id="1c943-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="1c943-107">Фоновый рисунок рабочего стола</span><span class="sxs-lookup"><span data-stu-id="1c943-107">Desktop background picture</span></span>
<span data-ttu-id="1c943-p102">Вы можете настроить фоновый рисунок рабочего стола для устройств, управляемых Майкрософт, в Организации. Вы можете использовать этот параметр для применения фирменной символики компании или маркетинговой компании</span><span class="sxs-lookup"><span data-stu-id="1c943-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="1c943-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1c943-110">Requirements</span></span>

<span data-ttu-id="1c943-111">Для фонового рисунка на рабочем столе должны быть выполнены следующие требования:</span><span class="sxs-lookup"><span data-stu-id="1c943-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="1c943-112">Формат файла изображений — JPG, JPEG или PNG</span><span class="sxs-lookup"><span data-stu-id="1c943-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="1c943-113">Расположение файлов — узел в надежном расположении Secure HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="1c943-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="1c943-114">Не разрешено: HTTP и расположения файлов общего доступа (UNC) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1c943-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="1c943-115">Настройка и развертывание фонового рисунка рабочего стола</span><span class="sxs-lookup"><span data-stu-id="1c943-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="1c943-116">**Добавление пользовательского фонового рисунка рабочего стола**</span><span class="sxs-lookup"><span data-stu-id="1c943-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="1c943-117">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="1c943-118">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="1c943-119">В **настраиваемой** рабочей области выберите пункт **фоновЫй рисунок на рабочем столе**.</span><span class="sxs-lookup"><span data-stu-id="1c943-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="1c943-120">Введите путь к рисунку, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="1c943-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="1c943-121">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="1c943-122">Начальные страницы браузера</span><span class="sxs-lookup"><span data-stu-id="1c943-122">Browser start pages</span></span>
<span data-ttu-id="1c943-p103">Начальная страница браузера открывается на отдельных вкладках, когда пользователи запускают Microsoft Edge. Чтобы пользователи могли легко открыть набор часто используемых сайтов, добавьте начальную страницу браузера для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="1c943-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="1c943-125">Требования</span><span class="sxs-lookup"><span data-stu-id="1c943-125">Requirements</span></span>

<span data-ttu-id="1c943-p104">Для начальных страниц браузера необходимо указать полное доменное имя (FQDN) для веб-сайтов интрасети или Интернета. Если настроены внутренние сайты, сообщите пользователям о том, что доступ к этим сайтам разрешен только при подключении к внутренней сети в офисе или при подключении к VPN-подключению.</span><span class="sxs-lookup"><span data-stu-id="1c943-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="1c943-128">Настройка и развертывание начальных страниц браузера</span><span class="sxs-lookup"><span data-stu-id="1c943-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="1c943-129">**Добавление начальной страницы браузера**</span><span class="sxs-lookup"><span data-stu-id="1c943-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="1c943-130">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="1c943-131">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="1c943-132">В **настраиваемой** рабочей области выберите **начальные страницы браузера**.</span><span class="sxs-lookup"><span data-stu-id="1c943-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="1c943-133">Выберите **Добавить начальную страницу**.</span><span class="sxs-lookup"><span data-stu-id="1c943-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="1c943-134">На **странице "Запуск браузера**" введите URL-адрес сайта, который необходимо использовать, а затем нажмите кнопку **Добавить начальную страницу**.</span><span class="sxs-lookup"><span data-stu-id="1c943-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="1c943-135">Повторите шаги 1-5 для дополнительных начальных страниц браузера.</span><span class="sxs-lookup"><span data-stu-id="1c943-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="1c943-136">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="1c943-137">Расположение списка сайтов в режиме предприятия</span><span class="sxs-lookup"><span data-stu-id="1c943-137">Enterprise mode site list location</span></span>

<span data-ttu-id="1c943-p105">Если у вас есть определенные веб-сайты и приложения, у которых есть проблемы совместимости с Microsoft EDGE, вы можете использовать список сайтов режима предприятия, чтобы веб-сайты автоматически открывались с помощью Internet Explorer 11. Кроме того, если вы знаете, что сайты интрасети не будут правильно работать с Microsoft EDGE, вы можете настроить все сайты интрасети для автоматического открытия с помощью Internet Explorer 11. Использование режима предприятия означает, что вы можете продолжать использовать Microsoft EDGE в качестве используемого по умолчанию браузера, а также убедиться, что ваши приложения продолжают работать в Internet Explorer 11. Дополнительные сведения о списках сайтов в корпоративном режиме см. в разделе [Корпоративный режим и список сайтов в режиме](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)предприятия.</span><span class="sxs-lookup"><span data-stu-id="1c943-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="1c943-142">Можно указать расположение https://или расположение для внутреннего общего ресурса, в котором вы размещаете список сайтов в режиме предприятия.</span><span class="sxs-lookup"><span data-stu-id="1c943-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="1c943-143">Требования</span><span class="sxs-lookup"><span data-stu-id="1c943-143">Requirements</span></span>

<span data-ttu-id="1c943-144">Эти требования должны выполняться для файла списка сайтов в режиме предприятия:</span><span class="sxs-lookup"><span data-stu-id="1c943-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="1c943-145">Формат файла XML-файл, соответствующий [требованиям к файлам](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="1c943-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="1c943-146">Location файл — файл узла во внутреннем расположении HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1c943-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="1c943-147">Не разрешается размещение на внутреннем файловом ресурсе, например *//шаренаме*, запрещено</span><span class="sxs-lookup"><span data-stu-id="1c943-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="1c943-148">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1c943-148">Best practices</span></span>

<span data-ttu-id="1c943-149">Эти рекомендации помогут клиентам принимать решения, модернизация их ИТ – инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="1c943-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="1c943-p106">**Выберите ограниченное число сайтов** — управляемый корпорацией Майкрософт настольный браузер использует Microsoft EDGE в качестве предпочтительного браузера для оптимизации общей безопасности Организации и удобства использования для пользователей. Большинство сайтов в этом списке предназначены для устаревших веб-приложений, которым необходима более старая версия браузера, не включающая в себя все функции безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c943-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="1c943-p107">**Рассмотрите альтернативу** – рассмотрите другой сайт или веб-приложение, для которого не требуется более старая версия браузера. Или обновите сайт, чтобы он мог использовать новые браузеры. Новые браузеры используют новейшие технологии и помогают повысить безопасность.</span><span class="sxs-lookup"><span data-stu-id="1c943-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="1c943-155">Настройка и развертывание расположения списка в режиме корпоративного сайта</span><span class="sxs-lookup"><span data-stu-id="1c943-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="1c943-156">**Добавление расположения списка в режиме корпоративного сайта**</span><span class="sxs-lookup"><span data-stu-id="1c943-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="1c943-157">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="1c943-158">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="1c943-159">В **настраиваемой** рабочей области выберите **Расположение списка сайтов в режиме предприятия**.</span><span class="sxs-lookup"><span data-stu-id="1c943-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="1c943-160">Введите расположение HTTPS для списка сайтов.</span><span class="sxs-lookup"><span data-stu-id="1c943-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="1c943-161">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="1c943-162">Надежные сайты</span><span class="sxs-lookup"><span data-stu-id="1c943-162">Trusted sites</span></span>

<span data-ttu-id="1c943-p108">Надежные сайты позволяют настраивать зоны безопасности или сайты, которые можно использовать для разных сайтов. К зонам безопасности относятся:</span><span class="sxs-lookup"><span data-stu-id="1c943-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="1c943-165">Зона 1 — зона местной интрасети</span><span class="sxs-lookup"><span data-stu-id="1c943-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="1c943-166">Зона 2 — зона надежных сайтов</span><span class="sxs-lookup"><span data-stu-id="1c943-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="1c943-167">Зона 3 — зона Интернета</span><span class="sxs-lookup"><span data-stu-id="1c943-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="1c943-168">Зона 4 — Зона ограниченных сайтов</span><span class="sxs-lookup"><span data-stu-id="1c943-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="1c943-169">Требования</span><span class="sxs-lookup"><span data-stu-id="1c943-169">Requirements</span></span>

<span data-ttu-id="1c943-170">Укажите полное доменное имя (FQDN) для сайтов интрасети или Интернета для каждого надежного сайта.</span><span class="sxs-lookup"><span data-stu-id="1c943-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="1c943-171">Настройка и развертывание надежных сайтов</span><span class="sxs-lookup"><span data-stu-id="1c943-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="1c943-172">**Добавление надежного сайта**</span><span class="sxs-lookup"><span data-stu-id="1c943-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="1c943-173">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="1c943-174">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="1c943-175">В **настраиваемой** рабочей области выберите **Надежные сайты**, а затем нажмите **Добавить доверенный сайт**.</span><span class="sxs-lookup"><span data-stu-id="1c943-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="1c943-176">На **странице Добавление надежного сайта**введите URL-адрес, выберите зону безопасности, а затем нажмите **Добавить доверенный сайт**.</span><span class="sxs-lookup"><span data-stu-id="1c943-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="1c943-177">Повторите шаги 1-4 для каждого надежного сайта, который нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="1c943-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="1c943-178">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="1c943-179">**Удаление надежного сайта**</span><span class="sxs-lookup"><span data-stu-id="1c943-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="1c943-180">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="1c943-181">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="1c943-182">В **настраиваемой** рабочей области выберите **Надежные сайты**.</span><span class="sxs-lookup"><span data-stu-id="1c943-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="1c943-183">Выберите сайт, который нужно удалить, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1c943-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="1c943-184">Повторите шаги 1-4 для каждого надежного сайта, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="1c943-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="1c943-185">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="1c943-186">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1c943-186">Proxy</span></span>
<span data-ttu-id="1c943-p109">Для организации можно управлять параметрами прокси-сервера сети. Добавьте прокси-сервер и номер порта, а затем добавьте исключения прокси-сайта. Рабочий стол, управляемый Майкрософт, включает набор исключений прокси-серверов по умолчанию, необходимых для работы службы. Список исключений по умолчанию может быть изменен только службой "управляемые наСтольные компьютеры Майкрософт".  Дополнительные сведения можно найти в разделе [Настройка сети для управляемОго рабочего стола Майкрософт](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="1c943-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="1c943-192">Исключения прокси-сайта, которые вы добавляете на портале для наСтольных компьютеров Майкрософт, добавляются к исключениям прокси-сервера по умолчанию, включенным в службу управляемых компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1c943-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="1c943-p110">Обновление списка исключений прокси-сервера по умолчанию всегда назначается по приоритету при развертывании клиентов. Это означает, что поэтапное развертывание будет приостановлено при наличии развертывания для списка исключений прокси-сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c943-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="1c943-195">Требования</span><span class="sxs-lookup"><span data-stu-id="1c943-195">Requirements</span></span>

<span data-ttu-id="1c943-196">Эти требования должны выполняться для исключений прокси-сервера и прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1c943-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="1c943-197">Должен быть допустимым адресом сервера и номером порта</span><span class="sxs-lookup"><span data-stu-id="1c943-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="1c943-198">URL-адреса должны быть допустимым сайтом http</span><span class="sxs-lookup"><span data-stu-id="1c943-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="1c943-199">Настройка и развертывание прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="1c943-199">Customize and deploy proxies</span></span>

<span data-ttu-id="1c943-200">**Добавление исключения для отдельного прокси-сайта**</span><span class="sxs-lookup"><span data-stu-id="1c943-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="1c943-201">Вход на [портал администрирования рабочих столов с управляемЫми Майкрософт](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="1c943-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="1c943-202">В разделе **Параметры**выберите пункт **Настраиваемая**.</span><span class="sxs-lookup"><span data-stu-id="1c943-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="1c943-203">В **настраиваемой** рабочей области выберите **прокси-сервер**.</span><span class="sxs-lookup"><span data-stu-id="1c943-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="1c943-204">Введите **адрес** и **номер порта** для прокси-сервера, а затем выберите **Добавить исключение прокси-** сервера.</span><span class="sxs-lookup"><span data-stu-id="1c943-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="1c943-205">Введите URL-адрес действительного сайта http, а затем выберите **Добавить исключение прокси-сервера**.</span><span class="sxs-lookup"><span data-stu-id="1c943-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="1c943-206">Повторите шаги 1-5 для каждого надежного сайта, который нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="1c943-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="1c943-207">Выберите **развертывание стадии** , чтобы сохранить изменения и развернуть их в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="1c943-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c943-208">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1c943-208">Additional resources</span></span>
- [<span data-ttu-id="1c943-209">Общие сведения о настраиваемых параметрах</span><span class="sxs-lookup"><span data-stu-id="1c943-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="1c943-210">Развертывание настраиваемых параметров</span><span class="sxs-lookup"><span data-stu-id="1c943-210">Deploy configurable settings</span></span>](config-setting-deploy.md)