---
title: ИТ-инфраструктура Contoso и бизнес-потребности
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
description: Понимание базовой структуры локальной ИТ-инфраструктуры Contoso и того, как бизнес-потребности компании Microsoft 365 для предприятия.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558410"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="6b9e9-103">ИТ-инфраструктура Contoso и бизнес-потребности</span><span class="sxs-lookup"><span data-stu-id="6b9e9-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="6b9e9-104">Contoso переходит из локальной централизованной ИТ-инфраструктуры в облачную установку, которая включает в себя рабочие нагрузки и приложения на основе облачной личной производительности.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="6b9e9-105">Существующая ИТ-инфраструктура Contoso</span><span class="sxs-lookup"><span data-stu-id="6b9e9-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="6b9e9-106">В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="6b9e9-107">Здесь расположен офис штаб-квартиры с центрами обработки данных приложений, dmZ и интернетом.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Существующая ИТ-инфраструктура Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="6b9e9-109">В локальных центрах обработки данных приложений размещены указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="6b9e9-110">Настраиваемые бизнес-приложения, которые используют SQL Server и другие базы данных Linux.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="6b9e9-111">Набор устаревших серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="6b9e9-112">Серверы уровня организации и групп для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="6b9e9-113">Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="6b9e9-114">Этими серверами управляют региональные ИТ-отделы.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="6b9e9-115">Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="6b9e9-116">В dmz штаб-квартиры Contoso различные наборы серверов обеспечивают:</span><span class="sxs-lookup"><span data-stu-id="6b9e9-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="6b9e9-117">Размещение для государственного веб-сайта Contoso, на котором клиенты могут заказать продукты, части, материалы и службу.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="6b9e9-118">Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="6b9e9-119">Удаленный доступ на основе частной виртуальной сети (VPN) к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="6b9e9-120">Потребности бизнеса Contoso</span><span class="sxs-lookup"><span data-stu-id="6b9e9-120">Contoso business needs</span></span>

<span data-ttu-id="6b9e9-121">Потребности бизнеса Contoso подпадают под пять основных категорий:</span><span class="sxs-lookup"><span data-stu-id="6b9e9-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="6b9e9-122">**Производительность труда**</span><span class="sxs-lookup"><span data-stu-id="6b9e9-122">**Productivity**</span></span>

- <span data-ttu-id="6b9e9-123">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="6b9e9-123">Make collaboration easier</span></span>

  <span data-ttu-id="6b9e9-124">Замените совместную работу на основе обмена электронной почтой и файлами на веб-модель, которая позволяет в режиме реального времени вносить изменения в документы, упрощать собрания в Интернете и захватывать потоки бесед.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="6b9e9-125">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="6b9e9-126">Многие сотрудники, работающие из дома или на местах, заменяют узкое VPN-решение с возможностью выполнения доступа к данным и ресурсам Contoso в облаке.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="6b9e9-127">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="6b9e9-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="6b9e9-128">Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="6b9e9-129">**Безопасность**</span><span class="sxs-lookup"><span data-stu-id="6b9e9-129">**Security**</span></span>

- <span data-ttu-id="6b9e9-130">Управление идентификацией и доступом</span><span class="sxs-lookup"><span data-stu-id="6b9e9-130">Identity and access management</span></span>

  <span data-ttu-id="6b9e9-131">Обеспечение многофакторной и других форм проверки подлинности и защита учетных данных пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="6b9e9-132">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="6b9e9-132">Threat protection</span></span>

  <span data-ttu-id="6b9e9-133">Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="6b9e9-134">Защита информации</span><span class="sxs-lookup"><span data-stu-id="6b9e9-134">Information protection</span></span>

  <span data-ttu-id="6b9e9-135">Шифрование важных цифровых ресурсов, например данных клиентов, конструкторских и производственных спецификаций и сведений о сотрудниках, а также блокирование доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="6b9e9-136">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="6b9e9-136">Security management</span></span>

  <span data-ttu-id="6b9e9-137">Отслеживайте положение в области безопасности и обнаруживать угрозы и реагировать на них в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="6b9e9-138">**Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами**</span><span class="sxs-lookup"><span data-stu-id="6b9e9-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="6b9e9-139">Повышение безопасности удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="6b9e9-140">Реализация принесите собственное устройство (BYOD) и управление устройствами, которые принадлежат компании, чтобы обеспечить защищенный доступ, правильное поведение приложения и защиту данных компании.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="6b9e9-141">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="6b9e9-142">Снижение затрат на обслуживание и поддержку и повышение производительности для решения удаленного доступа путем перемещения ресурсов с обычным доступом в облако.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="6b9e9-143">Обеспечение лучшей возможности подключения и снижения накладных расходов для транзакций бизнес-к-susiness (B2B)</span><span class="sxs-lookup"><span data-stu-id="6b9e9-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="6b9e9-144">Замените стареющую и дорогую партнерской экстрасети облачным решением с федерацией проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="6b9e9-145">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="6b9e9-145">**Compliance**</span></span>

- <span data-ttu-id="6b9e9-146">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="6b9e9-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="6b9e9-147">Обеспечение соответствия отраслевым и региональным правилам хранения данных, шифрования, конфиденциальности данных и персональных данных, таких как Общие правила защиты данных (GDPR) для Европейского союза.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="6b9e9-148">**Управление**</span><span class="sxs-lookup"><span data-stu-id="6b9e9-148">**Management**</span></span>

