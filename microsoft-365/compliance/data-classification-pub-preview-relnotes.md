---
title: Заметки о выпуске классификации данных
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Заметки о выпуске для классификации данных.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086710"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="8ea6a-103">Заметки о выпуске классификации данных</span><span class="sxs-lookup"><span data-stu-id="8ea6a-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="8ea6a-104">Количество почтовых ящиков Exchange</span><span class="sxs-lookup"><span data-stu-id="8ea6a-104">Exchange mailbox count</span></span>

<span data-ttu-id="8ea6a-105">При детализации почтовых ящиков Exchange выводится небольшая подсказка.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="8ea6a-106">В ней сообщается, что общее число типов конфиденциальной информации, меток конфиденциальности и меток хранения, которое отображается, может не совпадать с количеством элементов, которые будут найдены в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="8ea6a-107">Это объясняется тем, что при детализации папки общее число рассчитывается в процессе классификации интерактивного представления содержимого.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="8ea6a-108">Отображение зашифрованных документов</span><span class="sxs-lookup"><span data-stu-id="8ea6a-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="8ea6a-109">Зашифрованные файлы SharePoint, Exchange и OneDrive не отображаются в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="8ea6a-110">Соображения конфиденциальности требуют баланса между необходимостью просматривать содержимое файла в обозревателе содержимого и необходимостью отображать содержимое в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="8ea6a-111">Разрешения, предоставленные группами ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**, позволяют увидеть представление списка файлов, метаданные файлов и ссылку для получения доступа к содержимому через веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="8ea6a-112">Поддерживаемые символы в именах меток хранения в поиске SharePoint</span><span class="sxs-lookup"><span data-stu-id="8ea6a-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="8ea6a-113">Служба поиска SharePoint не поддерживает имена меток хранения с символами `-` или `_`.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="8ea6a-114">Например, имена меток `Label-MIP` и `Label_MIP` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="8ea6a-115">Служба поиска SharePoint поддерживает такие символы в именах меток конфиденциальности и типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="8ea6a-116">OneDrive остается на этапе предварительной версии</span><span class="sxs-lookup"><span data-stu-id="8ea6a-116">OneDrive remains in preview</span></span>

<span data-ttu-id="8ea6a-117">Благодарим вас ценные отзывы об интеграции OneDrive, которые мы получили в рамках программы предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="8ea6a-118">Пока мы разбираем и реализуем конкретные решения, вы можете столкнуться с несогласованными данными или потоками.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="8ea6a-119">Мы продолжим демонстрировать OneDrive в предварительной версии, пока все исправления не будут реализованы.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="8ea6a-120">Благодарим вас за поддержку.</span><span class="sxs-lookup"><span data-stu-id="8ea6a-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="8ea6a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8ea6a-121">See also</span></span>

- [<span data-ttu-id="8ea6a-122">Начало работы с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8ea6a-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="8ea6a-123">Просмотр действий с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8ea6a-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8ea6a-124">Просмотр содержимого с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8ea6a-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="8ea6a-125">Сведения о метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="8ea6a-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="8ea6a-126">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="8ea6a-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="8ea6a-127">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="8ea6a-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)