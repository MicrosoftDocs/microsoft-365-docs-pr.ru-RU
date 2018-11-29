---
title: Шаг 13. Отслеживание действий в клиенте и при входе в систему
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
description: В этой статье рассказывается, как настроить функцию создания отчетов о доступе к Azure AD и использовании этой службы.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870425"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="d9523-103">Шаг 13. Отслеживание действий в клиенте и при входе в систему</span><span class="sxs-lookup"><span data-stu-id="d9523-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="d9523-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d9523-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d9523-p101">На этом шаге вы научитесь проверять журналы аудита и действия при входе в систему с помощью функции создания отчетов в Azure AD. Доступны два типа отчетов.</span><span class="sxs-lookup"><span data-stu-id="d9523-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="d9523-p102">В **отчете о действиях в журналах аудита** указаны сведения о каждой задаче, выполненной в вашем клиенте Azure AD. Этот отчет отвечает на указанные ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="d9523-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="d9523-109">Кто добавил определенного пользователя в группу администраторов?</span><span class="sxs-lookup"><span data-stu-id="d9523-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="d9523-110">Какие пользователи выполняют вход в определенном приложении?</span><span class="sxs-lookup"><span data-stu-id="d9523-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="d9523-111">Какое количество сбросов паролей выполняется?</span><span class="sxs-lookup"><span data-stu-id="d9523-111">How many password resets are happening?</span></span>

<span data-ttu-id="d9523-p103">В **отчете о действиях при входе в систему** указаны сведения о том, кто выполнял задачи, указанные в отчете журналов аудита. Этот отчет отвечает на указанные ниже вопросы.</span><span class="sxs-lookup"><span data-stu-id="d9523-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="d9523-114">Каков шаблон входа в систему для определенного пользователя?</span><span class="sxs-lookup"><span data-stu-id="d9523-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="d9523-115">Сколько входов в систему было выполнено за день, неделю или месяц?</span><span class="sxs-lookup"><span data-stu-id="d9523-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="d9523-116">Какое количество попыток входа в систему было неуспешным и для каких учетных записей?</span><span class="sxs-lookup"><span data-stu-id="d9523-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="d9523-117">Дополнительные сведения об отчетах и о том, как получить доступ к ним, см. в статье [Отчеты Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d9523-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="d9523-118">В результате выполнения этого шага вы узнаете об этих отчетах и будете понимать, как использовать их для анализа событий и действий в Azure AD с целью планирования и обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="d9523-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="d9523-119">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="d9523-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="d9523-120">Разрешение пользователям создавать собственные группы и управлять ими</span><span class="sxs-lookup"><span data-stu-id="d9523-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
