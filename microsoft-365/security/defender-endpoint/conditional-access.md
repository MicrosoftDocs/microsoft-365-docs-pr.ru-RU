---
title: Включить условный доступ для более лучшей защиты пользователей, устройств и данных
description: Включить условный доступ, чтобы предотвратить запуск приложений, если устройство считается в опасности, а приложение определяется как не соответствующим требованиям.
keywords: условный доступ, блокировка приложений, уровень безопасности, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166201"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="8a8f5-104">Включить условный доступ для более лучшей защиты пользователей, устройств и данных</span><span class="sxs-lookup"><span data-stu-id="8a8f5-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a8f5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8a8f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a8f5-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8a8f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a8f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a8f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8a8f5-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="8a8f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a8f5-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="8a8f5-110">Условный доступ — это возможность, которая помогает лучше защитить пользователей и корпоративные сведения, убедившись, что доступ к приложениям имеют только защищенные устройства.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="8a8f5-111">С помощью условного доступа можно управлять доступом к корпоративной информации в зависимости от уровня риска устройства.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="8a8f5-112">Это помогает сохранить доверенных пользователей на надежных устройствах с помощью надежных приложений.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="8a8f5-113">Вы можете определить условия безопасности, при которых устройства и приложения могут запускать и получать доступ к данным из сети, применив политики, чтобы не запускать приложения до тех пор, пока устройство не вернется в состояние, удовлетворяющее требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="8a8f5-114">Реализация условного доступа в Defender для конечной точки основана на политиках соответствия устройствам Microsoft Intune (Intune) и политике условного доступа Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8a8f5-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="8a8f5-115">Политика соответствия требованиям используется с помощью условного доступа, чтобы разрешить доступ к приложениям только устройствам, которые выполняют одно или несколько правил политики соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="8a8f5-116">Понимание потока условного доступа</span><span class="sxs-lookup"><span data-stu-id="8a8f5-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="8a8f5-117">При наложении условного доступа на устройство доступ к конфиденциальному контенту блокируется до устранения угрозы.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="8a8f5-118">Поток начинается с того, что устройства, как видно, имеют низкий, средний или высокий риск.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="8a8f5-119">Затем эти определения риска отправляются в Intune.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="8a8f5-120">В зависимости от настройки политик в Intune можно настроить условный доступ, чтобы при определенных условиях применялась политика.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="8a8f5-121">Например, можно настроить Intune для применения условного доступа на устройствах с высоким риском.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="8a8f5-122">В Intune политика соответствия требованиям для устройств используется совместно с Условным доступом Azure AD для блокировки доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="8a8f5-123">Параллельно запускается автоматизированный процесс расследования и устранения последствий.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="8a8f5-124">Пользователь по-прежнему может использовать устройство во время автоматического расследования и восстановления, но доступ к корпоративным данным блокируется до полного устранения угрозы.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="8a8f5-125">Чтобы устранить риск, найденный на устройстве, необходимо вернуть устройство в состояние, удовлетворяющее требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="8a8f5-126">Устройство возвращается в состояние совместимым, если на нем нет риска.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="8a8f5-127">Существует три способа устранения риска:</span><span class="sxs-lookup"><span data-stu-id="8a8f5-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="8a8f5-128">Используйте ручное или автоматическое исправление.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="8a8f5-129">Устранение активных оповещений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="8a8f5-130">Это снимет риск с устройства.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="8a8f5-131">Вы можете удалить устройство из активных политик и, следовательно, условный доступ не будет применяться на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="8a8f5-132">Ручное исправление требует от администратора секопов для проверки оповещений и устранения риска на устройстве.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="8a8f5-133">Автоматическое исправление настраивается с помощью параметров конфигурации, которые предоставляются в следующем разделе [Настройка условного доступа.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="8a8f5-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="8a8f5-134">Когда риск удаляется с помощью ручного или автоматического восстановления, устройство возвращается в состояние, удовлетворяющее требованиям, и доступ к приложениям предоставляется.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="8a8f5-135">В следующем примере последовательности событий объясняется условный доступ в действии:</span><span class="sxs-lookup"><span data-stu-id="8a8f5-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="8a8f5-136">Пользователь открывает вредоносный файл, а Защитник для конечной точки пометит устройство как высокий риск.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="8a8f5-137">Оценка высокого риска передается в Intune.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="8a8f5-138">Параллельно начато автоматическое расследование для устранения выявленной угрозы.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="8a8f5-139">Для устранения выявленной угрозы также может быть сделано исправление вручную.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="8a8f5-140">На основе политики, созданной в Intune, устройство помечено как не соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="8a8f5-141">Затем оценка передается в Azure AD политикой условного доступа Intune.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="8a8f5-142">В Azure AD соответствующая политика применяется для блокировки доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="8a8f5-143">Руководство или автоматическое расследование и исправление завершены, и угроза удаляется.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="8a8f5-144">Защитник для конечной точки видит, что на устройстве нет риска, и Intune оценивает устройство в соответствии с требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="8a8f5-145">Azure AD применяет политику, которая позволяет получать доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="8a8f5-146">Теперь пользователи могут получать доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8a8f5-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="8a8f5-147">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="8a8f5-147">Related topic</span></span>
- [<span data-ttu-id="8a8f5-148">Настройка условного доступа в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8a8f5-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
