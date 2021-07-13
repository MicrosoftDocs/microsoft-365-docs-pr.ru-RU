---
title: Обзор использования базовых данных для развертывания стандартных конфигураций клиента
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP), использующих Microsoft 365 Lighthouse, узнайте об использовании базовых показателей для развертывания стандартных конфигураций клиента.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409187"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="1b3f2-103">Обзор использования базовых данных для развертывания стандартных конфигураций клиента</span><span class="sxs-lookup"><span data-stu-id="1b3f2-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="1b3f2-104">Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют [требованиям.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1b3f2-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="1b3f2-105">Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="1b3f2-106">Microsoft 365 Lighthouse базовые показатели обеспечивают повторяемый и масштабируемый способ оценки и управления Microsoft 365 параметров безопасности для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="1b3f2-107">Базовые параметры также помогают отслеживать основные политики безопасности и стандарты соответствия требованиям клиентов конфигурациями, которые обеспечивает безопасность пользователей, устройств и данных.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="1b3f2-108">Разработанный для того, чтобы помочь партнерам в обеспечении безопасности в их собственном темпе, Microsoft 365 Lighthouse предоставляет стандартный набор базовых параметров и заранее определенных конфигураций для Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="1b3f2-109">Эти конфигурации безопасности помогают оценить Microsoft 365 безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="1b3f2-110">Вы можете просмотреть базовый уровень по умолчанию и его этапы развертывания из Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="1b3f2-111">Чтобы применить базовые параметры к клиенту, выберите **"Клиенты"** в левой области навигации, а затем выберите клиента.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="1b3f2-112">Далее перейдите на **вкладку Планы развертывания** и реализуем нужную базовую линию.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="1b3f2-113">Стандартные базовые шаблоны безопасности</span><span class="sxs-lookup"><span data-stu-id="1b3f2-113">Standard baseline security templates</span></span>

<span data-ttu-id="1b3f2-114">Microsoft 365 Lighthouse стандартные базовые конфигурации для рабочих нагрузок безопасности предназначены для того, чтобы помочь всем управляемым арендаторам достичь приемлемого состояния обеспечения безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="1b3f2-115">Базовые конфигурации в следующей таблице стандартны с базовой Microsoft 365 Lighthouse по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="1b3f2-116">Базовая конфигурация</span><span class="sxs-lookup"><span data-stu-id="1b3f2-116">Baseline configuration</span></span> | <span data-ttu-id="1b3f2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1b3f2-117">Description</span></span> |
|--|--|
| <span data-ttu-id="1b3f2-118">Требовать MFA для администраторов</span><span class="sxs-lookup"><span data-stu-id="1b3f2-118">Require MFA for admins</span></span> | <span data-ttu-id="1b3f2-119">Политика условного доступа только для отчетов, требующая многофакторной проверки подлинности для администраторов.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="1b3f2-120">Это необходимо для всех облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="1b3f2-121">Требовать MFA для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="1b3f2-121">Require MFA for end users</span></span> | <span data-ttu-id="1b3f2-122">Политика условного доступа только для отчетов, которая требует многофакторной проверки подлинности для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="1b3f2-123">Это необходимо для всех облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="1b3f2-124">Блокирование традиционной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="1b3f2-124">Block legacy authentication</span></span> | <span data-ttu-id="1b3f2-125">Политика условного доступа только для отчетов, чтобы заблокировать проверку подлинности устаревших клиентов.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="1b3f2-126">Регистрация устройств в Microsoft Endpoint Manager - Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="1b3f2-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="1b3f2-127">Регистрация устройств, чтобы позволить устройствам клиента зарегистрироваться в Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="1b3f2-128">Это делается путем настройки автоматической регистрации между Azure Active Directory и Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="1b3f2-129">Конфигурация политики антивируса (AV)</span><span class="sxs-lookup"><span data-stu-id="1b3f2-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="1b3f2-130">Профиль конфигурации устройств для Windows устройств с предварительно настроенными антивирусная программа в Microsoft Defender настройками.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="1b3f2-131">Настройка политики соответствия требованиям window 10</span><span class="sxs-lookup"><span data-stu-id="1b3f2-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="1b3f2-132">Политика Windows устройств с предварительно настроенными настройками для соответствия основным требованиям соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1b3f2-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="1b3f2-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b3f2-133">Related content</span></span>

<span data-ttu-id="1b3f2-134">[Развертывание Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="1b3f2-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="1b3f2-135">[Microsoft 365 Lighthouse (статья)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="1b3f2-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
