---
title: ИТ-инфраструктура и бизнес-потребности компании Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите базовую структуру локальной ИТ-инфраструктуры компании Contoso и ее соответствие требованиям Microsoft 365 для предприятий.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637179"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="db94c-103">ИТ-инфраструктура и бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="db94c-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="db94c-104">Компания Contoso переходит от локальной, централизованной ИТ-инфраструктуры к настройке, включающей облачную среду, которая включает в себя рабочие нагрузки и приложения, основанные на облачных средах.</span><span class="sxs-lookup"><span data-stu-id="db94c-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="db94c-105">Существующая ИТ инфраструктура contoso</span><span class="sxs-lookup"><span data-stu-id="db94c-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="db94c-106">В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="db94c-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="db94c-107">На рисунке 1 показан Центральный офис с центрами обработки данных приложений, демилитаризованной зоной и Интернетом.</span><span class="sxs-lookup"><span data-stu-id="db94c-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Существующая ИТ инфраструктура contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="db94c-109">**Рисунок 1: существующая ИТ инфраструктура contoso**</span><span class="sxs-lookup"><span data-stu-id="db94c-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="db94c-110">В локальных центрах обработки данных приложений размещены указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="db94c-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="db94c-111">Настраиваемые бизнес-приложения, использующие SQL Server и другие базы данных Linux.</span><span class="sxs-lookup"><span data-stu-id="db94c-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="db94c-112">Набор устаревших серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="db94c-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="db94c-113">Серверы уровня организации и групп для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="db94c-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="db94c-114">Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений.</span><span class="sxs-lookup"><span data-stu-id="db94c-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="db94c-115">Этими серверами управляют региональные ИТ-отделы.</span><span class="sxs-lookup"><span data-stu-id="db94c-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="db94c-116">Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.</span><span class="sxs-lookup"><span data-stu-id="db94c-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="db94c-117">В ДЕМИЛИТАРИЗОВАНной зоне Contoso headquarters различные наборы серверов предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="db94c-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="db94c-118">Размещение для общедоступного веб-сайта Contoso, с которого клиенты могут заказать продукты, запчасти, Канцелярские товары и услуги.</span><span class="sxs-lookup"><span data-stu-id="db94c-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="db94c-119">Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.</span><span class="sxs-lookup"><span data-stu-id="db94c-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="db94c-120">Удаленный доступ на основе частной виртуальной сети (VPN) к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.</span><span class="sxs-lookup"><span data-stu-id="db94c-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="db94c-121">Бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="db94c-121">Contoso business needs</span></span>

<span data-ttu-id="db94c-122">Бизнес-потребности компании Contoso делятся на пять основных категорий:</span><span class="sxs-lookup"><span data-stu-id="db94c-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="db94c-123">**Производительность труда**</span><span class="sxs-lookup"><span data-stu-id="db94c-123">**Productivity**</span></span>

- <span data-ttu-id="db94c-124">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="db94c-124">Make collaboration easier</span></span>

  <span data-ttu-id="db94c-125">Замена электронной почты и совместной работы на основе общих файлов с помощью интерактивной модели, позволяющей вносить в реальном времени изменения в документах, упростить собрания по сети и захваченные цепочки бесед.</span><span class="sxs-lookup"><span data-stu-id="db94c-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="db94c-126">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="db94c-127">Так как многие сотрудники работают дома или в поле, замените узкое решение VPN на доступ к данным и ресурсам Contoso в облаке.</span><span class="sxs-lookup"><span data-stu-id="db94c-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="db94c-128">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="db94c-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="db94c-129">Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.</span><span class="sxs-lookup"><span data-stu-id="db94c-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="db94c-130">**Безопасность**</span><span class="sxs-lookup"><span data-stu-id="db94c-130">**Security**</span></span>

- <span data-ttu-id="db94c-131">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="db94c-131">Identity and access management</span></span>

  <span data-ttu-id="db94c-132">Применение многофакторной проверки подлинности и других форм проверки подлинности и защита учетных данных учетных записей пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="db94c-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="db94c-133">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="db94c-133">Threat protection</span></span>

  <span data-ttu-id="db94c-134">Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="db94c-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="db94c-135">Защита информации</span><span class="sxs-lookup"><span data-stu-id="db94c-135">Information protection</span></span>

  <span data-ttu-id="db94c-136">Шифрование важных цифровых ресурсов, например данных клиентов, конструкторских и производственных спецификаций и сведений о сотрудниках, а также блокирование доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="db94c-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="db94c-137">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="db94c-137">Security management</span></span>

  <span data-ttu-id="db94c-138">Наблюдение за безопасностью и обнаружение угроз в режиме реального времени и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="db94c-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="db94c-139">**Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами**</span><span class="sxs-lookup"><span data-stu-id="db94c-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="db94c-140">Повышенная безопасность для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="db94c-141">Реализуйте свое устройство (BYOD) и управление устройствами, принадлежащее компании, чтобы обеспечить безопасный доступ, правильное поведение приложения и защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="db94c-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="db94c-142">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="db94c-143">Снижение затрат на обслуживание и поддержку и повышение производительности решения удаленного доступа путем перемещения часто используемых ресурсов в облако.</span><span class="sxs-lookup"><span data-stu-id="db94c-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="db94c-144">Обеспечение лучшей связи и снижения нагрузки для транзакций "бизнес-сусинесс" (B2B)</span><span class="sxs-lookup"><span data-stu-id="db94c-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="db94c-145">Замена общепринятых и дорогых партнеров экстрасети на облачное решение, использующее федеративный способ проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="db94c-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="db94c-146">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="db94c-146">**Compliance**</span></span>

