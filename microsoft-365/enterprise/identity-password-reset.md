---
title: Шаг 5. Упрощение доступа для пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить функцию самостоятельного сброса паролей для Azure AD.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287074"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="c8e7f-103">Шаг 5. Упрощение доступа для пользователей</span><span class="sxs-lookup"><span data-stu-id="c8e7f-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="c8e7f-104">Упрощение процедуры обновления паролей</span><span class="sxs-lookup"><span data-stu-id="c8e7f-104">Simplify password updates</span></span>

<span data-ttu-id="c8e7f-105">*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c8e7f-105">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c8e7f-106">В этом разделе описывается, как разрешить пользователям сбрасывать свои пароли в Azure Active Directory (Azure AD), которые затем реплицируются в локальные доменные службы Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="c8e7f-107">Этот процесс называется обратной записью паролей.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-107">This process is known as password writeback.</span></span> <span data-ttu-id="c8e7f-108">Благодаря обратной записи паролей пользователям не нужно обновлять свои пароли в локальных доменных службах Active Directory (AD DS), где хранятся учетные записи и их атрибуты.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="c8e7f-109">Это важно для роуминга и удаленных пользователей, у которых нет подключения к локальной сети для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="c8e7f-110">Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции защиты идентификации, например пользователям требовалось менять свои локальные пароли при высоком риске компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-110">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>

<span data-ttu-id="c8e7f-111">Дополнительные сведения и инструкции по настройке см. в статье [Практическое руководство. Настройка компонента обратной записи паролей](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="c8e7f-112">Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-112">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="c8e7f-113">Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-113">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c8e7f-115">Руководство для лаборатории тестирования: обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="c8e7f-115">Test Lab Guide: Password reset</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="c8e7f-116">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-pw-writeback).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="c8e7f-117">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="c8e7f-117">Simplify password resets</span></span>

<span data-ttu-id="c8e7f-118">*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="c8e7f-118">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c8e7f-119">В этом разделе описывается включение самостоятельного сброса паролей (SSPR), позволяющего пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="c8e7f-120">Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-120">In this step, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts. To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="c8e7f-121">Прежде чем развертывать функцию сброса паролей необходимо включить обратную запись паролей.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="c8e7f-122">См. [инструкции по развертыванию функции сброса паролей](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-122">See the [instructions to enable password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c8e7f-124">Руководство по лаборатории тестирования: сброс пароля</span><span class="sxs-lookup"><span data-stu-id="c8e7f-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="c8e7f-125">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-pw-reset).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this step.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="c8e7f-126">Упрощение входа пользователей</span><span class="sxs-lookup"><span data-stu-id="c8e7f-126">Simplify user sign-in</span></span>

<span data-ttu-id="c8e7f-127">*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c8e7f-127">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c8e7f-128">В этом разделе описывается настройка эффективного единого входа в Azure Active Directory, чтобы разрешить пользователям входить в службы, использующие учетные записи пользователей Azure AD, не вводя свои пароли и (во многих случаях) имена пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-128">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span> <span data-ttu-id="c8e7f-129">Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="c8e7f-130">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="c8e7f-131">См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c8e7f-133">Руководство по лаборатории тестирования: простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8e7f-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="c8e7f-134">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-sso).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="c8e7f-135">Настройка страницы входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="c8e7f-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="c8e7f-136">*Этот шаг не является обязательным. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c8e7f-136">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c8e7f-137">В этом разделе описывается, как помочь пользователям узнавать страницу входа в систему вашей организации, добавив на нее название и логотип компании, а также другие отличительные элементы.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-137">In this step, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="c8e7f-138">С помощью Microsoft 365 корпоративный вы можете настроить внешний вид страницы входа и страниц Панели доступа так, чтобы на них отображались логотип вашей компании, цветовые схемы и настраиваемая пользовательская информация.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="c8e7f-139">Когда пользователь пытается войти в систему с какого-либо устройства (*до настройки страницы входа*), для него отображается приблизительно такая страница входа в Office 365, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="c8e7f-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![Пример страницы входа в Office 365 до ее настройки](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="c8e7f-141">А вот что отображается для того же пользователя компании Contoso Corporation *после настройки страницы входа в систему*:</span><span class="sxs-lookup"><span data-stu-id="c8e7f-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![Пример страницы входа в Office 365 после ее настройки](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="c8e7f-143">Дополнительные сведения см. в статье [Добавление фирменной символики компании на страницу входа в Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="c8e7f-144">Инструкции по настройке см. в статье [Краткое руководство по добавлению фирменной символики организации на страницу входа в Azure Active Directory](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="c8e7f-145">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-custom-sign-in).</span><span class="sxs-lookup"><span data-stu-id="c8e7f-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="c8e7f-146">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="c8e7f-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="c8e7f-147">Упрощение управления с помощью групп</span><span class="sxs-lookup"><span data-stu-id="c8e7f-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


