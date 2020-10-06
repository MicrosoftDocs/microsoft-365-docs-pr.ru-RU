---
title: Оценка Защиты от угроз (Майкрософт)
description: Настройте пробную лабораторию и пилотную среду Microsoft Threat Protection, чтобы проверить, как согласованное решение для защиты от угроз предназначено для защиты устройств, удостоверений, данных и приложений, которые могут помочь Организации
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368063"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="b4c95-104">Создание пробной лаборатории или пилотной среды Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b4c95-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4c95-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b4c95-105">**Applies to:**</span></span>
- <span data-ttu-id="b4c95-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b4c95-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b4c95-107">Цель создания пробной лаборатории или пилотной среды — продемонстрировать комплексные, интегрированные и интеллектуальные возможности защиты от угроз Майкрософт при обнаружении, предотвращении, расследовании и откликах, которые можно использовать в Организации.</span><span class="sxs-lookup"><span data-stu-id="b4c95-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="b4c95-108">В этом руководстве описано, как начать оценку системы защиты от угроз Майкрософт на основе рекомендуемых путей развертывания.</span><span class="sxs-lookup"><span data-stu-id="b4c95-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b4c95-109">Цель состоит в том, чтобы помочь вам настроить интегрированные службы защиты от угроз Майкрософт в лабораторной среде при использовании пробной учетной записи или в пилотной среде в рабочей среде при использовании полной лицензии.</span><span class="sxs-lookup"><span data-stu-id="b4c95-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="b4c95-110">Результаты, которые будут использоваться для представления вариантов использования системы безопасности в решениях по обеспечению безопасности в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b4c95-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="b4c95-111">Когда вы закончите работу с имитацией атаки и удовлетворены результатами, вы можете полностью развернуть и оператионализе его в вашей организации с помощью технических специалистов Майкрософт по продажам или экспертов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b4c95-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b4c95-112">Это руководство поможет вам:</span><span class="sxs-lookup"><span data-stu-id="b4c95-112">This guide will help you:</span></span>
- <span data-ttu-id="b4c95-113">Настройка сервера лаборатории и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b4c95-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="b4c95-114">Настройка Active Directory для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="b4c95-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b4c95-115">Настройка и настройка Azure ATP, Office ATP, Microsoft Defender ATP и Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b4c95-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b4c95-116">Настройка локальных политик для сервера и компьютеров</span><span class="sxs-lookup"><span data-stu-id="b4c95-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="b4c95-117">Имитирует атаку угроз для создания тестового инцидента или оповещения в Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="b4c95-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="b4c95-118">Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="b4c95-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b4c95-119">Этапы развертывания</span><span class="sxs-lookup"><span data-stu-id="b4c95-119">Deployment phases</span></span>

