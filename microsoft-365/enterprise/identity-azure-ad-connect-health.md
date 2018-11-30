---
title: Шаг 8. Отслеживание работоспособности функции синхронизации
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
description: В этой статье рассказывается, как настроить Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870861"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="dbcd1-103">Шаг 8. Отслеживание работоспособности функции синхронизации</span><span class="sxs-lookup"><span data-stu-id="dbcd1-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="dbcd1-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="dbcd1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="dbcd1-p101">На этом шаге вы установите агент Azure AD Connect Health на все свои локальные серверы удостоверений, чтобы отслеживать инфраструктуру идентификации и службы синхронизации, предоставляемые Azure AD Connect. Сведения, полученные в результате мониторинга, доступны на портале Azure AD Connect Health. Там вы можете просматривать предупреждения, результаты мониторинга производительности, аналитические данные об использовании и прочие сведения.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Компоненты Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="dbcd1-108">Ключевое решение о способе использования Azure AD Connect Health зависит от способа, которым вы используете Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="dbcd1-109">Если вы используете **управляемую проверку подлинности**, начните работу с прочтения статьи [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="dbcd1-110">Если вы синхронизируете только имена учетных записей и групп, используя **федеративную проверку подлинности** с помощью служб федерации Active Directory (AD FS), для начала прочитайте статью [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="dbcd1-111">Когда вы завершите этот этап, у вас будут указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="dbcd1-112">На каждом из ваших локальных серверов поставщиков удостоверений установлен агент Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="dbcd1-113">На портале Azure AD Connect Health отображается текущее состояние вашей локальной инфраструктуры и действий по синхронизации с клиентом Azure AD для ваших подписок Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="dbcd1-114">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync-health), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="dbcd1-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="dbcd1-115">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="dbcd1-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="dbcd1-116">Упрощение процедуры обновления паролей</span><span class="sxs-lookup"><span data-stu-id="dbcd1-116">Simplify password updates</span></span>](identity-password-writeback.md) |

