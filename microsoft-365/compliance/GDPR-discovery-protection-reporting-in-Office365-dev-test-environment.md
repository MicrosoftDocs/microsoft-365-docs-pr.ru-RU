---
title: Обнаружение, защита и создание отчетов в рамках GDPR в среде разработки и тестирования Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: В этой статье рассказывается, как продемонстрировать возможности для выполнения требований GDPR, имеющиеся в Office 365.
ms.openlocfilehash: 98339aeec2c89edd4fead1482f98aa3d9f316856
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38749983"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a><span data-ttu-id="eaf00-103">Обнаружение, защита и создание отчетов в рамках GDPR в среде разработки и тестирования Office 365</span><span class="sxs-lookup"><span data-stu-id="eaf00-103">GDPR discovery, protection, and reporting in the Office 365 dev/test environment</span></span>

 <span data-ttu-id="eaf00-104">**Сводка:** в этой статье рассказывается, как продемонстрировать возможности для выполнения требований GDPR, имеющиеся в Office 365.</span><span class="sxs-lookup"><span data-stu-id="eaf00-104">**Summary:** Demonstrate GDPR capabilities in Office 365.</span></span> 
  
<span data-ttu-id="eaf00-105">В этой статье рассказывается, как настроить и продемонстрировать функции обнаружения и защиты личных сведений, а также функции составления отчетов о них для выполнения требований общего регламента по защите данных (GDPR) в среде разработки и тестирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="eaf00-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in an Office 365 dev/test environment.</span></span>
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a><span data-ttu-id="eaf00-106">Этап 1. Создание и настройка пробной подписки на Office 365</span><span class="sxs-lookup"><span data-stu-id="eaf00-106">Phase 1: Create and configure your trial Office 365 subscription</span></span>

