---
title: 'Шаг 7: Синхронизация удостоверений'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается о параметрах удостоверений и настройке Azure AD Connect для синхронизации локального Windows Server AD с Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870513"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="7e155-103">Шаг 7: Синхронизация удостоверений</span><span class="sxs-lookup"><span data-stu-id="7e155-103">Step 7: Synchronize identities</span></span>

<span data-ttu-id="7e155-104">*Этот шаг — обязательный для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7e155-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7e155-105">На данном шаге вы синхронизируете локальную версию Windows Server Active Directory (AD) с клиентом Azure Active Directory (AD), используемым в ваших подписках на Office 365 и Enterprise Mobility + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="7e155-105">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="7e155-106">Azure AD Connect — это поддерживаемое Корпорацией Майкрософт средство, с помощью которого вы сможете синхронизировать только те удостоверения, которые вам действительно нужны, из одного или нескольких лесов сред Windows Server AD в свой клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7e155-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="7e155-108">*Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD*</span><span class="sxs-lookup"><span data-stu-id="7e155-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="7e155-p101">Первое решение, которое необходимо принять касательно гибридного решения для работы с удостоверениями, связано с требованием проверки подлинности. Ниже перечислены возможные варианты.</span><span class="sxs-lookup"><span data-stu-id="7e155-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="7e155-p102">С помощью **управляемой проверки подлинности** Azure AD выполняет процесс проверки подлинности при входе пользователей в систему. Существует два указанных ниже метода управляемой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="7e155-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="7e155-p103">**Синхронизация хэша пароля (PHS)**. [Рекомендованный и обязательный метод для некоторых премиум-функций.] Это самый простой способ включения проверки подлинности для объектов локального каталога в Azure AD. Microsoft Azure AD Connect извлекает хэшированный пароль из Windows Server AD, выполняет дополнительную обработку пароля для повышения безопасности и сохраняет его в Microsoft Azure AD. Дополнительные сведения см. в статье [Реализация синхронизации хэшированных паролей в службе синхронизации Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span><span class="sxs-lookup"><span data-stu-id="7e155-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Windows Server AD, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="7e155-p104">**Сквозная проверка подлинности** — это простое решение для проверки подлинности паролей для служб на основе Azure AD. При сквозной проверке подлинности используется агент, работающий на одном или нескольких локальных серверах и проверяющий операции проверки подлинности пользователей непосредственно с помощью вашего локального Windows Server AD. Дополнительные сведения см. в статье [Вход пользователей с помощью сквозной проверки подлинности Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="7e155-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="7e155-p105">При использовании **федеративной проверки подлинности** процесс проверки подлинности перенаправляется другому поставщику удостоверений через сервер федерации удостоверений, например через службы федерации Active Directory (AD FS), для входа пользователя в систему. Поставщик удостоверений может использовать дополнительные методы проверки подлинности, например проверку подлинности на основе смарт-карт. Дополнительные сведения см. в статье [Выбор подходящего метода проверки подлинности для вашего гибридного решения для работы с удостоверениями Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="7e155-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="7e155-123">После того как вы определили гибридное решение для работы с удостоверениями, скачайте и запустите [средство устранения ошибок синхронизации каталогов IdFix](https://www.microsoft.com/download/details.aspx?id=36832), чтобы проанализировать Windows Server AD на наличие проблем.</span><span class="sxs-lookup"><span data-stu-id="7e155-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="7e155-p106">После устранения всех проблем, найденных средством IdFix, прочитайте статью [Реализация синхронизации хэшей паролей](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) с рекомендациями по установке средства Azure AD Connect и настройке синхронизации каталогов между вашим локальным Windows Server AD и клиентом Azure AD для ваших подписок на Office 365 и EMS. После начала синхронизации вы будете обслуживать свои учетные записи пользователей и группы с помощью своего локального поставщика удостоверений, например Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="7e155-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="7e155-126">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7e155-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="7e155-127">Данные о рекомендуемых требованиях для гибридных сред см. в колонке **Active Directory с синхронизацией хэша пароля** [предварительных требований](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="7e155-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="7e155-128">Данные о рекомендуемых требованиях для исключительно облачных сред см. в колонке **Только в облаке** [предварительных требований](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="7e155-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7e155-130">Руководство по лаборатории тестирования: синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="7e155-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="7e155-131">Руководство по лаборатории тестирования: сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="7e155-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="7e155-132">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="7e155-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7e155-133">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="7e155-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="7e155-134">Отслеживание работоспособности функции синхронизации</span><span class="sxs-lookup"><span data-stu-id="7e155-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

