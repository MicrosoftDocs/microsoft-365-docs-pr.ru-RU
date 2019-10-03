---
title: Условия, при выполнении которых можно считать Information Protection настроенной
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучите условия для служб и инфраструктуры, основанных на Information Protection, и проверьте, соответствует ли используемая вами конфигурация требованиям Microsoft 365 корпоративный.
ms.openlocfilehash: f4896baeb4c18fc1eabac10b15f3ad8e150ab260
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370136"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="7265f-103">Условия, при выполнении которых можно считать Information Protection настроенной</span><span class="sxs-lookup"><span data-stu-id="7265f-103">Information protection infrastructure exit criteria</span></span>

![Этап 6. Защита данных](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="7265f-105">Убедитесь, что инфраструктура защиты информации соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="7265f-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="7265f-106">Обязательное требование: определены уровни безопасности и защиты информации в организации</span><span class="sxs-lookup"><span data-stu-id="7265f-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="7265f-p101">Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.</span><span class="sxs-lookup"><span data-stu-id="7265f-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="7265f-109">Вы используете не менее трех указанных ниже уровней безопасности.</span><span class="sxs-lookup"><span data-stu-id="7265f-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="7265f-110">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="7265f-110">Baseline</span></span>
- <span data-ttu-id="7265f-111">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="7265f-111">Sensitive</span></span>
- <span data-ttu-id="7265f-112">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="7265f-112">Highly regulated</span></span>

<span data-ttu-id="7265f-113">Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="7265f-114">Обязательное требование: настроена усиленная защита для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7265f-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="7265f-115">Вы настроили указанные ниже параметры [для повышения безопасности Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="7265f-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="7265f-116">Политики управления угрозами в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7265f-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="7265f-117">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7265f-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="7265f-118">Политики общего доступа для всего клиента в Центре администрирования SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7265f-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="7265f-119">Параметры в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7265f-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="7265f-120">Вы также [включили Office 365 Advanced Threat Protection для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="7265f-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="7265f-121">Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="7265f-122">Необязательное требование: в используемой вами среде настроена классификация</span><span class="sxs-lookup"><span data-stu-id="7265f-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="7265f-123">Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для управления данными вашей организации и политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="7265f-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="7265f-124">Эти политики соответствуют настройке и развертыванию следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="7265f-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="7265f-125">Типы конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="7265f-125">Sensitive data types</span></span>
- <span data-ttu-id="7265f-126">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="7265f-126">Retention labels</span></span>
- <span data-ttu-id="7265f-127">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7265f-127">Sensitivity labels</span></span>
- <span data-ttu-id="7265f-128">Метки Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7265f-128">Azure Information Protection labels</span></span>

<span data-ttu-id="7265f-129">Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="7265f-130">Необязательно: функция Windows Information Protection развернута в вашей среде</span><span class="sxs-lookup"><span data-stu-id="7265f-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="7265f-131">На ваших зарегистрированных устройствах Windows 10 Корпоративная развернута и применена политика Intune, которая определяет:</span><span class="sxs-lookup"><span data-stu-id="7265f-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="7265f-132">Какие приложения следует защищать.</span><span class="sxs-lookup"><span data-stu-id="7265f-132">Which apps to protect.</span></span>
- <span data-ttu-id="7265f-133">Уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="7265f-133">The level of protection.</span></span>
- <span data-ttu-id="7265f-134">На что распространяется защита.</span><span class="sxs-lookup"><span data-stu-id="7265f-134">Where the protection extends.</span></span>

<span data-ttu-id="7265f-135">Чтобы выполнить это требование, см. [шаг 4](infoprotect-deploy-windows-information-protection.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="7265f-136">Необязательно: развернута служба защиты от потери данных (DLP) Office 365</span><span class="sxs-lookup"><span data-stu-id="7265f-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="7265f-137">Вы проанализировали, протестировали, а затем развернули набор политик DLP с указанием местоположений и правил с условиями и действиями, требуемых вашей организацией для защиты данных клиентов и других типов конфиденциальных данных, а также для соблюдения отраслевых и региональных норм и требований.</span><span class="sxs-lookup"><span data-stu-id="7265f-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="7265f-138">Ваши сотрудники, ответственные за соблюдение норм и безопасность данных, используют панель мониторинга безопасности и соответствия требованиям Office 365 для контроля инцидентов с DLP.</span><span class="sxs-lookup"><span data-stu-id="7265f-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="7265f-139">Чтобы выполнить это требование, см. [шаг 5](infoprotect-data-loss-prevention.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="7265f-140">Необязательное требование: настроено шифрование электронной почты</span><span class="sxs-lookup"><span data-stu-id="7265f-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="7265f-141">Вы настроили следующий метод шифрования электронной почты в соответствии с требованиями организации:</span><span class="sxs-lookup"><span data-stu-id="7265f-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="7265f-142">**Метод шифрования**</span><span class="sxs-lookup"><span data-stu-id="7265f-142">**Encryption method**</span></span> | <span data-ttu-id="7265f-143">**При отправке почты**</span><span class="sxs-lookup"><span data-stu-id="7265f-143">**For email sent**</span></span> |
| [<span data-ttu-id="7265f-144">Шифрование сообщений Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="7265f-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="7265f-145">За пределы организации с шифрованием</span><span class="sxs-lookup"><span data-stu-id="7265f-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="7265f-146">Управление правами на доступ к данным (IRM)</span><span class="sxs-lookup"><span data-stu-id="7265f-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="7265f-147">С шифрованием и разрешениями</span><span class="sxs-lookup"><span data-stu-id="7265f-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="7265f-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="7265f-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="7265f-149">С шифрованием и цифровыми подписями с использованием шифрования с открытым ключом</span><span class="sxs-lookup"><span data-stu-id="7265f-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="7265f-150">Чтобы выполнить это требование, см. [шаг 6](infoprotect-email-encryption.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="7265f-151">Необязательное требование: настроено управление привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="7265f-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="7265f-152">С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации.</span><span class="sxs-lookup"><span data-stu-id="7265f-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="7265f-153">Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7265f-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="7265f-154">Чтобы выполнить это требование, см. [шаг 7](infoprotect-configure-privileged-access-management.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7265f-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="7265f-155">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7265f-155">Results and next steps</span></span>

<span data-ttu-id="7265f-156">Ваша инфраструктура защиты информации для Microsoft 365 корпоративный использует определенные уровни безопасности, усиленную защиту для Office 365, классификацию с применением типов и меток конфиденциальных данных, Windows Information Protection, защиту от потери данных, шифрование электронной почты и управление привилегированным доступом.</span><span class="sxs-lookup"><span data-stu-id="7265f-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="7265f-157">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, вы готовы к применению в ваших [полезных нагрузках и сценариях](deploy-workloads.md) всех функций и настроек базовой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7265f-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
