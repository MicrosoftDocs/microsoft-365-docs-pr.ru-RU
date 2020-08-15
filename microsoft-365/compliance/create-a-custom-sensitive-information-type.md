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
ms.openlocfilehash: 0c54cd9d4969c87bbd83b3048883d8a84dd9bc59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686663"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="7ae8b-103">Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="7ae8b-104">Ознакомьтесь с этой статьей, чтобы создать пользовательский тип конфиденциальной информации в Центре безопасности и соответствия требованиям ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-104">Read this article to create a custom sensitive information type in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="7ae8b-105">Пользовательские типы конфиденциальной информации, создаваемые этим методом, добавляются в пакет правил `Microsoft.SCCManaged.CustomRulePack`.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="7ae8b-106">Вы также можете создавать пользовательские типы конфиденциальной информации с помощью PowerShell и функций точного совпадения данных.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="7ae8b-107">Дополнительные сведения об этих методах см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="7ae8b-108">Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="7ae8b-109">Создание пользовательского типа конфиденциальной информации для защиты от потери данных с помощью точного совпадения данных (EDM)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

> [!NOTE]
> <span data-ttu-id="7ae8b-110">Служба защиты информации Microsoft 365 теперь поддерживает в предварительный версии языки с  	набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="7ae8b-111">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="7ae8b-112">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="7ae8b-113">Корейский</span><span class="sxs-lookup"><span data-stu-id="7ae8b-113">Korean</span></span>
> - <span data-ttu-id="7ae8b-114">Японский</span><span class="sxs-lookup"><span data-stu-id="7ae8b-114">Japanese</span></span>
> 
><span data-ttu-id="7ae8b-115">Эта предварительная версия доступна только в коммерческом облаке, а развертывание ограничено следующими странами:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-115">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="7ae8b-116">Япония</span><span class="sxs-lookup"><span data-stu-id="7ae8b-116">Japan</span></span>
> - <span data-ttu-id="7ae8b-117">Республика Корея</span><span class="sxs-lookup"><span data-stu-id="7ae8b-117">Korea</span></span>
> - <span data-ttu-id="7ae8b-118">Китай</span><span class="sxs-lookup"><span data-stu-id="7ae8b-118">China</span></span>
> - <span data-ttu-id="7ae8b-119">Гонконг (САР)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-119">Hong Kong</span></span>
> - <span data-ttu-id="7ae8b-120">Макао (САР)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-120">Macau</span></span>
> - <span data-ttu-id="7ae8b-121">Тайвань</span><span class="sxs-lookup"><span data-stu-id="7ae8b-121">Taiwan</span></span>
>
><span data-ttu-id="7ae8b-122">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-122">This support is available for sensitive information types.</span></span> <span data-ttu-id="7ae8b-123">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-123">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ae8b-124">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7ae8b-124">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="7ae8b-125">Чтобы создать, тестировать и развернуть собственный тип конфиденциальной информации с помощью пользовательского интерфейса, необходимы разрешения глобального администратора или администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-125">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="7ae8b-126">См. [сведения о ролях администраторов](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-126">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="7ae8b-127">У вашей организации должна быть подписка, например на Office 365 корпоративный, включающая защиту от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-127">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="7ae8b-128">См. статью [Описание политики обмена сообщениями и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-128">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="7ae8b-p106">Для работы с пользовательскими типами конфиденциальной информации вы должны быть знакомы с регулярными выражениями (RegEx). Дополнительные сведения о модуле Boost.RegEx (прежнее название — RegEx++), используемом для обработки текста, см. в статье [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p106">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="7ae8b-131">Центр обслуживания клиентов Майкрософт не может оказывать помощь при создании пользовательских категорий или шаблонов регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-131">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="7ae8b-132">Инженеры службы поддержки могут оказывать ограниченную поддержку по этой функции, например предоставлять примеры шаблонов регулярных выражений для тестирования или помогать с устранением неполадок имеющегося шаблона, который не срабатывает должным образом, но не могут гарантировать, что то или иное решение для сопоставления контента будет соответствовать вашим требованиям или обязательствам.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-132">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="7ae8b-133">В службе защиты от потери данных используется агент данных для выявления и классификации конфиденциальной информации на сайтах SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-133">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="7ae8b-134">Для выявления в имеющемся контенте элементов, относящихся к новому пользовательскому типу конфиденциальной информации, необходимо заново выполнить его обход.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-134">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="7ae8b-135">Обход контента выполняется по расписанию, но вы можете повторно выполнить обход контента вручную для семейства веб-сайтов, списка или библиотеки.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-135">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="7ae8b-136">Дополнительные сведения см. в статье [Ручной запрос обхода контента и переиндексации сайта, библиотеки или списка](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-136">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="7ae8b-137">Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-137">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="7ae8b-138">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации** и нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-138">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="7ae8b-139">Параметры не требуют особых пояснений и описываются на соответствующей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-139">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="7ae8b-140">**Имя**</span><span class="sxs-lookup"><span data-stu-id="7ae8b-140">**Name**</span></span>

- <span data-ttu-id="7ae8b-141">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7ae8b-141">**Description**</span></span>

- <span data-ttu-id="7ae8b-142">**Расстояние**</span><span class="sxs-lookup"><span data-stu-id="7ae8b-142">**Proximity**</span></span>

- <span data-ttu-id="7ae8b-143">**Уровень вероятности**</span><span class="sxs-lookup"><span data-stu-id="7ae8b-143">**Confidence level**</span></span>

- <span data-ttu-id="7ae8b-144">**Элемент основного шаблона** (ключевые слова, регулярное выражение или словарь)</span><span class="sxs-lookup"><span data-stu-id="7ae8b-144">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="7ae8b-145">Необязательные **элементы вспомогательного шаблона** (ключевые слова, регулярное выражение или словарь) и соответствующее значение **минимальной стоимости**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-145">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="7ae8b-p109">Предположим, вам нужен пользовательский тип конфиденциальной информации, обнаруживающий в контенте 9-значные номера сотрудников, а также ключевые слова "сотрудник", "ИД" и "бейдж". Чтобы создать этот тип, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p109">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="7ae8b-148">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации** и нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-148">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Создать"](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="7ae8b-150">На открывшейся странице **Выберите имя и описание** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-150">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="7ae8b-151">**Имя**: "ИД сотрудника".</span><span class="sxs-lookup"><span data-stu-id="7ae8b-151">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="7ae8b-152">**Описание**: "Обнаружение девятизначных кодов сотрудников Contoso".</span><span class="sxs-lookup"><span data-stu-id="7ae8b-152">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Страница имени и описания](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="7ae8b-154">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-154">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="7ae8b-155">На открывшейся странице **Требования для сопоставления** нажмите **Добавить элемент** и настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-155">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="7ae8b-156">Чтобы настроить **Обнаруживать контент, содержащий**:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-156">**Detect content containing**:</span></span>
 
      <span data-ttu-id="7ae8b-p110">Щелкните **Любое из указанных** и выберите **Регулярное выражение**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p110">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="7ae8b-p111">В поле регулярного выражения введите `(\s)(\d{9})(\s)` (девятизначное число с пробелами с обеих сторон).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p111">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="7ae8b-161">Чтобы настроить **Вспомогательные элементы**, нажмите **Добавить вспомогательные элементы** и выберите **Содержит этот список ключевых слов**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-161">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="7ae8b-162">В открывшейся области **Содержит этот список ключевых слов** настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-162">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="7ae8b-163">**Список ключевых слов.** Введите следующее значение: сотрудник,ИД,бейдж.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-163">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="7ae8b-164">**Минимальное количество.** Оставьте значение по умолчанию (1).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-164">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="7ae8b-165">Оставьте для параметра **Уровень вероятности** значение по умолчанию (60).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-165">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="7ae8b-166">Оставьте для параметра **Расстояние между символами** значение по умолчанию (300).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-166">Leave the default **Character proximity** value 300.</span></span>

    ![Страница "Требования для сопоставления"](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="7ae8b-168">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-168">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7ae8b-169">На открывшейся странице **Проверка и завершение** проверьте параметры и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-169">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Страница "Проверка и завершение"](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="7ae8b-p112">На следующей странице вам предлагается протестировать новый тип конфиденциальной информации, нажав кнопку **Да**. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center). Чтобы протестировать правило позже, нажмите кнопку **Нет**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p112">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Страница с рекомендацией провести тестирование](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ae8b-175">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="7ae8b-175">How do you know this worked?</span></span>

<span data-ttu-id="7ae8b-176">Чтобы убедиться, что вы успешно создали новый тип конфиденциальной информации, выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-176">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="7ae8b-177">Откройте раздел **Классификации** \> **Типы конфиденциальной информации** и убедитесь, что новый тип присутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-177">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="7ae8b-p113">Протестируйте новый тип конфиденциальной информации. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p113">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="7ae8b-180">Редактирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-180">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="7ae8b-181">**Примечания**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-181">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="7ae8b-p114">Редактировать можно только пользовательские типы конфиденциальной информации. Изменить встроенный тип невозможно. Однако вы можете использовать PowerShell, чтобы экспортировать встроенные типы конфиденциальной информации, настроить их и импортировать в качестве пользовательских типов. Дополнительные сведения см. в статье [Настройка встроенных типов конфиденциальной информации](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p114">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="7ae8b-p115">Редактировать можно только пользовательские типы конфиденциальной информации, созданные в интерфейсе. Если вы использовали [процедуру PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) для импорта пакета правил с типом пользовательской конфиденциальной информации, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p115">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="7ae8b-187">В Центре безопасности и соответствия требованиям откройте раздел **Классификации** \> **Типы конфиденциальной информации**, выберите нужный пользовательский тип и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-187">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Изменить"](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="7ae8b-p116">При этом доступны те же параметры, что и при создании типа конфиденциальной информации в Центре безопасности и соответствия требованиям. Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p116">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ae8b-191">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="7ae8b-191">How do you know this worked?</span></span>

<span data-ttu-id="7ae8b-192">Чтобы убедиться, что вы успешно изменили тип конфиденциальной информации, выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-192">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="7ae8b-193">Откройте раздел **Классификации** \> **Типы конфиденциальной информации** и проверьте параметры измененного типа.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-193">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="7ae8b-p117">Протестируйте измененный тип конфиденциальной информации. Дополнительные сведения см. в статье [Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p117">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="7ae8b-196">Удаление пользовательского типа конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-196">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="7ae8b-197">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="7ae8b-197">**Notes**:</span></span>

- <span data-ttu-id="7ae8b-198">Удалять можно только пользовательские типы конфиденциальной информации. Удалить встроенный тип невозможно.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-198">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="7ae8b-199">Перед удалением пользовательского типа конфиденциальной информации убедитесь, что политики защиты от потери данных и правила потока обработки почты Exchange (также называемые правилами транспорта) не ссылаются на этот тип.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-199">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="7ae8b-200">В Центре безопасности и соответствия требованиям откройте раздел **Классификации** \> **Типы конфиденциальной информации** и выберите один или несколько пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-200">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="7ae8b-201">В открывшемся всплывающем окне нажмите **Удалить** (или **Удалить типы конфиденциальной информации**, если выбрано несколько типов).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-201">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Удалить"](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="7ae8b-203">В появившемся предупреждающем сообщении нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-203">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ae8b-204">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="7ae8b-204">How do you know this worked?</span></span>

<span data-ttu-id="7ae8b-205">Чтобы убедиться, что вы успешно удалили пользовательский тип конфиденциальной информации, откройте раздел **Классификации** \> **Типы конфиденциальной информации** и проверьте, исчез ли этот тип из списка.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-205">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="7ae8b-206">Тестирование пользовательских типов конфиденциальной информации в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="7ae8b-206">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="7ae8b-207">В Центре безопасности и соответствия требованиям выберите **Классификации** \> **Типы конфиденциальной информации**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-207">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="7ae8b-p118">Выберите один или несколько типов конфиденциальной информации. В появившемся всплывающем окне нажмите **Тестировать тип** (или **Тестировать типы конфиденциальной информации**, если выбрано несколько типов).</span><span class="sxs-lookup"><span data-stu-id="7ae8b-p118">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Расположение элемента "Типы конфиденциальной информации" и кнопки "Тестировать тип"](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="7ae8b-211">На открывшейся странице **Добавление файла для тестирования** отправьте документ на проверку, перетащив файл или нажав кнопку **Обзор** и выбрав файл.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-211">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Страница "Добавление файла для тестирования"](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="7ae8b-213">Нажмите кнопку **Тестировать**, чтобы проверить документ на совпадения с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-213">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="7ae8b-214">На странице **Результаты проверки соответствия** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7ae8b-214">On the **Match results** page, click **Finish**.</span></span>

    ![Результаты проверки соответствия](../media/scc-cust-sens-info-type-test-results.png)
