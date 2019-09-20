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
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047242"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="6d455-103">Условия, при выполнении которых можно считать Information Protection настроенной</span><span class="sxs-lookup"><span data-stu-id="6d455-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6d455-104">Убедитесь, что инфраструктура защиты информации соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.</span><span class="sxs-lookup"><span data-stu-id="6d455-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="6d455-105">Обязательное требование: определены уровни безопасности и защиты информации в организации</span><span class="sxs-lookup"><span data-stu-id="6d455-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="6d455-p101">Вы запланировали и определили уровни безопасности, необходимые вашей организации. Эти уровни определяют минимальный уровень безопасности и дополнительные уровни для конфиденциальной информации и требуемой защиты данных.</span><span class="sxs-lookup"><span data-stu-id="6d455-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="6d455-108">Вы используете не менее трех указанных ниже уровней безопасности.</span><span class="sxs-lookup"><span data-stu-id="6d455-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="6d455-109">Базовый уровень</span><span class="sxs-lookup"><span data-stu-id="6d455-109">Baseline</span></span>
- <span data-ttu-id="6d455-110">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="6d455-110">Sensitive</span></span>
- <span data-ttu-id="6d455-111">Строго регулируемый уровень</span><span class="sxs-lookup"><span data-stu-id="6d455-111">Highly regulated</span></span>

