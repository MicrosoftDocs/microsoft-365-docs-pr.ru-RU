---
title: ИТ-инфраструктура и бизнес-потребности компании Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказано о базовой структуре локальной ИТ-инфраструктуры компании Contoso и о том, как можно удовлетворить потребности компании с помощью Microsoft 365 корпоративный.
ms.openlocfilehash: a4a86c56f956361e58730f328ef940a627370ea6
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353140"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="505f0-103">ИТ-инфраструктура и бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="505f0-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="505f0-104">**Сводка**: в этой статье рассказано о базовой структуре локальной ИТ-инфраструктуры компании Contoso и о том, как можно удовлетворить потребности компании с помощью Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="505f0-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="505f0-105">Компания Contoso выполнила переход от локальной централизованной ИТ-инфраструктуры к инфраструктуре, включающей облако. В состав этой инфраструктуры входят рабочие нагрузки и приложения для повышения производительности труда сотрудников.</span><span class="sxs-lookup"><span data-stu-id="505f0-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="505f0-106">Существующая ИТ-инфраструктура Contoso</span><span class="sxs-lookup"><span data-stu-id="505f0-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="505f0-107">В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.</span><span class="sxs-lookup"><span data-stu-id="505f0-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="505f0-108">На рис. 1 показан главный офис с центрами обработки данных приложений, сетью периметра и Интернетом.</span><span class="sxs-lookup"><span data-stu-id="505f0-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="505f0-109">**Рис. 1. Существующая инфраструктура компании Contoso**</span><span class="sxs-lookup"><span data-stu-id="505f0-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="505f0-110">В локальных центрах обработки данных приложений размещены указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="505f0-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="505f0-111">Пользовательские бизнес-приложения, использующие SQL Server и другие базы данных, работающие в ОС Linux.</span><span class="sxs-lookup"><span data-stu-id="505f0-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="505f0-112">Набор устаревших серверов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="505f0-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="505f0-113">Серверы уровня организации и групп для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="505f0-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="505f0-p101">Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений. Этими серверами управляют региональные ИТ-отделы.</span><span class="sxs-lookup"><span data-stu-id="505f0-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="505f0-116">Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.</span><span class="sxs-lookup"><span data-stu-id="505f0-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="505f0-117">В сети периметра главного офиса компании Contoso различные наборы серверов предоставляют указанные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="505f0-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="505f0-118">Удаленный VPN-доступ к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.</span><span class="sxs-lookup"><span data-stu-id="505f0-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="505f0-119">Хостинг для общедоступного веб-сайта компании Contoso, на котором клиенты могут заказывать продукцию, запасные части, расходные материалы или услуги.</span><span class="sxs-lookup"><span data-stu-id="505f0-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="505f0-120">Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.</span><span class="sxs-lookup"><span data-stu-id="505f0-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="505f0-121">Бизнес-потребности компании Contoso</span><span class="sxs-lookup"><span data-stu-id="505f0-121">Contoso's business needs</span></span>

<span data-ttu-id="505f0-122">Бизнес-потребности компании Contoso можно разделить на пять основных категорий.</span><span class="sxs-lookup"><span data-stu-id="505f0-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="505f0-123">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="505f0-123">Productivity:</span></span>

- <span data-ttu-id="505f0-124">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="505f0-124">Make collaboration easier</span></span>

  <span data-ttu-id="505f0-125">Замена модели совместной работы, предусматривающей использование электронной почты и файловых ресурсов, на онлайн-модель, которая позволяет вносить изменения в документы в режиме реального времени и записывать цепочки в беседах, а также упрощает проведение собраний по сети.</span><span class="sxs-lookup"><span data-stu-id="505f0-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="505f0-126">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="505f0-127">Так как большое количество сотрудников работает дома или в разъездах, необходимо заменить решение на базе VPN, т. е. "узкое" место, решением, которое предусматривает высокопроизводительный доступ к данным и ресурсам компании Contoso в облаке.</span><span class="sxs-lookup"><span data-stu-id="505f0-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="505f0-128">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="505f0-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="505f0-129">Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.</span><span class="sxs-lookup"><span data-stu-id="505f0-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="505f0-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="505f0-130">Security:</span></span>

