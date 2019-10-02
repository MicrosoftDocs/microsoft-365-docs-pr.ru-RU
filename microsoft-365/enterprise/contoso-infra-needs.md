---
title: ИТ-инфраструктура и бизнес-потребности компании Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье описана базовая структура локальной ИТ-инфраструктуры компании Contoso и способы удовлетворения потребностей компании с помощью Microsoft 365 корпоративный.
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369590"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="67bd7-103">ИТ-инфраструктура и бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="67bd7-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="67bd7-104">**Сводка**: в этой статье описана базовая структура локальной ИТ-инфраструктуры компании Contoso и способы удовлетворения потребностей компании с помощью Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="67bd7-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="67bd7-105">Компания Contoso выполнила переход от локальной централизованной ИТ-инфраструктуры к инфраструктуре, включающей облако. В состав этой инфраструктуры входят рабочие нагрузки и приложения для повышения производительности труда сотрудников.</span><span class="sxs-lookup"><span data-stu-id="67bd7-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="67bd7-106">Существующая ИТ-инфраструктура Contoso</span><span class="sxs-lookup"><span data-stu-id="67bd7-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="67bd7-107">В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="67bd7-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="67bd7-108">На рис. 1 показан главный офис с центрами обработки данных приложений, сетью периметра и Интернетом.</span><span class="sxs-lookup"><span data-stu-id="67bd7-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Существующая ИТ-инфраструктура Contoso](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="67bd7-110">**Рис. 1. Существующая инфраструктура компании Contoso**</span><span class="sxs-lookup"><span data-stu-id="67bd7-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="67bd7-111">В локальных центрах обработки данных приложений размещены указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="67bd7-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="67bd7-112">Пользовательские бизнес-приложения, использующие SQL Server и другие базы данных, работающие в ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="67bd7-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="67bd7-113">Набор устаревших серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67bd7-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="67bd7-114">Серверы уровня организации и групп для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="67bd7-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="67bd7-115">Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений.</span><span class="sxs-lookup"><span data-stu-id="67bd7-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="67bd7-116">Этими серверами управляют региональные ИТ-отделы.</span><span class="sxs-lookup"><span data-stu-id="67bd7-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="67bd7-117">Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.</span><span class="sxs-lookup"><span data-stu-id="67bd7-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="67bd7-118">В сети периметра главного офиса компании Contoso различные наборы серверов предоставляют указанные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="67bd7-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="67bd7-119">Хостинг для общедоступного веб-сайта компании Contoso, на котором клиенты могут заказывать продукцию, запасные части, расходные материалы или услуги.</span><span class="sxs-lookup"><span data-stu-id="67bd7-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="67bd7-120">Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.</span><span class="sxs-lookup"><span data-stu-id="67bd7-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="67bd7-121">Удаленный доступ на основе частной виртуальной сети (VPN) к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.</span><span class="sxs-lookup"><span data-stu-id="67bd7-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="67bd7-122">Бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="67bd7-122">Contoso's business needs</span></span>

<span data-ttu-id="67bd7-123">Бизнес-потребности компании Contoso можно разделить на пять основных категорий.</span><span class="sxs-lookup"><span data-stu-id="67bd7-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="67bd7-124">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="67bd7-124">Productivity:</span></span>

- <span data-ttu-id="67bd7-125">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="67bd7-125">Make collaboration easier</span></span>

  <span data-ttu-id="67bd7-126">Замена модели совместной работы, предусматривающей использование электронной почты и файловых ресурсов, на онлайн-модель, которая позволяет вносить изменения в документы в режиме реального времени и записывать цепочки в беседах, а также упрощает проведение собраний по сети.</span><span class="sxs-lookup"><span data-stu-id="67bd7-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="67bd7-127">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="67bd7-128">Так как большое количество сотрудников работает дома или в разъездах, необходимо заменить решение на базе VPN, т. е. "узкое" место, решением, которое предусматривает высокопроизводительный доступ к данным и ресурсам компании Contoso в облаке.</span><span class="sxs-lookup"><span data-stu-id="67bd7-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="67bd7-129">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="67bd7-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="67bd7-130">Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.</span><span class="sxs-lookup"><span data-stu-id="67bd7-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="67bd7-131">Безопасность</span><span class="sxs-lookup"><span data-stu-id="67bd7-131">Security:</span></span>

