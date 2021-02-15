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
description: Узнайте, как начать сбор данных для клиента с помощью шаблона "Аналитика использования Microsoft 365" в Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114241"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="2bc43-103">Включение аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2bc43-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2bc43-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="2bc43-104">The admin center is changing.</span></span> <span data-ttu-id="2bc43-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="2bc43-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="2bc43-106">Аналитика использования Microsoft 365 пока недоступна для сообщества Microsoft 365 для государственных организаций США.</span><span class="sxs-lookup"><span data-stu-id="2bc43-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="2bc43-107">Действия, позволяющие включить аналитику использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2bc43-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="2bc43-108">Чтобы приступить к работе с аналитикой использования Microsoft 365, необходимо сначала сделать данные доступными в Центре администрирования Microsoft 365, а затем инициировать приложение шаблона в Power BI.</span><span class="sxs-lookup"><span data-stu-id="2bc43-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="2bc43-109">Получение Power BI</span><span class="sxs-lookup"><span data-stu-id="2bc43-109">Get Power BI</span></span>

<span data-ttu-id="2bc43-110">Если у вас еще нет Power BI, вы можете [зарегистрироваться в Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="2bc43-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="2bc43-111">Выберите **"Попробовать бесплатно",** чтобы зарегистрироваться для получения пробной, или **"Купить сейчас",** чтобы получить Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="2bc43-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="2bc43-112">Вы также можете развернуть раздел **Продукты** и приобрести Power BI.</span><span class="sxs-lookup"><span data-stu-id="2bc43-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bc43-113">Для установки, настройки и распространения приложения шаблона необходима лицензия Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="2bc43-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="2bc43-114">Дополнительные сведения см. в [необходимых условия.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2bc43-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="2bc43-115">Чтобы поделиться своими данными, вам и вашим людям, с которыми вы делитесь данными, нужна лицензия Power BI Pro или контент должен быть в рабочей области в службе [Power BI premium.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="2bc43-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="2bc43-116">Включить приложение шаблона</span><span class="sxs-lookup"><span data-stu-id="2bc43-116">Enable the template app</span></span>

<span data-ttu-id="2bc43-117">Чтобы включить приложение шаблона, необходимо быть глобальным **администратором.**</span><span class="sxs-lookup"><span data-stu-id="2bc43-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="2bc43-118">Дополнительные [сведения см. в](../add-users/about-admin-roles.md) сведениях о ролях администраторов.</span><span class="sxs-lookup"><span data-stu-id="2bc43-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="2bc43-119">В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="2bc43-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="2bc43-120">На странице **"Использование"** найдите карту аналитики использования **Microsoft 365** и выберите **"Начало работы".**</span><span class="sxs-lookup"><span data-stu-id="2bc43-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="2bc43-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="2bc43-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="2bc43-122">Процесс сбора данных будет завершен в течение 2-48 часов в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="2bc43-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="2bc43-123">После завершения сбора данных кнопка "Перейти к **Power BI"** будет включена (не серая).</span><span class="sxs-lookup"><span data-stu-id="2bc43-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="2bc43-124">Запуск приложения шаблона</span><span class="sxs-lookup"><span data-stu-id="2bc43-124">Start the template app</span></span>

<span data-ttu-id="2bc43-125">Чтобы запустить приложение шаблона, необходимо быть глобальным администратором, читателем отчетов, администратором **Exchange,** администратором **Skype** для бизнеса или **администратором SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="2bc43-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="2bc43-126">Скопируйте ИД клиента и выберите **"Перейти в Power BI".**</span><span class="sxs-lookup"><span data-stu-id="2bc43-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="2bc43-127">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="2bc43-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="2bc43-128">Затем **выберите приложения** -> **"Получить приложения"** из меню навигации.</span><span class="sxs-lookup"><span data-stu-id="2bc43-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="2bc43-129">На **вкладке "Приложения"** введите Microsoft 365 в поле поиска, а затем выберите "Аналитика использования **Microsoft 365"** \> **"Получить сейчас".**</span><span class="sxs-lookup"><span data-stu-id="2bc43-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="2bc43-130">[![Выберите "Получить"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="2bc43-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="2bc43-131">После установки приложения.</span><span class="sxs-lookup"><span data-stu-id="2bc43-131">Once the app is installed.</span></span> <span data-ttu-id="2bc43-132">Выберите плитку, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="2bc43-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="2bc43-133">Выберите **"Обзор" для** просмотра приложения с примерами данных.</span><span class="sxs-lookup"><span data-stu-id="2bc43-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="2bc43-134">Choose **Connect** to connect the app to your organization's data.</span><span class="sxs-lookup"><span data-stu-id="2bc43-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="2bc43-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span><span class="sxs-lookup"><span data-stu-id="2bc43-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="2bc43-136">На следующем экране выберите **OAuth2** в качестве метода **проверки** подлинности \> **для регистрации.**</span><span class="sxs-lookup"><span data-stu-id="2bc43-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="2bc43-137">При выборе другого метода проверки подлинности подключение к приложению шаблона не будет работать.</span><span class="sxs-lookup"><span data-stu-id="2bc43-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Выбор учетной записи Майкрософт в качестве метода проверки подлинности](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="2bc43-139">После того как приложение шаблона создается, информационная панель аналитики использования Microsoft 365 станет доступна в Power BI в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2bc43-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="2bc43-140">Начальная загрузка панели мониторинга займет от 2 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="2bc43-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="2bc43-141">Агрегированные данные на уровне клиента будут доступны во всех отчетах после его отказа.</span><span class="sxs-lookup"><span data-stu-id="2bc43-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="2bc43-142">Сведения на уровне пользователя станут доступны только **5-го** месяца следующего календарного месяца после его выбора.</span><span class="sxs-lookup"><span data-stu-id="2bc43-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="2bc43-143">Это повлияет на все отчеты по активности пользователей (советы по просмотру и использованию этих отчетов см. в статье "Навигация и использование отчетов в аналитике использования [Microsoft 365").](navigate-and-utilize-reports.md)</span><span class="sxs-lookup"><span data-stu-id="2bc43-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="2bc43-144">Как сделать собранные данные анонимными?</span><span class="sxs-lookup"><span data-stu-id="2bc43-144">Make the collected data anonymous</span></span>

<span data-ttu-id="2bc43-145">Данные, собираемые для отчетов, может сделать анонимными только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="2bc43-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="2bc43-146">Это позволит скрыть идентифицируемые сведения, такие как имена пользователей, групп и сайтов, в отчетах и в приложении шаблона.</span><span class="sxs-lookup"><span data-stu-id="2bc43-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="2bc43-147">В Центре администрирования перейдите на вкладку "Параметры организации" и на вкладке "Службы"  \> выберите  **"Отчеты".**</span><span class="sxs-lookup"><span data-stu-id="2bc43-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="2bc43-148">Выберите **"Отчеты",** а затем выберите отображение **анонимных идентификаторов.**</span><span class="sxs-lookup"><span data-stu-id="2bc43-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="2bc43-149">Этот параметр применяется как к отчетам об использовании, так и к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="2bc43-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="2bc43-150">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="2bc43-150">Select **Save changes**.</span></span>
