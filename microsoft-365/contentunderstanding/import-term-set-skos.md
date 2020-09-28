---
title: Импорт набора терминов в формате, основанном на скос
description: Сведения о том, как импортировать набор терминов с использованием формата скос
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296076"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="42ca5-103">Импорт набора терминов в формате, основанном на скос</span><span class="sxs-lookup"><span data-stu-id="42ca5-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="42ca5-104">Вы можете импортировать набор терминов, используя формат на основе скос.</span><span class="sxs-lookup"><span data-stu-id="42ca5-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="42ca5-105">Подробные сведения о формате приведены в статье [скос Format таксономия SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="42ca5-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="42ca5-106">Рекомендуется хранить файлы импорта менее 20 000 терминов.</span><span class="sxs-lookup"><span data-stu-id="42ca5-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="42ca5-107">Большие файлы могут увеличить время, затрачиваемое на проверку и импорт.</span><span class="sxs-lookup"><span data-stu-id="42ca5-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="42ca5-108">В центре администрирования SharePoint разверните узел **службы контента**и выберите пункт **банк терминов**.</span><span class="sxs-lookup"><span data-stu-id="42ca5-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="42ca5-109">Выберите группу терминов, в которой нужно импортировать набор терминов.</span><span class="sxs-lookup"><span data-stu-id="42ca5-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="42ca5-110">На панели команд щелкните **Импорт набора терминов**.</span><span class="sxs-lookup"><span data-stu-id="42ca5-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="42ca5-111">Если вы хотите скачать пример файла для использования в качестве шаблона, нажмите **сампле-Метадата. TTL** , чтобы получить пример файла, в котором используется формат на основе скос.</span><span class="sxs-lookup"><span data-stu-id="42ca5-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="42ca5-112">Создайте файл импорта, содержащий набор терминов, & термины, которые вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="42ca5-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="42ca5-113">В разделе **Формат файла**выберите **скос (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="42ca5-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="42ca5-114">Нажмите кнопку **Обзор** и перейдите к файлу импорта и добавьте его.</span><span class="sxs-lookup"><span data-stu-id="42ca5-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="42ca5-115">Нажмите кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="42ca5-115">Click **Import**.</span></span> <span data-ttu-id="42ca5-116">Не закрывайте панель, пока не завершится импорт.</span><span class="sxs-lookup"><span data-stu-id="42ca5-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="42ca5-117">При успешном импорте файла отображается сообщение об успешном выполнении, и банк терминов обновится, и вы сможете перейти к новым созданным наборам терминов.</span><span class="sxs-lookup"><span data-stu-id="42ca5-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="42ca5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="42ca5-118">See also</span></span>

[<span data-ttu-id="42ca5-119">Общие сведения об управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="42ca5-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="42ca5-120">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="42ca5-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="42ca5-121">Импорт наборов терминов (уровень сайта)</span><span class="sxs-lookup"><span data-stu-id="42ca5-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)