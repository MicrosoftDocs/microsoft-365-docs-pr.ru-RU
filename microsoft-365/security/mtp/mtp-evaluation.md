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
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846488"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="b0861-104">Создание пробной лаборатории или пилотной среды защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0861-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b0861-105">**Applies to:**</span></span>
- <span data-ttu-id="b0861-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b0861-107">Цель создания пробной лаборатории или пилотной среды — продемонстрировать комплексные и интегрированные возможности защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0861-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="b0861-108">Сведения о том, как данное интеллектуальное решение для обеспечения безопасности обнаруживает, предотвращает и автоматически исследует и реагирует на дополнительные угрозы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b0861-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="b0861-109">В этом руководстве описано, как запустить оценку защитника Microsoft 365 на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="b0861-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b0861-110">Цель состоит в том, чтобы помочь вам настроить решение для обеспечения безопасности в лабораторной среде с пробной учетной записью или в пилотной среде в рабочей среде с полной лицензией.</span><span class="sxs-lookup"><span data-stu-id="b0861-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="b0861-111">Подготовка пробной лаборатории или пилотной среды может помочь в обеспечении использования операций по обеспечению безопасности для лиц, принимающих решения в Организации.</span><span class="sxs-lookup"><span data-stu-id="b0861-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="b0861-112">Когда вы закончите работу с имитацией атаки и удовлетворены результатами, вы сможете полностью развернуть и оператионализе его в вашей организации с помощью технических специалистов Майкрософт по продажам или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b0861-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b0861-113">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="b0861-113">This guide will help you:</span></span>
- <span data-ttu-id="b0861-114">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b0861-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="b0861-115">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="b0861-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b0861-116">Настройка и настройка защитника Майкрософт для идентификации, защитник Майкрософт для Office 365, защитник Майкрософт для конечной точки и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b0861-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b0861-117">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b0861-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="b0861-118">Имитация атаки на угрозу для создания тестового инцидента или оповещения в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="b0861-119">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="b0861-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b0861-120">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="b0861-120">Deployment phases</span></span>

<span data-ttu-id="b0861-121">Создание пробной лабораторной среды защитника Microsoft 365 и ее развертывание состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="b0861-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="b0861-122">Этап</span><span class="sxs-lookup"><span data-stu-id="b0861-122">Phase</span></span> | <span data-ttu-id="b0861-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b0861-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b0861-124">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b0861-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="b0861-125">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="b0861-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b0861-126">Сведения о том, что необходимо учитывать при развертывании защитника Microsoft 365 в испытательной лаборатории или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="b0861-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="b0861-127">— Заинтересованные стороны и подпись</span><span class="sxs-lookup"><span data-stu-id="b0861-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b0861-128">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="b0861-128">- Environment considerations</span></span> <br><span data-ttu-id="b0861-129">Доступ</span><span class="sxs-lookup"><span data-stu-id="b0861-129">- Access</span></span> <br><span data-ttu-id="b0861-130">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0861-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b0861-131">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="b0861-131">- Configuration order</span></span>
|  <span data-ttu-id="b0861-132">![Этап 2: Настройка](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b0861-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b0861-133">Этап 2: Настройка</span><span class="sxs-lookup"><span data-stu-id="b0861-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b0861-134">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365 для настройки пробной лаборатории или пилотной среды защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0861-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="b0861-135">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b0861-135">You'll be guided to:</span></span><br><br><span data-ttu-id="b0861-136">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b0861-137">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b0861-137">- Configure domain</span></span><br><span data-ttu-id="b0861-138">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b0861-139">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="b0861-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="b0861-140">![Этап 3: Настройка встроенного &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b0861-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b0861-141">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="b0861-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b0861-142">Настройте каждую из базовых и встроенных конечных точек защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0861-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="b0861-143">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b0861-143">You'll be guided to:</span></span><br><br><span data-ttu-id="b0861-144">— Настройка защитника Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="b0861-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="b0861-145">— Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b0861-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b0861-146">Настройка защитника Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="b0861-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="b0861-147">Настройка защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b0861-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="b0861-148">В области</span><span class="sxs-lookup"><span data-stu-id="b0861-148">In scope</span></span>

<span data-ttu-id="b0861-149">В этом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b0861-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="b0861-150">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0861-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b0861-151">Настройка защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="b0861-152">Подпишитесь на пробную версию Microsoft 365 и используйте полную лицензию, если вы используете пилотный проект</span><span class="sxs-lookup"><span data-stu-id="b0861-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="b0861-153">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b0861-153">Configure domain</span></span>
    -   <span data-ttu-id="b0861-154">Назначение лицензий на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b0861-155">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="b0861-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b0861-156">Настройка всех базовых принципов защитника Microsoft 365 на основе рекомендаций</span><span class="sxs-lookup"><span data-stu-id="b0861-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="b0861-157">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="b0861-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="b0861-158">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="b0861-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="b0861-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b0861-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b0861-160">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b0861-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b0861-161">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="b0861-161">Out of scope</span></span>

<span data-ttu-id="b0861-162">Ниже приведены рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b0861-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b0861-163">Конфигурация сторонних решений, которые могут интегрироваться с защитником Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="b0861-164">Тестирование уязвимости в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="b0861-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b0861-165">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b0861-165">Next step</span></span>
<span data-ttu-id="b0861-166">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b0861-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="b0861-167">[Этап 1: подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="b0861-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="b0861-168">Подготовка пробной лаборатории или пилотной среды защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0861-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
