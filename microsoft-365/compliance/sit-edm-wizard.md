---
title: Использование мастера для схемы точного соответствия данных и типа конфиденциальной информации
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как использовать мастер для схемы точного соответствия данных и типа конфиденциальной информации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861663"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="3c9ec-103">Использование мастера для схемы точного соответствия данных и типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="3c9ec-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="3c9ec-104">[Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) выполняется в несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="3c9ec-105">Вы можете использовать этот мастер для создания файлов шаблона схемы и типа конфиденциальной информации (SIT) (пакет правил), чтобы упростить процесс.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="3c9ec-106">Мастер схемы точного соответствия данных и типа конфиденциальной информации доступен только для облаков World Wide и GCC.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="3c9ec-107">Этот мастер можно использовать вместо перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="3c9ec-108">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="3c9ec-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="3c9ec-109">Настройка шаблона (пакета правил)</span><span class="sxs-lookup"><span data-stu-id="3c9ec-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="3c9ec-110">Шаги в [части 1: "Настройка классификации на основе EDM"](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="3c9ec-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="3c9ec-111">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="3c9ec-111">Pre-requisites</span></span>

1. <span data-ttu-id="3c9ec-112">Ознакомьтесь с пошаговыми инструкциями по созданию настраиваемого типа конфиденциальной информации с помощью [быстрого обзора рабочего процесса](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) EDM.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="3c9ec-113">Выполните шаги, описанные в разделе [Сохранение конфиденциальных данных в формате .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="3c9ec-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="3c9ec-114">Использование мастера схемы точного соответствия данных и шаблона типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="3c9ec-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="3c9ec-115">В центре Соответствия требованиям Microsoft 365 для вашего клиента перейдите к пункту **Классификация данных** > **Точное соответствие данных**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="3c9ec-116">Выберите **Создание схемы EDM**, чтобы открыть всплывающее окно конфигурации мастера схемы.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Всплывающее окно конфигурации мастера создания схемы EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="3c9ec-118">Введите соответствующее **Имя** и **Описание**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="3c9ec-119">Если вы хотите такое **поведение,** выберите игнорировать делимитеры и пунктуацию для всех полей схемы.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="3c9ec-120">Дополнительные сведения о настройке EDM для игнорирования делимитеров или делимитеров см. в примере Создание настраиваемого типа конфиденциальной информации с помощью классификации точного совпадения данных [(EDM).](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="3c9ec-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="3c9ec-121">Введите нужные значения в **Поле схемы 1** и при необходимости добавьте дополнительные поля.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3c9ec-122">От одного до пяти полей схемы нужно указать как доступные для поиска.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="3c9ec-123">Нажмите кнопку "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="3c9ec-123">Choose save.</span></span> <span data-ttu-id="3c9ec-124">После этого схема будет указана в списке.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="3c9ec-125">Выберите **Типы конфиденциальной информации EDM** и **Создать тип конфиденциальной информации EDM**, чтобы открыть мастер настройки типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="3c9ec-126">Нажмите **Выбрать существующую схему EDM** и выберите схему, созданную при выполнении шагов 2–6 из списка.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="3c9ec-127">Нажмите **Далее** и выберите **Создать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="3c9ec-128">Выберите **Доверительный уровень** и **Основной элемент**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="3c9ec-129">Дополнительные сведения о настройке шаблона см. в статье [Создание пользовательского типа конфиденциальной информации в Центре соответствия требованиям](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="3c9ec-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="3c9ec-130">Выберите **Тип конфиденциальной информации основного элемента** для ассоциации.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="3c9ec-131">Дополнительные сведения о доступных типах конфиденциальной информации см. в статье [Определения сущностей типов конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="3c9ec-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="3c9ec-132">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-132">Choose **Done**.</span></span>

13. <span data-ttu-id="3c9ec-133">Выберите необходимый **Доверительный уровень и расстояние между символами**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="3c9ec-134">Это значение будет использоваться по умолчанию для всех типов конфиденциальной информации EDM</span><span class="sxs-lookup"><span data-stu-id="3c9ec-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="3c9ec-135">Выберите **Создать шаблон,** если вы хотите создать дополнительные шаблоны для конфиденциального типа информации EDM.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="3c9ec-136">Нажмите **Далее**, введите **Имя** и **Описание для администраторов**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="3c9ec-137">Проверьте информацию и нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="3c9ec-138">Чтобы удалить или изменить шаблон типа конфиденциальной информации, выберите его, после чего на экран будут выведены элементы управления для изменения и удаления.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c9ec-139">Чтобы удалить схему, уже связанную с типом конфиденциальной информации EDM, нужно сначала удалить тип конфиденциальной информации, после чего можно будет удалить схему.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="3c9ec-140">Этапы создания публикации</span><span class="sxs-lookup"><span data-stu-id="3c9ec-140">Post creation steps</span></span>

<span data-ttu-id="3c9ec-141">После использования этого мастера для создания файлов схемы и шаблона EDM (пакета правил) необходимо выполнить шаги, описанные в [ части 2: "Хеширование и отправка конфиденциальных данных"](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data), затем можно будет применять пользовательский тип конфиденциальных данных EDM.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="3c9ec-142">После проверки правильной загрузки таблицы конфиденциальной информации можно проверить ее правильность.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="3c9ec-143">Open **Compliance Center** Data  >  **classification** Sensitive Information  >  **Types**.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="3c9ec-144">Выберите EDM SIT из списка, а затем **выберите Тест** в области вылетов.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="3c9ec-145">Upload элемент, содержащий данные, которые необходимо обнаружить, например создать элемент, содержащий некоторые данные в таблице конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="3c9ec-146">Если в схеме используется настраиваемая функция совпадения для определения проигнорированых делимитеров, убедитесь, что элемент содержит примеры с этими делимитерами и без них.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="3c9ec-147">После отправки и сканирования файла проверьте совпадения в EDM SIT.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="3c9ec-148">Если **функция Test** в SIT обнаруживает совпадение, убедитесь, что она не обрезка или извлечение некорректно.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="3c9ec-149">Например, извлекая только подстройку полной строки, которая должна быть обнаружена, или взяв только первое слово в строке с несколькими словами или включив дополнительные символы или символы в извлечении.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="3c9ec-150">См. [регулярный язык выражения — быстрая ссылка](/dotnet/standard/base-types/regular-expression-language-quick-reference) для ссылки на регулярный язык выражения.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="3c9ec-151">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="3c9ec-151">Troubleshooting</span></span>

<span data-ttu-id="3c9ec-152">Если вы не найдете совпадений, попробуйте следующее:</span><span class="sxs-lookup"><span data-stu-id="3c9ec-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="3c9ec-153">Подтверждение правильной загрузки конфиденциальных данных с помощью команд, которые указаны в руководстве по отправке конфиденциальных данных с помощью [средства EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="3c9ec-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="3c9ec-154">Убедитесь, что примеры, которые вы ввели в элемент, присутствуют в таблице конфиденциальной информации и правильно ли игнорируются делимитеры.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="3c9ec-155">**Проверьте** sit, который использовался при настройке основного элемента в каждом из шаблонов.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="3c9ec-156">Это подтвердит, что SIT может соответствовать примерам элемента.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="3c9ec-157">Если выбранный элемент SIT для основного элемента типа EDM не находит совпадений в элементе или находит меньше совпадений, чем ожидалось, проверьте, поддерживает ли он сепараторы и делимитеры, которые существуют в содержимом.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="3c9ec-158">Обязательно включите проигнорированые делимитеры, определенные в схеме.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="3c9ec-159">Если функция **Test** вообще не обнаруживает контент, проверьте, включает ли выбранный sit требования к дополнительным ключевым словам или другим проверкам.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="3c9ec-160">Для встроенных СИТ [](sensitive-information-type-entity-definitions.md) см. определения сущности типов конфиденциальной информации для проверки минимальных требований к каждому типу.</span><span class="sxs-lookup"><span data-stu-id="3c9ec-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
