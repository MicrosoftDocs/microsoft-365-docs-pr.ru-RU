---
title: Обнаружение и устранение незаконного получения согласия
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Узнайте, как распознавать и устранять незаконное согласие, предоставляя атаку в Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1c724bb3b201e0ddf1edea4794606c7083605e8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165443"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="06908-103">Обнаружение и устранение незаконного получения согласия</span><span class="sxs-lookup"><span data-stu-id="06908-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="06908-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="06908-104">**Applies to**</span></span>
- [<span data-ttu-id="06908-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="06908-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="06908-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06908-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="06908-107">**Сводка**  Узнайте, как распознавать и устранять незаконное согласие, предоставляя атаки в Office 365.</span><span class="sxs-lookup"><span data-stu-id="06908-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="06908-108">Что такое атака с предоставлением незаконного согласия в Office 365?</span><span class="sxs-lookup"><span data-stu-id="06908-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="06908-109">В случае незаконного предоставления согласия злоумышленник создает зарегистрированное в Azure приложение, которое запрашивает доступ к таким данным, как контактные данные, электронная почта или документы.</span><span class="sxs-lookup"><span data-stu-id="06908-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="06908-110">Затем злоумышленник дает конечному пользователю согласие на доступ к своим данным с помощью фишинговой атаки или путем внесения незаконного кода в доверенный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="06908-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="06908-111">После предоставления незаконного согласия приложение имеет доступ к данным на уровне учетной записи без необходимости в учетной записи организации.</span><span class="sxs-lookup"><span data-stu-id="06908-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="06908-112">Обычные действия по исправлению, такие как сброс паролей для учетных записей с нарушением безопасности или требование многофакторной проверки подлинности (MFA) для учетных записей, не являются эффективными для этого типа атак, так как это сторонние приложения, которые являются внешними по отношению к организации.</span><span class="sxs-lookup"><span data-stu-id="06908-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="06908-113">Эти атаки используют модель взаимодействия, которая предполагает, что вызываемая информация является автоматизацией, а не человеком.</span><span class="sxs-lookup"><span data-stu-id="06908-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06908-114">Вы подозреваете, что у вас возникли проблемы с незаконной предоставлением согласия из приложения?</span><span class="sxs-lookup"><span data-stu-id="06908-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="06908-115">Microsoft Cloud App Security (MCAS) имеет средства для обнаружения, изучения и устранения ваших приложений OAuth.</span><span class="sxs-lookup"><span data-stu-id="06908-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="06908-116">В этой статье MCAS имеется руководство по исследованию рискованных приложений [OAuth.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="06908-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="06908-117">Вы также можете настроить политики [приложений OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) для изучения разрешений, запрашиваемого приложением, пользователей, которые авторизют эти приложения, и широко утвердить или запретить эти запросы разрешений.</span><span class="sxs-lookup"><span data-stu-id="06908-117">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="06908-118">Как выглядит атака с предоставлением незаконного согласия в Office 365?</span><span class="sxs-lookup"><span data-stu-id="06908-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="06908-119">Вам необходимо найти в журнале **аудита** признаки этой атаки, также называемые индикаторами компрометации (IOC).</span><span class="sxs-lookup"><span data-stu-id="06908-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="06908-120">Для организаций с большим количеством зарегистрированных в Azure приложений и большой пользовательской базой лучше всего еженедельно пересматривать предоставление согласия вашей организации.</span><span class="sxs-lookup"><span data-stu-id="06908-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="06908-121">Действия по обнаружению признаков этой атаки</span><span class="sxs-lookup"><span data-stu-id="06908-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="06908-122">Откройте Центр **безопасности & соответствия требованиям по** <https://protection.office.com></span><span class="sxs-lookup"><span data-stu-id="06908-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="06908-123">Перейдите **в поиск и** выберите поиск в **журнале аудита.**</span><span class="sxs-lookup"><span data-stu-id="06908-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="06908-124">Поиск (всех действий и всех пользователей) и введите дату начала и даты окончания, если это необходимо, а затем нажмите кнопку **"Поиск".**</span><span class="sxs-lookup"><span data-stu-id="06908-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="06908-125">Нажмите **кнопку "Фильтр" и** введите "Согласие на приложение" **в поле "Действие".**</span><span class="sxs-lookup"><span data-stu-id="06908-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="06908-126">Щелкните результат, чтобы увидеть сведения о действии.</span><span class="sxs-lookup"><span data-stu-id="06908-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="06908-127">Щелкните **"Дополнительные сведения",** чтобы получить сведения о действии.</span><span class="sxs-lookup"><span data-stu-id="06908-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="06908-128">Проверьте, установлено ли для isAdminContent true.</span><span class="sxs-lookup"><span data-stu-id="06908-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="06908-129">Отображение соответствующей записи журнала аудита в результатах поиска после возникновения события может занять от 30 минут до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="06908-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="06908-130">Продолжительность сохранения записи аудита и поиска в журнале аудита зависит от подписки на Microsoft 365, а именно от типа лицензии, назначенной определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="06908-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="06908-131">Дополнительные сведения [см. в журнале аудита.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="06908-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="06908-132">Если это значение имеет значение true, это означает, что кто-то с доступом глобального администратора мог предоставить широкий доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="06908-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="06908-133">Если это непредвиденное, примите меры [для подтверждения атаки.](#how-to-confirm-an-attack)</span><span class="sxs-lookup"><span data-stu-id="06908-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="06908-134">Подтверждение атаки</span><span class="sxs-lookup"><span data-stu-id="06908-134">How to confirm an attack</span></span>

<span data-ttu-id="06908-135">Если у вас есть один или несколько указанных выше экземпляров IOC, необходимо дополнительно исследовать, чтобы положительно подтвердить, что атака произошла.</span><span class="sxs-lookup"><span data-stu-id="06908-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="06908-136">Для подтверждения атаки можно использовать любой из этих трех методов:</span><span class="sxs-lookup"><span data-stu-id="06908-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="06908-137">Инвентаризация приложений и их разрешений с помощью портала Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06908-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="06908-138">Этот метод является тщательным, но вы можете проверить только одного пользователя за раз, что может быть очень много времени, если у вас много пользователей для проверки.</span><span class="sxs-lookup"><span data-stu-id="06908-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="06908-139">Инвентаризация приложений и их разрешений с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06908-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="06908-140">Это самый быстрый и тщательный метод с наименьшим объемом накладных расходов.</span><span class="sxs-lookup"><span data-stu-id="06908-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="06908-141">Пользователи должны отдельно проверять свои приложения и разрешения и сообщать администраторам результаты для их устранения.</span><span class="sxs-lookup"><span data-stu-id="06908-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="06908-142">Инвентаризация приложений с доступом в организации</span><span class="sxs-lookup"><span data-stu-id="06908-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="06908-143">Вы можете сделать это для пользователей с помощью портала Azure Active Directory или PowerShell или по отдельности с помощью приложения.</span><span class="sxs-lookup"><span data-stu-id="06908-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="06908-144">Действия по использованию портала Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="06908-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="06908-145">Вы можете найти приложения, которым любой пользователь предоставил разрешения, с помощью портала [Azure Active Directory.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="06908-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="06908-146">Во sign in to the Azure Portal with administrative rights.</span><span class="sxs-lookup"><span data-stu-id="06908-146">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="06908-147">Выберите blade Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06908-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="06908-148">Выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="06908-148">Select **Users**.</span></span>

4. <span data-ttu-id="06908-149">Выберите пользователя, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="06908-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="06908-150">Выберите **приложения.**</span><span class="sxs-lookup"><span data-stu-id="06908-150">Select **Applications**.</span></span>

<span data-ttu-id="06908-151">В этом документе покажутся приложения, которые назначены пользователю, и разрешения, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="06908-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="06908-152">Действия по предоставлению пользователям доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="06908-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="06908-153">Пользователи должны перейти к ним https://myapps.microsoft.com и просмотреть собственный доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="06908-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="06908-154">Они должны иметь возможность просматривать все приложения с доступом, просматривать сведения о них (включая область доступа) и отоскить привилегии подозрительным или запрещенным приложениям.</span><span class="sxs-lookup"><span data-stu-id="06908-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="06908-155">Действия для этого с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="06908-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="06908-156">Самый простой способ проверить, что атака с предоставлением незаконного согласия — это запустить [Get-AzureADPSPermissions.ps1, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)в результате чего все разрешения OAuth и приложения OAuth для всех пользователей в вашем аренде будут сброшены в один CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="06908-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="06908-157">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="06908-157">Pre-requisites</span></span>

- <span data-ttu-id="06908-158">Установлена библиотека Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06908-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="06908-159">Права глобального администратора в клиенте, в отношении который будет запускаться сценарий.</span><span class="sxs-lookup"><span data-stu-id="06908-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="06908-160">Локальный администратор на компьютере, с которого будут запускаться сценарии.</span><span class="sxs-lookup"><span data-stu-id="06908-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06908-161">Настоятельно ***рекомендуется использовать*** многофакторную проверку подлинности для учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="06908-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="06908-162">Этот сценарий поддерживает проверку подлинности MFA.</span><span class="sxs-lookup"><span data-stu-id="06908-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="06908-163">Во sign in to the computer that you will run the script from with with local administrator rights.</span><span class="sxs-lookup"><span data-stu-id="06908-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="06908-164">Скачайте или [ скопируйтеGet-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) из GitHub в папку, из которой будет запускаться сценарий.</span><span class="sxs-lookup"><span data-stu-id="06908-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="06908-165">Это будет та же папка, в которую будет записан выходной permissions.csv".</span><span class="sxs-lookup"><span data-stu-id="06908-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="06908-166">Откройте экземпляр PowerShell от учетной записи администратора и откройте папку, в которая сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="06908-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="06908-167">Подключись к каталогу с помощью [cmdlet Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="06908-167">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="06908-168">Запустите эту команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="06908-168">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="06908-169">Сценарий создает один файл с именем Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="06908-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="06908-170">Выполните следующие действия, чтобы найти незаконное предоставление разрешений для приложений:</span><span class="sxs-lookup"><span data-stu-id="06908-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="06908-171">В столбце ConsentType (столбец G) на поиск значения "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="06908-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="06908-172">Разрешение AllPrincipals позволяет клиентского приложения для доступа к контенту всех в клиенте.</span><span class="sxs-lookup"><span data-stu-id="06908-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="06908-173">Для правильной работы приложений Microsoft 365 необходимо это разрешение.</span><span class="sxs-lookup"><span data-stu-id="06908-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="06908-174">Каждое приложение от корпорации Майкрософт с этим разрешением должно быть тщательно проанализировано.</span><span class="sxs-lookup"><span data-stu-id="06908-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="06908-175">В столбце "Разрешение" (столбец F) просмотрите разрешения, которые каждое делегированное приложение имеет для контента.</span><span class="sxs-lookup"><span data-stu-id="06908-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="06908-176">Найми разрешения "Чтение" и "Записать" или "\*". Разрешение "Все" и внимательно просмотрите их, так как они могут быть не подходящими.</span><span class="sxs-lookup"><span data-stu-id="06908-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="06908-177">Просмотрите конкретных пользователей, которые получили согласие.</span><span class="sxs-lookup"><span data-stu-id="06908-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="06908-178">Если пользователям с высоким уровнем профиля или пользователям с высоким уровнем воздействия предоставлены недопустимые разрешения, следует провести дальнейшее исследование.</span><span class="sxs-lookup"><span data-stu-id="06908-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="06908-179">В столбце ClientDisplayName (столбец C) найди приложения, которые кажутся подозрительными.</span><span class="sxs-lookup"><span data-stu-id="06908-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="06908-180">Приложения с опечатными именами, суперпустые имена или имена, звучающие от хакеров, следует тщательно проанализировать.</span><span class="sxs-lookup"><span data-stu-id="06908-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="06908-181">Определение области атаки</span><span class="sxs-lookup"><span data-stu-id="06908-181">Determine the scope of the attack</span></span>

<span data-ttu-id="06908-182">После завершения инвентаризации доступа к приложениям просмотрите журнал аудита, чтобы определить полную область нарушения. </span><span class="sxs-lookup"><span data-stu-id="06908-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="06908-183">Поиск затронутых пользователей, время, в которое у незаконного приложения был доступ к вашей организации, и разрешения, которые у приложения есть.</span><span class="sxs-lookup"><span data-stu-id="06908-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="06908-184">Поиск по **журналу аудита** можно найти в Центре безопасности и [соответствия требованиям Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="06908-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06908-185">[Чтобы получить](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) эти [](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) сведения, необходимо включить аудит и аудит действий почтовых ящиков для администраторов и пользователей до атаки.</span><span class="sxs-lookup"><span data-stu-id="06908-185">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="06908-186">Как остановить и исправление атаки с предоставлением незаконного согласия</span><span class="sxs-lookup"><span data-stu-id="06908-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="06908-187">После того как вы определили приложение с незаконными разрешениями, у вас есть несколько способов удалить этот доступ.</span><span class="sxs-lookup"><span data-stu-id="06908-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="06908-188">Вы можете отопросить разрешение приложения на портале Azure Active Directory с помощью:</span><span class="sxs-lookup"><span data-stu-id="06908-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="06908-189">Перейдите к затронутого пользователя в blade **пользователя Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="06908-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="06908-190">Выберите **приложения.**</span><span class="sxs-lookup"><span data-stu-id="06908-190">Select **Applications**.</span></span>

  - <span data-ttu-id="06908-191">Выберите незаконное приложение.</span><span class="sxs-lookup"><span data-stu-id="06908-191">Select the illicit application.</span></span>

  - <span data-ttu-id="06908-192">Click **Remove** in the drill down.</span><span class="sxs-lookup"><span data-stu-id="06908-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="06908-193">Вы можете отоскить предоставление согласия OAuth с помощью PowerShell, вы следуя шагам в [remove-AzureADOAuth2PermissionGrant.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)</span><span class="sxs-lookup"><span data-stu-id="06908-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="06908-194">Вы можете отоскить назначение роли приложения-службы с помощью PowerShell, выполв действия в [remove-AzureADServiceAppRoleAssignment.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)</span><span class="sxs-lookup"><span data-stu-id="06908-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="06908-195">Вы также можете отключить вход для затронутой учетной записи, что, в свою очередь, отключит доступ приложения к данным в этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="06908-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="06908-196">Конечно, это не идеальное решение для повышения производительности конечного пользователя, но если вы работаете над быстрой работой по ограничению влияния, это может быть допустимым краткосрочным исправлением.</span><span class="sxs-lookup"><span data-stu-id="06908-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="06908-197">Вы можете отключить интегрированные приложения для своего аренды.</span><span class="sxs-lookup"><span data-stu-id="06908-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="06908-198">Это очень важный шаг, который отключает возможность предоставления пользователями согласия на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="06908-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="06908-199">Это предотвращает непреднамеренное предоставление пользователям доступа к вредоносному приложению.</span><span class="sxs-lookup"><span data-stu-id="06908-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="06908-200">Это не рекомендуется, так как это серьезно снижает производительность работы пользователей со сторонними приложениями.</span><span class="sxs-lookup"><span data-stu-id="06908-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="06908-201">Это можно сделать, выверив или выключив интегрированные [приложения.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)</span><span class="sxs-lookup"><span data-stu-id="06908-201">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="06908-202">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="06908-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="06908-203">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="06908-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="06908-204">Используйте статью к [Стратегия развития безопасности Microsoft 365: приоритеты на первые 30 дней, 90 дней и далее](security-roadmap.md), чтобы применить лучшие методики, рекомендованные корпорацией Майкрософт, для защиты вашего клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06908-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="06908-205">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="06908-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="06908-206">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="06908-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="06908-207">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="06908-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="06908-208">Эти задачи требуют немного больше времени на планирование и реализацию, но значительно укрепляют вашу безопасность.</span><span class="sxs-lookup"><span data-stu-id="06908-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="06908-209">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="06908-209">Beyond 90 days.</span></span> <span data-ttu-id="06908-210">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="06908-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="06908-211">См. также:</span><span class="sxs-lookup"><span data-stu-id="06908-211">See also:</span></span>

- <span data-ttu-id="06908-212">[Непредвиденное](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) приложение в списке моих приложений проходит администраторам по различным действиям, которые могут потребоваться им после того, как они понимают, что существуют непредвиденные приложения с доступом к данным.</span><span class="sxs-lookup"><span data-stu-id="06908-212">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="06908-213">[Интеграция приложений с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) — это высокоуровневый обзор согласия и разрешений.</span><span class="sxs-lookup"><span data-stu-id="06908-213">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="06908-214">[Проблемы, связанные с разработкой приложения,](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) предоставляют ссылки на различные статьи, связанные с согласием.</span><span class="sxs-lookup"><span data-stu-id="06908-214">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="06908-215">Объекты приложений и основных служб [в Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) предоставляют обзор основных объектов приложений и служб, которые являются основными для модели приложений.</span><span class="sxs-lookup"><span data-stu-id="06908-215">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="06908-216">[Управление доступом к приложениям](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) — это обзор возможностей, которые администраторы должны использовать для управления доступом пользователей к приложениям.</span><span class="sxs-lookup"><span data-stu-id="06908-216">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