- <span data-ttu-id="db94c-147">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="db94c-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="db94c-148">Обеспечьте соответствие отраслевым и региональным нормативам, предъявляемым к хранению данных, шифрованию, конфиденциальности данных и персональным данным, например к общему законодательству по защите данных (GDPR) для союза ЕС.</span><span class="sxs-lookup"><span data-stu-id="db94c-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="db94c-149">**Управление**</span><span class="sxs-lookup"><span data-stu-id="db94c-149">**Management**</span></span>

- <span data-ttu-id="db94c-150">Снижение затрат на ИТ для управления программным обеспечением, работающим на клиентских компьютерах и устройствах</span><span class="sxs-lookup"><span data-stu-id="db94c-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="db94c-151">Автоматизация установки обновлений операционной системы Windows и приложений Microsoft 365 для предприятий в Организации.</span><span class="sxs-lookup"><span data-stu-id="db94c-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="db94c-152">Сопоставление потребностей компании Contoso Business с Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="db94c-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="db94c-153">ИТ-отдел Contoso определил следующее сопоставление бизнес-потребностей для функций Microsoft 365/с и до развертывания:</span><span class="sxs-lookup"><span data-stu-id="db94c-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="db94c-154">Category</span><span class="sxs-lookup"><span data-stu-id="db94c-154">Category</span></span> | <span data-ttu-id="db94c-155">Потребности бизнеса</span><span class="sxs-lookup"><span data-stu-id="db94c-155">Business need</span></span> | <span data-ttu-id="db94c-156">Microsoft 365 для корпоративных продуктов и функций</span><span class="sxs-lookup"><span data-stu-id="db94c-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="db94c-157">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="db94c-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="db94c-158">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="db94c-158">Make collaboration easier</span></span> | <span data-ttu-id="db94c-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="db94c-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="db94c-160">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="db94c-161">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="db94c-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="db94c-162">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="db94c-162">Increase creativity and innovation</span></span> | <span data-ttu-id="db94c-163">Windows Ink, Кортана на рабочем месте, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="db94c-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="db94c-164">Безопасность</span><span class="sxs-lookup"><span data-stu-id="db94c-164">Security</span></span> |  |  |
|  | <span data-ttu-id="db94c-165">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="db94c-165">Identity & access management</span></span> | <span data-ttu-id="db94c-166">Выделенные учетные записи глобальных администраторов с многофакторной проверкой подлинности Azure (MFA) и управление личными удостоверениями Azure Active Directory (PIM)</span><span class="sxs-lookup"><span data-stu-id="db94c-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="db94c-167">Многофакторная проверка подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="db94c-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="db94c-168">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="db94c-168">Conditional Access</span></span> <BR> <span data-ttu-id="db94c-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="db94c-169">Windows Hello</span></span> <BR> <span data-ttu-id="db94c-170">Credential Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="db94c-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="db94c-171">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="db94c-171">Threat protection</span></span> | <span data-ttu-id="db94c-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="db94c-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="db94c-173">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="db94c-173">Windows Defender</span></span> <BR> <span data-ttu-id="db94c-174">Расширенная защита от угроз</span><span class="sxs-lookup"><span data-stu-id="db94c-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="db94c-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="db94c-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="db94c-176">Исследование угроз и ответ Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db94c-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="db94c-177">Защита информации</span><span class="sxs-lookup"><span data-stu-id="db94c-177">Information protection</span></span> | <span data-ttu-id="db94c-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="db94c-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="db94c-179">Защита от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="db94c-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="db94c-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="db94c-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="db94c-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="db94c-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="db94c-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db94c-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="db94c-183">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="db94c-183">Security management</span></span> | <span data-ttu-id="db94c-184">Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="db94c-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="db94c-185">Центр безопасности Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="db94c-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="db94c-186">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="db94c-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="db94c-187">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="db94c-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db94c-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="db94c-189">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="db94c-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="db94c-190">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="db94c-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="db94c-191">Улучшите возможности подключения и более низкие затраты для транзакций B2B</span><span class="sxs-lookup"><span data-stu-id="db94c-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="db94c-192">Федеративная проверка подлинности и облачные ресурсы</span><span class="sxs-lookup"><span data-stu-id="db94c-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="db94c-193">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="db94c-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="db94c-194">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="db94c-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="db94c-195">Функции GDPR в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db94c-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="db94c-196">Управление</span><span class="sxs-lookup"><span data-stu-id="db94c-196">Management</span></span> |  |  |
|  | <span data-ttu-id="db94c-197">Снижение затрат на ИТ для установки обновлений клиентов</span><span class="sxs-lookup"><span data-stu-id="db94c-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="db94c-198">Круги развертывания</span><span class="sxs-lookup"><span data-stu-id="db94c-198">Deployment rings</span></span> <BR> <span data-ttu-id="db94c-199">Обновления Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="db94c-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="db94c-200">Обновления приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="db94c-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="db94c-201">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="db94c-201">Next step</span></span>

<span data-ttu-id="db94c-202">[Узнайте](contoso-networking.md) о локальной сети Contoso Corporation, а также о том, как она была оптимизирована для доступа и задержки в облачных ресурсах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db94c-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="db94c-203">См. также</span><span class="sxs-lookup"><span data-stu-id="db94c-203">See also</span></span>

[<span data-ttu-id="db94c-204">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="db94c-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="db94c-205">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="db94c-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