- <span data-ttu-id="67bd7-132">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="67bd7-132">Identity and access management</span></span>

  <span data-ttu-id="67bd7-133">Реализация многофакторной и других форм проверки подлинности, а также защиты данных учетных записей пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="67bd7-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="67bd7-134">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="67bd7-134">Threat protection</span></span>

  <span data-ttu-id="67bd7-135">Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="67bd7-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="67bd7-136">Защита информации</span><span class="sxs-lookup"><span data-stu-id="67bd7-136">Information protection</span></span>

  <span data-ttu-id="67bd7-137">Шифрование важных цифровых ресурсов, например данных клиентов, конструкторских и производственных спецификаций и сведений о сотрудниках, а также блокирование доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="67bd7-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="67bd7-138">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="67bd7-138">Security management</span></span>

  <span data-ttu-id="67bd7-139">Отслеживание состояния безопасности и готовность к обнаружению угроз и реагированию на них в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="67bd7-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="67bd7-140">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="67bd7-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="67bd7-141">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="67bd7-142">Применение концепции BYOD (Bring Your Own Device, использование личных устройств сотрудников для работы) и управление принадлежащими компании устройствами для обеспечения защищенного доступа, правильного поведения приложений и защиты данных компании.</span><span class="sxs-lookup"><span data-stu-id="67bd7-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="67bd7-143">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="67bd7-144">Сокращение издержек на техническое обслуживание и поддержку, а также повышение производительности решения для удаленного доступа путем перемещения часто используемых ресурсов в облако.</span><span class="sxs-lookup"><span data-stu-id="67bd7-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="67bd7-145">Повышение качества подключения и снижение издержек на транзакции типа бизнес-бизнес (B2B)</span><span class="sxs-lookup"><span data-stu-id="67bd7-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="67bd7-146">Замена устаревающей и дорого обходящейся экстрасети для партнеров облачным решением, в котором используется федеративная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="67bd7-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="67bd7-147">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="67bd7-147">Compliance:</span></span>

- <span data-ttu-id="67bd7-148">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="67bd7-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="67bd7-149">Соблюдение требований отраслевых и региональных нормативных актов в части хранения, шифрования и конфиденциальности данных, а также нормативных документов, касающихся личных сведений, например Общего регламента по защите данных (GDPR), принятого в ЕС.</span><span class="sxs-lookup"><span data-stu-id="67bd7-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="67bd7-150">Управление</span><span class="sxs-lookup"><span data-stu-id="67bd7-150">Management:</span></span>

