---
title: Включение аналитики использования Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Узнайте, как начать сбор данных для клиента с помощью Microsoft 365 Analytics использования в Power BI.
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635418"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c0058-103">Включение аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0058-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c0058-104">Microsoft 365 аналитика использования пока недоступна для Microsoft 365 правительственных Community.</span><span class="sxs-lookup"><span data-stu-id="c0058-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="c0058-105">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c0058-105">Before you begin</span></span>

<span data-ttu-id="c0058-106">Чтобы начать работу с Microsoft 365 аналитики использования, сначала необходимо сделать данные доступными в центре администрирования Microsoft 365, а затем инициировать приложение шаблона в Power BI.</span><span class="sxs-lookup"><span data-stu-id="c0058-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
## <a name="get-power-bi"></a><span data-ttu-id="c0058-107">Получение Power BI</span><span class="sxs-lookup"><span data-stu-id="c0058-107">Get Power BI</span></span>

<span data-ttu-id="c0058-108">Если у вас еще нет Power BI, вы можете [зарегистрироваться на Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="c0058-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="c0058-109">Выберите **Попробуйте** бесплатно зарегистрироваться на пробную попытку или **купить** сейчас, чтобы получить Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="c0058-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="c0058-110">Вы также можете развернуть раздел **Продукты** и приобрести Power BI.</span><span class="sxs-lookup"><span data-stu-id="c0058-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="c0058-111">Вам нужна Power BI Pro лицензия для установки, настройки и распространения приложения-шаблона.</span><span class="sxs-lookup"><span data-stu-id="c0058-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="c0058-112">Дополнительные сведения см. в [дополнительных сведениях.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="c0058-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="c0058-113">Чтобы обмениваться данными, как вам, так и людям, с которыми вы делитесь данными, требуется лицензия Power BI Pro или контент должен быть в рабочей области в Power BI [премиум-службе.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="c0058-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
## <a name="enable-the-template-app"></a><span data-ttu-id="c0058-114">Включить приложение шаблона</span><span class="sxs-lookup"><span data-stu-id="c0058-114">Enable the template app</span></span>

<span data-ttu-id="c0058-115">Чтобы включить приложение шаблона, необходимо быть глобальным **администратором.**</span><span class="sxs-lookup"><span data-stu-id="c0058-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="c0058-116">Дополнительные [сведения см. в дополнительных](../add-users/about-admin-roles.md) сведениях о ролях администратора.</span><span class="sxs-lookup"><span data-stu-id="c0058-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="c0058-117">В центре администрирования перейдите на **вкладку Параметры** \> **параметров Org.** \> </span><span class="sxs-lookup"><span data-stu-id="c0058-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span> 
    
2. <span data-ttu-id="c0058-118">На **вкладке Services** выберите  **Отчеты**.</span><span class="sxs-lookup"><span data-stu-id="c0058-118">On the **Services** tab, select  **Reports**.</span></span>
    
3. <span data-ttu-id="c0058-119">На открываемой панели  Отчеты установите Сделать данные отчета доступными для аналитики Microsoft 365 использования для Power BI **on** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="c0058-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="c0058-120">Процесс сбора данных будет завершен через 2-48 часов в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="c0058-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="c0058-121">Кнопка **Go to Power BI** будет включена (более не серая) после завершения сбора данных.</span><span class="sxs-lookup"><span data-stu-id="c0058-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
## <a name="start-the-template-app"></a><span data-ttu-id="c0058-122">Запуск приложения шаблона</span><span class="sxs-lookup"><span data-stu-id="c0058-122">Start the template app</span></span>

<span data-ttu-id="c0058-123">Чтобы запустить приложение шаблона, необходимо быть глобальным администратором, читателем отчетов, Exchange администратором,  **Skype для бизнеса** администратором или SharePoint **администратором**.</span><span class="sxs-lookup"><span data-stu-id="c0058-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="c0058-124">Скопируйте ID клиента и выберите **Перейти к Power BI**.</span><span class="sxs-lookup"><span data-stu-id="c0058-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="c0058-125">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="c0058-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="c0058-126">Затем **выберите приложения Для** получения -> **приложений** из меню навигации.</span><span class="sxs-lookup"><span data-stu-id="c0058-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="c0058-127">На **вкладке Apps** введите Microsoft 365 в поле поиска, а затем **выберите** Microsoft 365 аналитику использования \> **Get it now**.</span><span class="sxs-lookup"><span data-stu-id="c0058-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="c0058-128">[![Выберите Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="c0058-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="c0058-129">После установки приложения.</span><span class="sxs-lookup"><span data-stu-id="c0058-129">Once the app is installed.</span></span> <span data-ttu-id="c0058-130">Выберите плитку, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="c0058-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="c0058-131">Выберите **приложение Explore,** чтобы просмотреть приложение с примерами данных.</span><span class="sxs-lookup"><span data-stu-id="c0058-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="c0058-132">Выберите **Подключение** для подключения приложения к данным организации.</span><span class="sxs-lookup"><span data-stu-id="c0058-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="c0058-133">Выберите **Подключение** на экране **Подключение** Microsoft 365 использования, затем введите в ID клиента (без тире) скопированную в шаге (1) и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c0058-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="c0058-134">На следующем экране выберите **OAuth2** в качестве метода **проверки подлинности.** \> </span><span class="sxs-lookup"><span data-stu-id="c0058-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="c0058-135">Если вы выберете любой другой метод проверки подлинности, подключение к приложению шаблона не удастся.</span><span class="sxs-lookup"><span data-stu-id="c0058-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Выберите учетную запись Майкрософт в качестве метода проверки подлинности](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="c0058-137">После мгновенного использования приложения шаблона Microsoft 365 панель аналитики использования будет доступна Power BI в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c0058-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="c0058-138">Начальная загрузка панели мониторинга займет от 2 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="c0058-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="c0058-139">Агрегаты уровня клиента будут доступны во всех отчетах после выбора.</span><span class="sxs-lookup"><span data-stu-id="c0058-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="c0058-140">Сведения на уровне пользователя станут доступны только **в 5-м** месяце следующего календарного месяца после выбора.</span><span class="sxs-lookup"><span data-stu-id="c0058-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="c0058-141">Это повлияет на все отчеты в статье User Activity (см. в статье [Перейдите](navigate-and-utilize-reports.md) и используйте отчеты в Microsoft 365 аналитике использования, чтобы получить советы по просмотру и использованию этих отчетов.</span><span class="sxs-lookup"><span data-stu-id="c0058-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="c0058-142">Как сделать собранные данные анонимными?</span><span class="sxs-lookup"><span data-stu-id="c0058-142">Make the collected data anonymous</span></span>

<span data-ttu-id="c0058-143">Данные, собираемые для отчетов, может сделать анонимными только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="c0058-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="c0058-144">Это позволит скрыть идентифицируемые сведения, такие как имена пользователей, групп и сайтов в отчетах и в приложении шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c0058-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="c0058-145">В центре администрирования перейдите в **Параметры** \> **org Параметры, а на** вкладке **Services** выберите **Отчеты**.</span><span class="sxs-lookup"><span data-stu-id="c0058-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="c0058-146">Выберите **отчеты,** а затем выберите **отображение анонимных идентификаторов.**</span><span class="sxs-lookup"><span data-stu-id="c0058-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="c0058-147">Этот параметр применяется как к отчетам об использовании, так и к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="c0058-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="c0058-148">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c0058-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="c0058-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0058-149">Related content</span></span>

<span data-ttu-id="c0058-150">[Об аналитике использования](usage-analytics.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c0058-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="c0058-151">[Получить последнюю версию аналитики использования](get-the-latest-version-of-usage-analytics.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c0058-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="c0058-152">[Навигация и использование отчетов в Microsoft 365 использования](navigate-and-utilize-reports.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="c0058-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>