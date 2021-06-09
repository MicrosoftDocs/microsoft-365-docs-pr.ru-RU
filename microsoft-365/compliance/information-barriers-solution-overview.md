---
title: Информационные барьеры в Microsoft 365
description: Узнайте, как настроить информационные барьеры в Microsoft 365.
keywords: Microsoft 365, инсайдерский риск, соответствие требованиям
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
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423600"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="41304-104">Информационные барьеры в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41304-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="41304-105">Microsoft 365 связи и совместной работы между группами и организациями и поддерживает способы ограничения связи и совместной работы между определенными группами пользователей при необходимости.</span><span class="sxs-lookup"><span data-stu-id="41304-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="41304-106">Это может включать ситуации или сценарии, в которых необходимо ограничить общение и совместную работу между двумя группами, чтобы избежать конфликта интересов в организации.</span><span class="sxs-lookup"><span data-stu-id="41304-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="41304-107">Это также может включать ситуации, когда для защиты внутренней информации необходимо ограничить общение и совместную работу между определенными людьми в организации.</span><span class="sxs-lookup"><span data-stu-id="41304-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="41304-108">Информационные барьеры поддерживаются в Microsoft Teams, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="41304-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="41304-109">Администратор соответствия требованиям или администратор информационных барьеров может определять политики, позволяющие или препятствуя общению между группами пользователей в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="41304-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="41304-110">Политики информационного барьера можно использовать для таких ситуаций:</span><span class="sxs-lookup"><span data-stu-id="41304-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="41304-111">Пользователь в группе трейдера дня не должен общаться или делиться файлами с маркетинговой группой.</span><span class="sxs-lookup"><span data-stu-id="41304-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="41304-112">Финансы сотрудников, работающих с конфиденциальной информацией компании, не должны обмениваться файлами с определенными группами в их организации.</span><span class="sxs-lookup"><span data-stu-id="41304-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="41304-113">Внутренняя группа с материалами секрета торговли не должна звонить или общаться в интернете с людьми в определенных группах в их организации</span><span class="sxs-lookup"><span data-stu-id="41304-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="41304-114">Исследовательская группа должна звонить или общаться в интернете только с командой разработки продукта.</span><span class="sxs-lookup"><span data-stu-id="41304-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="41304-115">Настройка информационных барьеров для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41304-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="41304-116">Чтобы настроить информационные барьеры для организации, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="41304-116">Use the following steps to configure information barriers for your organization:</span></span>

![Действия по информационным барьерам для решения проблем, связанных с инсайдерской информацией](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="41304-118">Сведения о [информационных барьерах](information-barriers.md) в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41304-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="41304-119">Настройка [необходимых условий и разрешений](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="41304-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="41304-120">Сегмент [пользователей в организации](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="41304-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="41304-121">Создание и настройка политик [информационного барьера](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="41304-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="41304-122">Применение [политик информационного барьера](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="41304-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="41304-123">Дополнительные сведения о информационных барьерах</span><span class="sxs-lookup"><span data-stu-id="41304-123">More information about information barriers</span></span>

- [<span data-ttu-id="41304-124">Атрибуты для политик информационных барьеров</span><span class="sxs-lookup"><span data-stu-id="41304-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="41304-125">Изменение или удаление политик информационного барьера</span><span class="sxs-lookup"><span data-stu-id="41304-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)