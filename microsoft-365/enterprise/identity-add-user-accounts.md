---
title: Шаг 4. Добавление учетных записей пользователей
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
description: Добавляйте учетные записи пользователей и группы непосредственно в облаке или с помощью синхронизации с локальным каталогом.
ms.openlocfilehash: ce831a6866f61342f6eb93836d44637742007c03
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090816"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="83591-103">Шаг 4. Добавление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="83591-103">Step 4: Add your user accounts</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="83591-104">Создание учетных записей пользователей, если используется только облачная идентификация</span><span class="sxs-lookup"><span data-stu-id="83591-104">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="83591-105">Если используется только облачная идентификация, создавайте пользователей и группы в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="83591-105">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="83591-106">Вы можете использовать:</span><span class="sxs-lookup"><span data-stu-id="83591-106">You can use:</span></span>

- <span data-ttu-id="83591-107">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83591-107">Microsoft Office 365 admin center</span></span>
- <span data-ttu-id="83591-108">Портал Azure</span><span class="sxs-lookup"><span data-stu-id="83591-108">The Azure portal</span></span>
- <span data-ttu-id="83591-109">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="83591-109">Azure Powershell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="83591-110">Синхронизация удостоверений для гибридного удостоверения</span><span class="sxs-lookup"><span data-stu-id="83591-110">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="83591-111">*Это обязательный этап для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="83591-111">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="83591-112">В этом разделе синхронизируются локальные доменные службы Active Directory (AD DS) с клиентом Azure AD, используемым в Office 365, Microsoft Intune и других облачных службах, входящих в состав Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="83591-112">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="83591-113">Azure AD Connect — это поддерживаемое корпорацией Майкрософт средство, с помощью которого вы сможете синхронизировать только те удостоверения, которые вам действительно нужны, из сред AD DS с одним или несколькими лесами в свой клиент Azure AD.</span><span class="sxs-lookup"><span data-stu-id="83591-113">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="83591-114">На рисунке ниже показан базовый процесс для синхронизации Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="83591-114">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD](./media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="83591-116">Средство Azure AD Connect, запущенное на сервере, опрашивает службы AD DS на наличие изменений в учетных записях, группах и контактах.</span><span class="sxs-lookup"><span data-stu-id="83591-116">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="83591-117">Azure AD Connect отправляет эти изменения в клиент Azure AD вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83591-117">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="83591-p103">Первое решение, которое необходимо принять касательно гибридного решения для работы с удостоверениями, связано с требованием проверки подлинности. Ниже перечислены возможные варианты.</span><span class="sxs-lookup"><span data-stu-id="83591-p103">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="83591-p104">С помощью **управляемой проверки подлинности** Azure AD выполняет процесс проверки подлинности при входе пользователей в систему. Существует два указанных ниже метода управляемой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="83591-p104">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="83591-122">**Синхронизация хэша паролей (PHS)**. [Рекомендованный и обязательный метод для некоторых премиум-функций.]</span><span class="sxs-lookup"><span data-stu-id="83591-122">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="83591-123">Это самый простой способ включения проверки подлинности для объектов локального каталога в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="83591-123">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="83591-124">Azure AD Connect извлекает хэшированный пароль из AD DS, выполняет дополнительную обработку пароля для хэширования пароля и синхронизирует его с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="83591-124">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="83591-125">Дополнительные сведения см. в статье о [реализации синхронизации хэша паролей с помощью службы синхронизации Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="83591-125">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="83591-126">**Сквозная проверка подлинности** — это простое решение для проверки подлинности паролей для служб на основе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="83591-126">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="83591-127">При сквозной проверке подлинности используется агент, работающий на одном или нескольких локальных серверах и проверяющий операции проверки подлинности пользователей непосредственно с помощью локальных служб AD DS.</span><span class="sxs-lookup"><span data-stu-id="83591-127">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="83591-128">Дополнительные сведения см. в статье [Вход пользователей с помощью сквозной проверки подлинности Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="83591-128">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="83591-p107">При использовании **федеративной проверки подлинности** процесс проверки подлинности перенаправляется другому поставщику удостоверений через сервер федерации удостоверений, например через службы федерации Active Directory (AD FS), для входа пользователя в систему. Поставщик удостоверений может использовать дополнительные методы проверки подлинности, например проверку подлинности на основе смарт-карт. Дополнительные сведения см. в статье [Выбор подходящего метода проверки подлинности для вашего гибридного решения для работы с удостоверениями Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="83591-p107">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="83591-132">Просмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="83591-132">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="83591-133"><p> </p></span><span class="sxs-lookup"><span data-stu-id="83591-133"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="83591-134">После того как вы определили гибридное решение для работы с удостоверениями, скачайте и запустите [средство устранения ошибок синхронизации каталогов IdFix](https://www.microsoft.com/download/details.aspx?id=36832), чтобы проанализировать AD DS на наличие проблем.</span><span class="sxs-lookup"><span data-stu-id="83591-134">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="83591-135">После устранения всех проблем, найденных средством IdFix, прочитайте статью [Реализация синхронизации хэшей паролей](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) с рекомендациями по установке средства Azure AD Connect и настройке синхронизации каталогов между локальными службами AD DS и клиентом Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83591-135">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span> <span data-ttu-id="83591-136">После начала синхронизации вы будете обслуживать свои учетные записи пользователей и группы с помощью своего локального поставщика удостоверений, например AD DS.</span><span class="sxs-lookup"><span data-stu-id="83591-136">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="83591-137">Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="83591-137">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="83591-138">Данные о рекомендуемых требованиях для гибридных сред см. в колонке **Active Directory с синхронизацией хэша пароля** [предварительных требований](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="83591-138">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="83591-139">Данные о рекомендуемых требованиях для исключительно облачных сред см. в колонке **Только в облаке** [предварительных требований](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="83591-139">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="83591-140">После появления локальных пользователей и групп в Azure AD вы можете приступить к назначению лицензий и использованию рабочих нагрузок, например OneDrive для бизнеса и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="83591-140">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="83591-142">Руководство по лаборатории тестирования: синхронизация хэшей паролей</span><span class="sxs-lookup"><span data-stu-id="83591-142">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="83591-143">Руководство по лаборатории тестирования: сквозная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="83591-143">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="83591-144">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync), при выполнении которых можно считать данный раздел завершенным.</span><span class="sxs-lookup"><span data-stu-id="83591-144">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="83591-145">Отслеживание работоспособности функции синхронизации</span><span class="sxs-lookup"><span data-stu-id="83591-145">Monitor synchronization health</span></span>

<span data-ttu-id="83591-146">*Это необязательная процедура, применимая к версиям Microsoft 365 Enterprise E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="83591-146">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="83591-147">В этом разделе вы установите агент Azure AD Connect Health на все свои локальные контроллеры доменов AD DS, чтобы отслеживать инфраструктуру идентификации и службы синхронизации, предоставляемые Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="83591-147">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="83591-148">Сведения, полученные в результате отслеживания, доступны на портале Azure AD Connect Health. Там вы можете просматривать оповещения, результаты отслеживания производительности, аналитические данные об использовании и прочие сведения.</span><span class="sxs-lookup"><span data-stu-id="83591-148">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Компоненты Azure AD Connect Health](./media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="83591-150">Ключевое решение о способе использования Azure AD Connect Health зависит от способа, которым вы используете Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="83591-150">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="83591-151">Если вы используете **управляемую проверку подлинности**, начните работу с прочтения статьи [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="83591-151">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="83591-152">Если вы синхронизируете только имена учетных записей и групп, используя **федеративную проверку подлинности** с помощью служб федерации Active Directory (AD FS), для начала прочитайте статью [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), чтобы понять и настроить Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="83591-152">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="83591-153">Когда вы завершите этот раздел, у вас будут указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="83591-153">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="83591-154">На каждом из ваших локальных серверов поставщиков удостоверений установлен агент Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="83591-154">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="83591-155">На портале Azure AD Connect Health отображается текущее состояние вашей локальной инфраструктуры и действий по синхронизации с клиентом Azure AD для вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83591-155">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="83591-156">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-sync-health).</span><span class="sxs-lookup"><span data-stu-id="83591-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="83591-157">Упрощение процедуры обновления паролей</span><span class="sxs-lookup"><span data-stu-id="83591-157">Simplify password updates</span></span>

<span data-ttu-id="83591-158">*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="83591-158">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="83591-159">В этом разделе описывается, как разрешить пользователям сбрасывать свои пароли в Azure Active Directory (Azure AD), которые затем реплицируются в локальные доменные службы Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="83591-159">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="83591-160">Этот процесс называется обратной записью паролей.</span><span class="sxs-lookup"><span data-stu-id="83591-160">This process is known as password writeback.</span></span> <span data-ttu-id="83591-161">Благодаря обратной записи паролей пользователям не нужно обновлять свои пароли в локальных доменных службах AD DS, где хранятся учетные записи и их атрибуты.</span><span class="sxs-lookup"><span data-stu-id="83591-161">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="83591-162">Это важно для роуминга и удаленных пользователей, у которых нет подключения к локальной сети для удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="83591-162">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="83591-163">Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="83591-163">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="83591-164">Дополнительные сведения и инструкции по настройке см. в статье [Практическое руководство. Настройка компонента обратной записи паролей](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="83591-164">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="83591-165">Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска.</span><span class="sxs-lookup"><span data-stu-id="83591-165">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="83591-166">Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="83591-166">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="83591-168">Руководство для лаборатории тестирования: обратная запись пароля</span><span class="sxs-lookup"><span data-stu-id="83591-168">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="83591-169">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-pw-writeback).</span><span class="sxs-lookup"><span data-stu-id="83591-169">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="83591-170">Управление с помощью групп</span><span class="sxs-lookup"><span data-stu-id="83591-170">Use groups for easier management</span></span>](identity-use-group-management.md) |
