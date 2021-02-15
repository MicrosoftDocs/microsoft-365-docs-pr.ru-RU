---
title: Информационные барьеры в Microsoft 365
description: Узнайте, как настроить информационные барьеры в Microsoft 365.
keywords: Microsoft 365, внутренний риск, соответствие требованиям
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613847"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="2b2a9-104">Информационные барьеры в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b2a9-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="2b2a9-105">Microsoft 365 обеспечивает взаимодействие и совместную работу между группами и организациями и поддерживает способы ограничения взаимодействия и совместной работы между определенными группами пользователей при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="2b2a9-106">Это могут быть ситуации или сценарии, в которых необходимо ограничить взаимодействие и совместную работу между двумя группами, чтобы избежать конфликта интересов в организации.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="2b2a9-107">Это также может включать ситуации, когда необходимо ограничить взаимодействие и совместную работу между определенными людьми в организации для защиты внутренней информации.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="2b2a9-108">Информационные барьеры поддерживаются в Microsoft Teams, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="2b2a9-109">Администратор соответствия требованиям или администратор информационных барьеров может определить политики, позволяющие разрешить или запретить взаимодействие между группами пользователей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="2b2a9-110">Политики информационных барьеров можно использовать в таких ситуациях:</span><span class="sxs-lookup"><span data-stu-id="2b2a9-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="2b2a9-111">Пользователь в группе "День" не должен обмениваться файлами с маркетинговой группой или делиться ими</span><span class="sxs-lookup"><span data-stu-id="2b2a9-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="2b2a9-112">Финансовый персонал, работающий с конфиденциальной информацией компании, не должен обмениваться файлами с определенными группами в своей организации или делиться ими</span><span class="sxs-lookup"><span data-stu-id="2b2a9-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="2b2a9-113">Внутренняя команда с материалами торгового секрета не должна звонить или общаться в чате с людьми из определенных групп в организации</span><span class="sxs-lookup"><span data-stu-id="2b2a9-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="2b2a9-114">Исследовательская группа должна звонить или общаться в чате только с командой разработчиков продуктов.</span><span class="sxs-lookup"><span data-stu-id="2b2a9-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="2b2a9-115">Настройка информационных барьеров для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b2a9-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="2b2a9-116">Чтобы настроить информационные барьеры для организации, с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2b2a9-116">Use the following steps to configure information barriers for your organization:</span></span>

![Этапы информационных барьеров решения для оценки риска](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="2b2a9-118">Сведения о [информационных барьерах](information-barriers.md) в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b2a9-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="2b2a9-119">Настройка [необходимых условий и разрешений](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2b2a9-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="2b2a9-120">Сегментация [пользователей в организации](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="2b2a9-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="2b2a9-121">Создание и настройка политик [информационных барьеров](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="2b2a9-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="2b2a9-122">Применение [политик информационных барьеров](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="2b2a9-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="2b2a9-123">Дополнительные сведения о информационных барьерах</span><span class="sxs-lookup"><span data-stu-id="2b2a9-123">More information about information barriers</span></span>

- [<span data-ttu-id="2b2a9-124">Атрибуты для политик информационных барьеров</span><span class="sxs-lookup"><span data-stu-id="2b2a9-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="2b2a9-125">Изменение и удаление политик информационных барьеров</span><span class="sxs-lookup"><span data-stu-id="2b2a9-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)