<span data-ttu-id="6d455-112">Чтобы выполнить это требование, см. [шаг 1](infoprotect-define-sec-infoprotect-levels.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="6d455-113">Обязательное требование: настроена усиленная защита для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d455-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="6d455-114">Вы настроили указанные ниже параметры [для повышения безопасности Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="6d455-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="6d455-115">Политики управления угрозами в Центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d455-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="6d455-116">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6d455-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="6d455-117">Политики общего доступа для всего клиента в Центре администрирования SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6d455-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="6d455-118">Параметры в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6d455-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="6d455-119">Вы также [включили Office 365 Advanced Threat Protection для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="6d455-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="6d455-120">Чтобы выполнить это требование, см. [шаг 3](infoprotect-configure-increased-security-office-365.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="6d455-121">Необязательное требование: в используемой вами среде настроена классификация</span><span class="sxs-lookup"><span data-stu-id="6d455-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="6d455-122">Совместно с юридическим отделом и отделом соответствия требованиям вы разработали соответствующую классификацию и схему маркировки для управления данными вашей организации и политик безопасности.</span><span class="sxs-lookup"><span data-stu-id="6d455-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="6d455-123">Эти политики соответствуют настройке и развертыванию следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="6d455-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="6d455-124">Типы конфиденциальных данных</span><span class="sxs-lookup"><span data-stu-id="6d455-124">Sensitive data types</span></span>
- <span data-ttu-id="6d455-125">Метки хранения</span><span class="sxs-lookup"><span data-stu-id="6d455-125">Retention labels</span></span>
- <span data-ttu-id="6d455-126">Метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="6d455-126">Sensitivity labels</span></span>
- <span data-ttu-id="6d455-127">Метки Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="6d455-127">Azure Information Protection labels</span></span>

<span data-ttu-id="6d455-128">Чтобы выполнить это требование, см. [шаг 2](infoprotect-configure-classification.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="6d455-129">Необязательно: функция Windows Information Protection развернута в вашей среде</span><span class="sxs-lookup"><span data-stu-id="6d455-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="6d455-130">На ваших зарегистрированных устройствах Windows 10 Корпоративная развернута и применена политика Intune, которая определяет:</span><span class="sxs-lookup"><span data-stu-id="6d455-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="6d455-131">Какие приложения следует защищать.</span><span class="sxs-lookup"><span data-stu-id="6d455-131">Which apps to protect.</span></span>
- <span data-ttu-id="6d455-132">Уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="6d455-132">The level of protection.</span></span>
- <span data-ttu-id="6d455-133">На что распространяется защита.</span><span class="sxs-lookup"><span data-stu-id="6d455-133">Where the protection extends.</span></span>

<span data-ttu-id="6d455-134">Чтобы выполнить это требование, см. [шаг 4](infoprotect-deploy-windows-information-protection.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="6d455-135">Необязательно: развернута служба защиты от потери данных (DLP) Office 365</span><span class="sxs-lookup"><span data-stu-id="6d455-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="6d455-136">Вы проанализировали, протестировали, а затем развернули набор политик DLP с указанием местоположений и правил с условиями и действиями, требуемых вашей организацией для защиты данных клиентов и других типов конфиденциальных данных, а также для соблюдения отраслевых и региональных норм и требований.</span><span class="sxs-lookup"><span data-stu-id="6d455-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="6d455-137">Ваши сотрудники, ответственные за соблюдение норм и безопасность данных, используют панель мониторинга безопасности и соответствия требованиям Office 365 для контроля инцидентов с DLP.</span><span class="sxs-lookup"><span data-stu-id="6d455-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="6d455-138">Чтобы выполнить это требование, см. [шаг 5](infoprotect-data-loss-prevention.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="6d455-139">Необязательное требование: настроено шифрование электронной почты</span><span class="sxs-lookup"><span data-stu-id="6d455-139">Optional: Email encryption is configured</span></span>

<span data-ttu-id="6d455-140">Вы настроили следующий метод шифрования электронной почты в соответствии с требованиями организации:</span><span class="sxs-lookup"><span data-stu-id="6d455-140">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="6d455-141">**Метод шифрования**</span><span class="sxs-lookup"><span data-stu-id="6d455-141">**Encryption method**</span></span> | <span data-ttu-id="6d455-142">**При отправке почты**</span><span class="sxs-lookup"><span data-stu-id="6d455-142">**For email sent**</span></span> |
| [<span data-ttu-id="6d455-143">Шифрование сообщений Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="6d455-143">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="6d455-144">За пределы организации с шифрованием</span><span class="sxs-lookup"><span data-stu-id="6d455-144">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="6d455-145">Управление правами на доступ к данным (IRM)</span><span class="sxs-lookup"><span data-stu-id="6d455-145">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="6d455-146">С шифрованием и разрешениями</span><span class="sxs-lookup"><span data-stu-id="6d455-146">With both encryption and permissions</span></span> |
| [<span data-ttu-id="6d455-147">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="6d455-147">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="6d455-148">С шифрованием и цифровыми подписями с использованием шифрования с открытым ключом</span><span class="sxs-lookup"><span data-stu-id="6d455-148">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="6d455-149">Чтобы выполнить это требование, см. [шаг 6](infoprotect-email-encryption.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-149">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="6d455-150">Необязательное требование: настроено управление привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="6d455-150">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="6d455-151">С помощью сведений в статье [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) вы включили привилегированный доступ и создали одну или несколько политик привилегированного доступа в организации.</span><span class="sxs-lookup"><span data-stu-id="6d455-151">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="6d455-152">Вы настроили эти политики и включили своевременный доступ для получения доступа к конфиденциальным данным или важным параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6d455-152">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="6d455-153">Чтобы выполнить это требование, см. [шаг 7](infoprotect-configure-privileged-access-management.md) (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="6d455-153">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="6d455-154">Результаты и дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6d455-154">Results and next steps</span></span>

<span data-ttu-id="6d455-155">Ваша инфраструктура защиты информации для Microsoft 365 корпоративный использует определенные уровни безопасности, усиленную защиту для Office 365, классификацию с применением типов и меток конфиденциальных данных, Windows Information Protection, защиту от потери данных, шифрование электронной почты и управление привилегированным доступом.</span><span class="sxs-lookup"><span data-stu-id="6d455-155">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="6d455-156">Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, вы готовы к применению в ваших [полезных нагрузках и сценариях](deploy-workloads.md) всех функций и настроек базовой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6d455-156">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
