---
title: Условия, при выполнении которых можно считать Information Protection настроенной
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите условия для служб и инфраструктуры, основанных на Information Protection, и проверьте, соответствует ли используемая вами конфигурация требованиям Microsoft 365 корпоративный.
ms.openlocfilehash: 267a6efaef5a5bcfb0ec9f8e0e9f33d525f5ce74
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071949"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="1a0dd-103">Условия, при выполнении которых можно считать Information Protection настроенной</span><span class="sxs-lookup"><span data-stu-id="1a0dd-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="1a0dd-104">Убедитесь, что инфраструктура защиты информации соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="1a0dd-105">Обязательное требование: определены уровни безопасности и защиты информации в организации</span><span class="sxs-lookup"><span data-stu-id="1a0dd-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="1a0dd-p101">Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="1a0dd-108">Вы используете не менее трех указанных ниже уровней безопасности.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="1a0dd-109">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="1a0dd-109">Baseline</span></span>
- <span data-ttu-id="1a0dd-110">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="1a0dd-110">Sensitive</span></span>
- <span data-ttu-id="1a0dd-111">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="1a0dd-111">Highly regulated</span></span>

<span data-ttu-id="1a0dd-112">Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="1a0dd-113">Обязательное требование: настроена усиленная защита для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a0dd-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="1a0dd-114">Вы настроили указанные ниже параметры [для повышения безопасности Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="1a0dd-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="1a0dd-115">Политики управления угрозами в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a0dd-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="1a0dd-116">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1a0dd-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="1a0dd-117">Политики общего доступа для всего клиента в Центре администрирования SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1a0dd-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="1a0dd-118">Параметры в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1a0dd-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="1a0dd-119">Вы также [включили Office 365 Advanced Threat Protection для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="1a0dd-120">Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="1a0dd-121">Необязательное требование: в используемой вами среде настроена классификация</span><span class="sxs-lookup"><span data-stu-id="1a0dd-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="1a0dd-122">Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для управления данными вашей организации и политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="1a0dd-123">Эти политики соответствуют настройке и развертыванию следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="1a0dd-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="1a0dd-124">Типы конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="1a0dd-124">Sensitive data types</span></span>
- <span data-ttu-id="1a0dd-125">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="1a0dd-125">Retention labels</span></span>
- <span data-ttu-id="1a0dd-126">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="1a0dd-126">Sensitivity labels</span></span>
- <span data-ttu-id="1a0dd-127">Метки Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1a0dd-127">Azure Information Protection labels</span></span>

<span data-ttu-id="1a0dd-128">Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="1a0dd-129">Необязательно: функция Windows Information Protection развернута в вашей среде</span><span class="sxs-lookup"><span data-stu-id="1a0dd-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="1a0dd-130">На ваших зарегистрированных устройствах Windows 10 Корпоративная развернута и применена политика Intune, которая определяет:</span><span class="sxs-lookup"><span data-stu-id="1a0dd-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="1a0dd-131">Какие приложения следует защищать.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-131">Which apps to protect.</span></span>
- <span data-ttu-id="1a0dd-132">Уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-132">The level of protection.</span></span>
- <span data-ttu-id="1a0dd-133">На что распространяется защита.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-133">Where the protection extends.</span></span>

<span data-ttu-id="1a0dd-134">Чтобы выполнить это требование, см. [шаг 4](infoprotect-deploy-windows-information-protection.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="1a0dd-135">Необязательно: развернута служба защиты от потери данных (DLP) Office 365</span><span class="sxs-lookup"><span data-stu-id="1a0dd-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="1a0dd-136">Вы проанализировали, протестировали, а затем развернули набор политик DLP с указанием местоположений и правил с условиями и действиями, требуемых вашей организацией для защиты данных клиентов и других типов конфиденциальных данных, а также для соблюдения отраслевых и региональных норм и требований.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="1a0dd-137">Ваши сотрудники, ответственные за соблюдение норм и безопасность данных, используют панель мониторинга безопасности и соответствия требованиям Office 365 для контроля инцидентов с DLP.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="1a0dd-138">Чтобы выполнить это требование, см. [шаг 5](infoprotect-data-loss-prevention.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="1a0dd-139">Необязательное требование: настроено управление привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="1a0dd-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="1a0dd-140">С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="1a0dd-141">Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="1a0dd-142">Чтобы выполнить это требование, см. [шаг 6](infoprotect-configure-privileged-access-management.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="1a0dd-142">If needed, [Step 6](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="1a0dd-143">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="1a0dd-143">Results and next steps</span></span>

<span data-ttu-id="1a0dd-144">Ваша инфраструктура защиты информации для Microsoft 365 корпоративный использует определенные уровни безопасности, усиленную защиту для Office 365, классификацию с применением типов и меток конфиденциальных данных, Windows Information Protection, защиту от потери данных и управление привилегированным доступом.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="1a0dd-145">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, вы готовы к применению в ваших [полезных нагрузках и сценариях](deploy-workloads.md) всех функций и настроек базовой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="1a0dd-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
