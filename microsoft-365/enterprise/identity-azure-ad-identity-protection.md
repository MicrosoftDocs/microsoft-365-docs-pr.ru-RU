---
title: Шаг 6. Защита от компрометации учетных данных
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
description: В этом разделе рассказывается, как настроить защиту идентификации Azure AD.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871083"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="3f51a-103">Шаг 6. Защита от компрометации учетных данных</span><span class="sxs-lookup"><span data-stu-id="3f51a-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="3f51a-104">*Этот шаг — необязательный; он применяется только к плану E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="3f51a-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="3f51a-p101">На этом шаге вы научитесь настраивать политики, защищающие от компрометации учетных данных, для случаев, когда злоумышленник определяет имя и пароль учетной записи пользователя, чтобы получить доступ к облачным службам и данным организации. В системе защиты идентификации Azure AD имеются несколько способов помешать злоумышленнику получить доступ к вашим учетным записям и группам и, соответственно, к самым ценным данным.</span><span class="sxs-lookup"><span data-stu-id="3f51a-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="3f51a-107">С помощью системы защиты идентификации Azure AD вы можете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3f51a-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="3f51a-108">Определять и устранять потенциальные уязвимости в удостоверениях вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3f51a-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="3f51a-p102">В Azure AD используется система машинного обучения, позволяющая обнаруживать аномалии и подозрительные действия, например ряд действий при входе в систему и после него. Используя эти данные, Identity Protection создает отчеты и предупреждения, с помощью которых можно оценить возникшие проблемы и предпринять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="3f51a-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="3f51a-111">Определять подозрительные действия, связанные с удостоверениями вашей организации, и автоматически реагировать на них.</span><span class="sxs-lookup"><span data-stu-id="3f51a-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="3f51a-p103">Вы можете настроить политики на основе риска, автоматически реагирующие на обнаруженные проблемы при достижении указанного уровня риска. Эти политики (в дополнение к другим средствам управления условным доступом, предоставляемым Azure Active Directory и Enterprise Mobility + Security [EMS]), могут либо автоматически блокировать доступ, либо предпринимать необходимые действия, включая сбросы паролей и требование многофакторной проверки подлинности при последующих входах в систему.</span><span class="sxs-lookup"><span data-stu-id="3f51a-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="3f51a-114">Исследовать подозрительные инциденты и разрешать их с помощью административных действий.</span><span class="sxs-lookup"><span data-stu-id="3f51a-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="3f51a-p104">Вы можете исследовать события, сопряженные с риском, используя информацию об инцидентах безопасности. Вам доступны базовые рабочие процессы, предназначенные для отслеживания расследований и инициирования необходимых действий, например сбросов паролей.</span><span class="sxs-lookup"><span data-stu-id="3f51a-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="3f51a-117">См. [дополнительные сведения о защите идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="3f51a-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="3f51a-118">См. описание [действий по включению защиты идентификации Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="3f51a-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="3f51a-119">В результате выполнения данного шага у вас будет включена защита идентификации Azure AD, и вы будете использовать ее для выполнения указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3f51a-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="3f51a-120">Устранение потенциальных уязвимостей, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="3f51a-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="3f51a-121">Обнаружение попыток компрометации учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3f51a-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="3f51a-122">Изучение и разрешение текущих подозрительных инцидентов, связанных с идентификацией.</span><span class="sxs-lookup"><span data-stu-id="3f51a-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="3f51a-124">Руководства по лаборатории тестирования: защита идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f51a-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="3f51a-125">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-ident-prot), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="3f51a-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="3f51a-126">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3f51a-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="3f51a-127">Синхронизация каталогов</span><span class="sxs-lookup"><span data-stu-id="3f51a-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


