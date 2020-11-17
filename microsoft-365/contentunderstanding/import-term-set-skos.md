---
title: Импорт набора терминов в формате SKOS
description: Подробнее об импорте набора терминов в формате SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 96ffa22880aa9bcb70c0f7159ac7587c911b375b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087359"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="647b8-103">Импорт набора терминов в формате SKOS</span><span class="sxs-lookup"><span data-stu-id="647b8-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="647b8-104">Можно импортировать набор терминов в формате SKOS.</span><span class="sxs-lookup"><span data-stu-id="647b8-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="647b8-105">Дополнительные сведения о формате см. в статье [Справка по формату SKOS для таксономии SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="647b8-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="647b8-106">Рекомендуем хранить в файлах импорта не более 20 000 терминов.</span><span class="sxs-lookup"><span data-stu-id="647b8-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="647b8-107">Большие файлы могут увеличить время, необходимое для проверки и импорта.</span><span class="sxs-lookup"><span data-stu-id="647b8-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="647b8-108">В центре администрирования SharePoint разверните раздел **Службы контента**, а затем выберите пункт **Банк терминов**.</span><span class="sxs-lookup"><span data-stu-id="647b8-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="647b8-109">Выберите группу терминов, в которую нужно импортировать набор терминов.</span><span class="sxs-lookup"><span data-stu-id="647b8-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="647b8-110">На панели команд нажмите кнопку **Импортировать набор терминов**.</span><span class="sxs-lookup"><span data-stu-id="647b8-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="647b8-111">Если нужно скачать образец файла, чтобы использовать его в качестве шаблона, нажмите кнопку **sample-metadata.ttl**, чтобы получить образец файла в формате SKOS.</span><span class="sxs-lookup"><span data-stu-id="647b8-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="647b8-112">Создание файла импорта, содержащего набор терминов, и термины, которые нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="647b8-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="647b8-113">В разделе **Формат файла**, выберите **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="647b8-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="647b8-114">Нажмите кнопку **Обзор**, а затем перейдите к файлу импорта и добавьте его.</span><span class="sxs-lookup"><span data-stu-id="647b8-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="647b8-115">Нажмите кнопку **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="647b8-115">Click **Import**.</span></span> <span data-ttu-id="647b8-116">Не закрывайте панель до завершения импорта.</span><span class="sxs-lookup"><span data-stu-id="647b8-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="647b8-117">При удачном импорте файла отобразится сообщение об успешном выполнении, банк терминов обновится и вы сможете перейти к недавно созданным наборам терминов.</span><span class="sxs-lookup"><span data-stu-id="647b8-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="647b8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="647b8-118">See also</span></span>

[<span data-ttu-id="647b8-119">Общие сведения об управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="647b8-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="647b8-120">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="647b8-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="647b8-121">Импорт наборов терминов (уровень сайта)</span><span class="sxs-lookup"><span data-stu-id="647b8-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)