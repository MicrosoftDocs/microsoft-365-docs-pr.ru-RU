---
title: Шаг 2. Защита паролей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Необходимо обеспечить надежность и управляемость ваших паролей в масштабах организации.
ms.openlocfilehash: 143f7727846316100e4133ccf4b34646645bfd7f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801744"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="5c9a4-103">Шаг 2. Защита паролей</span><span class="sxs-lookup"><span data-stu-id="5c9a4-103">Step 2: Secure your passwords</span></span>

![Этап 2. Удостоверения](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="5c9a4-105">Запрет слабых паролей</span><span class="sxs-lookup"><span data-stu-id="5c9a4-105">Prevent bad passwords</span></span>

<span data-ttu-id="5c9a4-106">*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="5c9a4-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5c9a4-107">Все ваши пользователи должны применять [Руководство по паролям корпорации Майкрософт](https://www.microsoft.com/research/publication/password-guidance/) для создания своих паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="5c9a4-108">Чтобы запретить пользователям создавать легко подбираемые пароли, применяйте службу защиты паролей Azure AD, в которой используется как глобальный список запрещенных паролей, так и необязательный настраиваемый список запрещенных паролей, указываемый вами.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="5c9a4-109">Например, вы можете указать следующие термины, относящиеся к вашей организации:</span><span class="sxs-lookup"><span data-stu-id="5c9a4-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="5c9a4-110">Фирменные названия</span><span class="sxs-lookup"><span data-stu-id="5c9a4-110">Brand names</span></span>
- <span data-ttu-id="5c9a4-111">Названия продуктов</span><span class="sxs-lookup"><span data-stu-id="5c9a4-111">Product names</span></span>
- <span data-ttu-id="5c9a4-112">Расположения (например, штаб-квартира компании)</span><span class="sxs-lookup"><span data-stu-id="5c9a4-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="5c9a4-113">Внутренние термины, относящиеся к компании</span><span class="sxs-lookup"><span data-stu-id="5c9a4-113">Company-specific internal terms</span></span>
- <span data-ttu-id="5c9a4-114">Сокращения с определенным значением в компании</span><span class="sxs-lookup"><span data-stu-id="5c9a4-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="5c9a4-115">Вы можете запретить слабые пароли в [облачной среде](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) и [локальных доменных службах Active Directory (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="5c9a4-116">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-password-prot).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="5c9a4-117">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="5c9a4-117">Simplify password resets</span></span>

<span data-ttu-id="5c9a4-118">*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="5c9a4-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5c9a4-119">В этом разделе описывается включение самостоятельного сброса паролей (SSPR), позволяющего пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="5c9a4-120">Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="5c9a4-121">Прежде чем развертывать функцию сброса паролей необходимо включить обратную запись паролей.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="5c9a4-122">См. [инструкции по развертыванию функции сброса паролей](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5c9a4-124">Руководство по лаборатории тестирования: сброс пароля</span><span class="sxs-lookup"><span data-stu-id="5c9a4-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5c9a4-125">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-pw-reset).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="5c9a4-126">Упрощение входа пользователей</span><span class="sxs-lookup"><span data-stu-id="5c9a4-126">Simplify user sign-in</span></span>

<span data-ttu-id="5c9a4-127">*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5c9a4-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5c9a4-128">В этом разделе описывается настройка эффективного единого входа в Azure Active Directory в сочетании с синхронизацией хэша паролей (PHS) и сквозной проверкой подлинности (PTA), чтобы разрешить пользователям входить в службы, использующие учетные записи пользователей Azure AD, не вводя свои пароли и (во многих случаях) имена пользователей.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="5c9a4-129">Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="5c9a4-130">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="5c9a4-131">См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5c9a4-133">Руководство по лаборатории тестирования: простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c9a4-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5c9a4-134">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-sso).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="5c9a4-135">Настройка страницы входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="5c9a4-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="5c9a4-136">*Этот шаг не является обязательным. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5c9a4-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5c9a4-137">В этом разделе описывается, как помочь пользователям узнавать страницу входа в систему вашей организации, добавив на нее название и логотип компании, а также другие отличительные элементы.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="5c9a4-138">С помощью Microsoft 365 корпоративный вы можете настроить внешний вид страницы входа и страниц Панели доступа так, чтобы на них отображались логотип вашей компании, цветовые схемы и настраиваемая пользовательская информация.</span><span class="sxs-lookup"><span data-stu-id="5c9a4-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="5c9a4-139">Дополнительные сведения см. в статье [Добавление фирменной символики компании на страницу входа в Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="5c9a4-140">Инструкции по настройке см. в статье [Краткое руководство по добавлению фирменной символики организации на страницу входа в Azure Active Directory](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="5c9a4-141">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-custom-sign-in).</span><span class="sxs-lookup"><span data-stu-id="5c9a4-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c9a4-142">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="5c9a4-142">Next step</span></span>

|||
|:-------|:-----|
|![Шаг 3](./media/stepnumbers/Step3.png)| [<span data-ttu-id="5c9a4-144">Защита пользовательских входов и управление ими</span><span class="sxs-lookup"><span data-stu-id="5c9a4-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
