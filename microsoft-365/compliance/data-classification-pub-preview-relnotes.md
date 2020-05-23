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
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327618"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="a7f10-103">Заметки о выпуске классификации данных</span><span class="sxs-lookup"><span data-stu-id="a7f10-103">Data classification release notes</span></span>

<span data-ttu-id="a7f10-104">Ознакомьтесь с этими заметками о выпуске для оптимальной работы с классификацией данных.</span><span class="sxs-lookup"><span data-stu-id="a7f10-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="a7f10-105">Количество почтовых ящиков Exchange</span><span class="sxs-lookup"><span data-stu-id="a7f10-105">Exchange mailbox count</span></span>

<span data-ttu-id="a7f10-106">При детализации почтовых ящиков Exchange выводится небольшая подсказка.</span><span class="sxs-lookup"><span data-stu-id="a7f10-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="a7f10-107">В ней сообщается, что общее число типов конфиденциальной информации, меток конфиденциальности и меток хранения, которое отображается, может не совпадать с количеством элементов, которые будут найдены в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a7f10-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="a7f10-108">Это объясняется тем, что при детализации папки общее число рассчитывается в процессе классификации интерактивного представления содержимого.</span><span class="sxs-lookup"><span data-stu-id="a7f10-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="a7f10-109">Отображение зашифрованных документов</span><span class="sxs-lookup"><span data-stu-id="a7f10-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="a7f10-110">Зашифрованные файлы SharePoint, Exchange и OneDrive не отображаются в обозревателе содержимого.</span><span class="sxs-lookup"><span data-stu-id="a7f10-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="a7f10-111">Соображения конфиденциальности требуют баланса между необходимостью просматривать содержимое файла в обозревателе содержимого и необходимостью отображать содержимое в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="a7f10-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="a7f10-112">Разрешения, предоставленные группами ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**, позволяют увидеть представление списка файлов, метаданные файлов и ссылку для получения доступа к содержимому через веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="a7f10-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="a7f10-113">Поддерживаемые символы в именах меток хранения в поиске SharePoint</span><span class="sxs-lookup"><span data-stu-id="a7f10-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="a7f10-114">Служба поиска SharePoint не поддерживает имена меток хранения с символами `-` или `_`.</span><span class="sxs-lookup"><span data-stu-id="a7f10-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="a7f10-115">Например, не поддерживаются имена меток `Label-MIP` и `Label_MIP`.</span><span class="sxs-lookup"><span data-stu-id="a7f10-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="a7f10-116">Служба поиска SharePoint поддерживает такие символы в именах меток конфиденциальности и типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="a7f10-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="a7f10-117">OneDrive остается на этапе предварительной версии</span><span class="sxs-lookup"><span data-stu-id="a7f10-117">OneDrive remains in preview</span></span>

<span data-ttu-id="a7f10-118">В рамках программы предварительной версии мы получили ценные отзывы об интеграции OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a7f10-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="a7f10-119">Пока мы разбираем и реализуем конкретные решения, вы можете столкнуться с несогласованными данными или потоками.</span><span class="sxs-lookup"><span data-stu-id="a7f10-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="a7f10-120">Мы продолжим демонстрировать OneDrive в предварительной версии, пока все исправления не будут реализованы.</span><span class="sxs-lookup"><span data-stu-id="a7f10-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="a7f10-121">Благодарим вас за поддержку.</span><span class="sxs-lookup"><span data-stu-id="a7f10-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="a7f10-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a7f10-122">See also</span></span>

- [<span data-ttu-id="a7f10-123">Начало работы с классификацией данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a7f10-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="a7f10-124">Просмотр действий с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a7f10-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a7f10-125">Просмотр содержимого с метками (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a7f10-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="a7f10-126">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="a7f10-126">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a7f10-127">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="a7f10-127">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a7f10-128">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a7f10-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)