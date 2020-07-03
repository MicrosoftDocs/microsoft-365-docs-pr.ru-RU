---
title: Работать с custodians в Advanced eDiscovery
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать средство управления хранитель в Advanced eDiscovery для управления данными в юридическом случае.
ms.openlocfilehash: 159ee0b0365ec7c2419fd9abe1426ad9c5efed4a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024689"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="2611b-103">Работать с источниками данных custodians и не кустодиал в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2611b-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="2611b-104">Когда Организация реагирует на судебное исследование, Рабочий процесс, определяющий, сохранение и сбор потенциально релевантного контента, зависит от людей в Организации, которые являются custodiansми соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="2611b-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="2611b-105">В случае обнаружения электронных данных эти пользователи называются *Data custodians* (или просто *custodians*) и определяются как "лица, имеющие административный контроль над документом или электронным файлом".</span><span class="sxs-lookup"><span data-stu-id="2611b-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="2611b-106">Например, хранитель сообщения электронной почты может быть владельцем почтового ящика, содержащего соответствующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="2611b-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="2611b-107">Кроме того, в почтовых ящиках и сайтах, которые не связаны с хранитель, может находиться содержимое, но это относится к этому случаю.</span><span class="sxs-lookup"><span data-stu-id="2611b-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="2611b-108">Для различения расположений контента, в которых регистр custodians не имеет административного управления, но может содержать релевантные данные, они называются *источниками данных, не являющимися кустодиал*.</span><span class="sxs-lookup"><span data-stu-id="2611b-108">To differentiate content locations where case custodians don't have administrative control but may contain relevant data, these are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="2611b-109">В расширенном случае обнаружения электронных данных юридические команды могут добавлять пользователей в своей организации в виде custodians и автоматически определять и сохранять источники данных кустодиал, такие как почтовые ящики Exchange, учетные записи OneDrive и сайты SharePoint и Teams.</span><span class="sxs-lookup"><span data-stu-id="2611b-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="2611b-110">Кроме того, они могут определять и сохранять источники данных, не относящиеся к кустодиал.</span><span class="sxs-lookup"><span data-stu-id="2611b-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="2611b-111">С помощью встроенного средства управления хранитель и управления источниками данных в Advanced eDiscovery организации могут защитить электронно хранимые данные от случайного (или намеренного) удаления.</span><span class="sxs-lookup"><span data-stu-id="2611b-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="2611b-112">Это позволяет избежать длительных и подверженных ошибкам процессов, которые вручную выполняют процессы удержания.</span><span class="sxs-lookup"><span data-stu-id="2611b-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="2611b-113">Более подробную информацию о работе с custodians можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2611b-113">For more information about working with custodians, see the following:</span></span>

- [<span data-ttu-id="2611b-114">Добавление хранителей в дело</span><span class="sxs-lookup"><span data-stu-id="2611b-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="2611b-115">Массовое добавление custodians к случаю</span><span class="sxs-lookup"><span data-stu-id="2611b-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="2611b-116">Управление custodians в случае</span><span class="sxs-lookup"><span data-stu-id="2611b-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="2611b-117">Просмотр действий хранителя</span><span class="sxs-lookup"><span data-stu-id="2611b-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="2611b-118">Добавление источников данных, не относящихся к кустодиал, к случаю</span><span class="sxs-lookup"><span data-stu-id="2611b-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
