---
title: Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Этапы миграции служб Федерации active Directory (AD FS) для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727471"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="96a90-103">Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="96a90-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="96a90-104">Это изменение конфигурации может применяться в любое время до начала этапа 4.</span><span class="sxs-lookup"><span data-stu-id="96a90-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="96a90-105">После завершения второго этапа изменение конфигурации будет работать, и вы сможете войти в Глобальные конечные точки Office 365, такие как `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="96a90-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="96a90-106">Если вы реализуете изменение конфигурации до этапа 2, глобальные конечные  точки Office 365 еще не работают, но новое доверяющий доверие сторон по-прежнему является частью конфигурации служб Федерации Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="96a90-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="96a90-107">Чтобы перенести ферму AD FS из Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="96a90-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="96a90-108">Сохраняйте параметры AD FS, включая сведения о доверии FF с [помощью этих действий.](#backup)</span><span class="sxs-lookup"><span data-stu-id="96a90-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="96a90-109">Назови **резервную Deutschland_Only** Microsoft Cloud, чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="96a90-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="96a90-110">Проверьте восстановление с помощью резервного Deutschland_Only Microsoft Cloud, ферма AD FS должна продолжать работать только в Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="96a90-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="96a90-111">После завершения и тестирования резервного копирования AD FS выполните следующие действия, чтобы добавить новое доверение сторон в конфигурацию ADFS:</span><span class="sxs-lookup"><span data-stu-id="96a90-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="96a90-112">Откройте консоль управления AD FS</span><span class="sxs-lookup"><span data-stu-id="96a90-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="96a90-113">В левом окантовке консоли управления ADFS раздвяйте **ADFS,** затем доверяйте **отношениям,** а затем доверяйте **доверием сторон.**</span><span class="sxs-lookup"><span data-stu-id="96a90-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="96a90-114">В правой области выберите **Add Relying Party Trust...**</span><span class="sxs-lookup"><span data-stu-id="96a90-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="96a90-115">Выберите **Далее** на странице **Приветствие** мастера доверяющих сторон добавить.</span><span class="sxs-lookup"><span data-stu-id="96a90-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="96a90-116">На странице **Выбор источника данных** выберите импорт данных о стороне, которая полагается, опубликованной в Интернете или в **локальной сети.**</span><span class="sxs-lookup"><span data-stu-id="96a90-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="96a90-117">Значение **адреса метаданных Федерации (имя хозяина или URL-адрес)** должно быть задано `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="96a90-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="96a90-118">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96a90-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="96a90-119">На странице **Выбор источника данных** введите имя отображения, например Microsoft Office **365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="96a90-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="96a90-120">Затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96a90-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="96a90-121">На странице Мастер **Настройка многофакторной** проверки подлинности сейчас? Выберите подходящий выбор в соответствии с требованиями проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="96a90-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="96a90-122">Если вы придерживались по умолчанию, выберите, что в данный момент не нужно настраивать параметры многофакторной проверки подлинности для этого доверяемого **участника.**</span><span class="sxs-lookup"><span data-stu-id="96a90-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="96a90-123">Вы можете изменить этот параметр позже, если хотите.</span><span class="sxs-lookup"><span data-stu-id="96a90-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="96a90-124">В **правилах разрешения** на выдачу выберите разрешить всем пользователям доступ к выбранной стороне, которая полагается, нажмите  **кнопку Далее**</span><span class="sxs-lookup"><span data-stu-id="96a90-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="96a90-125">Нажмите **кнопку Далее** на **странице Готово добавить доверие,** чтобы завершить мастер.</span><span class="sxs-lookup"><span data-stu-id="96a90-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="96a90-126">Нажмите **Кнопку Закрыть** на **финишной** странице.</span><span class="sxs-lookup"><span data-stu-id="96a90-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="96a90-127">Закрыв мастера, устанавливается доверяющий участник с глобальными службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="96a90-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="96a90-128">Однако правила преобразования выдачи пока не настроены.</span><span class="sxs-lookup"><span data-stu-id="96a90-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="96a90-129">Вы можете использовать [AD FS Help для](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) создания правильных правил преобразования выдачи.</span><span class="sxs-lookup"><span data-stu-id="96a90-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="96a90-130">Созданные правила утверждения, созданные с помощью AD FS Help, можно добавлять вручную через консоль управления AD FS или с Помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96a90-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="96a90-131">AD FS Help будет создавать необходимые скрипты PowerShell, которые необходимо выполнять.</span><span class="sxs-lookup"><span data-stu-id="96a90-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="96a90-132">Запустите **создание утверждений** в справке AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.</span><span class="sxs-lookup"><span data-stu-id="96a90-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="96a90-133">Откройте предпочтительный текстовый редактор и вклейте скрипт PowerShell в новое текстовое окно.</span><span class="sxs-lookup"><span data-stu-id="96a90-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="96a90-134">Добавьте следующие строки PowerShell в конец вклеит скрипт из шага 2</span><span class="sxs-lookup"><span data-stu-id="96a90-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="96a90-135">Безопасность и выполнение сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96a90-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="96a90-136">Убедитесь, что присутствуют два доверчивых участника; один для Microsoft Cloud Deutschland и один для глобальной службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="96a90-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="96a90-137">Резервное копирование доверия с помощью [этих действий.](#backup)</span><span class="sxs-lookup"><span data-stu-id="96a90-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="96a90-138">Сохраните его с именем **FFAndWorldwide.**</span><span class="sxs-lookup"><span data-stu-id="96a90-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="96a90-139">Выполните миграцию backend и убедитесь, что AD FS по-прежнему работает во время процесса миграции.</span><span class="sxs-lookup"><span data-stu-id="96a90-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="96a90-140">Аварийное восстановление AD FS (база данных WID)</span><span class="sxs-lookup"><span data-stu-id="96a90-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="96a90-141">Чтобы восстановить ферму AD FS в аварийной ситуации, необходимо использовать средство быстрого восстановления [AD FS.](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool)</span><span class="sxs-lookup"><span data-stu-id="96a90-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="96a90-142">Поэтому необходимо скачать средство и перед началом миграции создать и безопасно хранить резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="96a90-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="96a90-143">В этом примере (средах TAT) для обратного запуска фермы запускаются следующие команды:</span><span class="sxs-lookup"><span data-stu-id="96a90-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="96a90-144">Back up an AD FS Farm</span><span class="sxs-lookup"><span data-stu-id="96a90-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="96a90-145">Установите средство быстрого восстановления AD FS на основном сервере AD FS.</span><span class="sxs-lookup"><span data-stu-id="96a90-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="96a90-146">Импортировать модуль в сеансе PowerShell с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="96a90-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="96a90-147">Запустите команду резервного копирования:</span><span class="sxs-lookup"><span data-stu-id="96a90-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="96a90-148">Безопасно храните резервную копию в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="96a90-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="96a90-149">Восстановление фермы AD FS</span><span class="sxs-lookup"><span data-stu-id="96a90-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="96a90-150">Если ферма полностью сбой и нет способа вернуться к старой ферме, делайте следующее.</span><span class="sxs-lookup"><span data-stu-id="96a90-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="96a90-151">Перемещение ранее сгенерированной и хранимой резервной копии на новый основной сервер AD FS.</span><span class="sxs-lookup"><span data-stu-id="96a90-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="96a90-152">Запустите следующую `Restore-ADFS` команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96a90-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="96a90-153">При необходимости импортировать сертификат SSL AD FS заранее.</span><span class="sxs-lookup"><span data-stu-id="96a90-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="96a90-154">Указать новые записи DNS или балансировку нагрузки на новые серверы AD FS.</span><span class="sxs-lookup"><span data-stu-id="96a90-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="96a90-155">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="96a90-155">More information</span></span>

<span data-ttu-id="96a90-156">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="96a90-156">Getting started:</span></span>

- [<span data-ttu-id="96a90-157">Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии</span><span class="sxs-lookup"><span data-stu-id="96a90-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="96a90-158">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="96a90-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="96a90-159">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="96a90-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="96a90-160">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="96a90-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="96a90-161">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="96a90-161">Moving through the transition:</span></span>

- [<span data-ttu-id="96a90-162">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="96a90-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="96a90-163">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="96a90-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="96a90-164">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="96a90-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="96a90-165">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="96a90-165">Cloud apps:</span></span>

- [<span data-ttu-id="96a90-166">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="96a90-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="96a90-167">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="96a90-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="96a90-168">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96a90-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
