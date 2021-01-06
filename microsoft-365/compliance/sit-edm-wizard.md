---
title: Использование мастера для схемы точного соответствия данных и типа конфиденциальной информации
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как использовать мастер для схемы точного соответствия данных и типа конфиденциальной информации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699158"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="b68f8-103">Использование мастера для схемы точного соответствия данных и типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="b68f8-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="b68f8-104">[Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) выполняется в несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="b68f8-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="b68f8-105">С помощью этого мастера можно создать файлы схемы и шаблона для типа конфиденциальной информации (пакет правил), чтобы упростить процесс.</span><span class="sxs-lookup"><span data-stu-id="b68f8-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="b68f8-106">Мастер схемы точного соответствия данных и типа конфиденциальной информации доступен только для облаков World Wide и GCC.</span><span class="sxs-lookup"><span data-stu-id="b68f8-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="b68f8-107">Этот мастер можно использовать вместо перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="b68f8-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="b68f8-108">Определение схемы для базы данных конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="b68f8-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="b68f8-109">Настройка шаблона (пакета правил)</span><span class="sxs-lookup"><span data-stu-id="b68f8-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="b68f8-110">Шаги в [части 1: "Настройка классификации на основе EDM"](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="b68f8-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="b68f8-111">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="b68f8-111">Pre-requisites</span></span>

1. <span data-ttu-id="b68f8-112">Ознакомьтесь с пошаговыми инструкциями по созданию настраиваемого типа конфиденциальной информации с помощью [быстрого обзора рабочего процесса](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) EDM.</span><span class="sxs-lookup"><span data-stu-id="b68f8-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="b68f8-113">Выполните шаги, описанные в разделе [Сохранение конфиденциальных данных в формате .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="b68f8-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="b68f8-114">Использование мастера схемы точного соответствия данных и шаблона типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="b68f8-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="b68f8-115">В центре Соответствия требованиям Microsoft 365 для вашего клиента перейдите к пункту **Классификация данных** > **Точное соответствие данных**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="b68f8-116">Выберите **Создание схемы EDM**, чтобы открыть всплывающее окно конфигурации мастера схемы.</span><span class="sxs-lookup"><span data-stu-id="b68f8-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Всплывающее окно конфигурации мастера создания схемы EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="b68f8-118">Введите соответствующее **Имя** и **Описание**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="b68f8-119">Чтобы сделать это, выберите пункт **Игнорировать разделители и знаки пунктуации для всех полей схемы**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="b68f8-120">Дополнительные сведения о настройке EDM для игнорирования регистра дела или разделителя см. в статье [Создание пользовательского типа конфиденциальной информации с помощью классификации основанной на точности соответствия данных (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="b68f8-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="b68f8-121">Введите нужные значения в **Поле схемы 1** и при необходимости добавьте дополнительные поля.</span><span class="sxs-lookup"><span data-stu-id="b68f8-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b68f8-122">От одного до пяти полей схемы нужно указать как доступные для поиска.</span><span class="sxs-lookup"><span data-stu-id="b68f8-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="b68f8-123">Нажмите кнопку "Сохранить".</span><span class="sxs-lookup"><span data-stu-id="b68f8-123">Choose save.</span></span> <span data-ttu-id="b68f8-124">После этого схема будет указана в списке.</span><span class="sxs-lookup"><span data-stu-id="b68f8-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="b68f8-125">Выберите **Типы конфиденциальной информации EDM** и **Создать тип конфиденциальной информации EDM**, чтобы открыть мастер настройки типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="b68f8-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="b68f8-126">Нажмите **Выбрать существующую схему EDM** и выберите схему, созданную при выполнении шагов 2–6 из списка.</span><span class="sxs-lookup"><span data-stu-id="b68f8-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="b68f8-127">Нажмите **Далее** и выберите **Создать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="b68f8-128">Выберите **Доверительный уровень** и **Основной элемент**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="b68f8-129">Дополнительные сведения о настройке шаблона см. в статье [Создание пользовательского типа конфиденциальной информации в Центре соответствия требованиям](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="b68f8-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="b68f8-130">Выберите **Тип конфиденциальной информации основного элемента** для ассоциации.</span><span class="sxs-lookup"><span data-stu-id="b68f8-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="b68f8-131">Дополнительные сведения о доступных типах конфиденциальной информации см. в статье [Определения сущностей типов конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="b68f8-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="b68f8-132">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-132">Choose **Done**.</span></span>

13. <span data-ttu-id="b68f8-133">Выберите необходимый **Доверительный уровень и расстояние между символами**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="b68f8-134">Это значение будет использоваться по умолчанию для всех типов конфиденциальной информации EDM</span><span class="sxs-lookup"><span data-stu-id="b68f8-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="b68f8-135">Выберите **Создать шаблон**, если хотите создать дополнительные шаблоны для типа конфиденциальной информации EDM.</span><span class="sxs-lookup"><span data-stu-id="b68f8-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="b68f8-136">Нажмите **Далее**, введите **Имя** и **Описание для администраторов**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="b68f8-137">Проверьте информацию и нажмите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="b68f8-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="b68f8-138">Чтобы удалить или изменить шаблон типа конфиденциальной информации, выберите его, после чего на экран будут выведены элементы управления для изменения и удаления.</span><span class="sxs-lookup"><span data-stu-id="b68f8-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b68f8-139">Чтобы удалить схему, уже связанную с типом конфиденциальной информации EDM, нужно сначала удалить тип конфиденциальной информации, после чего можно будет удалить схему.</span><span class="sxs-lookup"><span data-stu-id="b68f8-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="b68f8-140">Шаги публикации</span><span class="sxs-lookup"><span data-stu-id="b68f8-140">Post steps</span></span>

<span data-ttu-id="b68f8-141">После использования этого мастера для создания файлов схемы и шаблона EDM (пакета правил) необходимо выполнить шаги, описанные в [ части 2: "Хеширование и отправка конфиденциальных данных"](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data), затем можно будет применять пользовательский тип конфиденциальных данных EDM.</span><span class="sxs-lookup"><span data-stu-id="b68f8-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>