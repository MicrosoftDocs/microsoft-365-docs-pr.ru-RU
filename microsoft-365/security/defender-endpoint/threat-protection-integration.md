---
title: Интеграция Microsoft Defender для конечной точки с другими решениями Майкрософт
description: Узнайте, как Microsoft Defender для конечной точки интегрируется с другими решениями Майкрософт, включая Центр безопасности Microsoft Defender для удостоверений и Azure.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: защитник Microsoft 365, условный доступ, office, расширенные средства защиты от угроз, защитник Microsoft для удостоверений, защитник Microsoft для office, центр безопасности azure, безопасность облачных приложений Майкрософт, лазурный sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7d12afd27288655f4f5a82eeed24686f27171a7a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765399"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="74d9c-104">Защитник Microsoft для конечной точки и другие решения Майкрософт</span><span class="sxs-lookup"><span data-stu-id="74d9c-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74d9c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="74d9c-105">**Applies to:**</span></span>
- [<span data-ttu-id="74d9c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="74d9c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="74d9c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74d9c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74d9c-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="74d9c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74d9c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="74d9c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="74d9c-110">Интеграция с другими решениями Майкрософт</span><span class="sxs-lookup"><span data-stu-id="74d9c-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="74d9c-111">Microsoft Defender для конечной точки напрямую интегрируется с различными решениями Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="74d9c-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="74d9c-112">Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="74d9c-112">Azure Security Center</span></span>
<span data-ttu-id="74d9c-113">Microsoft Defender for Endpoint предоставляет комплексное решение для защиты серверов, включая возможности обнаружения конечных точек и реагирования (EDR) на Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="74d9c-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="74d9c-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="74d9c-114">Azure Sentinel</span></span>
<span data-ttu-id="74d9c-115">Соединитель Microsoft Defender для конечной точки позволяет передавать оповещения из Microsoft Defender для конечной точки в Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="74d9c-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="74d9c-116">Это позволит более комплексно анализировать события безопасности в организации и создавать книги для эффективного и немедленного реагирования.</span><span class="sxs-lookup"><span data-stu-id="74d9c-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="74d9c-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="74d9c-117">Azure Information Protection</span></span>
<span data-ttu-id="74d9c-118">Недавно мы отключили интеграцию Azure Information Protection, так как наши возможности DLP конечных точек включают улучшенное решение обнаружения и защиты конфиденциальных данных, хранимых на конечных устройствах, что облегчает большую видимость и интеграцию решений.</span><span class="sxs-lookup"><span data-stu-id="74d9c-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="74d9c-119">Об этом было объявлено в следующем [блоге](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span><span class="sxs-lookup"><span data-stu-id="74d9c-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="74d9c-120">Мы рекомендуем клиентам перейти к использованию DLP конечной точки.</span><span class="sxs-lookup"><span data-stu-id="74d9c-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="74d9c-121">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="74d9c-121">Conditional Access</span></span>
<span data-ttu-id="74d9c-122">Динамический показатель риска устройств Microsoft Defender для конечной точки интегрирован в оценку условного доступа, обеспечивая доступ к ресурсам только защищенным устройствам.</span><span class="sxs-lookup"><span data-stu-id="74d9c-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="74d9c-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74d9c-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="74d9c-124">Microsoft Cloud App Security использует сигналы Microsoft Defender для конечных точек, чтобы обеспечить прямую видимость использования облачных приложений, включая использование неподтвердимых облачных служб (теневых ИТ) со всех устройств, отслеживаемых Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="74d9c-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="74d9c-125">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="74d9c-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="74d9c-126">Подозрительные действия — это процессы, запущенные в контексте пользователя.</span><span class="sxs-lookup"><span data-stu-id="74d9c-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="74d9c-127">Интеграция между Microsoft Defender для конечной точки и Azure ATP обеспечивает гибкость проведения расследования кибербезопасности в различных действиях и удостоверениях.</span><span class="sxs-lookup"><span data-stu-id="74d9c-127">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="74d9c-128">Microsoft Defender для Office</span><span class="sxs-lookup"><span data-stu-id="74d9c-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="74d9c-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) помогает защитить организацию от вредоносных программ в сообщениях электронной почты или файлах с помощью безопасных ссылок ATP, безопасных вложений ATP, расширенных возможностей для защиты от фишинга и подмены данных.</span><span class="sxs-lookup"><span data-stu-id="74d9c-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="74d9c-130">Интеграция между ATP Office 365 и Microsoft Defender для endpoint позволяет аналитикам безопасности перейти вверх по течению для изучения точки входа атаки.</span><span class="sxs-lookup"><span data-stu-id="74d9c-130">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="74d9c-131">С помощью обмена сведениями об угрозах атаки могут быть задержаны и заблокированы.</span><span class="sxs-lookup"><span data-stu-id="74d9c-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="74d9c-132">Данные Defender for Office 365 отображаются для событий в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="74d9c-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="74d9c-133">Для оповещений данные Defender for Office 365 отображаются в зависимости от времени первого действия.</span><span class="sxs-lookup"><span data-stu-id="74d9c-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="74d9c-134">После этого данные больше не доступны в Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="74d9c-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="74d9c-135">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="74d9c-135">Skype for Business</span></span>
<span data-ttu-id="74d9c-136">Интеграция Skype для бизнеса позволяет аналитикам общаться с потенциально скомпрометированным пользователем или владельцем устройств с помощью простой кнопки с портала.</span><span class="sxs-lookup"><span data-stu-id="74d9c-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="74d9c-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74d9c-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="74d9c-138">С помощью Microsoft 365 Defender, Microsoft Defender для конечной точки и различных решений безопасности Майкрософт образуют единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечные точки, удостоверения, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки.</span><span class="sxs-lookup"><span data-stu-id="74d9c-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="74d9c-139">Дополнительные информацию о Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74d9c-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="74d9c-140">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="74d9c-140">Related topics</span></span>
- [<span data-ttu-id="74d9c-141">Настройка интеграции и других расширенных функций</span><span class="sxs-lookup"><span data-stu-id="74d9c-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="74d9c-142">Обзор Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74d9c-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="74d9c-143">Включение Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74d9c-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="74d9c-144">Защита пользователей, данных и устройств с помощью условного доступа</span><span class="sxs-lookup"><span data-stu-id="74d9c-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