<span data-ttu-id="eaf00-107">Сначала выполните инструкции, описанные в разделе ["Этап 2" статьи о среде разработки и тестирования Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription).</span><span class="sxs-lookup"><span data-stu-id="eaf00-107">First, follow the steps in [Phase 2 of the Office 365 dev/test environment](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="eaf00-108">Затем настройте менеджера по обнаружению электронных данных, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="eaf00-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="eaf00-109">Выполните вход в пробный клиент Office 365, используя свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="eaf00-109">Sign in to your Office 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="eaf00-110">На домашней странице Office 365 щелкните **Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-110">From the Office 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="eaf00-111">На новой вкладке "Безопасность и соответствие требованиям" щелкните **Разрешения** > **Менеджер по обнаружению электронных данных**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="eaf00-112">Нажмите кнопку **Изменить** для менеджера по обнаружению электронных данных, а затем щелкните **Выбрать менеджера по обнаружению электронных данных**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="eaf00-113">Нажмите кнопку **+ Добавить**, найдите имя своей учетной записи глобального администратора и добавьте ее в качестве менеджера по обнаружению электронных данных.</span><span class="sxs-lookup"><span data-stu-id="eaf00-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="eaf00-114">Нажмите кнопки **Готово** > **Сохранить** > **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-114">Click **Done** > **Save** > **Close**.</span></span>
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="eaf00-115">Этап 2. Добавление личных сведений в клиент</span><span class="sxs-lookup"><span data-stu-id="eaf00-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="eaf00-116">На этом этапе вы можете создать документ с личными сведениями для набора примеров IBAN (международных номеров банковских счетов) и сохранить этот документ на сайте SharePoint Online в вашей среде разработки и тестирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="eaf00-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Office 365 dev/test environment.</span></span>

1. <span data-ttu-id="eaf00-117">На локальном компьютере откройте приложение Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="eaf00-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="eaf00-118">Вставьте приведенную ниже таблицу в файл Word и сохраните файл под именем IBANs.docx на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="eaf00-118">Paste the following table in the Word file and save it as ‘IBANs.docx’ on your local computer.</span></span>
    
    <span data-ttu-id="eaf00-119">Номер</span><span class="sxs-lookup"><span data-stu-id="eaf00-119">Number</span></span>  |<span data-ttu-id="eaf00-120">Страна</span><span class="sxs-lookup"><span data-stu-id="eaf00-120">Country</span></span>  |<span data-ttu-id="eaf00-121">Код</span><span class="sxs-lookup"><span data-stu-id="eaf00-121">Code</span></span> |<span data-ttu-id="eaf00-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="eaf00-122">IBAN</span></span>  |
    |---------|---------|---------|---------|
    |<span data-ttu-id="eaf00-123">1</span><span class="sxs-lookup"><span data-stu-id="eaf00-123">1</span></span>     |  <span data-ttu-id="eaf00-124">Австрия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-124">Austria SEPA</span></span>      | <span data-ttu-id="eaf00-125">AT</span><span class="sxs-lookup"><span data-stu-id="eaf00-125">AT</span></span>            |<span data-ttu-id="eaf00-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="eaf00-126">AT611904300234573201</span></span>       |
    |<span data-ttu-id="eaf00-127">2</span><span class="sxs-lookup"><span data-stu-id="eaf00-127">2</span></span>     |  <span data-ttu-id="eaf00-128">Болгария, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-128">Bulgaria SEPA</span></span>       |<span data-ttu-id="eaf00-129">BG</span><span class="sxs-lookup"><span data-stu-id="eaf00-129">BG</span></span>    |<span data-ttu-id="eaf00-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="eaf00-130">BG80BNBG96611020345678</span></span>      |
    |<span data-ttu-id="eaf00-131">3</span><span class="sxs-lookup"><span data-stu-id="eaf00-131">3</span></span>     |  <span data-ttu-id="eaf00-132">Дания, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-132">Denmark SEPA</span></span>      |   <span data-ttu-id="eaf00-133">DK</span><span class="sxs-lookup"><span data-stu-id="eaf00-133">DK</span></span>      |<span data-ttu-id="eaf00-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="eaf00-134">DK5000400440116243</span></span>      |
    |<span data-ttu-id="eaf00-135">4</span><span class="sxs-lookup"><span data-stu-id="eaf00-135">4</span></span>     |  <span data-ttu-id="eaf00-136">Финляндия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-136">Finland SEPA</span></span>      |   <span data-ttu-id="eaf00-137">FI</span><span class="sxs-lookup"><span data-stu-id="eaf00-137">FI</span></span>      |<span data-ttu-id="eaf00-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="eaf00-138">FI2112345600000785</span></span>         |
    |<span data-ttu-id="eaf00-139">5</span><span class="sxs-lookup"><span data-stu-id="eaf00-139">5</span></span>     |  <span data-ttu-id="eaf00-140">Франция, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-140">France SEPA</span></span>       |   <span data-ttu-id="eaf00-141">FR</span><span class="sxs-lookup"><span data-stu-id="eaf00-141">FR</span></span>      |<span data-ttu-id="eaf00-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="eaf00-142">FR1420041010050500013M02606</span></span>         |
    |<span data-ttu-id="eaf00-143">6</span><span class="sxs-lookup"><span data-stu-id="eaf00-143">6</span></span>     |  <span data-ttu-id="eaf00-144">Германия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-144">Germany SEPA</span></span>      |   <span data-ttu-id="eaf00-145">DE</span><span class="sxs-lookup"><span data-stu-id="eaf00-145">DE</span></span>      |<span data-ttu-id="eaf00-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="eaf00-146">DE89370400440532013000</span></span>         |
    |<span data-ttu-id="eaf00-147">7</span><span class="sxs-lookup"><span data-stu-id="eaf00-147">7</span></span>     |  <span data-ttu-id="eaf00-148">Греция, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-148">Greece SEPA</span></span>       |   <span data-ttu-id="eaf00-149">GR</span><span class="sxs-lookup"><span data-stu-id="eaf00-149">GR</span></span>      |<span data-ttu-id="eaf00-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="eaf00-150">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="eaf00-151">8</span><span class="sxs-lookup"><span data-stu-id="eaf00-151">8</span></span>     |  <span data-ttu-id="eaf00-152">Италия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-152">Italy SEPA</span></span>       |    <span data-ttu-id="eaf00-153">IT</span><span class="sxs-lookup"><span data-stu-id="eaf00-153">IT</span></span>     |<span data-ttu-id="eaf00-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="eaf00-154">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="eaf00-155">9</span><span class="sxs-lookup"><span data-stu-id="eaf00-155">9</span></span>     |  <span data-ttu-id="eaf00-156">Нидерланды, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-156">Netherlands SEPA</span></span>      |   <span data-ttu-id="eaf00-157">NL</span><span class="sxs-lookup"><span data-stu-id="eaf00-157">NL</span></span>      |    <span data-ttu-id="eaf00-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="eaf00-158">NL91ABNA0417164300</span></span>     |
    |<span data-ttu-id="eaf00-159">10</span><span class="sxs-lookup"><span data-stu-id="eaf00-159">10</span></span>     | <span data-ttu-id="eaf00-160">Польша, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-160">Poland SEPA</span></span>       |  <span data-ttu-id="eaf00-161">PL</span><span class="sxs-lookup"><span data-stu-id="eaf00-161">PL</span></span>       | <span data-ttu-id="eaf00-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="eaf00-162">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="eaf00-163">Примечание. Этот пример набора данных получен из общедоступных сведений и предназначен исключительно для тестирования.</span><span class="sxs-lookup"><span data-stu-id="eaf00-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="eaf00-164">На новой вкладке браузера введите **https://**\<ИмяВашегоКлиента\>**.sharepoint.com**</span><span class="sxs-lookup"><span data-stu-id="eaf00-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="eaf00-p101">Щелкните **Документы**. Откроется библиотека документов для этого сайта. Если вам будет предложена демонстрация нового интерфейса списков, нажимайте кнопку **Далее**, пока демонстрация не закончится.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p101">Click **Documents** to open the document library for this site. If you’re prompted for a new list experience tour, click **Next** until it’s finished.</span></span>
5.  <span data-ttu-id="eaf00-167">Щелкните **Отправить** > **Файлы** и выберите файл IBANs.docx, который вы создали на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="eaf00-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

  
## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="eaf00-168">Этап 3. Демонстрация функции обнаружения данных</span><span class="sxs-lookup"><span data-stu-id="eaf00-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="eaf00-169">На этом этапе вы продемонстрируете функцию поиска, с помощью которой можно находить документы, созданные и сохраненные на этапе 2, на основании их содержимого, в котором имеются номера IBAN.</span><span class="sxs-lookup"><span data-stu-id="eaf00-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="eaf00-170">На вкладке "Безопасность и соответствие требованиям" щелкните **Главная**, а затем выберите **Поиск и расследование** > **Поиск контента**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="eaf00-171">Создайте элемент поиска, щелкнув **+**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="eaf00-172">В новом окне укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="eaf00-172">In a new window, provide the following information:</span></span>  
    <span data-ttu-id="eaf00-p102">1. "Имя": Поиск IBAN.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p102">a. Name: IBAN Search</span></span>  
    <span data-ttu-id="eaf00-p103">2. "Где выполнять поиск?": **выберите конкретные сайты, на которых необходимо искать данные** (щелкните **+**) и введите URL-адрес сайта **https://**\<ИмяВашегоКлиента\>**.sharepoint.com/**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p103">b. Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/**</span></span>  
    <span data-ttu-id="eaf00-p104">3. Последовательно нажмите кнопки **Добавить** и **ОК**. Если отобразится предупреждение, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p104">c. Click **Add**, and then click **OK**. If you see a Warning, click **OK**.</span></span>  
    <span data-ttu-id="eaf00-p105">4. Нажмите кнопку **Далее** в окне **Новая операция поиска**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p105">d. Click **Next** on a **New search** window.</span></span>  
    <span data-ttu-id="eaf00-p106">5. В пункте **Что необходимо искать?** введите **SensitiveType:"Международный номер банковского счета (IBAN)"** и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p106">e. For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="eaf00-184">Убедитесь, что в списке результатов **Поиск IBAN** есть хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="eaf00-184">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="eaf00-185">Этап 4. Создание пользовательского типа конфиденциальной информации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eaf00-185">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="eaf00-p107">На этом этапе вы создадите пользовательский тип конфиденциальной информации для вымышленной компании Contoso Corporation с помощью Microsoft PowerShell. В компании Contoso для идентификации клиентов в базе данных используется идентификатор Contoso Customer Number (CCN). Идентификатор CCN имеет указанную ниже структуру.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p107">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>
- <span data-ttu-id="eaf00-189">Две цифры для обозначения года, в котором была создана запись.</span><span class="sxs-lookup"><span data-stu-id="eaf00-189">Two digits to represent the year that the record was created.</span></span>
    - <span data-ttu-id="eaf00-190">Компания Contoso была основана в 2002 г, поэтому минимальное возможное значение — 02.</span><span class="sxs-lookup"><span data-stu-id="eaf00-190">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span> 
- <span data-ttu-id="eaf00-191">Три цифры для обозначения агентства-партнера, создавшего запись.</span><span class="sxs-lookup"><span data-stu-id="eaf00-191">Three digits to represent the partner agency that created the record.</span></span>
    - <span data-ttu-id="eaf00-192">Возможные значения для агентства: от 000 до 999.</span><span class="sxs-lookup"><span data-stu-id="eaf00-192">Possible agency values range from 000 to 999.</span></span> 
- <span data-ttu-id="eaf00-193">Буквенный символ для обозначения бизнес-подразделения.</span><span class="sxs-lookup"><span data-stu-id="eaf00-193">An alphabetic character to represent the line of business.</span></span>
    - <span data-ttu-id="eaf00-194">Возможные значения: от a до z без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="eaf00-194">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="eaf00-195">Четыре цифры серийного номера.</span><span class="sxs-lookup"><span data-stu-id="eaf00-195">A four-digit serial number.</span></span> 
    - <span data-ttu-id="eaf00-196">Возможные значения серийного номера: от 0000 до 9999.</span><span class="sxs-lookup"><span data-stu-id="eaf00-196">Possible serial number values range from 0000 to 9999.</span></span>   

<span data-ttu-id="eaf00-p108">Для ссылки на своих клиентов во внутренней и внешней корреспонденции, документах и других формах компания Contoso всегда использует идентификатор CCN. Компании Contoso необходим пользовательский тип конфиденциальных данных, чтобы обнаруживать случаи использования идентификатора CCN в контенте Office 365 и применять защиту при использовании этой формы личных сведений.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p108">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Office 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="eaf00-199">Выполнив инструкции в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям с помощью многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps), подключитесь к Центру безопасности и соответствия требованиям с помощью имени участника-пользователя вашей учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="eaf00-199">Use the instructions in [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>
2. <span data-ttu-id="eaf00-200">Выполните указанные ниже команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaf00-200">Run the following PowerShell commands.</span></span>

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. <span data-ttu-id="eaf00-201">Выполните указанные ниже команды PowerShell и скопируйте созданные GUID в открытый экземпляр приложения "Блокнот" на своем компьютере в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="eaf00-201">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. <span data-ttu-id="eaf00-202">На локальном компьютере откройте еще один экземпляр приложения "Блокнот" и вставьте указанный ниже контент.</span><span class="sxs-lookup"><span data-stu-id="eaf00-202">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. <span data-ttu-id="eaf00-203">Замените значения GUID1, GUID2 и GUID3 в тексте XML на этапе 4 соответствующими значениями из этапа 3, а затем сохраните содержимое на локальном компьютере в файле с именем ContosoCCN.xml.</span><span class="sxs-lookup"><span data-stu-id="eaf00-203">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>
6. <span data-ttu-id="eaf00-204">Укажите путь к файлу ContosoCCN.xml и выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="eaf00-204">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. <span data-ttu-id="eaf00-p109">На вкладке "Безопасность и соответствие требованиям" щелкните **Классификации** > **Типы конфиденциальной информации**. В списке должен отобразиться идентификатор Contoso Customer Number (CCN).</span><span class="sxs-lookup"><span data-stu-id="eaf00-p109">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="eaf00-207">Этап 5. Демонстрация функции защиты данных</span><span class="sxs-lookup"><span data-stu-id="eaf00-207">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="eaf00-208">Защита персональных данных в Office 365 включает использование функций защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="eaf00-208">Protection of personal information in Office 365 includes using data loss prevention (DLP) capabilities.</span></span>  <span data-ttu-id="eaf00-209">Политики защиты от потери данных позволяют автоматически защищать конфиденциальную информацию в Office 365.</span><span class="sxs-lookup"><span data-stu-id="eaf00-209">With DLP policies, you can automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="eaf00-p111">Применить защиту можно несколькими способами. Один из уровней защиты информации с помощью функций защиты от потери данных в Office 365 — рассказывать клиентам, где хранятся данные резидентов ЕС и каким образом вашим сотрудникам разрешено обрабатывать их.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p111">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="eaf00-212">На этом этапе вы создадите политику защиты от потери данных и продемонстрируете, как система применяет ее к файлу IBANs.docx, который вы сохранили в SharePoint Online на этапе 2, а также как действует политика, когда вы пытаетесь отправлять электронные письма, содержащие IBAN.</span><span class="sxs-lookup"><span data-stu-id="eaf00-212">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="eaf00-213">На вкладке "Безопасность и соответствие требованиям" браузера щелкните **Главная**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-213">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="eaf00-214">Щелкните **Защита от потери данных** > **Политика**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-214">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="eaf00-215">Щелкните **+ Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-215">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="eaf00-216">В разделе **Начать работу с помощью шаблона или создать пользовательскую политику** щелкните **Пользовательская** > **Пользовательская политика** > **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-216">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="eaf00-p112">В разделе **Задайте имя для политики** введите указанные ниже сведения и щелкните **Далее**: а) имя: **Политика личных данных граждан ЕС**; б) описание: **Защита личных данных граждан ЕС**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p112">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="eaf00-p113">В разделе **Выбор расположений** щелкните **Все расположения в Office 365**. Благодаря этому будет включен контент в почте Exchange и документы в OneDrive и SharePoint. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p113">In **Choose locations**, select **All locations in Office 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="eaf00-223">В разделе **Настройка типа контента, который необходимо защитить** щелкните **Найти контент, который содержит:** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-223">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="eaf00-224">В разделе **Выбор типов контента, который необходимо защитить** щелкните **Добавить** > **Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-224">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="eaf00-225">В разделе **Типы конфиденциальной информации** щелкните **+ Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-225">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="eaf00-226">В разделе **Типы конфиденциальной информации** выполните поиск **IBAN**, установите флажок **Международный номер банковского счета (IBAN)** и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-226">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="eaf00-227">Убедитесь, что тип конфиденциальной информации **Международный номер банковского счета (IBAN)** добавлен, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-227">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="eaf00-228">В разделе **Контент содержит** подтвердите, что необходимые типы конфиденциальной информации были добавлены, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-228">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="eaf00-229">В разделе **Настройка типа контента, который необходимо защитить** убедитесь, что поле **Найти контент, который содержит:** содержит значение **Международный номер банковского счета (IBAN)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-229">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="eaf00-230">В разделе **Обнаруживать, когда контент, к которому предоставлен общий доступ, содержит:** замените значение **10** на **1** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-230">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="eaf00-231">В разделе **Вы хотите включить политику или сначала протестировать ее?** выберите указанные ниже параметры, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-231">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>  
    <span data-ttu-id="eaf00-p114">1. Выберите вариант **Я хочу сначала протестировать**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p114">a. Select the option for **I'd like to test it out first**</span></span>  
    <span data-ttu-id="eaf00-p115">2. Установите флажок **Показывать подсказки политики в тестовом режиме**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p115">b. Select the check box for **Show policy tips while in test mode**</span></span> 
16. <span data-ttu-id="eaf00-p116">В разделе **Проверьте параметры** проверьте значения параметров и щелкните **Создать**. ПРИМЕЧАНИЕ. После создания политики защиты от потери данных потребуется некоторое время, чтобы она вступила в силу.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p116">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="eaf00-238">На локальном компьютере откройте приватное окно браузера.</span><span class="sxs-lookup"><span data-stu-id="eaf00-238">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="eaf00-239">В адресной строке введите **https://**\<ИмяВашегоКлиента\>**.sharepoint.com** и выполните вход, используя вашу учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="eaf00-239">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="eaf00-240">Щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-240">Click **Documents**.</span></span>
20. <span data-ttu-id="eaf00-p117">Щелкните файл IBANs.docx. Должна отобразиться подсказка политики для файла IBANs.docx. Вы пытались отправить файл IBANs.docx внешним получателям, что привело к нарушению политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p117">Click the file named ‘IBANs.docx’. You should see ‘Policy tip for IBANs.docx’.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span> 
21. <span data-ttu-id="eaf00-244">В адресной строке введите следующее: `https://outlook.office365.com`</span><span class="sxs-lookup"><span data-stu-id="eaf00-244">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="eaf00-245">Щелкните **Создать** - **Сообщение электронной почты** и введите указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="eaf00-245">Click **New** - **Email message** and provide the following:</span></span>  
    - <span data-ttu-id="eaf00-246">**Кому:** \<личный электронный адрес\></span><span class="sxs-lookup"><span data-stu-id="eaf00-246">**To:** \<a personal email address\></span></span>  
    - <span data-ttu-id="eaf00-247">**Тема:** тест в рамках GDPR</span><span class="sxs-lookup"><span data-stu-id="eaf00-247">**Subject:** GDPR Test</span></span>  
    - <span data-ttu-id="eaf00-248">**Текст:** скопируйте из таблицы значений ниже.</span><span class="sxs-lookup"><span data-stu-id="eaf00-248">**Body:** Copy in the table of values shown below.</span></span>
  
        |<span data-ttu-id="eaf00-249">Номер</span><span class="sxs-lookup"><span data-stu-id="eaf00-249">Number</span></span>  |<span data-ttu-id="eaf00-250">Страна</span><span class="sxs-lookup"><span data-stu-id="eaf00-250">Country</span></span>  |<span data-ttu-id="eaf00-251">Код</span><span class="sxs-lookup"><span data-stu-id="eaf00-251">Code</span></span> |<span data-ttu-id="eaf00-252">IBAN</span><span class="sxs-lookup"><span data-stu-id="eaf00-252">IBAN</span></span>  |
        |---------|---------|---------|---------|
        |<span data-ttu-id="eaf00-253">1</span><span class="sxs-lookup"><span data-stu-id="eaf00-253">1</span></span>     |  <span data-ttu-id="eaf00-254">Австрия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-254">Austria SEPA</span></span>      | <span data-ttu-id="eaf00-255">AT</span><span class="sxs-lookup"><span data-stu-id="eaf00-255">AT</span></span>            |<span data-ttu-id="eaf00-256">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="eaf00-256">AT611904300234573201</span></span>       |
        |<span data-ttu-id="eaf00-257">2</span><span class="sxs-lookup"><span data-stu-id="eaf00-257">2</span></span>     |  <span data-ttu-id="eaf00-258">Болгария, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-258">Bulgaria SEPA</span></span>       |<span data-ttu-id="eaf00-259">BG</span><span class="sxs-lookup"><span data-stu-id="eaf00-259">BG</span></span>    |<span data-ttu-id="eaf00-260">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="eaf00-260">BG80BNBG96611020345678</span></span>      |
        |<span data-ttu-id="eaf00-261">3</span><span class="sxs-lookup"><span data-stu-id="eaf00-261">3</span></span>     |  <span data-ttu-id="eaf00-262">Дания, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-262">Denmark SEPA</span></span>      |   <span data-ttu-id="eaf00-263">DK</span><span class="sxs-lookup"><span data-stu-id="eaf00-263">DK</span></span>      |<span data-ttu-id="eaf00-264">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="eaf00-264">DK5000400440116243</span></span>      |
        |<span data-ttu-id="eaf00-265">4</span><span class="sxs-lookup"><span data-stu-id="eaf00-265">4</span></span>     |  <span data-ttu-id="eaf00-266">Финляндия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-266">Finland SEPA</span></span>      |   <span data-ttu-id="eaf00-267">FI</span><span class="sxs-lookup"><span data-stu-id="eaf00-267">FI</span></span>      |<span data-ttu-id="eaf00-268">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="eaf00-268">FI2112345600000785</span></span>         |
        |<span data-ttu-id="eaf00-269">5</span><span class="sxs-lookup"><span data-stu-id="eaf00-269">5</span></span>     |  <span data-ttu-id="eaf00-270">Франция, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-270">France SEPA</span></span>       |   <span data-ttu-id="eaf00-271">FR</span><span class="sxs-lookup"><span data-stu-id="eaf00-271">FR</span></span>      |<span data-ttu-id="eaf00-272">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="eaf00-272">FR1420041010050500013M02606</span></span>         |
        |<span data-ttu-id="eaf00-273">6</span><span class="sxs-lookup"><span data-stu-id="eaf00-273">6</span></span>     |  <span data-ttu-id="eaf00-274">Германия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-274">Germany SEPA</span></span>      |   <span data-ttu-id="eaf00-275">DE</span><span class="sxs-lookup"><span data-stu-id="eaf00-275">DE</span></span>      |<span data-ttu-id="eaf00-276">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="eaf00-276">DE89370400440532013000</span></span>         |
        |<span data-ttu-id="eaf00-277">7</span><span class="sxs-lookup"><span data-stu-id="eaf00-277">7</span></span>     |  <span data-ttu-id="eaf00-278">Греция, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-278">Greece SEPA</span></span>       |   <span data-ttu-id="eaf00-279">GR</span><span class="sxs-lookup"><span data-stu-id="eaf00-279">GR</span></span>      |<span data-ttu-id="eaf00-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="eaf00-280">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="eaf00-281">8</span><span class="sxs-lookup"><span data-stu-id="eaf00-281">8</span></span>     |  <span data-ttu-id="eaf00-282">Италия, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-282">Italy SEPA</span></span>       |    <span data-ttu-id="eaf00-283">IT</span><span class="sxs-lookup"><span data-stu-id="eaf00-283">IT</span></span>     |<span data-ttu-id="eaf00-284">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="eaf00-284">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="eaf00-285">9</span><span class="sxs-lookup"><span data-stu-id="eaf00-285">9</span></span>     |  <span data-ttu-id="eaf00-286">Нидерланды, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-286">Netherlands SEPA</span></span>      |   <span data-ttu-id="eaf00-287">NL</span><span class="sxs-lookup"><span data-stu-id="eaf00-287">NL</span></span>      |   <span data-ttu-id="eaf00-288">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="eaf00-288">NL91ABNA0417164300</span></span>      |
        |<span data-ttu-id="eaf00-289">10</span><span class="sxs-lookup"><span data-stu-id="eaf00-289">10</span></span>     | <span data-ttu-id="eaf00-290">Польша, SEPA</span><span class="sxs-lookup"><span data-stu-id="eaf00-290">Poland SEPA</span></span>       |  <span data-ttu-id="eaf00-291">PL</span><span class="sxs-lookup"><span data-stu-id="eaf00-291">PL</span></span>       | <span data-ttu-id="eaf00-292">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="eaf00-292">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="eaf00-293">Примечание. Этот пример набора данных получен из общедоступных сведений и предназначен исключительно для тестирования.</span><span class="sxs-lookup"><span data-stu-id="eaf00-293">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="eaf00-294">Вы увидите, что политика защиты от потери данных распознала, что в тексте электронного письма содержатся IBAN, и отобразила подсказку политики в верхней части окна сообщения.</span><span class="sxs-lookup"><span data-stu-id="eaf00-294">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="eaf00-295">Закройте приватное окно браузера.</span><span class="sxs-lookup"><span data-stu-id="eaf00-295">Close the private instance of your browser.</span></span>


## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="eaf00-296">Этап 6. Демонстрация функции создания отчетов</span><span class="sxs-lookup"><span data-stu-id="eaf00-296">Phase 6: Demonstrate reporting</span></span>
 
<span data-ttu-id="eaf00-297">На этом этапе вы продемонстрируете функцию создания отчетов Office 365 с учетом политики защиты от потери данных, настроенной на этапе 5.</span><span class="sxs-lookup"><span data-stu-id="eaf00-297">In this phase, you demonstrate Office 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="eaf00-298">На вкладке "Безопасность и соответствие требованиям" браузера щелкните **Главная**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-298">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="eaf00-299">Щелкните **Отчеты** > **Панель мониторинга** > **Соответствия политике защиты от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="eaf00-299">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="eaf00-p118">Созданная вами политика защиты от потери данных помогает идентифицировать и защищать конфиденциальные сведения организации. Например, в отчете вы увидите, что политика идентифицировала документ, который содержит IBAN, хранящиеся в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="eaf00-p118">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eaf00-302">См. также</span><span class="sxs-lookup"><span data-stu-id="eaf00-302">See Also</span></span>

[<span data-ttu-id="eaf00-303">Защита информации в Office 365 в соответствии с GDPR</span><span class="sxs-lookup"><span data-stu-id="eaf00-303">Office 365 Information Protection for GDPR</span></span>](office-365-information-protection-for-gdpr.md)

[<span data-ttu-id="eaf00-304">GDPR для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eaf00-304">GDPR for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
