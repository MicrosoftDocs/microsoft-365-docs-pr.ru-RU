---
title: Запись устройств в Microsoft Defender для конечной точки
description: Отслеживайте учет устройств, управляемых intune, в Microsoft Defender для конечной точки и увеличение скорости в составе.
keywords: управление intune, Microsoft Defender для конечной точки, Microsoft Defender, Защитник Windows, управление конфигурацией
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e0d5a13b0c33516209bd2d18361a1de6ab9245c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932945"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="71ee4-104">Запись устройств в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="71ee4-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71ee4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="71ee4-105">**Applies to:**</span></span>
- [<span data-ttu-id="71ee4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="71ee4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71ee4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71ee4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="71ee4-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="71ee4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71ee4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="71ee4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="71ee4-110">Каждое бортовом устройстве добавляет дополнительный датчик обнаружения конечных точек и ответа (EDR) и повышает видимость по поводу активности нарушения в сети.</span><span class="sxs-lookup"><span data-stu-id="71ee4-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="71ee4-111">Онбординг также обеспечивает проверку устройства на наличие уязвимых компонентов, а также проблемы с конфигурацией безопасности и получение критически важных действий по исправлению ситуации во время атак.</span><span class="sxs-lookup"><span data-stu-id="71ee4-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="71ee4-112">Перед отслеживанием и управлением на борту устройств:</span><span class="sxs-lookup"><span data-stu-id="71ee4-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="71ee4-113">Регистрация устройств в управление Intune</span><span class="sxs-lookup"><span data-stu-id="71ee4-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="71ee4-114">Убедитесь, что у вас есть необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="71ee4-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="71ee4-115">Обнаружение и отслеживание незащищенных устройств</span><span class="sxs-lookup"><span data-stu-id="71ee4-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="71ee4-116">Карта **onboarding** предоставляет высококачественный обзор скорости вмеяния, сравнивая количество устройств с Windows 10, которые фактически были на борту, с Defender для конечной точки, и общее число устройств Windows 10, управляемых intune.</span><span class="sxs-lookup"><span data-stu-id="71ee4-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="71ee4-117">![Карта onboarding управления конфигурацией устройств](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="71ee4-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="71ee4-118">*Карта, показывающая бортовые устройства по сравнению с общее число устройств с управлением Intune в Windows 10*</span><span class="sxs-lookup"><span data-stu-id="71ee4-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="71ee4-119">Если вы использовали диспетчер конфигурации Центра безопасности, сценарий бортовой обработки или другие методы бортовой обработки, которые не используют профили Intune, вы можете столкнуться с несоответствиями данных.</span><span class="sxs-lookup"><span data-stu-id="71ee4-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="71ee4-120">Чтобы устранить эти несоответствия, создайте соответствующий профиль конфигурации Intune для onboarding Defender для конечной точки и назначьте этот профиль устройствам.</span><span class="sxs-lookup"><span data-stu-id="71ee4-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="71ee4-121">На борту больше устройств с профилями Intune</span><span class="sxs-lookup"><span data-stu-id="71ee4-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="71ee4-122">Defender for Endpoint предоставляет несколько удобных вариантов для устройств [с Windows 10.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="71ee4-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="71ee4-123">Однако для устройств с управляемым intune можно использовать профили Intune для удобного развертывания датчика Defender для конечных точек для выбора устройств, эффективно вовсю перенаправив эти устройства в службу.</span><span class="sxs-lookup"><span data-stu-id="71ee4-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="71ee4-124">С **бортовой карты** выберите  дополнительные устройства для создания и назначения профиля в Intune.</span><span class="sxs-lookup"><span data-stu-id="71ee4-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="71ee4-125">Ссылка приводит вас на страницу соответствия требованиям устройств в Intune, которая предоставляет аналогичный обзор состояния бортового устройства.</span><span class="sxs-lookup"><span data-stu-id="71ee4-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="71ee4-126">![Страница Microsoft Defender для соответствия требованиям для конечных устройств в управлении устройствами Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="71ee4-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="71ee4-127">*Страница Microsoft Defender для соответствия требованиям для конечных устройств в управлении устройствами Intune*</span><span class="sxs-lookup"><span data-stu-id="71ee4-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="71ee4-128">Кроме того, вы можете перейти на страницу соответствия требованиям для конечной точки Defender для конечной точки на портале [Microsoft Azure](https://portal.azure.com/) из всех служб **> Intune >** устройств > Microsoft Defender ATP .</span><span class="sxs-lookup"><span data-stu-id="71ee4-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="71ee4-129">Если вы хотите просмотреть самые последние данные устройства, нажмите кнопку Список устройств **без датчика ATP**.</span><span class="sxs-lookup"><span data-stu-id="71ee4-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="71ee4-130">На странице соответствия требованиям устройства создайте профиль конфигурации специально для развертывания датчика Defender для конечной точки и назначьте этот профиль устройствам, которые необходимо на борту.</span><span class="sxs-lookup"><span data-stu-id="71ee4-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="71ee4-131">Для этого можно либо:</span><span class="sxs-lookup"><span data-stu-id="71ee4-131">To do this, you can either:</span></span>

- <span data-ttu-id="71ee4-132">Выберите **Создать профиль конфигурации устройства, чтобы настроить датчик ATP,** чтобы начать с предварительного профиля конфигурации устройства.</span><span class="sxs-lookup"><span data-stu-id="71ee4-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="71ee4-133">Создайте профиль конфигурации устройства с нуля.</span><span class="sxs-lookup"><span data-stu-id="71ee4-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="71ee4-134">Дополнительные сведения см. в материале Об использовании профилей конфигурации устройств Intune на бортовых устройствах [в Defender для конечной точки.](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="71ee4-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="71ee4-135">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="71ee4-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71ee4-136">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="71ee4-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="71ee4-137">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="71ee4-137">Related topics</span></span>
- [<span data-ttu-id="71ee4-138">Убедитесь, что ваши устройства настроены правильно</span><span class="sxs-lookup"><span data-stu-id="71ee4-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="71ee4-139">Повышение соответствия базовому стандарту безопасности Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="71ee4-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="71ee4-140">Оптимизация развертывания и обнаружений правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="71ee4-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
