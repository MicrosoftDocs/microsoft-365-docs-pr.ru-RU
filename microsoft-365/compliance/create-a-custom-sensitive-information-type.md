---
title: Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как создавать, редактировать, удалять и тестировать собственные типы конфиденциальной информации для DLP в графическом пользовательском интерфейсе Центра безопасности и соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818068"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="a90ac-103">Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="a90ac-104">Ознакомьтесь с этой статьей, чтобы создать [пользовательский тип конфиденциальной информации](custom-sensitive-info-types.md) в Центре безопасности и соответствия требованиям ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="a90ac-104">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="a90ac-105">Пользовательские типы конфиденциальной информации, создаваемые этим методом, добавляются в пакет правил `Microsoft.SCCManaged.CustomRulePack`.</span><span class="sxs-lookup"><span data-stu-id="a90ac-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="a90ac-106">Вы также можете создавать пользовательские типы конфиденциальной информации с помощью PowerShell и функций точного совпадения данных.</span><span class="sxs-lookup"><span data-stu-id="a90ac-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="a90ac-107">Дополнительные сведения об этих методах см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="a90ac-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="a90ac-108">Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="a90ac-109">Создание пользовательского типа конфиденциальной информации для защиты от потери данных с помощью точного совпадения данных (EDM)</span><span class="sxs-lookup"><span data-stu-id="a90ac-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="a90ac-110">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a90ac-110">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="a90ac-111">Чтобы создать, тестировать и развернуть собственный тип конфиденциальной информации с помощью пользовательского интерфейса, необходимы разрешения глобального администратора или администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a90ac-111">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="a90ac-112">См. [сведения о ролях администраторов](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a90ac-112">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="a90ac-113">У вашей организации должна быть подписка, например на Office 365 корпоративный, включающая защиту от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="a90ac-113">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="a90ac-114">См. статью [Описание политики обмена сообщениями и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span><span class="sxs-lookup"><span data-stu-id="a90ac-114">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="a90ac-p105">Для работы с пользовательскими типами конфиденциальной информации вы должны быть знакомы с регулярными выражениями (RegEx). Дополнительные сведения о модуле Boost.RegEx (прежнее название — RegEx++), используемом для обработки текста, см. в статье [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p105">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="a90ac-117">Центр обслуживания клиентов Майкрософт не может оказывать помощь при создании пользовательских категорий или шаблонов регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="a90ac-117">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="a90ac-118">Инженеры службы поддержки могут оказывать ограниченную поддержку по этой функции, например предоставлять примеры шаблонов регулярных выражений для тестирования или помогать с устранением неполадок имеющегося шаблона, который не срабатывает должным образом, но не могут гарантировать, что то или иное решение для сопоставления контента будет соответствовать вашим требованиям или обязательствам.</span><span class="sxs-lookup"><span data-stu-id="a90ac-118">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="a90ac-119">В службе защиты от потери данных используется агент данных для выявления и классификации конфиденциальной информации на сайтах SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a90ac-119">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="a90ac-120">Для выявления в имеющемся контенте элементов, относящихся к новому пользовательскому типу конфиденциальной информации, необходимо заново выполнить его обход.</span><span class="sxs-lookup"><span data-stu-id="a90ac-120">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="a90ac-121">Обход контента выполняется по расписанию, но вы можете повторно выполнить обход контента вручную для семейства веб-сайтов, списка или библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a90ac-121">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="a90ac-122">Дополнительные сведения см. в статье [Ручной запрос обхода контента и переиндексации сайта, библиотеки или списка](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="a90ac-122">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a90ac-123">Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-123">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="a90ac-124">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации** и нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-124">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="a90ac-125">Параметры не требуют особых пояснений и описываются на соответствующей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="a90ac-125">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="a90ac-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="a90ac-126">**Name**</span></span>

- <span data-ttu-id="a90ac-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a90ac-127">**Description**</span></span>

- <span data-ttu-id="a90ac-128">**Расстояние**</span><span class="sxs-lookup"><span data-stu-id="a90ac-128">**Proximity**</span></span>

- <span data-ttu-id="a90ac-129">**Уровень вероятности**</span><span class="sxs-lookup"><span data-stu-id="a90ac-129">**Confidence level**</span></span>

- <span data-ttu-id="a90ac-130">**Элемент основного шаблона** (ключевые слова, регулярное выражение или словарь)</span><span class="sxs-lookup"><span data-stu-id="a90ac-130">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="a90ac-131">Необязательные **элементы вспомогательного шаблона** (ключевые слова, регулярное выражение или словарь) и соответствующее значение **минимальной стоимости**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-131">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="a90ac-p108">Предположим, вам нужен пользовательский тип конфиденциальной информации, обнаруживающий в контенте 9-значные номера сотрудников, а также ключевые слова "сотрудник", "ИД" и "бейдж". Чтобы создать этот тип, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a90ac-p108">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="a90ac-134">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации** и нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-134">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Создать"](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="a90ac-136">На открывшейся странице **Выберите имя и описание** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a90ac-136">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="a90ac-137">**Имя**: "ИД сотрудника".</span><span class="sxs-lookup"><span data-stu-id="a90ac-137">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="a90ac-138">**Описание**: "Обнаружение девятизначных кодов сотрудников Contoso".</span><span class="sxs-lookup"><span data-stu-id="a90ac-138">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Страница имени и описания](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="a90ac-140">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-140">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="a90ac-141">На открывшейся странице **Требования для сопоставления** нажмите **Добавить элемент** и настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="a90ac-141">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="a90ac-142">Чтобы настроить **Обнаруживать контент, содержащий**:</span><span class="sxs-lookup"><span data-stu-id="a90ac-142">**Detect content containing**:</span></span>
 
      <span data-ttu-id="a90ac-p109">Щелкните **Любое из указанных** и выберите **Регулярное выражение**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-p109">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="a90ac-p110">В поле регулярного выражения введите `(\s)(\d{9})(\s)` (девятизначное число с пробелами с обеих сторон).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p110">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="a90ac-147">Чтобы настроить **Вспомогательные элементы**, нажмите **Добавить вспомогательные элементы** и выберите **Содержит этот список ключевых слов**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-147">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="a90ac-148">В открывшейся области **Содержит этот список ключевых слов** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="a90ac-148">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="a90ac-149">**Список ключевых слов.** Введите следующее значение: сотрудник,ИД,бейдж.</span><span class="sxs-lookup"><span data-stu-id="a90ac-149">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="a90ac-150">**Минимальное количество.** Оставьте значение по умолчанию (1).</span><span class="sxs-lookup"><span data-stu-id="a90ac-150">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="a90ac-151">Оставьте для параметра **Уровень вероятности** значение по умолчанию (60).</span><span class="sxs-lookup"><span data-stu-id="a90ac-151">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="a90ac-152">Оставьте для параметра **Расстояние между символами** значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="a90ac-152">Leave the default **Character proximity** value 300.</span></span>

    ![Страница "Требования для сопоставления"](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="a90ac-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a90ac-155">На открывшейся странице **Проверка и завершение** проверьте параметры и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-155">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Страница "Проверка и завершение"](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="a90ac-p111">На следующей странице вам предлагается протестировать новый тип конфиденциальной информации, нажав кнопку **Да**. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center). Чтобы протестировать правило позже, нажмите кнопку **Нет**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-p111">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Страница с рекомендацией провести тестирование](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a90ac-161">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="a90ac-161">How do you know this worked?</span></span>

<span data-ttu-id="a90ac-162">Чтобы убедиться, что вы успешно создали новый тип конфиденциальной информации, выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a90ac-162">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="a90ac-163">Откройте раздел **Классификации** \> **Типы конфиденциальной информации** и убедитесь, что новый тип присутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="a90ac-163">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="a90ac-p112">Протестируйте новый тип конфиденциальной информации. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p112">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a90ac-166">Редактирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-166">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="a90ac-167">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-167">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="a90ac-p113">Редактировать можно только пользовательские типы конфиденциальной информации. Изменить встроенный тип невозможно. Однако вы можете использовать PowerShell, чтобы экспортировать встроенные типы конфиденциальной информации, настроить их и импортировать в качестве пользовательских типов. Дополнительные сведения см. в статье [Настройка встроенных типов конфиденциальной информации](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p113">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="a90ac-p114">Редактировать можно только пользовательские типы конфиденциальной информации, созданные в интерфейсе. Если вы использовали [процедуру PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) для импорта пакета правил с типом пользовательской конфиденциальной информации, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a90ac-p114">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="a90ac-173">В Центре безопасности и соответствия требованиям откройте раздел **Классификации** \> **Типы конфиденциальной информации**, выберите нужный пользовательский тип и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-173">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Изменить"](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="a90ac-p115">При этом доступны те же параметры, что и при создании типа конфиденциальной информации в Центре безопасности и соответствия требованиям. Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p115">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a90ac-177">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="a90ac-177">How do you know this worked?</span></span>

<span data-ttu-id="a90ac-178">Чтобы убедиться, что вы успешно изменили тип конфиденциальной информации, выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a90ac-178">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="a90ac-179">Откройте раздел **Классификации** \> **Типы конфиденциальной информации** и проверьте параметры измененного типа.</span><span class="sxs-lookup"><span data-stu-id="a90ac-179">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="a90ac-p116">Протестируйте измененный тип конфиденциальной информации. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p116">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a90ac-182">Удаление пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-182">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="a90ac-183">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="a90ac-183">**Notes**:</span></span>

- <span data-ttu-id="a90ac-184">Удалять можно только пользовательские типы конфиденциальной информации. Удалить встроенный тип невозможно.</span><span class="sxs-lookup"><span data-stu-id="a90ac-184">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="a90ac-185">Перед удалением пользовательского типа конфиденциальной информации убедитесь, что политики защиты от потери данных и правила потока обработки почты Exchange (также называемые правилами транспорта) не ссылаются на этот тип.</span><span class="sxs-lookup"><span data-stu-id="a90ac-185">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="a90ac-186">В Центре безопасности и соответствия требованиям откройте раздел **Классификации** \> **Типы конфиденциальной информации** и выберите один или несколько пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="a90ac-186">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="a90ac-187">В открывшемся всплывающем окне нажмите **Удалить** (или **Удалить типы конфиденциальной информации**, если выбрано несколько типов).</span><span class="sxs-lookup"><span data-stu-id="a90ac-187">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Удалить"](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="a90ac-189">В появившемся предупреждающем сообщении нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-189">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a90ac-190">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="a90ac-190">How do you know this worked?</span></span>

<span data-ttu-id="a90ac-191">Чтобы убедиться, что вы успешно удалили пользовательский тип конфиденциальной информации, откройте раздел **Классификации** \> **Типы конфиденциальной информации** и проверьте, исчез ли этот тип из списка.</span><span class="sxs-lookup"><span data-stu-id="a90ac-191">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a90ac-192">Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a90ac-192">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a90ac-193">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="a90ac-p117">Выберите один или несколько типов конфиденциальной информации. В появившемся всплывающем окне нажмите **Тестировать тип** (или **Тестировать типы конфиденциальной информации**, если выбрано несколько типов).</span><span class="sxs-lookup"><span data-stu-id="a90ac-p117">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Тестировать тип"](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="a90ac-197">На открывшейся странице **Добавление файла для тестирования** отправьте документ на проверку, перетащив файл или нажав кнопку **Обзор** и выбрав файл.</span><span class="sxs-lookup"><span data-stu-id="a90ac-197">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Страница "Добавление файла для тестирования"](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="a90ac-199">Нажмите кнопку **Тестировать**, чтобы проверить документ на совпадения с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="a90ac-199">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="a90ac-200">На странице **Результаты проверки соответствия** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a90ac-200">On the **Match results** page, click **Finish**.</span></span>

    ![Результаты проверки соответствия](../media/scc-cust-sens-info-type-test-results.png)
