---
title: Часто задаваемые вопросы о включении защиты от угроз Майкрософт
description: Ответы на часто задаваемые вопросы о лицензировании, разрешениях, начальных параметрах и других продуктах и службах, связанных с включением защиты от угроз Майкрософт
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198843"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="9f601-104">Часто задаваемые вопросы о включении защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9f601-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9f601-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9f601-105">**Applies to:**</span></span>
- <span data-ttu-id="9f601-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="9f601-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9f601-107">В этой статье приведены ответы на часто задаваемые вопросы о включении [защиты от угроз Майкрософт](microsoft-threat-protection.md), в том числе о необходимых лицензиях и разрешениях, развертывании служб поддержки и начальных параметрах.</span><span class="sxs-lookup"><span data-stu-id="9f601-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="9f601-108">Инструкции по включению службы можно [узнать в статье Включение защиты от угроз Майкрософт](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="9f601-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="9f601-109">У меня нет лицензии на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f601-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="9f601-110">Можно ли по-прежнему использовать защиту от угроз Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="9f601-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="9f601-111">Клиенты со следующими лицензиями, не являющимися неизменяемыми лицензиями, могут использовать защиту от угроз Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="9f601-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="9f601-112">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9f601-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="9f601-113">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="9f601-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="9f601-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9f601-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9f601-115">Расширенная защита от угроз Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="9f601-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="9f601-116">Чтобы получить полный список поддерживаемых лицензий, [Ознакомьтесь с требованиями к лицензированию](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="9f601-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="9f601-117">Нужно ли устанавливать или развертывать что-либо, чтобы начать использовать защиту от угроз Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="9f601-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="9f601-118">Нет, защита от угроз Майкрософт консолидирует данные из уже развернутых служб безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f601-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="9f601-119">После включения функции, инцидентов, автоматизации и поиска по поиску начинают работать в пределах развернутых продуктов.</span><span class="sxs-lookup"><span data-stu-id="9f601-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="9f601-120">Если ни один из этих продуктов не развертывается надлежащим образом, защита от угроз Майкрософт не отображает данные и не может выполнить какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="9f601-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="9f601-121">Для оптимизации взаимодействия с Майкрософт для защиты от угроз рекомендуется развернуть *все* поддерживаемые [продукты и службы безопасности Microsoft 365](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f601-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="9f601-122">Где выполняется процесс защиты от угроз Майкрософт и хранятся ли данные?</span><span class="sxs-lookup"><span data-stu-id="9f601-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="9f601-123">Защита от угроз Майкрософт автоматически выбирает оптимальное расположение для центра обработки данных, в котором хранятся и обрабатываются консолидированные данные.</span><span class="sxs-lookup"><span data-stu-id="9f601-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="9f601-124">Если у вас есть пакет ATP для защитника Майкрософт, он выбирает то же расположение, что и для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9f601-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="9f601-125">Защитник Майкрософт автоматически подготавливается к центрам обработки данных Европейского союза (ЕС) при включении в центре безопасности Azure.</span><span class="sxs-lookup"><span data-stu-id="9f601-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="9f601-126">Защита от угроз Майкрософт автоматически подготавливается к работе с одним и тем же центром обработки данных ЕС для клиентов, у которых такой способ настроен с помощью пакета ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9f601-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="9f601-127">Расположение центра обработки данных показано до и после подготовки службы на странице "Параметры" для защиты от угроз Майкрософт (**параметры > Microsoft Threat protection**).</span><span class="sxs-lookup"><span data-stu-id="9f601-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="9f601-128">Если вы предпочитаете использовать другое расположение центра обработки данных, выберите **нужна помощь?** в центре безопасности Майкрософт 365 для обращения в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9f601-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="9f601-129">Где можно получить доступ к защите от угроз Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="9f601-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="9f601-130">Защита от угроз Майкрософт доступна в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f601-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="9f601-131">Чтобы перейти в центр обеспечения безопасности, перейдите по URL-адресу [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="9f601-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="9f601-132">Какие разрешения необходимы для доступа к защите от угроз Майкрософт в центре безопасности Майкрософт 365?</span><span class="sxs-lookup"><span data-stu-id="9f601-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="9f601-133">Доступ к данным и функциям Защиты от угроз (Майкрософт) имеют учетные записи, которым назначены следующие роли Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="9f601-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="9f601-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="9f601-134">Global administrator</span></span>
- <span data-ttu-id="9f601-135">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-135">Security administrator</span></span>
- <span data-ttu-id="9f601-136">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-136">Security Operator</span></span>
- <span data-ttu-id="9f601-137">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="9f601-137">Global Reader</span></span>
- <span data-ttu-id="9f601-138">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="9f601-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="9f601-139">Параметры управления доступом на основе ролей в защитнике Microsoft для ATP влияют на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="9f601-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="9f601-140">Для получения дополнительных сведений об [управлении доступом к защите от угроз Майкрософт](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9f601-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="9f601-141">В каком часовом поясе по умолчанию используется защита от угроз Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="9f601-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="9f601-142">По умолчанию защита от угроз Майкрософт отображает сведения о времени в часовом поясе UTC.</span><span class="sxs-lookup"><span data-stu-id="9f601-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="9f601-143">Вы можете изменить этот параметр, чтобы использовать местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="9f601-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="9f601-144">Сведения о настройке часового пояса</span><span class="sxs-lookup"><span data-stu-id="9f601-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="9f601-145">Как узнать о новых функциях защиты от угроз Майкрософт и возможностях обновления пользовательского интерфейса?</span><span class="sxs-lookup"><span data-stu-id="9f601-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="9f601-146">Корпорация Майкрософт регулярно предоставляет информацию по различным каналам, в том числе:</span><span class="sxs-lookup"><span data-stu-id="9f601-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="9f601-147">[Центр сообщений](../../admin/manage/message-center.md) в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9f601-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="9f601-148">Блогпостс в [сообществе 365 Майкрософт по безопасности & обеспечения соответствия требованиям](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="9f601-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="9f601-149">Получите последние общедоступные возможности, включив [функции предварительного просмотра](preview.md).</span><span class="sxs-lookup"><span data-stu-id="9f601-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="9f601-150">Доступна ли защита от угроз (Майкрософт) в облаке сообщества для государственных учреждений США (GCC) или GCC High?</span><span class="sxs-lookup"><span data-stu-id="9f601-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="9f601-151">В настоящее время она недоступна.</span><span class="sxs-lookup"><span data-stu-id="9f601-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f601-152">См. также</span><span class="sxs-lookup"><span data-stu-id="9f601-152">Related topics</span></span>

- [<span data-ttu-id="9f601-153">Обзор Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="9f601-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="9f601-154">[Включите защиту от угроз Майкрософт](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="9f601-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="9f601-155">Требования к лицензированию и другие предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9f601-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9f601-156">Развертывание поддерживаемых служб</span><span class="sxs-lookup"><span data-stu-id="9f601-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="9f601-157">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="9f601-157">Turn on preview features</span></span>](preview.md)
