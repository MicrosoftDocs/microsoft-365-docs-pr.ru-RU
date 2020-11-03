---
title: Часто задаваемые вопросы о включении защитника Microsoft 365
description: Ответы на часто задаваемые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением Microsoft 365 Defender
keywords: часто задаваемые вопросы, FAQ, GCC, начало работы, включение MTP, защита от угроз Майкрософт, M365, безопасность, расположение данных, необходимые разрешения, права на лицензирование, страница параметров
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842420"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="10fff-104">Часто задаваемые вопросы о включении защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10fff-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="10fff-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="10fff-105">**Applies to:**</span></span>
- <span data-ttu-id="10fff-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10fff-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="10fff-107">В этой статье приведены ответы на часто задаваемые вопросы о включении [защитника Microsoft 365](microsoft-threat-protection.md), в том числе о необходимых лицензиях и разрешениях, развертывании служб поддержки и начальных параметрах.</span><span class="sxs-lookup"><span data-stu-id="10fff-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="10fff-108">Для получения инструкций по включению службы, [Прочтите статью включение защитника Microsoft 365](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="10fff-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="10fff-109">У меня нет лицензии на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10fff-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="10fff-110">Можно ли по-прежнему использовать защитник Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="10fff-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="10fff-111">Клиенты со следующими лицензиями, не являющимися неизменяемыми лицензиями, могут использовать защитник Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="10fff-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="10fff-112">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="10fff-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="10fff-113">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="10fff-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="10fff-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="10fff-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="10fff-115">Защитник для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="10fff-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="10fff-116">Чтобы получить полный список поддерживаемых лицензий, [Ознакомьтесь с требованиями к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="10fff-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="10fff-117">Нужно ли устанавливать или развертывать все, чтобы начать использовать защитник Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="10fff-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="10fff-118">Нет, защитник Microsoft 365 объединяет данные из уже развернутых служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10fff-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="10fff-119">После включения функции, инцидентов, автоматизации и поиска по поиску начинают работать в пределах развернутых продуктов.</span><span class="sxs-lookup"><span data-stu-id="10fff-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="10fff-120">Если ни один из этих продуктов не развертывается надлежащим образом, защитник Microsoft 365 не будет отображать данные и не сможет предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="10fff-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="10fff-121">Чтобы оптимизировать взаимодействие с защитником Microsoft 365, рекомендуем развернуть *все* поддерживаемые [продукты и службы безопасности Microsoft 365](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="10fff-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="10fff-122">Где работает защитник Microsoft 365 и хранятся данные?</span><span class="sxs-lookup"><span data-stu-id="10fff-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="10fff-123">Защитник Microsoft 365 автоматически выбирает оптимальное расположение для центра обработки данных, в котором хранятся и обрабатываются консолидированные данные.</span><span class="sxs-lookup"><span data-stu-id="10fff-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="10fff-124">Если у вас есть защитник Майкрософт для конечной точки, он выбирает то же расположение, которое используется защитником для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="10fff-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="10fff-125">Защитник Майкрософт для конечных точек автоматически подготавливается в центрах обработки данных Европейского союза (ЕС) при включенном защитнике Azure \*.</span><span class="sxs-lookup"><span data-stu-id="10fff-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="10fff-126">Защитник Microsoft 365 автоматически подготавливается к работе с тем же центром обработки данных ЕС для клиентов, у которых в такой манере подготовлен защитник Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="10fff-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="10fff-127">Расположение центра обработки данных показано до и после подготовки службы на странице "Параметры" для защитника Microsoft 365 ( **параметры > защитника microsoft 365** ).</span><span class="sxs-lookup"><span data-stu-id="10fff-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="10fff-128">Если вы предпочитаете использовать другое расположение центра обработки данных, выберите **нужна помощь?** в центре безопасности Майкрософт 365 для обращения в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="10fff-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="10fff-129">Где можно получить доступ к защитнику Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="10fff-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="10fff-130">Защитник Microsoft 365 доступен в центре безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="10fff-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="10fff-131">Чтобы перейти в центр обеспечения безопасности, перейдите по URL-адресу [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="10fff-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="10fff-132">Какие разрешения необходимы для доступа к защитнику Microsoft 365 в центре безопасности Майкрософт 365?</span><span class="sxs-lookup"><span data-stu-id="10fff-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="10fff-133">Учетные записи, назначенные следующим ролям Azure Active Directory (AD), могут получать доступ к функциям и данным защитника Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="10fff-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="10fff-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="10fff-134">Global administrator</span></span>
- <span data-ttu-id="10fff-135">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="10fff-135">Security administrator</span></span>
- <span data-ttu-id="10fff-136">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="10fff-136">Security Operator</span></span>
- <span data-ttu-id="10fff-137">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="10fff-137">Global Reader</span></span>
- <span data-ttu-id="10fff-138">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="10fff-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="10fff-139">Параметры управления доступом на основе ролей в защитнике Майкрософт для конечной точки влияют на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="10fff-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="10fff-140">Для получения дополнительных сведений об [управлении доступом к защитнику Microsoft 365](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="10fff-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="10fff-141">В каком часовом поясе по умолчанию используется защитник Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="10fff-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="10fff-142">По умолчанию защитник Microsoft 365 отображает сведения о времени в часовом поясе в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="10fff-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="10fff-143">Вы можете изменить этот параметр, чтобы использовать местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="10fff-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="10fff-144">Сведения о настройке часового пояса</span><span class="sxs-lookup"><span data-stu-id="10fff-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="10fff-145">Как узнать о новых функциях защитника Microsoft 365 и обновлениях пользовательского интерфейса?</span><span class="sxs-lookup"><span data-stu-id="10fff-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="10fff-146">Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:</span><span class="sxs-lookup"><span data-stu-id="10fff-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="10fff-147">[Центр сообщений](../../admin/manage/message-center.md) в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10fff-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="10fff-148">Блогпостс в [сообществе 365 Майкрософт по безопасности & обеспечения соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="10fff-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="10fff-149">Получите последние общедоступные возможности, включив [функции предварительного просмотра](preview.md).</span><span class="sxs-lookup"><span data-stu-id="10fff-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="10fff-150">Доступен ли защитник Microsoft 365 для облака сообщества США (GCC) или GCC High?</span><span class="sxs-lookup"><span data-stu-id="10fff-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="10fff-151">В настоящее время она недоступна.</span><span class="sxs-lookup"><span data-stu-id="10fff-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10fff-152">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="10fff-152">Related topics</span></span>

- [<span data-ttu-id="10fff-153">Обзор защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10fff-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="10fff-154">[Включите Защитник Microsoft 365](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="10fff-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="10fff-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="10fff-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="10fff-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="10fff-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="10fff-157">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="10fff-157">Turn on preview features</span></span>](preview.md)
