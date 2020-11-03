---
title: ИТ-инфраструктура и бизнес-потребности компании Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите базовую структуру локальной ИТ-инфраструктуры компании Contoso и ее соответствие требованиям Microsoft 365 для предприятий.
ms.openlocfilehash: 0a837a457869fc579d94ee5e5f9bb114cb93f641
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847134"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="2048c-103">ИТ-инфраструктура и бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="2048c-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="2048c-104">Компания Contoso переходит от локальной, централизованной ИТ-инфраструктуры к настройке, включающей облачную среду, которая включает в себя рабочие нагрузки и приложения, основанные на облачных средах.</span><span class="sxs-lookup"><span data-stu-id="2048c-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="2048c-105">Существующая ИТ инфраструктура contoso</span><span class="sxs-lookup"><span data-stu-id="2048c-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="2048c-106">В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="2048c-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="2048c-107">Вот главный офис с центрами обработки данных приложений, демилитаризованной зоной и Интернетом.</span><span class="sxs-lookup"><span data-stu-id="2048c-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Существующая ИТ инфраструктура contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="2048c-109">В локальных центрах обработки данных приложений размещены указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="2048c-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="2048c-110">Настраиваемые бизнес-приложения, использующие SQL Server и другие базы данных Linux.</span><span class="sxs-lookup"><span data-stu-id="2048c-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="2048c-111">Набор устаревших серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2048c-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="2048c-112">Серверы уровня организации и групп для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="2048c-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="2048c-113">Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений.</span><span class="sxs-lookup"><span data-stu-id="2048c-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="2048c-114">Этими серверами управляют региональные ИТ-отделы.</span><span class="sxs-lookup"><span data-stu-id="2048c-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="2048c-115">Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.</span><span class="sxs-lookup"><span data-stu-id="2048c-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="2048c-116">В ДЕМИЛИТАРИЗОВАНной зоне Contoso headquarters различные наборы серверов предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="2048c-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="2048c-117">Размещение для общедоступного веб-сайта Contoso, с которого клиенты могут заказать продукты, запчасти, Канцелярские товары и услуги.</span><span class="sxs-lookup"><span data-stu-id="2048c-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="2048c-118">Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.</span><span class="sxs-lookup"><span data-stu-id="2048c-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="2048c-119">Удаленный доступ на основе частной виртуальной сети (VPN) к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.</span><span class="sxs-lookup"><span data-stu-id="2048c-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="2048c-120">Бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="2048c-120">Contoso business needs</span></span>

<span data-ttu-id="2048c-121">Бизнес-потребности компании Contoso делятся на пять основных категорий:</span><span class="sxs-lookup"><span data-stu-id="2048c-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="2048c-122">**Производительность труда**</span><span class="sxs-lookup"><span data-stu-id="2048c-122">**Productivity**</span></span>

- <span data-ttu-id="2048c-123">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="2048c-123">Make collaboration easier</span></span>

  <span data-ttu-id="2048c-124">Замена электронной почты и совместной работы на основе общих файлов с помощью интерактивной модели, позволяющей вносить в реальном времени изменения в документах, упростить собрания по сети и захваченные цепочки бесед.</span><span class="sxs-lookup"><span data-stu-id="2048c-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="2048c-125">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="2048c-126">Так как многие сотрудники работают дома или в поле, замените узкое решение VPN на доступ к данным и ресурсам Contoso в облаке.</span><span class="sxs-lookup"><span data-stu-id="2048c-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="2048c-127">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="2048c-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="2048c-128">Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.</span><span class="sxs-lookup"><span data-stu-id="2048c-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="2048c-129">**Безопасность**</span><span class="sxs-lookup"><span data-stu-id="2048c-129">**Security**</span></span>

- <span data-ttu-id="2048c-130">Управление идентификацией и доступом</span><span class="sxs-lookup"><span data-stu-id="2048c-130">Identity and access management</span></span>

  <span data-ttu-id="2048c-131">Применение многофакторной проверки подлинности и других форм проверки подлинности и защита учетных данных учетных записей пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="2048c-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="2048c-132">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="2048c-132">Threat protection</span></span>

  <span data-ttu-id="2048c-133">Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="2048c-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="2048c-134">Защита информации</span><span class="sxs-lookup"><span data-stu-id="2048c-134">Information protection</span></span>

  <span data-ttu-id="2048c-135">Шифрование важных цифровых ресурсов, например данных клиентов, конструкторских и производственных спецификаций и сведений о сотрудниках, а также блокирование доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="2048c-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="2048c-136">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="2048c-136">Security management</span></span>

  <span data-ttu-id="2048c-137">Наблюдение за безопасностью и обнаружение угроз в режиме реального времени и реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="2048c-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="2048c-138">**Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами**</span><span class="sxs-lookup"><span data-stu-id="2048c-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="2048c-139">Повышенная безопасность для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="2048c-140">Реализуйте свое устройство (BYOD) и управление устройствами, принадлежащее компании, чтобы обеспечить безопасный доступ, правильное поведение приложения и защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="2048c-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="2048c-141">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="2048c-142">Снижение затрат на обслуживание и поддержку и повышение производительности решения удаленного доступа путем перемещения часто используемых ресурсов в облако.</span><span class="sxs-lookup"><span data-stu-id="2048c-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="2048c-143">Обеспечение лучшей связи и снижения нагрузки для транзакций "бизнес-сусинесс" (B2B)</span><span class="sxs-lookup"><span data-stu-id="2048c-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="2048c-144">Замена общепринятых и дорогых партнеров экстрасети на облачное решение, использующее федеративный способ проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2048c-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="2048c-145">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="2048c-145">**Compliance**</span></span>

