---
title: Включение Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Узнайте, как включить Защиту от угроз (Майкрософт) и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: Начало работы, включение MTP, защита от угроз Майкрософт, M365, безопасность, расположение данных, необходимые разрешения, права на лицензирование, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a85680e323c7a8fba6f2d74d5cc00c58c2013d23
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662055"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="658de-104">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="658de-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="658de-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="658de-105">**Applies to:**</span></span>
- <span data-ttu-id="658de-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="658de-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="658de-107">Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="658de-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="658de-108">В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="658de-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="658de-109">Проверка допустимости лицензий и необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="658de-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="658de-110">Клиенты, имеющие Microsoft 365 365, а также эквивалентное сочетание лицензий, могут использовать защиту от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="658de-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="658de-111">Дополнительные сведения см. в статье [Требования к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="658de-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="658de-112">Чтобы включить защиту от угроз Майкрософт, необходимо быть **глобальным администратором** или **администратором безопасности** в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .</span><span class="sxs-lookup"><span data-stu-id="658de-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="658de-113">Начало работы со службой</span><span class="sxs-lookup"><span data-stu-id="658de-113">Start using the service</span></span>
<span data-ttu-id="658de-114">Защита от угроз Майкрософт собирает данные из различных интегрированных служб.</span><span class="sxs-lookup"><span data-stu-id="658de-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="658de-115">Он будет обрабатывать и хранить данные централизованно, чтобы определять новые аналитики и создавать централизованные рабочие процессы ответа.</span><span class="sxs-lookup"><span data-stu-id="658de-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="658de-116">Перед включением службы центр безопасности Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) не отображает **инциденты** и параметры **центра уведомлений** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="658de-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="658de-117">![Изображение области навигации центра безопасности Microsoft 365 без функций](../images/mtp-off.png)
защиты от угроз Майкрософт*Центр безопасности Майкрософт 365 с отключенной функцией защиты от угроз Майкрософт*</span><span class="sxs-lookup"><span data-stu-id="658de-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="658de-118">Чтобы включить защиту от угроз Майкрософт, выберите **Параметры** в области навигации.</span><span class="sxs-lookup"><span data-stu-id="658de-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="658de-119">На **[странице Параметры](https://security.microsoft.com/settings)** перейдите к разделу **Защита от угроз Майкрософт** > /отказ от участия **/отказ**.</span><span class="sxs-lookup"><span data-stu-id="658de-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="658de-120">Если вы не видите **Параметры** в области навигации или не смогли получить доступ к странице, проверьте свои разрешения и лицензии.</span><span class="sxs-lookup"><span data-stu-id="658de-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="658de-121">Выбор расположения центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="658de-121">Select data center location</span></span>
<span data-ttu-id="658de-122">Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="658de-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="658de-123">В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="658de-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="658de-124">Необходимо предоставить согласие, прежде чем данные будут совместно использоваться службами и объединены.</span><span class="sxs-lookup"><span data-stu-id="658de-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="658de-125">Подтверждение включения службы</span><span class="sxs-lookup"><span data-stu-id="658de-125">Confirm that the service is on</span></span>
<span data-ttu-id="658de-126">После подготовки службы в нее добавляются:</span><span class="sxs-lookup"><span data-stu-id="658de-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="658de-127">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="658de-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="658de-128">Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="658de-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="658de-129">Возможности [расширенного поиска](advanced-hunting-overview.md) на существующей странице **Поиск**</span><span class="sxs-lookup"><span data-stu-id="658de-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="658de-130">![Изображение области навигации центра безопасности Microsoft 365 с помощью функций](../images/mtp-on.png)
защиты от угроз Майкрософт*Центр безопасности Microsoft 365 с возможностью управления происшествиями и другими возможностями защиты от угроз Майкрософт*</span><span class="sxs-lookup"><span data-stu-id="658de-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="658de-131">Получение данных Azure ATP</span><span class="sxs-lookup"><span data-stu-id="658de-131">Getting Azure ATP data</span></span>
<span data-ttu-id="658de-132">Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="658de-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="658de-133">Подробнее об этой интеграции</span><span class="sxs-lookup"><span data-stu-id="658de-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="658de-134">Выключение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="658de-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="658de-135">Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**.</span><span class="sxs-lookup"><span data-stu-id="658de-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="658de-136">Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="658de-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="658de-137">Данные будут удалены без возможности восстановления, а соответствующие функции будут удалены из центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="658de-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="658de-138">Получение помощи</span><span class="sxs-lookup"><span data-stu-id="658de-138">Get assistance</span></span>

<span data-ttu-id="658de-139">Сотрудники службы поддержки Майкрософт могут помочь подготовить или отменить подготовку службы и связанных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="658de-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="658de-140">Для получения помощи выберите **нужна помощь?** в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="658de-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="658de-141">При обращении в службу поддержки следует упомянуть о защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="658de-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="658de-142">См. также</span><span class="sxs-lookup"><span data-stu-id="658de-142">Related topics</span></span>

- [<span data-ttu-id="658de-143">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="658de-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="658de-144">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="658de-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="658de-145">Обзор ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="658de-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="658de-146">Обзор Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="658de-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="658de-147">Обзор Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="658de-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="658de-148">Обзор Azure ATP</span><span class="sxs-lookup"><span data-stu-id="658de-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="658de-149">Хранение данных в службе ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="658de-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
