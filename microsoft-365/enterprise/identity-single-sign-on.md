---
title: Шаг 10. Упрощение входа для пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить функцию простого единого входа для Azure AD.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870982"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="0c431-103">Шаг 10. Упрощение входа для пользователей</span><span class="sxs-lookup"><span data-stu-id="0c431-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="0c431-104">*Этот шаг — необязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="0c431-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="0c431-p101">На этом шаге вы настроите функцию простого единого входа для Azure Active Directory. Благодаря этой функции ваши пользователи смогут входить в систему в службах, использующих учетные записи пользователей Azure AD, не вводя свои пароли, и, во многих случаях, свои имена пользователей. Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости использовать дополнительные локальные компоненты, например серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="0c431-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="0c431-107">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0c431-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="0c431-108">См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="0c431-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="0c431-110">Руководство по лаборатории тестирования: простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="0c431-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="0c431-111">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sso), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="0c431-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0c431-112">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="0c431-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="0c431-113">Настройка страницы входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="0c431-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

