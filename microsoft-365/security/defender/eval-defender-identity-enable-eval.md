---
title: Включить среду оценки для Microsoft Defender для identity, настроить экземпляр MDI, установить и настроить датчик MDI, чтобы датчик MDI обнаруживать локальных администраторов
description: Настройка Microsoft Defender для удостоверений в Microsoft 365 Defender пробной лаборатории или пилотной среде путем & настройки датчика и обнаружения локальных администраторов на других компьютерах.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458563"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="ef080-103">Включить среду оценки для Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ef080-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="ef080-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ef080-104">**Applies to:**</span></span>
- <span data-ttu-id="ef080-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef080-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="ef080-106">Эта статья — [шаг 2 из 2 в](eval-defender-identity-overview.md) процессе настройки среды оценки для Microsoft Defender для identity.</span><span class="sxs-lookup"><span data-stu-id="ef080-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="ef080-107">Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ef080-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="ef080-108">Чтобы настроить среду Microsoft Defender для удостоверений, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ef080-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Действия, направленные на то, чтобы включить Microsoft Defender для удостоверений в среде оценки Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="ef080-110">Шаг 1. Настройка экземпляра Defender для удостоверения</span><span class="sxs-lookup"><span data-stu-id="ef080-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="ef080-111">Шаг 2. Установка и настройка датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="ef080-112">Шаг 3. Настройка параметров журнала событий и прокси на компьютерах с помощью датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="ef080-113">Шаг 4. Разрешить defender for Identity для идентификации локальных администраторов на других компьютерах</span><span class="sxs-lookup"><span data-stu-id="ef080-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="ef080-114">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="ef080-114">Step 1.</span></span> <span data-ttu-id="ef080-115">Настройка экземпляра Defender для удостоверения</span><span class="sxs-lookup"><span data-stu-id="ef080-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="ef080-116">Во входе на портал Defender for Identity для создания экземпляра и подключения этого экземпляра к среде Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef080-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="ef080-117">Шаг</span><span class="sxs-lookup"><span data-stu-id="ef080-117">Step</span></span>     |<span data-ttu-id="ef080-118">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="ef080-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ef080-119">1</span><span class="sxs-lookup"><span data-stu-id="ef080-119">1</span></span>     | <span data-ttu-id="ef080-120">Создание экземпляра Defender для удостоверения</span><span class="sxs-lookup"><span data-stu-id="ef080-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="ef080-121">Quickstart: создание экземпляра Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ef080-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="ef080-122">2</span><span class="sxs-lookup"><span data-stu-id="ef080-122">2</span></span>     | <span data-ttu-id="ef080-123">Подключение экземпляр Defender for Identity в лесу Active Directory</span><span class="sxs-lookup"><span data-stu-id="ef080-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="ef080-124">Quickstart: Подключение в ваш лес Active Directory</span><span class="sxs-lookup"><span data-stu-id="ef080-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="ef080-125">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="ef080-125">Step 2.</span></span> <span data-ttu-id="ef080-126">Установка и настройка датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-126">Install and configure the sensor</span></span>

