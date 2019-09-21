---
title: Настройка параметров поиска и аналитики
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0456ee21087c7fe05c3ef96d517feb468c7cfe5e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089824"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="b1929-102">Настройка параметров поиска и аналитики</span><span class="sxs-lookup"><span data-stu-id="b1929-102">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="b1929-103">Почти повторяющиеся элементы и почтовые потоки</span><span class="sxs-lookup"><span data-stu-id="b1929-103">Near duplicates and email threading</span></span>

<span data-ttu-id="b1929-104">В этом разделе можно задать параметры обнаружения дубликатов, поиска повторяющихся сообщений и почтовых потоков.</span><span class="sxs-lookup"><span data-stu-id="b1929-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="b1929-105">Enable/Disable: Включение обнаружения повторяющихся данных, Поиск повторяющихся данных и цепочка электронной почты в составе потока анализа, если она включена.</span><span class="sxs-lookup"><span data-stu-id="b1929-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="b1929-106">Так как они создаются поверх остальных, их необходимо включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="b1929-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="b1929-107">Пороговое значение: Если уровень сходства двух документов превышает пороговое значение, они будут помещены в один и тот же самый близкий к дублированному набору.</span><span class="sxs-lookup"><span data-stu-id="b1929-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="b1929-108">Скрывать дубликаты по умолчанию: Если этот параметр включен, то по умолчанию в рабочем наборе будет применен фильтр для скрытия повторяющихся документов.</span><span class="sxs-lookup"><span data-stu-id="b1929-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="b1929-109">При необходимости фильтр можно удалить вручную в рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="b1929-109">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="b1929-110">Минимальное и максимальное число слов: почти повторяющиеся и почтовые цепочки будут выполняться только для документов, в которых минимальное количество слов и не превышает максимальное число слов.</span><span class="sxs-lookup"><span data-stu-id="b1929-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="b1929-111">Дополнительные сведения см. в статье [Обнаружение повторяющихся](near-duplicates.md) данных и [цепочка электронной почты](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="b1929-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="b1929-112">темы;</span><span class="sxs-lookup"><span data-stu-id="b1929-112">Themes</span></span>

<span data-ttu-id="b1929-113">В этом разделе можно задать параметры для тем.</span><span class="sxs-lookup"><span data-stu-id="b1929-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="b1929-114">Enable/Disable: включает кластеризацию тем в составе процесса аналитики, если она включена.</span><span class="sxs-lookup"><span data-stu-id="b1929-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="b1929-115">Динамическое изменение максимального числа тем: в некоторых случаях недостаточно документов для создания требуемого количества тем.</span><span class="sxs-lookup"><span data-stu-id="b1929-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="b1929-116">Если этот параметр включен, то вместо того, чтобы пытаться задать максимально допустимое число тем, система настраивает максимальное число тем динамически.</span><span class="sxs-lookup"><span data-stu-id="b1929-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="b1929-117">Максимальное число тем: необходимое количество тем</span><span class="sxs-lookup"><span data-stu-id="b1929-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="b1929-118">Включить числа в темы: Если этот параметр включен, при формировании тем будут включены цифры.</span><span class="sxs-lookup"><span data-stu-id="b1929-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="b1929-119">Оптическое распознавание текста (OCR)</span><span class="sxs-lookup"><span data-stu-id="b1929-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="b1929-120">Если этот параметр включен, распознавание текста выполняется для изображений, которые используются в рабочих множествах и могут быть доступны для поиска.</span><span class="sxs-lookup"><span data-stu-id="b1929-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="b1929-121">Игнорировать текст</span><span class="sxs-lookup"><span data-stu-id="b1929-121">Ignore text</span></span>

<span data-ttu-id="b1929-122">Существуют экземпляры, в которых определенные тексты будут отойти от качества аналитик, таких как длительные заявления об отказе, которые добавляются к определенным сообщениям электронной почты независимо от их содержимого.</span><span class="sxs-lookup"><span data-stu-id="b1929-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="b1929-123">Если вы помните о таких случаях, вы можете исключить этот текст из аналитики, указав текст (поддерживается регулярное выражение), а также модули, для которых необходимо исключить текст.</span><span class="sxs-lookup"><span data-stu-id="b1929-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>