---
title: Информационные барьеры в Microsoft 365
description: Узнайте, как настроить барьеры информации в Microsoft 365.
keywords: Microsoft 365, риск для участников, соответствие требованиям
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
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="03f0c-104">Информационные барьеры в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03f0c-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="03f0c-105">Microsoft 365 обеспечивает взаимодействие и совместную работу между группами и организациями, а также поддерживает способы ограничения взаимодействия и совместной работы между определенными группами пользователей, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="03f0c-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="03f0c-106">Это может быть ситуация или сценарии, в которых необходимо ограничить обмен данными и совместную работу между двумя группами, чтобы избежать конфликта интересов в Организации.</span><span class="sxs-lookup"><span data-stu-id="03f0c-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="03f0c-107">Сюда также могут относиться ситуации, когда необходимо ограничить обмен данными и совместную работу между определенными пользователями в Организации, чтобы защитить внутреннюю информацию.</span><span class="sxs-lookup"><span data-stu-id="03f0c-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="03f0c-108">Информационные барьеры поддерживаются в Microsoft Teams, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="03f0c-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="03f0c-109">Администратор соответствия требованиям или Администраторы могут определять политики для разрешения или запрета связи между группами пользователей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03f0c-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="03f0c-110">Политики барьера информации могут использоваться в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="03f0c-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="03f0c-111">Пользователь в течение дня пользовательской группы не должен обмениваться файлами и делиться файлами с помощью маркетинговой команды</span><span class="sxs-lookup"><span data-stu-id="03f0c-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="03f0c-112">Сотрудники финансового отдела, работающие с конфиденциальной информацией о компании, не должны обмениваться данными с определенными группами в Организации и обмениваться ими.</span><span class="sxs-lookup"><span data-stu-id="03f0c-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="03f0c-113">Внутренняя группа с коммерческими секретными материалами не должна звонить или общаться с людьми в определенных группах в Организации</span><span class="sxs-lookup"><span data-stu-id="03f0c-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="03f0c-114">Справочная группа должна обращаться к сети или общаться только с другими участниками группы разработчиков продуктов</span><span class="sxs-lookup"><span data-stu-id="03f0c-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="03f0c-115">Настройка барьеров информации для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03f0c-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="03f0c-116">Выполните указанные ниже действия, чтобы настроить барьеры информации для Организации.</span><span class="sxs-lookup"><span data-stu-id="03f0c-116">Use the following steps to configure information barriers for your organization:</span></span>

![Действия по информационным решениям для оценки рисков](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="03f0c-118">Узнайте о [барьерах информации](information-barriers.md) в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03f0c-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="03f0c-119">Настройка [необходимых компонентов и разрешений](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="03f0c-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="03f0c-120">Сегментация [пользователей в Организации](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="03f0c-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="03f0c-121">Создание и настройка [политик барьера данных](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="03f0c-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="03f0c-122">Применение [политик барьера информации](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="03f0c-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="03f0c-123">Дополнительные сведения о барьерах информации</span><span class="sxs-lookup"><span data-stu-id="03f0c-123">More information about information barriers</span></span>

- [<span data-ttu-id="03f0c-124">Атрибуты для политик информационных барьеров</span><span class="sxs-lookup"><span data-stu-id="03f0c-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="03f0c-125">Изменение или удаление политик барьера информации</span><span class="sxs-lookup"><span data-stu-id="03f0c-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)