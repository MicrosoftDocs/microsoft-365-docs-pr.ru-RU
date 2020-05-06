---
title: Оценка защиты от угроз Майкрософт
description: Настройте пробную среду лаборатории Майкрософт по защите от угроз, чтобы проверить, как согласованное решение для защиты от угроз предназначено для защиты устройств, удостоверений, данных и приложений, которые могут помочь вашей организации
keywords: Пробная версия системы защиты от угроз Майкрософт, пробная защита от угроз Майкрософт, Лаборатория Microsoft Threat Protection, Лаборатория Microsoft Threat Protection, Лаборатория оценки безопасности кибератак, повышенная постоянная угроза, Корпоративная защита, устройства, устройства, удостоверения, пользователи, данные, приложения, происшествия, автоматизированное исследование и исправление, расширенное Поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049643"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="b3b6c-104">Создание пробной лабораторной среды Майкрософт для защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="b3b6c-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="b3b6c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b3b6c-105">**Applies to:**</span></span>
- <span data-ttu-id="b3b6c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b3b6c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b3b6c-107">Цель создания пробной лабораторной среды — продемонстрировать комплексные, интегрированные и интеллектуальные возможности защиты от угроз Майкрософт для обнаружения, защиты, расследования и ответа, которые можно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="b3b6c-108">В этом руководстве описано, как начать оценку системы защиты от угроз Майкрософт на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b3b6c-109">Цель состоит в том, чтобы помочь вам настроить интегрированные службы защиты от угроз Майкрософт в лабораторной среде или в качестве эксперимента при предоставлении решений по обеспечению безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="b3b6c-110">Когда вы закончите работу с имитацией атак, автоматическим исследованием и ответом и удовлетворенными результатами, вы можете развернуть его в рабочей среде с помощью технических специалистов по продажам и экспертов Майкрософт в Организации.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b3b6c-111">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-111">This guide will help you:</span></span>
- <span data-ttu-id="b3b6c-112">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b3b6c-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="b3b6c-113">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="b3b6c-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b3b6c-114">Настройка и настройка Azure ATP, Office ATP, Microsoft Defender ATP и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3b6c-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b3b6c-115">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b3b6c-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="b3b6c-116">Имитирует атаку угроз для создания тестового инцидента или оповещения в Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b3b6c-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="b3b6c-117">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b3b6c-118">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="b3b6c-118">Deployment phases</span></span>

<span data-ttu-id="b3b6c-119">Создание пробной лабораторной среды Майкрософт по защите от угроз и ее развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="b3b6c-120">Этап</span><span class="sxs-lookup"><span data-stu-id="b3b6c-120">Phase</span></span> | <span data-ttu-id="b3b6c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b6c-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b3b6c-122">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b3b6c-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="b3b6c-123">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="b3b6c-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b3b6c-124">Сведения о том, что необходимо учитывать при развертывании защиты от угроз Майкрософт в испытательной лабораторной среде:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="b3b6c-125">— Заинтересованные стороны и подпись</span><span class="sxs-lookup"><span data-stu-id="b3b6c-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b3b6c-126">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="b3b6c-126">- Environment considerations</span></span> <br><span data-ttu-id="b3b6c-127">Доступ</span><span class="sxs-lookup"><span data-stu-id="b3b6c-127">- Access</span></span> <br><span data-ttu-id="b3b6c-128">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b3b6c-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b3b6c-129">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="b3b6c-129">- Configuration order</span></span>
|  <span data-ttu-id="b3b6c-130">![Этап 2: Настройка](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b3b6c-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b3b6c-131">Этап 2: Настройка</span><span class="sxs-lookup"><span data-stu-id="b3b6c-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b3b6c-132">Выполните начальные действия для доступа к центру безопасности Microsoft 365, чтобы настроить лабораторную среду пробной системы защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="b3b6c-133">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-133">You will be guided to:</span></span><br><br><span data-ttu-id="b3b6c-134">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3b6c-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b3b6c-135">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b3b6c-135">- Configure domain</span></span><br><span data-ttu-id="b3b6c-136">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3b6c-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b3b6c-137">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="b3b6c-138">![Этап 3: Настройка встроенного &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b3b6c-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b3b6c-139">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="b3b6c-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b3b6c-140">Настройте каждый из принципов и встроенных конечных точек защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="b3b6c-141">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-141">You will be guided to:</span></span><br><br><span data-ttu-id="b3b6c-142">— Настройка Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="b3b6c-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="b3b6c-143">— Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3b6c-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b3b6c-144">— Настройка службы Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="b3b6c-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="b3b6c-145">— Настройка Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b3b6c-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="b3b6c-146">В области</span><span class="sxs-lookup"><span data-stu-id="b3b6c-146">In scope</span></span>

<span data-ttu-id="b3b6c-147">В этом руководстве для пробной лабораторной лаборатории приведена следующая область:</span><span class="sxs-lookup"><span data-stu-id="b3b6c-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="b3b6c-148">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b3b6c-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b3b6c-149">Настройка защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b3b6c-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="b3b6c-150">Подписка на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3b6c-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="b3b6c-151">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b3b6c-151">Configure domain</span></span>
    -   <span data-ttu-id="b3b6c-152">Назначение лицензий на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3b6c-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b3b6c-153">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="b3b6c-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b3b6c-154">Настройка всех принципов защиты от угроз Майкрософт на основе рекомендаций</span><span class="sxs-lookup"><span data-stu-id="b3b6c-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="b3b6c-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b3b6c-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b3b6c-156">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="b3b6c-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b3b6c-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3b6c-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b3b6c-158">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b3b6c-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b3b6c-159">Вне области предоставляемых услуг</span><span class="sxs-lookup"><span data-stu-id="b3b6c-159">Out of scope</span></span>

<span data-ttu-id="b3b6c-160">Ниже приведены рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b3b6c-161">Конфигурация сторонних решений, которые могут интегрироваться с защитником Майкрософт ATP</span><span class="sxs-lookup"><span data-stu-id="b3b6c-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="b3b6c-162">Тестирование уязвимости в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="b3b6c-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b3b6c-163">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b3b6c-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="b3b6c-164">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b3b6c-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="b3b6c-165">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="b3b6c-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="b3b6c-166">Подготовка лабораторной среды оценки Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b3b6c-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