- <span data-ttu-id="505f0-131">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="505f0-131">Identity and access management</span></span>

  <span data-ttu-id="505f0-132">Реализация многофакторной и других форм проверки подлинности, а также защиты данных учетных записей пользователей и администраторов.</span><span class="sxs-lookup"><span data-stu-id="505f0-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="505f0-133">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="505f0-133">Threat protection</span></span>

  <span data-ttu-id="505f0-134">Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.</span><span class="sxs-lookup"><span data-stu-id="505f0-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="505f0-135">Защита информации</span><span class="sxs-lookup"><span data-stu-id="505f0-135">Information protection</span></span>

  <span data-ttu-id="505f0-136">Шифрование высокоценных цифровых активов, например данных клиентов, конструкторских спецификаций и сведений о сотрудниках, а также блокирование доступа к этим активам.</span><span class="sxs-lookup"><span data-stu-id="505f0-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="505f0-137">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="505f0-137">Security management</span></span>

  <span data-ttu-id="505f0-138">Отслеживание состояния безопасности и готовность к обнаружению угроз и реагированию на них в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="505f0-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="505f0-139">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="505f0-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="505f0-140">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="505f0-141">Применение концепции BYOD (Bring Your Own Device, использование личных устройств сотрудников для работы) и управление принадлежащими компании устройствами для обеспечения защищенного доступа, правильного поведения приложений и защиты данных компании.</span><span class="sxs-lookup"><span data-stu-id="505f0-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="505f0-142">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="505f0-143">Сокращение издержек на техническое обслуживание и поддержку, а также повышение производительности решения для удаленного доступа путем перемещения ресурсов с общим доступом в облако.</span><span class="sxs-lookup"><span data-stu-id="505f0-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="505f0-144">Повышение качества подключения и снижение издержек на транзакции типа бизнес-бизнес (B2B)</span><span class="sxs-lookup"><span data-stu-id="505f0-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="505f0-145">Замена устаревающей и дорого обходящейся экстрасети для партнеров облачным решением, в котором используется федеративная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="505f0-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="505f0-146">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="505f0-146">Compliance:</span></span>

- <span data-ttu-id="505f0-147">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="505f0-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="505f0-148">Соблюдение требований отраслевых и региональных нормативных актов в части хранения, шифрования и конфиденциальности данных, а также нормативных документов, касающихся личных сведений, например Общего регламента по защите данных (GDPR), принятого в ЕС.</span><span class="sxs-lookup"><span data-stu-id="505f0-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="505f0-149">Управление</span><span class="sxs-lookup"><span data-stu-id="505f0-149">Management:</span></span>

