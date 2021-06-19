---
title: Обнаружение и исправление незаконных грантов на согласие
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
description: Узнайте, как распознавать и устранять атаку незаконных грантов согласия в Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c3c3c06974feb2dab3985a60938fe7d543543c3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028923"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="0723d-103">Обнаружение и исправление незаконных грантов на согласие</span><span class="sxs-lookup"><span data-stu-id="0723d-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0723d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="0723d-104">**Applies to**</span></span>
- [<span data-ttu-id="0723d-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="0723d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0723d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0723d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0723d-107">**Сводка**  Узнайте, как распознавать и устранять атаку незаконных грантов согласия в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0723d-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="0723d-108">Что такое атака незаконного предоставления согласия в Office 365?</span><span class="sxs-lookup"><span data-stu-id="0723d-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="0723d-109">В случае незаконной атаки на предоставление согласия злоумышленник создает приложение, зарегистрированное в Azure, которое запрашивает доступ к таким данным, как контактные данные, электронная почта или документы.</span><span class="sxs-lookup"><span data-stu-id="0723d-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="0723d-110">Затем злоумышленник угостит конечного пользователя предоставлением этому приложению согласия на доступ к своим данным либо с помощью фишинговой атаки, либо путем внесения незаконного кода в надежный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="0723d-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="0723d-111">После того как незаконному приложению было предоставлено согласие, он имеет доступ к данным на уровне учетной записи без необходимости организации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0723d-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="0723d-112">Обычные действия по исправлению, такие как сброс паролей для взлома учетных записей или требование многофакторной проверки подлинности (MFA) на учетных записях, не эффективны для этого типа атаки, так как это сторонние приложения и внешние для организации.</span><span class="sxs-lookup"><span data-stu-id="0723d-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="0723d-113">Эти атаки используют модель взаимодействия, которая предполагает, что вызываемая информация является автоматизацией, а не человеком.</span><span class="sxs-lookup"><span data-stu-id="0723d-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0723d-114">Вы подозреваете, что у вас возникли проблемы с незаконными грантами на согласие из приложения, прямо сейчас?</span><span class="sxs-lookup"><span data-stu-id="0723d-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="0723d-115">Microsoft Cloud App Security (MCAS) имеет средства обнаружения, расследования и исправлений приложений OAuth.</span><span class="sxs-lookup"><span data-stu-id="0723d-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="0723d-116">В этой статье MCAS описаны инструкции по расследованию рискованных приложений [OAuth.](/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="0723d-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="0723d-117">Вы также можете установить политики приложений [OAuth](/cloud-app-security/app-permission-policy) для изучения разрешений, запрашиваемого приложениями, которые пользователи разрешают эти приложения, и широко утверждать или запрещать эти запросы разрешений.</span><span class="sxs-lookup"><span data-stu-id="0723d-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="0723d-118">Как выглядит атака незаконного предоставления согласия в Office 365?</span><span class="sxs-lookup"><span data-stu-id="0723d-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="0723d-119">Чтобы найти признаки  этой атаки, также называемые Индикаторы компромисса (МОК), необходимо искать журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="0723d-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="0723d-120">Для организаций с большим количеством зарегистрированных в Azure приложений и большой пользовательской базой, лучше всего еженедельно пересматривать гранты на согласие организаций.</span><span class="sxs-lookup"><span data-stu-id="0723d-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="0723d-121">Действия по обнаружению признаков этой атаки</span><span class="sxs-lookup"><span data-stu-id="0723d-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="0723d-122">Откройте портал **Microsoft 365 Defender** по <https://security.microsoft.com> ссылке .</span><span class="sxs-lookup"><span data-stu-id="0723d-122">Open the **Microsoft 365 Defender** portal at <https://security.microsoft.com>.</span></span>

2. <span data-ttu-id="0723d-123">Перейдите к **поиску** и выберите **поиск журнала аудита.**</span><span class="sxs-lookup"><span data-stu-id="0723d-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="0723d-124">Поиск (все действия и все пользователи) и введите дату начала и даты окончания, если требуется, а затем нажмите **кнопку Поиск**.</span><span class="sxs-lookup"><span data-stu-id="0723d-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="0723d-125">Нажмите **кнопку Фильтр результатов** и введите согласие на применение в **поле Действия.**</span><span class="sxs-lookup"><span data-stu-id="0723d-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="0723d-126">Нажмите на результат, чтобы узнать подробности действия.</span><span class="sxs-lookup"><span data-stu-id="0723d-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="0723d-127">Щелкните **дополнительные сведения,** чтобы получить сведения о действии.</span><span class="sxs-lookup"><span data-stu-id="0723d-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="0723d-128">Проверьте, задает ли IsAdminContent true.</span><span class="sxs-lookup"><span data-stu-id="0723d-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="0723d-129">Для отображения соответствующей записи журнала аудита в результатах поиска после события может занять от 30 минут до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="0723d-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="0723d-130">Продолжительность сохранения записи аудита и поиска в журнале аудита зависит от Microsoft 365 подписки и, в частности, от типа лицензии, назначенной конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="0723d-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="0723d-131">Дополнительные сведения см. в [журнале Аудит.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="0723d-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="0723d-132">Если это значение верно, это указывает на то, что кто-то с глобальным доступом администратора мог предоставить широкий доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="0723d-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="0723d-133">Если это непредвиденное, примите меры [для подтверждения атаки.](#how-to-confirm-an-attack)</span><span class="sxs-lookup"><span data-stu-id="0723d-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="0723d-134">Подтверждение атаки</span><span class="sxs-lookup"><span data-stu-id="0723d-134">How to confirm an attack</span></span>

<span data-ttu-id="0723d-135">Если выше указан один или несколько экземпляров IOCs, необходимо дополнительно исследовать, чтобы положительно подтвердить, что атака произошла.</span><span class="sxs-lookup"><span data-stu-id="0723d-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="0723d-136">Для подтверждения атаки можно использовать любой из этих трех методов:</span><span class="sxs-lookup"><span data-stu-id="0723d-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="0723d-137">Приложения инвентаризации и их разрешения с помощью Azure Active Directory портала.</span><span class="sxs-lookup"><span data-stu-id="0723d-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="0723d-138">Этот метод является тщательным, но вы можете проверить только одного пользователя в то время, которое может быть очень много времени, если у вас есть много пользователей, чтобы проверить.</span><span class="sxs-lookup"><span data-stu-id="0723d-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="0723d-139">Приложения инвентаризации и их разрешения с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0723d-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="0723d-140">Это самый быстрый и тщательный метод с наименьшим количеством накладных расходов.</span><span class="sxs-lookup"><span data-stu-id="0723d-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="0723d-141">Убедитесь, что пользователи лично проверяют свои приложения и разрешения и сообщают о полученных результатах администраторам для устранения последствий.</span><span class="sxs-lookup"><span data-stu-id="0723d-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="0723d-142">Инвентаризация приложений с доступом в организации</span><span class="sxs-lookup"><span data-stu-id="0723d-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="0723d-143">Вы можете сделать это для пользователей с помощью портала Azure Active Directory или PowerShell или у вас есть индивидуальный доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="0723d-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="0723d-144">Действия для использования Azure Active Directory Portal</span><span class="sxs-lookup"><span data-stu-id="0723d-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="0723d-145">Вы можете искать приложения, которым каждый пользователь предоставил разрешения с помощью [портала Azure Active Directory.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="0723d-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="0723d-146">Вход на портал Azure с административными правами.</span><span class="sxs-lookup"><span data-stu-id="0723d-146">Sign in to the Azure portal with administrative rights.</span></span>

2. <span data-ttu-id="0723d-147">Выберите Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0723d-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="0723d-148">Выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0723d-148">Select **Users**.</span></span>

4. <span data-ttu-id="0723d-149">Выберите пользователя, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="0723d-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="0723d-150">Выбор **приложений**.</span><span class="sxs-lookup"><span data-stu-id="0723d-150">Select **Applications**.</span></span>

<span data-ttu-id="0723d-151">В этом документе покажут приложения, которые назначены пользователю, и какие разрешения имеют приложения.</span><span class="sxs-lookup"><span data-stu-id="0723d-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="0723d-152">Действия, необходимые для того, чтобы пользователи переумеяли доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="0723d-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="0723d-153">Чтобы пользователи перейти https://myapps.microsoft.com к ним и просмотреть собственный доступ к приложению.</span><span class="sxs-lookup"><span data-stu-id="0723d-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="0723d-154">Они должны иметь возможность просматривать все приложения с доступом, просматривать сведения о них (в том числе область доступа) и отоискить привилегии для подозрительных или незаконных приложений.</span><span class="sxs-lookup"><span data-stu-id="0723d-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="0723d-155">Действия для этого с Помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0723d-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="0723d-156">Самый простой способ проверки атаки незаконного гранта на согласие — выполнить [Get-AzureADPSPermissions.ps1, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)которая сбросит все гранты на согласие OAuth и приложения OAuth для всех пользователей в вашем аренде в один .csv файл.</span><span class="sxs-lookup"><span data-stu-id="0723d-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="0723d-157">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="0723d-157">Pre-requisites</span></span>

- <span data-ttu-id="0723d-158">Установлена библиотека PowerShell Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0723d-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="0723d-159">Права глобального администратора на клиента, с чем будет работать сценарий.</span><span class="sxs-lookup"><span data-stu-id="0723d-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="0723d-160">Локальный администратор на компьютере, с которого будут запускаться сценарии.</span><span class="sxs-lookup"><span data-stu-id="0723d-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0723d-161">Настоятельно ***рекомендуется требовать*** многофакторной проверки подлинности в административной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0723d-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="0723d-162">Этот скрипт поддерживает проверку подлинности MFA.</span><span class="sxs-lookup"><span data-stu-id="0723d-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="0723d-163">Во входе на компьютер, на который будет запускаться сценарий с правами местного администратора.</span><span class="sxs-lookup"><span data-stu-id="0723d-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="0723d-164">Скачайте или [скопируйтеGet-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) из GitHub в папку, из которой будет запускаться сценарий.</span><span class="sxs-lookup"><span data-stu-id="0723d-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="0723d-165">Это будет та же папка, в которую будет permissions.csv".</span><span class="sxs-lookup"><span data-stu-id="0723d-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="0723d-166">Откройте экземпляр PowerShell в качестве администратора и откройте папку, в которая сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="0723d-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="0723d-167">Подключение каталога с помощью [Подключение AzureAD.](/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="0723d-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="0723d-168">Запустите эту команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0723d-168">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="0723d-169">Скрипт создает один файл с именем Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="0723d-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="0723d-170">Выполните следующие действия, чтобы найти незаконные гранты разрешений на приложения:</span><span class="sxs-lookup"><span data-stu-id="0723d-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="0723d-171">В столбце ConsentType (столбец G) поиск значения "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="0723d-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="0723d-172">Разрешение AllPrincipals позволяет клиентской приложению получать доступ к содержимому каждого в аренде.</span><span class="sxs-lookup"><span data-stu-id="0723d-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="0723d-173">Для Microsoft 365 приложениям необходимо это разрешение для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="0723d-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="0723d-174">Каждое приложение, не в microsoft с таким разрешением, должно быть тщательно рассмотрено.</span><span class="sxs-lookup"><span data-stu-id="0723d-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="0723d-175">В столбце Разрешения (столбец F) просмотрите разрешения, которые каждое делегированное приложение должно содержимым.</span><span class="sxs-lookup"><span data-stu-id="0723d-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="0723d-176">Обратите внимание на разрешения "Чтение" и "Написать" или "\*. Все" разрешения и внимательно просмотрите их, так как они могут быть не подходящими.</span><span class="sxs-lookup"><span data-stu-id="0723d-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="0723d-177">Просмотрите конкретные пользователи, у них есть предоставленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="0723d-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="0723d-178">Если у пользователей с высоким профилем или с высоким влиянием имеются недопустимые разрешения, следует изучить далее.</span><span class="sxs-lookup"><span data-stu-id="0723d-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="0723d-179">В столбце ClientDisplayName (столбец C) искать приложения, которые кажутся подозрительными.</span><span class="sxs-lookup"><span data-stu-id="0723d-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="0723d-180">Приложения с именами с ошибками, именами с ошибками или именами, звучаными хакерами, должны быть тщательно рассмотрены.</span><span class="sxs-lookup"><span data-stu-id="0723d-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="0723d-181">Определение области атаки</span><span class="sxs-lookup"><span data-stu-id="0723d-181">Determine the scope of the attack</span></span>

<span data-ttu-id="0723d-182">После завершения доступа к приложениям для  инвентаризации просмотрите журнал аудита, чтобы определить полный объем нарушения.</span><span class="sxs-lookup"><span data-stu-id="0723d-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="0723d-183">Поиск пострадавших пользователей, сроки доступа незаконного приложения к организации и разрешения, которые у приложения были.</span><span class="sxs-lookup"><span data-stu-id="0723d-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="0723d-184">Вы можете искать **журнал аудита** в [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="0723d-184">You can search the **audit log** in the [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0723d-185">[Аудит почтовых ящиков](../../compliance/enable-mailbox-auditing.md) и аудит действий для администраторов и пользователей должны быть включены до атаки, чтобы вы могли получить эту информацию. [](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="0723d-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="0723d-186">Как остановить и поправить атаку незаконного предоставления согласия</span><span class="sxs-lookup"><span data-stu-id="0723d-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="0723d-187">После того как вы определили приложение с незаконными разрешениями, у вас есть несколько способов удалить этот доступ.</span><span class="sxs-lookup"><span data-stu-id="0723d-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="0723d-188">Вы можете отопросить разрешение приложения на портале Azure Active Directory по:</span><span class="sxs-lookup"><span data-stu-id="0723d-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="0723d-189">Перейдите к пострадавшему пользователю в **лезвии Azure Active Directory пользователя.**</span><span class="sxs-lookup"><span data-stu-id="0723d-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="0723d-190">Выбор **приложений**.</span><span class="sxs-lookup"><span data-stu-id="0723d-190">Select **Applications**.</span></span>

  - <span data-ttu-id="0723d-191">Выберите незаконное приложение.</span><span class="sxs-lookup"><span data-stu-id="0723d-191">Select the illicit application.</span></span>

  - <span data-ttu-id="0723d-192">Нажмите **Кнопку Удалить** в упражнении вниз.</span><span class="sxs-lookup"><span data-stu-id="0723d-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="0723d-193">Вы можете отоперить грант на согласие OAuth в PowerShell, следуя шагам в [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span><span class="sxs-lookup"><span data-stu-id="0723d-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="0723d-194">Вы можете отогнать назначение роли приложения-службы в PowerShell, следуя шагам в [Remove-AzureADServiceAppRoleAssignment.](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)</span><span class="sxs-lookup"><span data-stu-id="0723d-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="0723d-195">Вы также можете отключить вход для пострадавшей учетной записи вообще, что в свою очередь отключит доступ приложения к данным в этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0723d-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="0723d-196">Это не идеально для производительности конечного пользователя, конечно, но если вы работаете, чтобы ограничить влияние быстро, это может быть жизнеспособным краткосрочным исправлением.</span><span class="sxs-lookup"><span data-stu-id="0723d-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="0723d-197">Вы можете отключить интегрированные приложения для аренды.</span><span class="sxs-lookup"><span data-stu-id="0723d-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="0723d-198">Это резкий шаг, который отключает возможность для конечных пользователей предоставлять согласие на основе клиента.</span><span class="sxs-lookup"><span data-stu-id="0723d-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="0723d-199">Это не позволяет пользователям непреднамеренно предоставлять доступ к вредоносному приложению.</span><span class="sxs-lookup"><span data-stu-id="0723d-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="0723d-200">Это не рекомендуется, так как это серьезно снижает производительность ваших пользователей в сторонних приложениях.</span><span class="sxs-lookup"><span data-stu-id="0723d-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="0723d-201">Вы можете сделать это, следуя шагам в повороте интегрированных [приложений на или выключение](../../admin/misc/user-consent.md).</span><span class="sxs-lookup"><span data-stu-id="0723d-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="0723d-202">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="0723d-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="0723d-203">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="0723d-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="0723d-204">Используйте статью к [Стратегия развития безопасности Microsoft 365: приоритеты на первые 30 дней, 90 дней и далее](security-roadmap.md), чтобы применить лучшие методики, рекомендованные корпорацией Майкрософт, для защиты вашего клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0723d-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="0723d-205">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="0723d-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="0723d-206">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="0723d-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="0723d-207">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="0723d-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="0723d-208">Эти задачи требуют немного больше времени на планирование и реализацию, но значительно укрепляют вашу безопасность.</span><span class="sxs-lookup"><span data-stu-id="0723d-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="0723d-209">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="0723d-209">Beyond 90 days.</span></span> <span data-ttu-id="0723d-210">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="0723d-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="0723d-211">См. также:</span><span class="sxs-lookup"><span data-stu-id="0723d-211">See also:</span></span>

- <span data-ttu-id="0723d-212">[Неожиданное приложение в списке](/azure/active-directory/application-access-unexpected-application) приложений проходит администраторам с помощью различных действий, которые они могут захоть принять после того, как поймем, что есть неожиданные приложения с доступом к данным.</span><span class="sxs-lookup"><span data-stu-id="0723d-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="0723d-213">[Интеграция приложений с Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) — это обзор согласия и разрешений на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="0723d-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="0723d-214">[Проблемы, связанные с разработкой приложения,](/azure/active-directory/active-directory-application-dev-development-content-map) предоставляют ссылки на различные статьи, связанные с согласием.</span><span class="sxs-lookup"><span data-stu-id="0723d-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="0723d-215">Основные объекты приложения и [службы в Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) предоставляют обзор основных объектов приложения и служб, которые являются ключевыми для модели приложений.</span><span class="sxs-lookup"><span data-stu-id="0723d-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="0723d-216">[Управление доступом к приложениям](/azure/active-directory/active-directory-managing-access-to-apps) — это обзор возможностей, которые администраторы должны управлять доступом пользователей к приложениям.</span><span class="sxs-lookup"><span data-stu-id="0723d-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