<span data-ttu-id="b4c95-120">Создание пробной лабораторной среды Майкрософт по защите от угроз и ее развертывание выполняется в три этапа:</span><span class="sxs-lookup"><span data-stu-id="b4c95-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="b4c95-121">Этап</span><span class="sxs-lookup"><span data-stu-id="b4c95-121">Phase</span></span> | <span data-ttu-id="b4c95-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c95-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b4c95-123">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b4c95-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="b4c95-124">Этап 1: подготовка</span><span class="sxs-lookup"><span data-stu-id="b4c95-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b4c95-125">Сведения о том, что необходимо учитывать при развертывании Microsoft Threat Protection в испытательной лаборатории или пилотной среде:</span><span class="sxs-lookup"><span data-stu-id="b4c95-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="b4c95-126">— Заинтересованные стороны и подпись</span><span class="sxs-lookup"><span data-stu-id="b4c95-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b4c95-127">Аспекты среды</span><span class="sxs-lookup"><span data-stu-id="b4c95-127">- Environment considerations</span></span> <br><span data-ttu-id="b4c95-128">Доступ</span><span class="sxs-lookup"><span data-stu-id="b4c95-128">- Access</span></span> <br><span data-ttu-id="b4c95-129">— Установка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b4c95-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b4c95-130">— Порядок настройки</span><span class="sxs-lookup"><span data-stu-id="b4c95-130">- Configuration order</span></span>
|  <span data-ttu-id="b4c95-131">![Этап 2: Настройка](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b4c95-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b4c95-132">Этап 2: Настройка</span><span class="sxs-lookup"><span data-stu-id="b4c95-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b4c95-133">Выполните начальные действия, чтобы получить доступ к центру безопасности Microsoft 365 для настройки пробной лаборатории или пилотной среды Майкрософт по защите от угроз.</span><span class="sxs-lookup"><span data-stu-id="b4c95-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="b4c95-134">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b4c95-134">You'll be guided to:</span></span><br><br><span data-ttu-id="b4c95-135">— Подписаться на пробную версию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4c95-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b4c95-136">— Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b4c95-136">- Configure domain</span></span><br><span data-ttu-id="b4c95-137">— Назначение лицензий Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4c95-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b4c95-138">— Завершите работу мастера установки на портале.</span><span class="sxs-lookup"><span data-stu-id="b4c95-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="b4c95-139">![Этап 3: Настройка встроенного &](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b4c95-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b4c95-140">Этап 3: Настройка встроенного &</span><span class="sxs-lookup"><span data-stu-id="b4c95-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b4c95-141">Настройте каждый из принципов и встроенных конечных точек защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b4c95-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="b4c95-142">Вы будете переработаны в следующих руководствах:</span><span class="sxs-lookup"><span data-stu-id="b4c95-142">You'll be guided to:</span></span><br><br><span data-ttu-id="b4c95-143">— Настройка Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="b4c95-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="b4c95-144">— Настройка Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b4c95-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b4c95-145">— Настройка службы Advanced Threat Protection в Azure</span><span class="sxs-lookup"><span data-stu-id="b4c95-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="b4c95-146">— Настройка Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b4c95-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="b4c95-147">В области</span><span class="sxs-lookup"><span data-stu-id="b4c95-147">In scope</span></span>

<span data-ttu-id="b4c95-148">В этом руководстве представлены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b4c95-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="b4c95-149">Настройка Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b4c95-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b4c95-150">Настройка защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b4c95-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="b4c95-151">Подпишитесь на пробную версию Microsoft 365 и используйте полную лицензию, если вы используете пилотный проект</span><span class="sxs-lookup"><span data-stu-id="b4c95-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="b4c95-152">Настройка домена</span><span class="sxs-lookup"><span data-stu-id="b4c95-152">Configure domain</span></span>
    -   <span data-ttu-id="b4c95-153">Назначение лицензий на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4c95-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b4c95-154">Завершение работы мастера установки на портале</span><span class="sxs-lookup"><span data-stu-id="b4c95-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b4c95-155">Настройка всех принципов защиты от угроз Майкрософт на основе рекомендаций</span><span class="sxs-lookup"><span data-stu-id="b4c95-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="b4c95-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b4c95-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b4c95-157">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="b4c95-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b4c95-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b4c95-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b4c95-159">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b4c95-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b4c95-160">Вне области поддержки</span><span class="sxs-lookup"><span data-stu-id="b4c95-160">Out of scope</span></span>

<span data-ttu-id="b4c95-161">Ниже приведены рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b4c95-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b4c95-162">Конфигурация сторонних решений, которые могут интегрироваться с защитой от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b4c95-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="b4c95-163">Тестирование уязвимости в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="b4c95-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b4c95-164">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b4c95-164">Next step</span></span>
<span data-ttu-id="b4c95-165">![Этап 1: подготовка](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b4c95-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="b4c95-166">[Этап 1: подготовка](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="b4c95-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="b4c95-167">Подготовка пробной лаборатории или пилотной среды Майкрософт для защиты от угроз</span><span class="sxs-lookup"><span data-stu-id="b4c95-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