- <span data-ttu-id="505f0-150">Снижение издержек на ИТ-инфраструктуру в части управления программным обеспечением, работающим на клиентских ПК и устройствах</span><span class="sxs-lookup"><span data-stu-id="505f0-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="505f0-151">Автоматизация установки обновлений в ОС Windows и Microsoft Office в организации.</span><span class="sxs-lookup"><span data-stu-id="505f0-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="505f0-152">Сопоставление бизнес-потребностей компании Contoso с возможностями, предоставляемыми Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="505f0-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="505f0-153">Перед развертыванием ИТ-подразделение компании Contoso сопоставило бизнес-потребности с функциями, имеющимися в плане Microsoft 365 корпоративный E5, указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="505f0-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="505f0-154">**Категория**</span><span class="sxs-lookup"><span data-stu-id="505f0-154">**Category**</span></span> | <span data-ttu-id="505f0-155">**Бизнес-потребность**</span><span class="sxs-lookup"><span data-stu-id="505f0-155">**Business need**</span></span> | <span data-ttu-id="505f0-156">**Продукты или функции Microsoft 365 корпоративный**</span><span class="sxs-lookup"><span data-stu-id="505f0-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="505f0-157">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="505f0-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="505f0-158">Упрощение совместной работы</span><span class="sxs-lookup"><span data-stu-id="505f0-158">Make collaboration easier</span></span> | <span data-ttu-id="505f0-159">Teams, SharePoint Online, Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="505f0-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="505f0-160">Повышение производительности труда удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="505f0-161">Рабочие нагрузки Office 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="505f0-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="505f0-162">Повышение уровня креативности и инноваций</span><span class="sxs-lookup"><span data-stu-id="505f0-162">Increase creativity and innovation</span></span> | <span data-ttu-id="505f0-163">Windows Ink, Кортана на рабочем месте, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="505f0-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="505f0-164">Безопасность</span><span class="sxs-lookup"><span data-stu-id="505f0-164">Security</span></span> |  |  |
|  | <span data-ttu-id="505f0-165">Управление удостоверениями и доступом</span><span class="sxs-lookup"><span data-stu-id="505f0-165">Identity & access management</span></span> | <span data-ttu-id="505f0-166">Выделенные учетные записи глобальных администраторов с многофакторной проверкой подлинности (MFA) и Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="505f0-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="505f0-167">Многофакторная проверка подлинности для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="505f0-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="505f0-168">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="505f0-168">Conditional access</span></span> <BR> <span data-ttu-id="505f0-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="505f0-169">Windows Hello</span></span> <BR> <span data-ttu-id="505f0-170">Credential Guard в Защитнике Windows</span><span class="sxs-lookup"><span data-stu-id="505f0-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="505f0-171">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="505f0-171">Threat protection</span></span> | <span data-ttu-id="505f0-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="505f0-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="505f0-173">Защитник Windows</span><span class="sxs-lookup"><span data-stu-id="505f0-173">Windows Defender</span></span> <BR> <span data-ttu-id="505f0-174">Расширенная защита от угроз</span><span class="sxs-lookup"><span data-stu-id="505f0-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="505f0-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="505f0-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="505f0-176">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="505f0-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="505f0-177">Защита информации</span><span class="sxs-lookup"><span data-stu-id="505f0-177">Information protection</span></span> | <span data-ttu-id="505f0-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="505f0-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="505f0-179">Защита от потери данных в Office \`365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="505f0-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="505f0-180">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="505f0-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="505f0-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="505f0-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="505f0-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="505f0-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="505f0-183">Управление безопасностью</span><span class="sxs-lookup"><span data-stu-id="505f0-183">Security management</span></span> | <span data-ttu-id="505f0-184">Центр безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="505f0-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="505f0-185">Центр безопасности Защитника Windows</span><span class="sxs-lookup"><span data-stu-id="505f0-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="505f0-186">Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами</span><span class="sxs-lookup"><span data-stu-id="505f0-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="505f0-187">Повышение уровня безопасности для удаленных и мобильных сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="505f0-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="505f0-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="505f0-189">Уменьшение инфраструктуры удаленного доступа для сотрудников</span><span class="sxs-lookup"><span data-stu-id="505f0-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="505f0-190">Рабочие нагрузки Office 365 и облачные данные</span><span class="sxs-lookup"><span data-stu-id="505f0-190">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="505f0-191">Повышение качества подключения и снижение издержек на транзакции типа бизнес-бизнес (B2B)</span><span class="sxs-lookup"><span data-stu-id="505f0-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="505f0-192">Федеративная проверка подлинности и облачные ресурсы</span><span class="sxs-lookup"><span data-stu-id="505f0-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="505f0-193">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="505f0-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="505f0-194">Соответствие требованиям региональных нормативных актов</span><span class="sxs-lookup"><span data-stu-id="505f0-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="505f0-195">Функции, необходимые для выполнения требований GDPR, в Office 365</span><span class="sxs-lookup"><span data-stu-id="505f0-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="505f0-196">Управление</span><span class="sxs-lookup"><span data-stu-id="505f0-196">Management</span></span> |  |  |
|  | <span data-ttu-id="505f0-197">Снижение затрат, связанных с ИТ, на установку обновлений клиентов</span><span class="sxs-lookup"><span data-stu-id="505f0-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="505f0-198">Круги развертывания</span><span class="sxs-lookup"><span data-stu-id="505f0-198">Deployment rings</span></span> <BR> <span data-ttu-id="505f0-199">Обновление на месте и Autopilot для Windows 10</span><span class="sxs-lookup"><span data-stu-id="505f0-199">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="505f0-200">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="505f0-200">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="505f0-201">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="505f0-201">Next step</span></span>

<span data-ttu-id="505f0-202">[Узнайте](contoso-networking.md) о локальной сети корпорации Contoso и о том, как ее оптимизировали для доступа и уменьшения задержек при работе с облачными ресурсами Microsoft 365 в организации.</span><span class="sxs-lookup"><span data-stu-id="505f0-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="505f0-203">См. также</span><span class="sxs-lookup"><span data-stu-id="505f0-203">See also</span></span>

[<span data-ttu-id="505f0-204">Руководство по развертыванию</span><span class="sxs-lookup"><span data-stu-id="505f0-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="505f0-205">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="505f0-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
