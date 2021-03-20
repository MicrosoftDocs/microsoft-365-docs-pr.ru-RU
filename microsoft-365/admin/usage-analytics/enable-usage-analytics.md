---
title: Включение аналитики использования Microsoft 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Узнайте, как начать сбор данных для клиента с помощью приложения шаблона Microsoft 365 Use Analytics в Power BI.
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913878"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b0400-103">Включение аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0400-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b0400-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="b0400-104">The admin center is changing.</span></span> <span data-ttu-id="b0400-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b0400-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b0400-106">Аналитика использования Microsoft 365 пока недоступна для сообщества microsoft 365 для правительства США.</span><span class="sxs-lookup"><span data-stu-id="b0400-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b0400-107">Действия, позволяющие аналитике использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0400-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b0400-108">Чтобы начать работу с аналитикой использования Microsoft 365, необходимо сначала сделать данные доступными в центре администрирования Microsoft 365, а затем инициировать приложение шаблона в Power BI.</span><span class="sxs-lookup"><span data-stu-id="b0400-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="b0400-109">Получение Power BI</span><span class="sxs-lookup"><span data-stu-id="b0400-109">Get Power BI</span></span>

<span data-ttu-id="b0400-110">Если у вас еще нет Power BI, вы можете [зарегистрироваться на Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="b0400-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="b0400-111">Выберите **Попробуйте** бесплатно зарегистрироваться на пробную попытку или **купить сейчас,** чтобы получить Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="b0400-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="b0400-112">Вы также можете развернуть раздел **Продукты** и приобрести Power BI.</span><span class="sxs-lookup"><span data-stu-id="b0400-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="b0400-113">Для установки, настройки и распространения приложения-шаблона нужна лицензия Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="b0400-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="b0400-114">Дополнительные сведения см. в [дополнительных сведениях.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="b0400-114">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="b0400-115">Чтобы обмениваться данными, вам и людям, с которыми вы делитесь данными, нужна лицензия Power BI Pro или содержимое должно быть в рабочем пространстве в премиум-службе [Power BI.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="b0400-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="b0400-116">Включить приложение шаблона</span><span class="sxs-lookup"><span data-stu-id="b0400-116">Enable the template app</span></span>

<span data-ttu-id="b0400-117">Чтобы включить приложение шаблона, необходимо быть глобальным **администратором.**</span><span class="sxs-lookup"><span data-stu-id="b0400-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="b0400-118">Дополнительные [сведения см. в дополнительных](../add-users/about-admin-roles.md) сведениях о ролях администратора.</span><span class="sxs-lookup"><span data-stu-id="b0400-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="b0400-119">В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="b0400-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="b0400-120">На странице **Использование** найдите карточку аналитики использования **Microsoft 365** и выберите **Начало работы.**</span><span class="sxs-lookup"><span data-stu-id="b0400-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="b0400-121">На открываемой панели Отчеты установите Make **data available to Microsoft 365 use analytics for Power BI** to **On** \> **Save.**</span><span class="sxs-lookup"><span data-stu-id="b0400-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="b0400-122">Процесс сбора данных будет завершен через 2-48 часов в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="b0400-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="b0400-123">После завершения сбора данных будет включена кнопка **Go to Power BI** (более не серая).</span><span class="sxs-lookup"><span data-stu-id="b0400-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="b0400-124">Запуск приложения шаблона</span><span class="sxs-lookup"><span data-stu-id="b0400-124">Start the template app</span></span>

<span data-ttu-id="b0400-125">Чтобы запустить приложение шаблона, необходимо быть глобальным администратором, читателем отчетов, администратором **Exchange,** администратором Skype **для** бизнеса или **администратором SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="b0400-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="b0400-126">Скопируйте ID клиента и выберите **Перейти к Power BI**.</span><span class="sxs-lookup"><span data-stu-id="b0400-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="b0400-127">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="b0400-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="b0400-128">Затем **выберите приложения Для** получения -> **приложений** из меню навигации.</span><span class="sxs-lookup"><span data-stu-id="b0400-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="b0400-129">На **вкладке Apps** введите Microsoft 365 в поле поиска и выберите аналитику использования **Microsoft 365** \> **Get it now.**</span><span class="sxs-lookup"><span data-stu-id="b0400-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="b0400-130">[![Выберите Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="b0400-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="b0400-131">После установки приложения.</span><span class="sxs-lookup"><span data-stu-id="b0400-131">Once the app is installed.</span></span> <span data-ttu-id="b0400-132">Выберите плитку, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="b0400-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="b0400-133">Выберите **приложение Explore,** чтобы просмотреть приложение с примерами данных.</span><span class="sxs-lookup"><span data-stu-id="b0400-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="b0400-134">Выберите **Подключение,** чтобы подключить приложение к данным организации.</span><span class="sxs-lookup"><span data-stu-id="b0400-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="b0400-135">Выберите **Подключение**, на экране аналитики использования Подключения к **Microsoft 365,** а затем введите в ID клиента (без тире), который вы скопировали в шаге (1), и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b0400-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="b0400-136">На следующем экране выберите **OAuth2** в качестве метода **проверки подлинности.** \> </span><span class="sxs-lookup"><span data-stu-id="b0400-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="b0400-137">Если вы выберете любой другой метод проверки подлинности, подключение к приложению шаблона не удастся.</span><span class="sxs-lookup"><span data-stu-id="b0400-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Выберите учетную запись Майкрософт в качестве метода проверки подлинности](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="b0400-139">После мгновенного использования приложения шаблона панель аналитики использования Microsoft 365 будет доступна в Power BI в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b0400-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="b0400-140">Начальная загрузка панели мониторинга займет от 2 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="b0400-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="b0400-141">Агрегаты уровня клиента будут доступны во всех отчетах после выбора.</span><span class="sxs-lookup"><span data-stu-id="b0400-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="b0400-142">Сведения на уровне пользователя станут доступны только **в 5-м** месяце следующего календарного месяца после выбора.</span><span class="sxs-lookup"><span data-stu-id="b0400-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="b0400-143">Это повлияет на все отчеты в статье User Activity (См. в статье Перейдите и используйте отчеты в аналитике использования [Microsoft 365,](navigate-and-utilize-reports.md) чтобы получить советы по просмотру и использованию этих отчетов).</span><span class="sxs-lookup"><span data-stu-id="b0400-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="b0400-144">Как сделать собранные данные анонимными?</span><span class="sxs-lookup"><span data-stu-id="b0400-144">Make the collected data anonymous</span></span>

<span data-ttu-id="b0400-145">Данные, собираемые для отчетов, может сделать анонимными только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="b0400-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="b0400-146">Это позволит скрыть идентифицируемые сведения, такие как имена пользователей, групп и сайтов в отчетах и в приложении шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b0400-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="b0400-147">В центре администрирования перейдите на **параметры параметров** организации, а на \> вкладке **Services** выберите **Отчеты**.</span><span class="sxs-lookup"><span data-stu-id="b0400-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="b0400-148">Выберите **отчеты,** а затем выберите **отображение анонимных идентификаторов.**</span><span class="sxs-lookup"><span data-stu-id="b0400-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="b0400-149">Этот параметр применяется как к отчетам об использовании, так и к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="b0400-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="b0400-150">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="b0400-150">Select **Save changes**.</span></span>