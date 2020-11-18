---
title: Оценка защитника Microsoft 365
description: Настройка пробной лаборатории или пилотной среды защитника Microsoft 365 для попробного использования решения по обеспечению безопасности, предназначенного для защиты устройств, удостоверений, данных и приложений в Организации.
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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130888"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="01dc3-104">Создание пробной лаборатории или пилотной среды защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01dc3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01dc3-105">**Applies to:**</span></span>
- <span data-ttu-id="01dc3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01dc3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="01dc3-107">Цель создания пробной лаборатории или пилотной среды — продемонстрировать комплексные и интегрированные возможности защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01dc3-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="01dc3-108">Сведения о том, как данное интеллектуальное решение для обеспечения безопасности обнаруживает, предотвращает и автоматически исследует и реагирует на дополнительные угрозы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="01dc3-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="01dc3-109">В этом руководстве описано, как запустить оценку защитника Microsoft 365 на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="01dc3-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="01dc3-110">Цель состоит в том, чтобы помочь вам настроить решение для обеспечения безопасности в лабораторной среде с пробной учетной записью или в пилотной среде в рабочей среде с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="01dc3-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="01dc3-111">Подготовка пробной лаборатории или пилотной среды может помочь в обеспечении использования операций по обеспечению безопасности для лиц, принимающих решения в Организации.</span><span class="sxs-lookup"><span data-stu-id="01dc3-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="01dc3-112">Когда вы закончите работу с имитацией атаки и удовлетворены результатами, вы сможете полностью развернуть и оператионализе его в вашей организации с помощью технических специалистов Майкрософт по продажам или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="01dc3-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="01dc3-113">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="01dc3-113">This guide will help you:</span></span>
- <span data-ttu-id="01dc3-114">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="01dc3-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="01dc3-115">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="01dc3-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="01dc3-116">Настройка и настройка защитника Майкрософт для идентификации, защитник Майкрософт для Office 365, защитник Майкрософт для конечной точки и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="01dc3-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="01dc3-117">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="01dc3-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="01dc3-118">Имитация атаки на угрозу для создания тестового инцидента или оповещения в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="01dc3-119">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="01dc3-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="01dc3-120">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="01dc3-120">Deployment phases</span></span>

<span data-ttu-id="01dc3-121">Создание пробной лабораторной среды защитника Microsoft 365 и ее развертывание состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="01dc3-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Этапы развертывания: подготовка, Настройка, встроенная](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="01dc3-123">Этап</span><span class="sxs-lookup"><span data-stu-id="01dc3-123">Phase</span></span> | <span data-ttu-id="01dc3-124">Описание</span><span class="sxs-lookup"><span data-stu-id="01dc3-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="01dc3-125">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="01dc3-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="01dc3-126">Сведения о том, что необходимо учитывать при развертывании защитника Microsoft 365 в испытательной лаборатории или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="01dc3-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="01dc3-127">— Заинтересованные стороны и подпись</span><span class="sxs-lookup"><span data-stu-id="01dc3-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="01dc3-128">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="01dc3-128">- Environment considerations</span></span> <br><span data-ttu-id="01dc3-129">Доступ</span><span class="sxs-lookup"><span data-stu-id="01dc3-129">- Access</span></span> <br><span data-ttu-id="01dc3-130">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01dc3-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="01dc3-131">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="01dc3-131">- Configuration order</span></span>
|[<span data-ttu-id="01dc3-132">Этап 2: Настройка</span><span class="sxs-lookup"><span data-stu-id="01dc3-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="01dc3-133">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365 для настройки пробной лаборатории или пилотной среды защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01dc3-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="01dc3-134">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="01dc3-134">You'll be guided to:</span></span><br><br><span data-ttu-id="01dc3-135">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="01dc3-136">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="01dc3-136">- Configure domain</span></span><br><span data-ttu-id="01dc3-137">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="01dc3-138">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="01dc3-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="01dc3-139">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="01dc3-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="01dc3-140">Настройте каждую из базовых и встроенных конечных точек защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01dc3-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="01dc3-141">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="01dc3-141">You'll be guided to:</span></span><br><br><span data-ttu-id="01dc3-142">— Настройка защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="01dc3-143">— Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="01dc3-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="01dc3-144">Настройка защитника Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="01dc3-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="01dc3-145">Настройка защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="01dc3-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="01dc3-146">В области</span><span class="sxs-lookup"><span data-stu-id="01dc3-146">In scope</span></span>

<span data-ttu-id="01dc3-147">В этом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="01dc3-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="01dc3-148">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01dc3-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="01dc3-149">Настройка защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="01dc3-150">Подпишитесь на пробную версию Microsoft 365 и используйте полную лицензию, если вы используете пилотный проект</span><span class="sxs-lookup"><span data-stu-id="01dc3-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="01dc3-151">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="01dc3-151">Configure domain</span></span>
    -   <span data-ttu-id="01dc3-152">Назначение лицензий на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="01dc3-153">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="01dc3-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="01dc3-154">Настройка всех базовых принципов защитника Microsoft 365 на основе рекомендаций</span><span class="sxs-lookup"><span data-stu-id="01dc3-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="01dc3-155">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="01dc3-156">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="01dc3-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="01dc3-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="01dc3-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="01dc3-158">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="01dc3-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="01dc3-159">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="01dc3-159">Out of scope</span></span>

<span data-ttu-id="01dc3-160">Ниже приведены рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="01dc3-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="01dc3-161">Конфигурация сторонних решений, которые могут интегрироваться с защитником Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="01dc3-162">Тестирование уязвимости в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="01dc3-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="01dc3-163">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="01dc3-163">Next step</span></span>
<span data-ttu-id="01dc3-164">[Этап 1: подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="01dc3-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="01dc3-165">Подготовка пробной лаборатории или пилотной среды защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01dc3-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
