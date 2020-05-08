---
title: Настройка отчетов в аналитике использования Microsoft 365
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Сведения о настройке отчетов в браузере и Power BI Desktop.
ms.openlocfilehash: 4f0c85802ecb5db9c57add2fa6dd561827e8fa22
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140713"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="30c6c-103">Настройка отчетов в аналитике использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30c6c-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="30c6c-104">Изменяется центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="30c6c-104">The admin center is changing.</span></span> <span data-ttu-id="30c6c-105">Если ваш интерфейс не отвечает указанным здесь сведениям, ознакомьтесь [со статьей о новом центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="30c6c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="30c6c-106">Служба аналитики использования Microsoft 365 предоставляет панель мониторинга в Power BI, которая предоставляет подробные сведения о том, как пользователи принимают и используют Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30c6c-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="30c6c-107">Панель мониторинга  это отправная точка для анализа данных об использовании.</span><span class="sxs-lookup"><span data-stu-id="30c6c-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="30c6c-108">Отчеты можно настроить для получения именно тех сведений, которые нужны вам.</span><span class="sxs-lookup"><span data-stu-id="30c6c-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="30c6c-109">Вы также можете уточнить отчеты с помощью Power BI Desktop, подключив их к другим источникам данных, позволяющим получить дополнительную информацию о вашей компании.</span><span class="sxs-lookup"><span data-stu-id="30c6c-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="30c6c-110">Настройка отчетов в браузере</span><span class="sxs-lookup"><span data-stu-id="30c6c-110">Customizing reports in the browser</span></span>

<span data-ttu-id="30c6c-111">Ниже на примерах объясняется, как изменить существующий визуальный элемент и создать новый.</span><span class="sxs-lookup"><span data-stu-id="30c6c-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="30c6c-112">Изменение визуального элемента</span><span class="sxs-lookup"><span data-stu-id="30c6c-112">Modify an existing visual</span></span>

<span data-ttu-id="30c6c-113">В этом примере показано, как изменить вкладку **Активация** в отчете об **активации и лицензировании** .</span><span class="sxs-lookup"><span data-stu-id="30c6c-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="30c6c-114">В отчете **Активация и лицензирование** перейдите на вкладку **Активация** .</span><span class="sxs-lookup"><span data-stu-id="30c6c-114">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="30c6c-115">Откройте режим редактирования, нажав кнопку **Правка** вверху ![кнопки Дополнительные страницы в Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) .</span><span class="sxs-lookup"><span data-stu-id="30c6c-115">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="30c6c-117">В правом верхнем углу щелкните **дублировать эту страницу**.</span><span class="sxs-lookup"><span data-stu-id="30c6c-117">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="30c6c-119">В правом нижнем углу щелкните любую линейчатую диаграмму, в которой отображается количество пользователей, активируемых на основе операционной системы, таких как Android, iOS, Mac и т. д.</span><span class="sxs-lookup"><span data-stu-id="30c6c-119">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="30c6c-120">В области **зрительных образов** справа, чтобы удалить **число MAC-адресов** из визуального отображения, щелкните значок **X** рядом с элементом.</span><span class="sxs-lookup"><span data-stu-id="30c6c-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Удаление счетчика Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="30c6c-122">Создание визуального элемента</span><span class="sxs-lookup"><span data-stu-id="30c6c-122">Create a new visual</span></span>

<span data-ttu-id="30c6c-123">Ниже показано, как создать визуальный элемент для отслеживания новых пользователей Yammer на ежемесячной основе.</span><span class="sxs-lookup"><span data-stu-id="30c6c-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="30c6c-124">Перейдите к отчету **об использовании продукта** с помощью левой панели навигации и откройте вкладку **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="30c6c-124">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="30c6c-125">Переключитесь в режим редактирования, нажав ![кнопку More Page (дополнительные страницы)](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) в Power BI и **Edit (изменить**).</span><span class="sxs-lookup"><span data-stu-id="30c6c-125">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="30c6c-126">В нижней части страницы нажмите кнопку</span><span class="sxs-lookup"><span data-stu-id="30c6c-126">At the bottom of the page, click on</span></span> ![Кнопка "добавить страницу" в Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="30c6c-128">для создания новой страницы.</span><span class="sxs-lookup"><span data-stu-id="30c6c-128">to create a new page.</span></span>
  
