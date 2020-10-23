---
title: Пользовательские типы конфиденциальной информации для защиты от потери данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Обзор пользовательских типов конфиденциальной информации для защиты от потери данных, таких как основной шаблон, расстояние между символами и уровень вероятности.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e414d9a31869e9b1382f0713d6d70df745c41471
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681767"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="79a36-103">Пользовательские типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="79a36-103">Custom sensitive information types</span></span>

<span data-ttu-id="79a36-104">Microsoft 365 содержит множество встроенных типов конфиденциальной информации, готовых к использованию в вашей организации, например для [защиты от потери данных](data-loss-prevention-policies.md) (DLP) или [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="79a36-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="79a36-105">Встроенные типы конфиденциальной информации помогают определять и защищать номера кредитных карт, номера банковских счетов, номера паспортов и многое другое на основе закономерностей, определенных регулярным выражением (regex) или функцией.</span><span class="sxs-lookup"><span data-stu-id="79a36-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="79a36-106">Дополнительные сведения см. в статье [Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79a36-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="79a36-107">Но что если вам нужно обнаруживать и защищать конфиденциальную информацию другого типа, например идентификаторы сотрудников или номера проектов с использованием особого формата в вашей организации?</span><span class="sxs-lookup"><span data-stu-id="79a36-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="79a36-108">Для этого вы можете создать пользовательский тип конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="79a36-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="79a36-109">Основные компоненты пользовательского типа конфиденциальной информации:</span><span class="sxs-lookup"><span data-stu-id="79a36-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="79a36-110">**Основной шаблон**: коды сотрудников, номера проектов и т. д. Как правило, он определяется регулярным выражением (RegEx), но также может представлять собой список ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="79a36-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="79a36-p103">**Дополнительные признаки.** Допустим, вы рассматриваете девятизначный код сотрудника. Не все девятизначные числа являются идентификаторами сотрудников, поэтому вы можете искать дополнительный текст: ключевые слова (например, "сотрудник", "бейдж", "ИД") или другие текстовые шаблоны, основанные на дополнительных регулярных выражениях. Дополнительные признаки (также называемые _вспомогательными_ или _подтверждающими_ признаками) повышают вероятность того, что девятизначный номер в содержимом действительно является кодом сотрудника.</span><span class="sxs-lookup"><span data-stu-id="79a36-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="79a36-p104">**Расстояние между символами.** Будет логично предположить, что чем ближе основной шаблон и вспомогательные признаки друг к другу, тем вероятнее, что обнаруженный контент будет именно тем, что вам нужно. Вы можете задать расстояние в символах между основным шаблоном и вспомогательными признаками (также называемое _интервалом вероятности_), как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="79a36-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Схема подтверждающего признака и интервала вероятности](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="79a36-p105">**Уровень вероятности.** Чем больше вспомогательных признаков, тем выше вероятность того, что обнаруженное совпадение относится к конфиденциальным данным. Вы можете назначать более высокие уровни вероятности для совпадений, обнаруженных по большему количеству признаков.</span><span class="sxs-lookup"><span data-stu-id="79a36-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="79a36-p106">При выполнении условия шаблон возвращает значения количества и уровня вероятности, которые вы можете использовать в условиях политик защиты от потери данных. Добавляя условие для обнаружения типа конфиденциальной информации в политику защиты от потери данных, вы можете изменить значения количества и уровня вероятности, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="79a36-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Пример параметров количества и точности совпадения](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="79a36-122">Создание пользовательских типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="79a36-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="79a36-123">Создать пользовательский тип конфиденциальной информации для защиты от потери данных в Центре безопасности и соответствия требованиям можно с помощью нескольких вариантов:</span><span class="sxs-lookup"><span data-stu-id="79a36-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="79a36-124">**С помощью EDM.** вы можете настроить пользовательские типы конфиденциальной информации с использованием классификации на основе точного совпадения данных (EDM).</span><span class="sxs-lookup"><span data-stu-id="79a36-124">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="79a36-125">Этот метод позволяет создать динамический тип конфиденциальной информации с помощью защищенной базы данных, которую можно периодически обновлять.</span><span class="sxs-lookup"><span data-stu-id="79a36-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="79a36-126">См. статью [Создание пользовательского типа конфиденциальной информации с помощью классификации на основе точного совпадения данных](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="79a36-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="79a36-127">**С помощью PowerShell.** Вы можете настроить пользовательские типы конфиденциальной информации с использованием PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79a36-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="79a36-128">Хотя этот метод сложнее, чем использование пользовательского интерфейса, он предоставляет дополнительные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="79a36-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="79a36-129">См. статью [Создание пользовательского типа конфиденциальной информации в PowerShell Центра безопасности и соответствия требованиям](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="79a36-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="79a36-130">**С помощью пользовательского интерфейса.** Вы можете настроить пользовательский тип конфиденциальной информации, используя пользовательский интерфейс Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="79a36-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="79a36-131">В этом методе можно использовать регулярные выражения, ключевые слова и словари ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="79a36-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="79a36-132">Дополнительные сведения см. в статье [Создание пользовательского типа конфиденциальной информации](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="79a36-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79a36-133">Служба защиты информации Microsoft 365 теперь в предварительный версии поддерживает языки с набором двухбайтовых символов:</span><span class="sxs-lookup"><span data-stu-id="79a36-133">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="79a36-134">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="79a36-134">Chinese (simplified)</span></span>
> - <span data-ttu-id="79a36-135">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="79a36-135">Chinese (traditional)</span></span>
> - <span data-ttu-id="79a36-136">Корейский</span><span class="sxs-lookup"><span data-stu-id="79a36-136">Korean</span></span>
> - <span data-ttu-id="79a36-137">Японский</span><span class="sxs-lookup"><span data-stu-id="79a36-137">Japanese</span></span>

><span data-ttu-id="79a36-138">Эта поддержка доступна для конфиденциальных типов информации.</span><span class="sxs-lookup"><span data-stu-id="79a36-138">This support is available for sensitive information types.</span></span> <span data-ttu-id="79a36-139">Дополнительные сведения см. в статье [Заметки о выпуске: поддержка защиты информации для наборов двухбайтовых символов (предварительная версия)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="79a36-139">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

