---
title: Заметки о выпуске классификации данных
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Заметки о выпуске для классификации данных.
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127144"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="aea1c-103">Заметки о выпуске классификации данных</span><span class="sxs-lookup"><span data-stu-id="aea1c-103">Data classification release notes</span></span>

<span data-ttu-id="aea1c-104">Ознакомьтесь с этими заметками о выпуске для оптимальной работы с классификацией данных.</span><span class="sxs-lookup"><span data-stu-id="aea1c-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="aea1c-105">Количество почтовых ящиков Exchange</span><span class="sxs-lookup"><span data-stu-id="aea1c-105">Exchange mailbox count</span></span>

<span data-ttu-id="aea1c-106">При детализации почтовых ящиков Exchange выводится небольшая подсказка.</span><span class="sxs-lookup"><span data-stu-id="aea1c-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="aea1c-107">В ней сообщается, что общее число типов конфиденциальной информации, меток конфиденциальности и меток хранения, которое отображается, может не совпадать с количеством элементов, которые будут найдены в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="aea1c-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="aea1c-108">Это объясняется тем, что при детализации папки общее число рассчитывается в процессе классификации интерактивного представления содержимого.</span><span class="sxs-lookup"><span data-stu-id="aea1c-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="aea1c-109">Отображение зашифрованных документов</span><span class="sxs-lookup"><span data-stu-id="aea1c-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="aea1c-110">Зашифрованные файлы SharePoint, Exchange и OneDrive не отображаются в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="aea1c-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="aea1c-111">Соображения конфиденциальности требуют баланса между необходимостью просматривать содержимое файла в обозревателе содержимого и необходимостью отображать содержимое в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="aea1c-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="aea1c-112">Разрешения, предоставленные группами ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**, позволяют увидеть представление списка файлов, метаданные файлов и ссылку для получения доступа к содержимому через веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="aea1c-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="aea1c-113">Поддерживаемые символы в именах меток хранения в поиске SharePoint</span><span class="sxs-lookup"><span data-stu-id="aea1c-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="aea1c-114">Служба поиска SharePoint не поддерживает имена меток хранения с символами `-` или `_`.</span><span class="sxs-lookup"><span data-stu-id="aea1c-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="aea1c-115">Например, не поддерживаются имена меток `Label-MIP` и `Label_MIP`.</span><span class="sxs-lookup"><span data-stu-id="aea1c-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="aea1c-116">Служба поиска SharePoint поддерживает такие символы в именах меток конфиденциальности и типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="aea1c-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="aea1c-117">OneDrive остается на этапе предварительной версии</span><span class="sxs-lookup"><span data-stu-id="aea1c-117">OneDrive remains in preview</span></span>

<span data-ttu-id="aea1c-118">В рамках программы предварительной версии мы получили ценные отзывы об интеграции OneDrive.</span><span class="sxs-lookup"><span data-stu-id="aea1c-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="aea1c-119">Пока мы разбираем и реализуем конкретные решения, вы можете столкнуться с несогласованными данными или потоками.</span><span class="sxs-lookup"><span data-stu-id="aea1c-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="aea1c-120">Мы продолжим демонстрировать OneDrive в предварительной версии, пока все исправления не будут реализованы.</span><span class="sxs-lookup"><span data-stu-id="aea1c-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="aea1c-121">Благодарим вас за поддержку.</span><span class="sxs-lookup"><span data-stu-id="aea1c-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="aea1c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="aea1c-122">See also</span></span>

- [<span data-ttu-id="aea1c-123">Начало работы с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aea1c-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="aea1c-124">Просмотр действий с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aea1c-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="aea1c-125">Просмотр содержимого с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aea1c-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="aea1c-126">Сведения о метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="aea1c-126">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="aea1c-127">Сведения о политиках хранения и метках хранения</span><span class="sxs-lookup"><span data-stu-id="aea1c-127">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="aea1c-128">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="aea1c-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)