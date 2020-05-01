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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Узнайте, как начать сбор данных для клиента с помощью приложения шаблона аналитики использования Microsoft 365 в Power BI.
ms.openlocfilehash: 249fadce15ca2e4c979d6e1930ff0d14ccd9bc08
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355010"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="3daa6-103">Включение аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3daa6-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="3daa6-104">Служба анализа сведений об использовании Microsoft 365 также доступна для сообщества 365 Майкрософт для государственных учреждений США.</span><span class="sxs-lookup"><span data-stu-id="3daa6-104">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="3daa6-105">Действия по включению анализа сведений об использовании Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3daa6-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="3daa6-106">Чтобы приступить к анализу использования Microsoft 365, сначала необходимо сделать данные доступными в центре администрирования Microsoft 365, а затем запустить его в Power BI.</span><span class="sxs-lookup"><span data-stu-id="3daa6-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="3daa6-107">Получение Power BI</span><span class="sxs-lookup"><span data-stu-id="3daa6-107">Get Power BI</span></span>

<span data-ttu-id="3daa6-108">Если у вас еще нет Power BI, вы можете [зарегистрироваться в Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="3daa6-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="3daa6-109">Выберите вариант **попробовать бесплатно** , чтобы получить пробную версию, или **купите сейчас** , чтобы получить Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="3daa6-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="3daa6-110">Вы также можете развернуть раздел **Продукты** и приобрести Power BI.</span><span class="sxs-lookup"><span data-stu-id="3daa6-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="3daa6-111">Для установки, настройки и распространения приложения-шаблона необходима лицензия Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="3daa6-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="3daa6-112">Дополнительные сведения можно найти в разделе [Предварительные требования](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3daa6-112">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="3daa6-113">Для предоставления общего доступа к контенту требуется лицензия Power BI Pro, а для пользователей, которым вы хотите предоставить общий доступ, или контент должен находиться в рабочей области с [расширенными возможностями](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="3daa6-113">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="3daa6-114">Включение приложения шаблона</span><span class="sxs-lookup"><span data-stu-id="3daa6-114">Enable the template app</span></span>

<span data-ttu-id="3daa6-115">Чтобы включить приложение-шаблон, необходимо быть **глобальным администратором**, **средством чтения отчетов**, **администратором Exchange**, **администратором Skype для бизнеса**или **администратором SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-115">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="3daa6-116">Более подробную информацию можно узнать в статье [сведения о ролях администратора](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="3daa6-116">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="3daa6-117">В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы.</span><span class="sxs-lookup"><span data-stu-id="3daa6-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="3daa6-118">На странице " **Использование** " выберите карточку **службы аналитики использования Microsoft 365** и нажмите кнопку **начать работу**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="3daa6-119">В открывшейся панели Отчеты **установите для** \> параметра **доступ к данным службы Microsoft 365 об использовании службы Power BI доступ** к **сохраненным**данным.</span><span class="sxs-lookup"><span data-stu-id="3daa6-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="3daa6-120">Это инициирует процесс сбора данных и будет выполняться в течение 2 – 48 часов в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="3daa6-120">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="3daa6-121">При завершении сбора данных кнопка " **Перейти к Power BI** " будет включена (перестает быть серым).</span><span class="sxs-lookup"><span data-stu-id="3daa6-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="3daa6-122">Запуск шаблона приложения</span><span class="sxs-lookup"><span data-stu-id="3daa6-122">Initiate the template app</span></span>

<span data-ttu-id="3daa6-123">Для запуска приложения-шаблона необходимо быть **глобальным администратором**, **средством чтения отчетов**, **администратором Exchange**, **администратором Skype для бизнеса**или **администратором SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-123">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="3daa6-124">Скопируйте идентификатор клиента и выберите пункт **Перейти в Power BI**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-124">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="3daa6-125">When you get to Power BI, sign in.</span><span class="sxs-lookup"><span data-stu-id="3daa6-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="3daa6-126">В меню навигации выберите пункт приложения >получить приложения.</span><span class="sxs-lookup"><span data-stu-id="3daa6-126">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="3daa6-127">На вкладке **приложения** введите Microsoft 365 в поле поиска, а затем выберите **Microsoft 365 использование аналитики** \> для **получения**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="3daa6-128">[![Нажмите кнопку получить сейчас](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="3daa6-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="3daa6-129">После установки приложения.</span><span class="sxs-lookup"><span data-stu-id="3daa6-129">Once the app is installed.</span></span> <span data-ttu-id="3daa6-130">Щелкните плитку, чтобы открыть ее.</span><span class="sxs-lookup"><span data-stu-id="3daa6-130">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="3daa6-131">Нажмите кнопку **Просмотреть приложение** , чтобы просмотреть приложение с примерами данных.</span><span class="sxs-lookup"><span data-stu-id="3daa6-131">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="3daa6-132">Нажмите кнопку **Подключиться** , чтобы подключить приложение к данным вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3daa6-132">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="3daa6-133">После нажатия кнопки **подключить**на экране **Подключение к службе анализа сведений об использовании Microsoft 365** введите идентификатор клиента, скопированный на шаге (1 \> ) **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-133">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="3daa6-134">На следующем экране выберите **oAuth2** в качестве \> **метода проверки подлинности** **Вход**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-134">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="3daa6-135">Если вы выбрали другой способ проверки подлинности, подключение к приложению шаблона завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="3daa6-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="3daa6-137">После создания экземпляра приложения шаблона панель мониторинга анализа использования Microsoft 365 будет доступна в Power BI в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3daa6-137">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="3daa6-138">Начальная загрузка панели мониторинга займет от 2 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3daa6-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="3daa6-139">Статистические функции на уровне клиента будут доступны во всех отчетах.</span><span class="sxs-lookup"><span data-stu-id="3daa6-139">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="3daa6-140">**Сведения на уровне пользователя становятся доступны только по истечении первого или 15-го дня в календарном месяце после пропуска**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-140">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="3daa6-141">Это повлияет на все отчеты в разделе действия пользователя (дополнительные советы по просмотру и использованию отчетов представлены [в статье Навигация и использование отчетов в аналитике использования Microsoft 365](navigate-and-utilize-reports.md) ).</span><span class="sxs-lookup"><span data-stu-id="3daa6-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="3daa6-142">Как сделать собранные данные анонимными?</span><span class="sxs-lookup"><span data-stu-id="3daa6-142">Make the collected data anonymous</span></span>

<span data-ttu-id="3daa6-143">Данные, собираемые для отчетов, может сделать анонимными только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="3daa6-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="3daa6-144">Это приведет к скрытию идентифицируемых сведений, таких как имена пользователей, групп и сайтов, в отчетах и в приложении-шаблоне.</span><span class="sxs-lookup"><span data-stu-id="3daa6-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="3daa6-145">В центре администрирования откройте раздел **Settings** \> **Параметры**, а затем на вкладке **службы** выберите **отчеты**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-145">In the admin center, go to the **Settings** \> **Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="3daa6-146">Выберите **отчеты**, а затем выберите для **отображения анонимных идентификаторов**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="3daa6-147">Этот параметр применяется как к отчетам об использовании, так и к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="3daa6-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="3daa6-148">Нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="3daa6-148">Select **Save changes**.</span></span>