- <span data-ttu-id="67bd7-151">Снижение издержек на ИТ-инфраструктуру в части управления программным обеспечением, работающим на клиентских ПК и устройствах</span><span class="sxs-lookup"><span data-stu-id="67bd7-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="67bd7-152">Автоматизация установки обновлений в ОС Windows и Microsoft Office профессиональный плюс в организации.</span><span class="sxs-lookup"><span data-stu-id="67bd7-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="67bd7-153">Сопоставление бизнес-потребностей компании Contoso с возможностями, предоставляемыми Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="67bd7-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="67bd7-154">Перед развертыванием ИТ-подразделение компании Contoso сопоставило бизнес-потребности с функциями, имеющимися в плане Microsoft 365 корпоративный E5, указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="67bd7-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="67bd7-155">**Категория**</span><span class="sxs-lookup"><span data-stu-id="67bd7-155">**Category**</span></span> | <span data-ttu-id="67bd7-156">**Бизнес-потребность**</span><span class="sxs-lookup"><span data-stu-id="67bd7-156">**Business need**</span></span> | <span data-ttu-id="67bd7-157">**Продукты или функции Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="67bd7-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="67bd7-158">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="67bd7-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="67bd7-159">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="67bd7-159">Make collaboration easier</span></span> | <span data-ttu-id="67bd7-160">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="67bd7-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="67bd7-161">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="67bd7-162">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="67bd7-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="67bd7-163">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="67bd7-163">Increase creativity and innovation</span></span> | <span data-ttu-id="67bd7-164">Windows Ink, Кортана на рабочем месте, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="67bd7-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="67bd7-165">Безопасность</span><span class="sxs-lookup"><span data-stu-id="67bd7-165">Security</span></span> |  |  |
|  | <span data-ttu-id="67bd7-166">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="67bd7-166">Identity & access management</span></span> | <span data-ttu-id="67bd7-167">Выделенные учетные записи глобальных администраторов с многофакторной проверкой подлинности (MFA) Azure и Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="67bd7-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="67bd7-168">Многофакторная проверка подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="67bd7-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="67bd7-169">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="67bd7-169">Conditional access</span></span> <BR> <span data-ttu-id="67bd7-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="67bd7-170">Windows Hello</span></span> <BR> <span data-ttu-id="67bd7-171">Credential Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="67bd7-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="67bd7-172">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="67bd7-172">Threat protection</span></span> | <span data-ttu-id="67bd7-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="67bd7-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="67bd7-174">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="67bd7-174">Windows Defender</span></span> <BR> <span data-ttu-id="67bd7-175">Расширенная защита от угроз</span><span class="sxs-lookup"><span data-stu-id="67bd7-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="67bd7-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="67bd7-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="67bd7-177">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="67bd7-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="67bd7-178">Защита информации</span><span class="sxs-lookup"><span data-stu-id="67bd7-178">Information protection</span></span> | <span data-ttu-id="67bd7-179">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="67bd7-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="67bd7-180">Защита от потери данных в Office 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="67bd7-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="67bd7-181">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="67bd7-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="67bd7-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="67bd7-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="67bd7-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67bd7-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="67bd7-184">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="67bd7-184">Security management</span></span> | <span data-ttu-id="67bd7-185">Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="67bd7-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="67bd7-186">Центр безопасности Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="67bd7-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="67bd7-187">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="67bd7-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="67bd7-188">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="67bd7-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67bd7-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="67bd7-190">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="67bd7-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="67bd7-191">Рабочие нагрузки Microsoft 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="67bd7-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="67bd7-192">Повышение качества подключения и снижение издержек на транзакции типа бизнес-бизнес (B2B)</span><span class="sxs-lookup"><span data-stu-id="67bd7-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="67bd7-193">Федеративная проверка подлинности и облачные ресурсы</span><span class="sxs-lookup"><span data-stu-id="67bd7-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="67bd7-194">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="67bd7-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="67bd7-195">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="67bd7-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="67bd7-196">Функции, необходимые для выполнения требований GDPR, в Office 365</span><span class="sxs-lookup"><span data-stu-id="67bd7-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="67bd7-197">Управление</span><span class="sxs-lookup"><span data-stu-id="67bd7-197">Management</span></span> |  |  |
|  | <span data-ttu-id="67bd7-198">Снижение затрат, связанных с ИТ, на установку обновлений клиентов</span><span class="sxs-lookup"><span data-stu-id="67bd7-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="67bd7-199">Круги развертывания</span><span class="sxs-lookup"><span data-stu-id="67bd7-199">Deployment rings</span></span> <BR> <span data-ttu-id="67bd7-200">Обновления Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="67bd7-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="67bd7-201">Обновления Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="67bd7-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="67bd7-202">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="67bd7-202">Next step</span></span>

<span data-ttu-id="67bd7-203">[Узнайте](contoso-networking.md) о локальной сети корпорации Contoso и о том, как ее оптимизировали для доступа и уменьшения задержек при работе с облачными ресурсами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67bd7-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="67bd7-204">См. также</span><span class="sxs-lookup"><span data-stu-id="67bd7-204">See also</span></span>

[<span data-ttu-id="67bd7-205">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="67bd7-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="67bd7-206">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="67bd7-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