<span data-ttu-id="ef080-127">Затем скачайте, установите и настройте датчик Defender for Identity на контроллерах домена и серверах AD FS в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="ef080-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="ef080-128">Шаг</span><span class="sxs-lookup"><span data-stu-id="ef080-128">Step</span></span>     |<span data-ttu-id="ef080-129">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="ef080-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ef080-130">1</span><span class="sxs-lookup"><span data-stu-id="ef080-130">1</span></span>     | <span data-ttu-id="ef080-131">Определите количество необходимых датчиков Microsoft Defender для удостоверений.</span><span class="sxs-lookup"><span data-stu-id="ef080-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="ef080-132">Планирование емкости для Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ef080-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="ef080-133">2</span><span class="sxs-lookup"><span data-stu-id="ef080-133">2</span></span>     | <span data-ttu-id="ef080-134">Скачайте пакет установки датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="ef080-135">Quickstart: Скачайте пакет установки датчика идентификации Microsoft Defender для идентификации</span><span class="sxs-lookup"><span data-stu-id="ef080-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="ef080-136">3</span><span class="sxs-lookup"><span data-stu-id="ef080-136">3</span></span>     | <span data-ttu-id="ef080-137">Установка датчика Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ef080-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="ef080-138">Quickstart: Установите датчик Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ef080-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="ef080-139">4 </span><span class="sxs-lookup"><span data-stu-id="ef080-139">4</span></span>     | <span data-ttu-id="ef080-140">Настройка датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-140">Configure the sensor</span></span>       |  [<span data-ttu-id="ef080-141">Настройка параметров датчика удостоверений Для защитника Майкрософт </span><span class="sxs-lookup"><span data-stu-id="ef080-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="ef080-142">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="ef080-142">Step 3.</span></span> <span data-ttu-id="ef080-143">Настройка параметров журнала событий и прокси на компьютерах с помощью датчика</span><span class="sxs-lookup"><span data-stu-id="ef080-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="ef080-144">На компьютерах, на которые установлен датчик, настройте Windows журнал событий и параметры прокси-сервера в Интернете, чтобы включить и повысить возможности обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ef080-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="ef080-145">Шаг</span><span class="sxs-lookup"><span data-stu-id="ef080-145">Step</span></span>     |<span data-ttu-id="ef080-146">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="ef080-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ef080-147">1</span><span class="sxs-lookup"><span data-stu-id="ef080-147">1</span></span>     | <span data-ttu-id="ef080-148">Настройка Windows журнала событий</span><span class="sxs-lookup"><span data-stu-id="ef080-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="ef080-149">Настройка коллекции Windows событий</span><span class="sxs-lookup"><span data-stu-id="ef080-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="ef080-150">2</span><span class="sxs-lookup"><span data-stu-id="ef080-150">2</span></span>     | <span data-ttu-id="ef080-151">Настройка параметров прокси-сервера в Интернете</span><span class="sxs-lookup"><span data-stu-id="ef080-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="ef080-152">Настройка параметров прокси-сервера конечной точки и подключения к Интернету для датчика удостоверений Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ef080-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="ef080-153">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="ef080-153">Step 4.</span></span> <span data-ttu-id="ef080-154">Разрешить defender for Identity для идентификации локальных администраторов на других компьютерах</span><span class="sxs-lookup"><span data-stu-id="ef080-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="ef080-155">Обнаружение путей с последующим движением в Microsoft Defender для удостоверений зависит от запросов, определяющих локальных администраторов на определенных машинах.</span><span class="sxs-lookup"><span data-stu-id="ef080-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="ef080-156">Эти запросы выполняются с помощью протокола SAM-R с помощью учетной записи Defender для службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="ef080-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="ef080-157">Чтобы Windows клиенты и серверы позволяли учетной записи Defender for Identity выполнять SAM-R, необходимо внести изменения в групповую политику, чтобы добавить учетную запись службы Defender для удостоверений в дополнение к настроенным учетным записям, указанным в политике доступа к сети.</span><span class="sxs-lookup"><span data-stu-id="ef080-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="ef080-158">Не забудьте применить групповые политики на всех компьютерах, **кроме контроллеров домена.**</span><span class="sxs-lookup"><span data-stu-id="ef080-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="ef080-159">Инструкции по этому делать см. в инструкции [Configure Microsoft Defender for Identity, чтобы сделать удаленные вызовы в SAM.](/defender-for-identity/install-step8-samr)</span><span class="sxs-lookup"><span data-stu-id="ef080-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="ef080-160">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ef080-160">Next steps</span></span>

<span data-ttu-id="ef080-161">Шаг 3 из 3: [пилотный microsoft Defender для удостоверений](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="ef080-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="ef080-162">Возвращение к обзору [оценки microsoft Defender для удостоверений](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ef080-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="ef080-163">Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ef080-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>