- <span data-ttu-id="6b9e9-149">Снижение накладных расходов на ИТ для управления программным обеспечением, работающим на клиентских ПК и устройствах</span><span class="sxs-lookup"><span data-stu-id="6b9e9-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="6b9e9-150">Автоматизация установки обновлений для Windows операционной системы и Приложения Microsoft 365 для предприятий всей организации.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="6b9e9-151">Сопоставление бизнеса Contoso необходимо Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="6b9e9-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="6b9e9-152">ИТ-отдел Contoso определил следующее сопоставление бизнес-потребностей для Microsoft 365 E5 функций перед развертыванием:</span><span class="sxs-lookup"><span data-stu-id="6b9e9-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="6b9e9-153">Category</span><span class="sxs-lookup"><span data-stu-id="6b9e9-153">Category</span></span> | <span data-ttu-id="6b9e9-154">Потребности бизнеса</span><span class="sxs-lookup"><span data-stu-id="6b9e9-154">Business need</span></span> | <span data-ttu-id="6b9e9-155">Microsoft 365 для корпоративных продуктов или функций</span><span class="sxs-lookup"><span data-stu-id="6b9e9-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="6b9e9-156">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="6b9e9-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="6b9e9-157">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="6b9e9-157">Make collaboration easier</span></span> | <span data-ttu-id="6b9e9-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6b9e9-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="6b9e9-159">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="6b9e9-160">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="6b9e9-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6b9e9-161">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="6b9e9-161">Increase creativity and innovation</span></span> | <span data-ttu-id="6b9e9-162">Windows Ink, Кортана на рабочем месте, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6b9e9-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="6b9e9-163">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6b9e9-163">Security</span></span> |  |  |
|  | <span data-ttu-id="6b9e9-164">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="6b9e9-164">Identity & access management</span></span> | <span data-ttu-id="6b9e9-165">Выделенные учетные записи глобального администратора с многофакторной проверкой подлинности Azure AD (MFA) и Azure AD управление привилегированными пользователями (PIM)</span><span class="sxs-lookup"><span data-stu-id="6b9e9-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="6b9e9-166">Многофакторная проверка подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="6b9e9-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="6b9e9-167">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="6b9e9-167">Conditional Access</span></span> <BR> <span data-ttu-id="6b9e9-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="6b9e9-168">Windows Hello</span></span> <BR> <span data-ttu-id="6b9e9-169">Credential Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e9-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="6b9e9-170">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="6b9e9-170">Threat protection</span></span> | <span data-ttu-id="6b9e9-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="6b9e9-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="6b9e9-172">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e9-172">Windows Defender</span></span> <BR> <span data-ttu-id="6b9e9-173">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6b9e9-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="6b9e9-174">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="6b9e9-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="6b9e9-175">Microsoft 365 расследования и реагирования на угрозы</span><span class="sxs-lookup"><span data-stu-id="6b9e9-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="6b9e9-176">Защита информации</span><span class="sxs-lookup"><span data-stu-id="6b9e9-176">Information protection</span></span> | <span data-ttu-id="6b9e9-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="6b9e9-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="6b9e9-178">Защита от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="6b9e9-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="6b9e9-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="6b9e9-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="6b9e9-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b9e9-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="6b9e9-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6b9e9-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6b9e9-182">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="6b9e9-182">Security management</span></span> | <span data-ttu-id="6b9e9-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="6b9e9-183">Azure Defender</span></span>  <BR> <span data-ttu-id="6b9e9-184">Центр безопасности Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e9-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="6b9e9-185">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="6b9e9-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="6b9e9-186">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="6b9e9-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6b9e9-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6b9e9-188">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="6b9e9-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="6b9e9-189">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="6b9e9-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6b9e9-190">Улучшение подключения и снижение накладных расходов для транзакций B2B</span><span class="sxs-lookup"><span data-stu-id="6b9e9-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="6b9e9-191">Федеративная проверка подлинности и облачные ресурсы</span><span class="sxs-lookup"><span data-stu-id="6b9e9-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="6b9e9-192">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="6b9e9-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="6b9e9-193">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="6b9e9-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="6b9e9-194">Функции GDPR в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b9e9-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="6b9e9-195">Управление</span><span class="sxs-lookup"><span data-stu-id="6b9e9-195">Management</span></span> |  |  |
|  | <span data-ttu-id="6b9e9-196">Снижение накладных расходов на ИТ для установки обновлений клиентов</span><span class="sxs-lookup"><span data-stu-id="6b9e9-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="6b9e9-197">Обновления Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="6b9e9-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="6b9e9-198">Обновления приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6b9e9-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="6b9e9-199">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="6b9e9-199">Next step</span></span>

<span data-ttu-id="6b9e9-200">Узнайте о локальной [](contoso-networking.md) сети Корпорации Contoso и о том, как она была оптимизирована для доступа и задержки Microsoft 365 облачных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6b9e9-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b9e9-201">См. также</span><span class="sxs-lookup"><span data-stu-id="6b9e9-201">See also</span></span>

[<span data-ttu-id="6b9e9-202">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6b9e9-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6b9e9-203">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="6b9e9-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
