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
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 318497b8b1815b281eff7d781820616c9be9d5ed
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321245"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="2c391-103">Импорт набора терминов в формате SKOS</span><span class="sxs-lookup"><span data-stu-id="2c391-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="2c391-104">Можно импортировать набор терминов в формате SKOS.</span><span class="sxs-lookup"><span data-stu-id="2c391-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="2c391-105">Дополнительные сведения о формате см. в статье [Справка по формату SKOS для таксономии SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2c391-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="2c391-106">Рекомендуем хранить в файлах импорта не более 20 000 терминов.</span><span class="sxs-lookup"><span data-stu-id="2c391-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="2c391-107">Большие файлы могут увеличить время, необходимое для проверки и импорта.</span><span class="sxs-lookup"><span data-stu-id="2c391-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="2c391-108">В центре администрирования SharePoint разверните раздел **Службы контента**, а затем выберите пункт **Банк терминов**.</span><span class="sxs-lookup"><span data-stu-id="2c391-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="2c391-109">Выберите группу терминов, в которую нужно импортировать набор терминов.</span><span class="sxs-lookup"><span data-stu-id="2c391-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="2c391-110">На панели команд нажмите кнопку **Импортировать набор терминов**.</span><span class="sxs-lookup"><span data-stu-id="2c391-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="2c391-111">Если нужно скачать образец файла, чтобы использовать его в качестве шаблона, нажмите кнопку **sample-metadata.ttl**, чтобы получить образец файла в формате SKOS.</span><span class="sxs-lookup"><span data-stu-id="2c391-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="2c391-112">Создание файла импорта, содержащего набор терминов, и термины, которые нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="2c391-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="2c391-113">В разделе **Формат файла**, выберите **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="2c391-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="2c391-114">Нажмите кнопку **Обзор**, а затем перейдите к файлу импорта и добавьте его.</span><span class="sxs-lookup"><span data-stu-id="2c391-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="2c391-115">Нажмите кнопку **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="2c391-115">Click **Import**.</span></span> <span data-ttu-id="2c391-116">Не закрывайте панель до завершения импорта.</span><span class="sxs-lookup"><span data-stu-id="2c391-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="2c391-117">При удачном импорте файла отобразится сообщение об успешном выполнении, банк терминов обновится и вы сможете перейти к недавно созданным наборам терминов.</span><span class="sxs-lookup"><span data-stu-id="2c391-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c391-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2c391-118">See also</span></span>

[<span data-ttu-id="2c391-119">Общие сведения об управляемых метаданных</span><span class="sxs-lookup"><span data-stu-id="2c391-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="2c391-120">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="2c391-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="2c391-121">Импорт наборов терминов (уровень сайта)</span><span class="sxs-lookup"><span data-stu-id="2c391-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)