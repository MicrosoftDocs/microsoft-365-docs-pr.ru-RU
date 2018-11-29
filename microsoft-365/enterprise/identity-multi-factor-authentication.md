---
title: Шаг 5. Настройка многофакторной проверки подлинности
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить многофакторную проверку подлинности для учетных записей пользователей.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870923"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="8f7ea-103">Шаг 5. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="8f7ea-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="8f7ea-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8f7ea-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8f7ea-p101">На этом шаге вы настроите многофакторную проверку подлинности, чтобы добавить второй уровень обеспечения безопасности при входе пользователей в систему и выполнении транзакций. При многофакторной проверке подлинности требуется использовать дополнительный метод проверки после того, как пользователь правильно ввел свой пароль. Если многофакторная проверка подлинности не используется, то пароль — единственный метод проверки. С паролями связана одна проблема: злоумышленники могут легко угадать многие пароли. Кроме того, пользователи могут непреднамеренно сообщить свои пароли ненадежным лицам и организациям.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="8f7ea-109">При многофакторной проверке подлинности можно использовать указанные ниже варианты второго уровня обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="8f7ea-110">Личное надежное устройство, которое трудно подделать, например смартфон.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="8f7ea-111">Биометрический атрибут, например отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="8f7ea-p102">Вы включите многофакторную проверку подлинности и настроите дополнительный метод проверки подлинности для каждой учетной записи. Обязательно сообщите пользователям, что включена многофакторная проверка подлинности, чтобы они понимали все требования (например, обязательное использование смартфона для входа в систему) и могли успешно входить в систему.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="8f7ea-114">Дополнительные сведения см. в статье [Планирование многофакторной проверки подлинности для развертываний Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span><span class="sxs-lookup"><span data-stu-id="8f7ea-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="8f7ea-115">Сведения о том, как настроить многофакторную проверку подлинности, см. в статье [Настройка многофакторной проверки подлинности для Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span><span class="sxs-lookup"><span data-stu-id="8f7ea-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="8f7ea-p103">Вы можете требовать использовать многофакторную проверку подлинности с помощью политик условного доступа. Например, вы можете настроить политику, которая требует использовать многофакторную проверку подлинности в случаях, когда проверка подлинности сопровождается средним или высоким риском. Дополнительные сведения см. в статье [Основные политики доступа для удостоверений и устройств](identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="8f7ea-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="8f7ea-p104">В некоторых приложениях, например в Microsoft Office 2010 и более ранних версий, а также в Apple Mail вам не удастся использовать многофакторную проверку подлинности. Чтобы использовать эти приложения, вам потребуется применять так называемые пароли приложений вместо традиционных паролей. Благодаря паролю приложений приложения могут "обходить" многофакторную проверку подлинности и продолжать работу. Дополнительные сведения о паролях приложений см. в статье [Создание пароля приложения для Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="8f7ea-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8f7ea-124">Руководства по лаборатории тестирования: многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="8f7ea-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="8f7ea-125">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-mfa), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="8f7ea-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8f7ea-126">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8f7ea-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="8f7ea-127">Защита от компрометации учетных данных</span><span class="sxs-lookup"><span data-stu-id="8f7ea-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

