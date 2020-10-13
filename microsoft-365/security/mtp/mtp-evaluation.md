---
title: Оценка Защиты от угроз (Майкрософт)
description: Настройте пробную лабораторию или пилотную среду защиты от угроз Майкрософт, чтобы испытать и использовать решение для защиты устройств, удостоверений, данных и приложений в Организации.
keywords: Пробная версия системы защиты от угроз Майкрософт, пробная защита от угроз Майкрософт, Лаборатория Майкрософт по защите от угроз, Лаборатория Microsoft Threat Protection, пилотный проект Microsoft Threat Protection, пилотная система защиты от угроз Майкрософт, кибератак безопасность, повышенная постоянная угроза, корпоративные системы безопасности, устройства, устройства, удостоверения, пользователи, данные, приложения, происшествия, автоматическое исследование и исправление
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447123"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="d40ed-104">Создание пробной лаборатории или пилотной среды Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="d40ed-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d40ed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d40ed-105">**Applies to:**</span></span>
- <span data-ttu-id="d40ed-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d40ed-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d40ed-107">Цель создания пробной лаборатории или пилотной среды — продемонстрировать комплексные и интегрированные возможности защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d40ed-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="d40ed-108">Сведения о том, как данное интеллектуальное решение для обеспечения безопасности обнаруживает, предотвращает и автоматически исследует и реагирует на дополнительные угрозы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d40ed-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="d40ed-109">В этом руководстве описано, как начать оценку системы защиты от угроз Майкрософт на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="d40ed-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="d40ed-110">Цель состоит в том, чтобы помочь вам настроить решение для обеспечения безопасности в лабораторной среде с пробной учетной записью или в пилотной среде в рабочей среде с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="d40ed-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="d40ed-111">Подготовка пробной лаборатории или пилотной среды может помочь в обеспечении использования операций по обеспечению безопасности для лиц, принимающих решения в Организации.</span><span class="sxs-lookup"><span data-stu-id="d40ed-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="d40ed-112">Когда вы закончите работу с имитацией атаки и удовлетворены результатами, вы сможете полностью развернуть и оператионализе его в вашей организации с помощью технических специалистов Майкрософт по продажам или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d40ed-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="d40ed-113">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="d40ed-113">This guide will help you:</span></span>
- <span data-ttu-id="d40ed-114">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="d40ed-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="d40ed-115">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="d40ed-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="d40ed-116">Настройка и настройка Azure ATP, Office ATP, Microsoft Defender ATP и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d40ed-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d40ed-117">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="d40ed-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="d40ed-118">Имитирует атаку угроз для создания тестового инцидента или оповещения в Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="d40ed-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="d40ed-119">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="d40ed-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="d40ed-120">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="d40ed-120">Deployment phases</span></span>

<span data-ttu-id="d40ed-121">Создание пробной лабораторной среды Майкрософт по защите от угроз и ее развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="d40ed-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="d40ed-122">Этап</span><span class="sxs-lookup"><span data-stu-id="d40ed-122">Phase</span></span> | <span data-ttu-id="d40ed-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d40ed-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="d40ed-124">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d40ed-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="d40ed-125">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="d40ed-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="d40ed-126">Сведения о том, что необходимо учитывать при развертывании Microsoft Threat Protection в испытательной лаборатории или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="d40ed-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="d40ed-127">— Заинтересованные стороны и подпись</span><span class="sxs-lookup"><span data-stu-id="d40ed-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="d40ed-128">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="d40ed-128">- Environment considerations</span></span> <br><span data-ttu-id="d40ed-129">Доступ</span><span class="sxs-lookup"><span data-stu-id="d40ed-129">- Access</span></span> <br><span data-ttu-id="d40ed-130">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d40ed-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="d40ed-131">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="d40ed-131">- Configuration order</span></span>
|  <span data-ttu-id="d40ed-132">![Этап 2: Настройка](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="d40ed-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="d40ed-133">Этап 2: Настройка</span><span class="sxs-lookup"><span data-stu-id="d40ed-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="d40ed-134">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365 для настройки пробной лаборатории или пилотной среды Майкрософт по защите от угроз.</span><span class="sxs-lookup"><span data-stu-id="d40ed-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="d40ed-135">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="d40ed-135">You'll be guided to:</span></span><br><br><span data-ttu-id="d40ed-136">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d40ed-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="d40ed-137">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="d40ed-137">- Configure domain</span></span><br><span data-ttu-id="d40ed-138">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d40ed-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="d40ed-139">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="d40ed-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="d40ed-140">![Этап 3: Настройка встроенного &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="d40ed-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="d40ed-141">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="d40ed-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="d40ed-142">Настройте каждый из принципов и встроенных конечных точек защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d40ed-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="d40ed-143">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="d40ed-143">You'll be guided to:</span></span><br><br><span data-ttu-id="d40ed-144">— Настройка Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="d40ed-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="d40ed-145">— Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d40ed-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="d40ed-146">— Настройка службы Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="d40ed-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="d40ed-147">— Настройка Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d40ed-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="d40ed-148">В области</span><span class="sxs-lookup"><span data-stu-id="d40ed-148">In scope</span></span>

<span data-ttu-id="d40ed-149">В этом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d40ed-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="d40ed-150">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d40ed-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="d40ed-151">Настройка защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d40ed-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="d40ed-152">Подпишитесь на пробную версию Microsoft 365 и используйте полную лицензию, если вы используете пилотный проект</span><span class="sxs-lookup"><span data-stu-id="d40ed-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="d40ed-153">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="d40ed-153">Configure domain</span></span>
    -   <span data-ttu-id="d40ed-154">Назначение лицензий на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d40ed-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="d40ed-155">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="d40ed-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="d40ed-156">Настройка всех принципов защиты от угроз Майкрософт на основе рекомендаций</span><span class="sxs-lookup"><span data-stu-id="d40ed-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="d40ed-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d40ed-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d40ed-158">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="d40ed-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d40ed-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d40ed-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="d40ed-160">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d40ed-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="d40ed-161">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="d40ed-161">Out of scope</span></span>

<span data-ttu-id="d40ed-162">Ниже приведены рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d40ed-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="d40ed-163">Конфигурация сторонних решений, которые могут интегрироваться с защитой от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d40ed-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="d40ed-164">Тестирование уязвимости в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="d40ed-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="d40ed-165">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="d40ed-165">Next step</span></span>
<span data-ttu-id="d40ed-166">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d40ed-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="d40ed-167">[Этап 1: подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="d40ed-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="d40ed-168">Подготовка пробной лаборатории или пилотной среды Майкрософт для защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="d40ed-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
