---
title: Условия, при выполнении которых можно считать Information Protection настроенной
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите условия для служб и инфраструктуры, основанных на Information Protection, и проверьте, соответствует ли используемая вами конфигурация требованиям Microsoft 365 корпоративный.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870967"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="3ee65-103">Условия, при выполнении которых можно считать Information Protection настроенной</span><span class="sxs-lookup"><span data-stu-id="3ee65-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3ee65-104">Прежде чем завершить работу над базовой инфраструктурой, убедитесь, что ваша инфраструктура Information Protection соответствует указанным ниже требованиям.</span><span class="sxs-lookup"><span data-stu-id="3ee65-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="3ee65-105">Обязательное требование: определены уровни безопасности и Information Protection в организации</span><span class="sxs-lookup"><span data-stu-id="3ee65-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="3ee65-p101">Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.</span><span class="sxs-lookup"><span data-stu-id="3ee65-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="3ee65-108">Вы используете не менее трех указанных ниже уровней безопасности.</span><span class="sxs-lookup"><span data-stu-id="3ee65-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="3ee65-109">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="3ee65-109">Baseline</span></span>
- <span data-ttu-id="3ee65-110">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="3ee65-110">Sensitive</span></span>
- <span data-ttu-id="3ee65-111">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="3ee65-111">Highly regulated</span></span>

<span data-ttu-id="3ee65-112">Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="3ee65-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="3ee65-113">Обязательное требование: настроена усиленная защита для Office 365</span><span class="sxs-lookup"><span data-stu-id="3ee65-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="3ee65-114">Вы настроили указанные ниже параметры для усиленной защиты согласно сведениям в статье [Настройка клиента Office 365 для повышения безопасности](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span><span class="sxs-lookup"><span data-stu-id="3ee65-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="3ee65-115">Политики управления угрозами в Центре безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="3ee65-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="3ee65-116">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ee65-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="3ee65-117">Политики общего доступа, используемые во всем клиенте, в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="3ee65-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="3ee65-118">Параметры в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ee65-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="3ee65-119">Вы также [включили Office 365 Advanced Threat Protection](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="3ee65-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="3ee65-120">Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="3ee65-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="3ee65-121">Необязательное требование: в используемой вами среде настроена классификация</span><span class="sxs-lookup"><span data-stu-id="3ee65-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="3ee65-122">Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для данных вашей организации, включающие следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="3ee65-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="3ee65-123">типы конфиденциальных данных;</span><span class="sxs-lookup"><span data-stu-id="3ee65-123">Sensitive data types</span></span>
- <span data-ttu-id="3ee65-124">метки Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ee65-124">Office 365 labels</span></span>
- <span data-ttu-id="3ee65-125">Метки Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="3ee65-125">Azure Information Protection labels</span></span>

<span data-ttu-id="3ee65-126">Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="3ee65-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="3ee65-127">Необязательное требование: настроено управление привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="3ee65-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="3ee65-p102">С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации Office 365. Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3ee65-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="3ee65-130">Чтобы выполнить это требование, см. [шаг 4](infoprotect-configure-privileged-access-management.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="3ee65-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="3ee65-131">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="3ee65-131">Next Step</span></span>

<span data-ttu-id="3ee65-132">Теперь вы готовы развернуть [рабочие нагрузки и сценарии](deploy-workloads.md), например Microsoft Teams и Exchange Online, работающие на базовой инфраструктуре Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="3ee65-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
