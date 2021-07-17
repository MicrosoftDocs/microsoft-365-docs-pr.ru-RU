---
title: Начало работы с обнаружением и устранением угроз приложений
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Начало работы с обнаружением угроз и исправлением угроз приложений.
ms.openlocfilehash: 77de3676a9a486bbed572a4a16bf62ad4d038406
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430724"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a><span data-ttu-id="44646-103">Начало работы с обнаружением и устранением угроз приложений</span><span class="sxs-lookup"><span data-stu-id="44646-103">Get started with app threat detection and remediation</span></span>

><span data-ttu-id="44646-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="44646-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="44646-105">Система управления приложениями Майкрософт собирает оповещения об угрозах, созданные встроенными методами обнаружения системы управления приложениями на основе действий вредоносных приложений и оповещений на основе политик, созданных активными политиками приложений.</span><span class="sxs-lookup"><span data-stu-id="44646-105">Microsoft app governance collects threat alerts that are generated by built-in app governance detection methods based on malicious app activities and policy-based alerts generated by active app policies that you create.</span></span>

<span data-ttu-id="44646-106">Первое место для просмотра оповещений приложений — это панель управления приложениями по адресу [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="44646-106">The first place to view app alerts is the app governance dashboard at [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span>

![Страница обзора управления приложениями в Центре соответствия требованиям Microsoft 365 с выделенным разделом "Оповещения обнаружения и политик".](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

<span data-ttu-id="44646-108">На этой странице обзора в разделе **Оповещения обнаружения и политик** перечислены последние оповещения.</span><span class="sxs-lookup"><span data-stu-id="44646-108">On this overview page, the **Detection and policy alerts** section lists the latest alerts.</span></span> <span data-ttu-id="44646-109">Вы можете использовать это, чтобы быстро просмотреть текущую активность оповещений приложений для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="44646-109">You can use this to quickly see the current app alert activity for your tenant.</span></span>

<span data-ttu-id="44646-110">Чтобы просмотреть все оповещения, выберите вкладку **Оповещения**.</span><span class="sxs-lookup"><span data-stu-id="44646-110">To see all of the alerts, select the **Alerts** tab.</span></span>

## <a name="whats-available-on-the-alerts-page"></a><span data-ttu-id="44646-111">Что доступно на странице "Оповещения"</span><span class="sxs-lookup"><span data-stu-id="44646-111">What’s available on the Alerts page</span></span>

<span data-ttu-id="44646-112">На странице **Оповещения** отображаются все оповещения на основе управления приложениями для вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="44646-112">The **Alerts** page lists all of the app governance-based alerts for your tenant.</span></span>

![Страница сводки оповещений системы управления приложениями в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

<span data-ttu-id="44646-114">Каждое оповещение в списке содержит следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="44646-114">Each listed alert has the following information:</span></span>

- <span data-ttu-id="44646-115">**Имя оповещения**: тип аномального поведения.</span><span class="sxs-lookup"><span data-stu-id="44646-115">**Alert name**: The type of anomalous behavior.</span></span>
- <span data-ttu-id="44646-116">**Имя приложения**: приложение, которое создало оповещение.</span><span class="sxs-lookup"><span data-stu-id="44646-116">**App name**: The app that generated the alert.</span></span>
- <span data-ttu-id="44646-117">**Серьезность**: уровень серьезности, присвоенный системой управления приложениями для созданных оповещений, или серьезность политики приложения, которая создала оповещение.</span><span class="sxs-lookup"><span data-stu-id="44646-117">**Severity**: The severity assigned by app governance for alerts it creates or the severity of the app policy that generated the alert.</span></span>
- <span data-ttu-id="44646-118">**Источник**: происхождение оповещения, которое может быть результатом политики (созданных пользователем политик), обнаружения (встроенных политик обнаружения) или MCAS.</span><span class="sxs-lookup"><span data-stu-id="44646-118">**Source**: Origination of the alert, which can be results from policy (user-created policies), detection (built-in detection policies), or MCAS.</span></span>
- <span data-ttu-id="44646-119">**Состояние**: **новое** указывает на оповещение, которому не был присвоен статус.</span><span class="sxs-lookup"><span data-stu-id="44646-119">**Status**: **New** indicates an alert that has not been assigned a status.</span></span> <span data-ttu-id="44646-120">После назначения состояние получает статус **В процессе**, пока исследуется, или **Устранено** для оповещений, устраненных с помощью автоматического или ручного исправления.</span><span class="sxs-lookup"><span data-stu-id="44646-120">Once assigned, the status is either **In progress** while being investigated or **Resolved** for alerts that have been addressed through automatic or manual remediation.</span></span>
- <span data-ttu-id="44646-121">**Дата создания**: дата создания оповещения с помощью обнаружения управления приложениями или политики приложения.</span><span class="sxs-lookup"><span data-stu-id="44646-121">**Date created**: The date the alert was generated by either app governance detection or through an app policy.</span></span> <span data-ttu-id="44646-122">Все даты указаны в местном часовом поясе Центра соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44646-122">All dates shown are in the local time zone of the Microsoft 365 compliance center.</span></span>
- <span data-ttu-id="44646-123">**Последнее действие**: дата последнего изменения состояния оповещения.</span><span class="sxs-lookup"><span data-stu-id="44646-123">**Last activity**: The date the status of the alert was last changed.</span></span> <span data-ttu-id="44646-124">Все даты указаны в местном часовом поясе Центра соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44646-124">All dates shown are in the local time zone of the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="44646-125">Список оповещений сортируется по **дате создания** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44646-125">The alert list is sorted by **Date created** by default.</span></span> <span data-ttu-id="44646-126">Чтобы отсортировать список по другому атрибуту, выберите имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="44646-126">To sort the list by another attribute, select the attribute name.</span></span>

<span data-ttu-id="44646-127">Вы также можете экспортировать текущий список оповещений в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="44646-127">You can also export the current alert list to a comma separated value (CSV) file.</span></span> <span data-ttu-id="44646-128">Например, можно открыть CVS-файл в Microsoft Excel и отсортировать список оповещений по **серьезности** а затем по **дате создания**.</span><span class="sxs-lookup"><span data-stu-id="44646-128">For example, you could open the CVS file in Microsoft Excel and sort the list of alerts by **Severity** and then **Date Created**.</span></span>

## <a name="next-step"></a><span data-ttu-id="44646-129">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="44646-129">Next step</span></span>

[<span data-ttu-id="44646-130">Устранение угроз приложения.</span><span class="sxs-lookup"><span data-stu-id="44646-130">Remediate app threats.</span></span>](app-governance-detect-remediate-detect-threats.md)