- <span data-ttu-id="2048c-146">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="2048c-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="2048c-147">Обеспечьте соответствие отраслевым и региональным нормативам, предъявляемым к хранению данных, шифрованию, конфиденциальности данных и персональным данным, например к общему законодательству по защите данных (GDPR) для союза ЕС.</span><span class="sxs-lookup"><span data-stu-id="2048c-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="2048c-148">**Управление**</span><span class="sxs-lookup"><span data-stu-id="2048c-148">**Management**</span></span>

- <span data-ttu-id="2048c-149">Снижение затрат на ИТ для управления программным обеспечением, работающим на клиентских компьютерах и устройствах</span><span class="sxs-lookup"><span data-stu-id="2048c-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="2048c-150">Автоматизация установки обновлений операционной системы Windows и приложений Microsoft 365 для предприятий в Организации.</span><span class="sxs-lookup"><span data-stu-id="2048c-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="2048c-151">Сопоставление потребностей компании Contoso Business с Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2048c-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="2048c-152">ИТ-отдел Contoso определил следующее сопоставление бизнес-потребностей для функций Microsoft 365/с и до развертывания:</span><span class="sxs-lookup"><span data-stu-id="2048c-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="2048c-153">Категория</span><span class="sxs-lookup"><span data-stu-id="2048c-153">Category</span></span> | <span data-ttu-id="2048c-154">Потребности бизнеса</span><span class="sxs-lookup"><span data-stu-id="2048c-154">Business need</span></span> | <span data-ttu-id="2048c-155">Microsoft 365 для корпоративных продуктов и функций</span><span class="sxs-lookup"><span data-stu-id="2048c-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="2048c-156">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="2048c-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="2048c-157">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="2048c-157">Make collaboration easier</span></span> | <span data-ttu-id="2048c-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="2048c-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="2048c-159">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="2048c-160">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="2048c-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="2048c-161">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="2048c-161">Increase creativity and innovation</span></span> | <span data-ttu-id="2048c-162">Windows Ink, Кортана на рабочем месте, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2048c-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="2048c-163">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2048c-163">Security</span></span> |  |  |
|  | <span data-ttu-id="2048c-164">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="2048c-164">Identity & access management</span></span> | <span data-ttu-id="2048c-165">Выделенные учетные записи глобальных администраторов с многофакторной проверкой подлинности (MFA) Azure и Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="2048c-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="2048c-166">Многофакторная проверка подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="2048c-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="2048c-167">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="2048c-167">Conditional Access</span></span> <BR> <span data-ttu-id="2048c-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="2048c-168">Windows Hello</span></span> <BR> <span data-ttu-id="2048c-169">Credential Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="2048c-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="2048c-170">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="2048c-170">Threat protection</span></span> | <span data-ttu-id="2048c-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="2048c-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="2048c-172">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="2048c-172">Windows Defender</span></span> <BR> <span data-ttu-id="2048c-173">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="2048c-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="2048c-174">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="2048c-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="2048c-175">Исследование угроз и ответ Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2048c-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="2048c-176">Защита информации</span><span class="sxs-lookup"><span data-stu-id="2048c-176">Information protection</span></span> | <span data-ttu-id="2048c-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2048c-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="2048c-178">Защита от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="2048c-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="2048c-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="2048c-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="2048c-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2048c-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="2048c-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2048c-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="2048c-182">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="2048c-182">Security management</span></span> | <span data-ttu-id="2048c-183">Защитник Azure \*</span><span class="sxs-lookup"><span data-stu-id="2048c-183">Azure Defender\*</span></span>  <BR> <span data-ttu-id="2048c-184">Центр безопасности Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="2048c-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="2048c-185">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="2048c-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="2048c-186">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="2048c-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2048c-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="2048c-188">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="2048c-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="2048c-189">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="2048c-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="2048c-190">Улучшите возможности подключения и более низкие затраты для транзакций B2B</span><span class="sxs-lookup"><span data-stu-id="2048c-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="2048c-191">Федеративная проверка подлинности и облачные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2048c-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="2048c-192">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="2048c-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="2048c-193">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="2048c-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="2048c-194">Функции GDPR в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2048c-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="2048c-195">Управление</span><span class="sxs-lookup"><span data-stu-id="2048c-195">Management</span></span> |  |  |
|  | <span data-ttu-id="2048c-196">Снижение затрат на ИТ для установки обновлений клиентов</span><span class="sxs-lookup"><span data-stu-id="2048c-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="2048c-197">Обновления Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="2048c-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="2048c-198">Обновления приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2048c-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="2048c-199">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="2048c-199">Next step</span></span>

<span data-ttu-id="2048c-200">Узнайте о [локальной сети](contoso-networking.md) Contoso Corporation, а также о том, как она была оптимизирована для доступа и задержки в облачных ресурсах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2048c-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="2048c-201">См. также</span><span class="sxs-lookup"><span data-stu-id="2048c-201">See also</span></span>

[<span data-ttu-id="2048c-202">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2048c-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2048c-203">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="2048c-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