4. <span data-ttu-id="30c6c-129">В области **зрительных образов** щелкните **линейчатую диаграмму с накоплением** (верхняя строка, первая — слева).</span><span class="sxs-lookup"><span data-stu-id="30c6c-129">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![Выбор линейчатой диаграммы](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="30c6c-131">Щелкните правый нижний угол визуализации и перетащите его, чтобы увеличить ее.</span><span class="sxs-lookup"><span data-stu-id="30c6c-131">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="30c6c-132">В области **поля** справа разверните таблицу **Календарь** .</span><span class="sxs-lookup"><span data-stu-id="30c6c-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="30c6c-133">Перетащите **MonthName** в область полей под заголовком **Axis** (Ось) в области **Visualizations**.</span><span class="sxs-lookup"><span data-stu-id="30c6c-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Имя месяца перетаскивания](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="30c6c-135">В области **Fields** (Поля) справа разверните таблицу **TenantProductUsage**.</span><span class="sxs-lookup"><span data-stu-id="30c6c-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="30c6c-136">Перетащите **FirstTimeUsers** в область полей под заголовком **Value** (Значение).</span><span class="sxs-lookup"><span data-stu-id="30c6c-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="30c6c-137">Перетащите **Product** в область **Filters** (Фильтры) под заголовком **Visual level filters** (Фильтры уровня визуального элемента).</span><span class="sxs-lookup"><span data-stu-id="30c6c-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="30c6c-138">В области **Filter Type** (Тип фильтра) установите флажок **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="30c6c-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Флажок "выбрать Yammer"](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="30c6c-140">Под списком зрительных образов щелкните значок формат ![значка **формата** в Power BI висуализаионс.](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)</span><span class="sxs-lookup"><span data-stu-id="30c6c-140">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="30c6c-141">Разверните заголовок и измените значение **Title Text** (Текст заголовка) на **First-Time Yammer Users by Month** (Новые пользователи Yammer по месяцам).</span><span class="sxs-lookup"><span data-stu-id="30c6c-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="30c6c-142">Измените значение **Text Size** (Размер текста) на **12**.</span><span class="sxs-lookup"><span data-stu-id="30c6c-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="30c6c-143">Измените название новой страницы, отредактировав имя страницы внизу справа.</span><span class="sxs-lookup"><span data-stu-id="30c6c-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="30c6c-144">Чтобы сохранить отчет, выберите **режим чтения** сверху и **Сохраните**его.</span><span class="sxs-lookup"><span data-stu-id="30c6c-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="30c6c-145">Настройка отчетов в Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="30c6c-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="30c6c-p103">Большинству клиентов будет достаточно возможностей изменения отчетов и диаграмм, доступных в веб-версии Power BI. Однако в некоторых случаях может существовать необходимость объединения с другими источниками данных для получения более точных сведений, важных для бизнеса. Для этого можно настраивать и создавать дополнительные отчеты с помощью Power BI Desktop. Вы можете скачать [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) бесплатно.</span><span class="sxs-lookup"><span data-stu-id="30c6c-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="30c6c-149">Использование API отчетов</span><span class="sxs-lookup"><span data-stu-id="30c6c-149">Use the reporting APIs</span></span>

<span data-ttu-id="30c6c-150">Вы можете начать с прямого подключения к API-интерфейсам отчетов ODATA из Microsoft 365, чтобы включить эти отчеты.</span><span class="sxs-lookup"><span data-stu-id="30c6c-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="30c6c-151">Выберите **get data** (получить данные) \> **Other** (Другое) \> **ODATA Feed** (Веб-канал OData) \> **Connect** (Подключить).</span><span class="sxs-lookup"><span data-stu-id="30c6c-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="30c6c-152">В окне "URL-адрес"<i></i>введите\<"\>HTTPS://Reports.Office.com/PBI/v1.0/tenantid"</span><span class="sxs-lookup"><span data-stu-id="30c6c-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="30c6c-153">**Примечание:** API отчетов в предварительной версии и могут изменяться, пока они не переходят в производственную среду.</span><span class="sxs-lookup"><span data-stu-id="30c6c-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="30c6c-155">Введите учетные данные администратора Microsoft 365 (организация или учебные заведения) для проверки подлинности в Microsoft 365 при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="30c6c-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="30c6c-156">Дополнительные сведения о том, кто может получить доступ к отчетам о приложениях-шаблоне внедрения Microsoft 365, можно найти в разделе [вопросы и ответы](usage-analytics.md#faq) .</span><span class="sxs-lookup"><span data-stu-id="30c6c-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="30c6c-157">После авторизации подключения вы увидите окно навигатора, в котором выводятся доступные наборы данных.</span><span class="sxs-lookup"><span data-stu-id="30c6c-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="30c6c-158">Выделите все наборы и щелкните **Load** (Загрузить).</span><span class="sxs-lookup"><span data-stu-id="30c6c-158">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="30c6c-p104">При этом данные будут загружены в Power BI Desktop. Сохраните этот файл и приступите к созданию необходимых отчетов.</span><span class="sxs-lookup"><span data-stu-id="30c6c-p104">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![Значения ODATA, доступные в API отчетов](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="30c6c-162">Использование шаблона аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30c6c-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="30c6c-163">Вы также можете использовать файл шаблона Power BI, соответствующий отчетам аналитики использования Microsoft 365, в качестве отправной точки для подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="30c6c-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="30c6c-164">Преимущество использования этого PBIT-файла заключается в том, что строка подключения уже задана.</span><span class="sxs-lookup"><span data-stu-id="30c6c-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="30c6c-165">Кроме того, вы можете применять готовые настраиваемые меры в дополнение к тем, которые возвращаются основной схемой, и уточнять их.</span><span class="sxs-lookup"><span data-stu-id="30c6c-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="30c6c-166">Вы можете скачать файл шаблона Power BI из центра загрузки Майкрософт в [центре загрузки](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="30c6c-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="30c6c-167">Скачав файл шаблона Power BI, выполните следующие действия, чтобы приступить к работе:</span><span class="sxs-lookup"><span data-stu-id="30c6c-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="30c6c-168">Откройте PBIT-файл.</span><span class="sxs-lookup"><span data-stu-id="30c6c-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="30c6c-169">Введите значение идентификатора клиента в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="30c6c-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="30c6c-171">Введите учетные данные администратора для проверки подлинности в Microsoft 365 при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="30c6c-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="30c6c-172">Дополнительные сведения о том, кому разрешен доступ к отчетам аналитики использования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30c6c-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="30c6c-173">После авторизации данные в файле Power BI будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="30c6c-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="30c6c-174">Загрузка данных может занять некоторое время. Когда она будет завершена, вы можете сохранить их как PBIX-файл и перейти к настройке отчетов или добавить дополнительный источник данных.</span><span class="sxs-lookup"><span data-stu-id="30c6c-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="30c6c-p107">Прочтите [инструкции по началу работы с Power BI](https://go.microsoft.com/fwlink/?linkid=849802), чтобы научиться создавать отчеты, публиковать их в службе Power BI и использовать их совместно с коллегами. Для настройки отчетов и предоставления доступа к ним могут потребоваться дополнительные лицензии на Power BI. Сведения о лицензировании Power BI можно найти [здесь](https://go.microsoft.com/fwlink/p/?linkid=849803).</span><span class="sxs-lookup"><span data-stu-id="30c6c-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

