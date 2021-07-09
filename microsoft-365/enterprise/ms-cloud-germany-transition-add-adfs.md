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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339614"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="84a74-103">Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="84a74-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="84a74-104">Это изменение конфигурации необходимо применять в любое время до начала этапа 2.</span><span class="sxs-lookup"><span data-stu-id="84a74-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="84a74-105">После завершения второго этапа изменение конфигурации будет работать, и вы сможете войти через Office 365 глобальных конечных точек, таких как `https://admin.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="84a74-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://admin.microsoft.com`.</span></span> <span data-ttu-id="84a74-106">Если вы реализуете изменение конфигурации до 2-го этапа,  Office 365 глобальные конечные точки еще не работают, но новое доверение доверчивых сторон по-прежнему является частью конфигурации служб Федерации Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="84a74-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="84a74-107">Клиенты, которые используют федерационную проверку подлинности с помощью служб Федерации Active Directory (AD FS), не должны вносить изменения в URL-адреса эмитента, используемые для всех проверки подлинности с локальной службой доменных служб Active Directory (AD DS) во время миграции.</span><span class="sxs-lookup"><span data-stu-id="84a74-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="84a74-108">Изменение URL-адресов эмитента приведет к сбоям проверки подлинности для пользователей домена.</span><span class="sxs-lookup"><span data-stu-id="84a74-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="84a74-109">URL-адреса эмитента можно изменить непосредственно в AD FS  или при преобразовании домена из управляемого в _федераторский_ и наоборот.</span><span class="sxs-lookup"><span data-stu-id="84a74-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="84a74-110">Рекомендуется не добавлять, удалять и не конвертировать федераированный домен в перенесенном клиенте Azure AD.</span><span class="sxs-lookup"><span data-stu-id="84a74-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="84a74-111">URL-адреса эмитента могут быть изменены после полного завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="84a74-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="84a74-112">Чтобы подготовить ферму AD FS к миграции из Microsoft Cloud Deutschland, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="84a74-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="84a74-113">С помощью этих действий необходимо создать параметров AD FS, в том числе существующего доверия сторон microsoft Cloud Deutschland Relying [Party.](#backup)</span><span class="sxs-lookup"><span data-stu-id="84a74-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="84a74-114">Назови **резервную копию MicrosoftCloudDeutschlandOnly,** чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="84a74-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="84a74-115">Резервное копирование будет содержать не только существующие Office 365 доверяющие стороны для Microsoft Cloud Deutschland, но и все другие доверчивые партийные траста, присутствующие в соответствующей ферме AD FS.</span><span class="sxs-lookup"><span data-stu-id="84a74-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="84a74-116">Проверьте восстановление с помощью резервного копирования MicrosoftCloudDeutschlandOnly, ферма AD FS должна продолжать работать только в Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="84a74-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="84a74-117">После завершения и тестирования резервного копирования AD FS выполните следующие действия, чтобы добавить новое доверение сторон в конфигурацию ADFS:</span><span class="sxs-lookup"><span data-stu-id="84a74-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="84a74-118">Откройте консоль управления AD FS.</span><span class="sxs-lookup"><span data-stu-id="84a74-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="84a74-119">В левой области консоли управления ADFS перейдите в меню **Доверчивые** стороны.</span><span class="sxs-lookup"><span data-stu-id="84a74-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="84a74-120">В правой области выберите **Add Relying Party Trust...**</span><span class="sxs-lookup"><span data-stu-id="84a74-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="84a74-121">Выберите **Начало** на странице **Добро** пожаловать мастера доверия для доверяющих сторон с добавлением.</span><span class="sxs-lookup"><span data-stu-id="84a74-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="84a74-122">На странице **Выбор источника данных** выберите импорт данных о стороне, которая полагается, опубликованной в Интернете или в **локальной сети.**</span><span class="sxs-lookup"><span data-stu-id="84a74-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="84a74-123">Значение **адреса метаданных Федерации (имя хозяина или URL-адрес)** должно быть задано `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="84a74-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="84a74-124">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84a74-124">Click **Next**.</span></span>

6. <span data-ttu-id="84a74-125">На странице **Укажите имя отображения** введите имя отображения, например **Microsoft Office 365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="84a74-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="84a74-126">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84a74-126">Click **Next**.</span></span>

7. <span data-ttu-id="84a74-127">Если вы используете ADFS в Windows Server 2012, на странице мастер Настройте многофакторную проверку подлинности **сейчас?** Выберите подходящий выбор в соответствии с требованиями проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="84a74-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="84a74-128">Если вы придерживались по умолчанию, выберите, что в данный момент не нужно настраивать параметры многофакторной проверки подлинности для этого доверяемого **участника.**</span><span class="sxs-lookup"><span data-stu-id="84a74-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="84a74-129">Вы можете изменить этот параметр позже, если хотите.</span><span class="sxs-lookup"><span data-stu-id="84a74-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="84a74-130">Для AD FS 2012: В правилах разрешения  на выдачу выберите разрешить всем пользователям доступ к выбранной стороне и нажмите **кнопку Далее**. </span><span class="sxs-lookup"><span data-stu-id="84a74-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="84a74-131">Для AD FS 2016 и AD FS 2019: на странице **Выбор** политики управления доступом выберите соответствующую политику управления доступом и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="84a74-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="84a74-132">Если ни один из них не выбран, доверение доверяющих сторон **не будет** работать.</span><span class="sxs-lookup"><span data-stu-id="84a74-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="84a74-133">Нажмите **кнопку Далее** на **странице Готово добавить доверие,** чтобы завершить мастер.</span><span class="sxs-lookup"><span data-stu-id="84a74-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="84a74-134">Нажмите **Кнопку Закрыть** на **финишной** странице.</span><span class="sxs-lookup"><span data-stu-id="84a74-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="84a74-135">Закрыв мастера, устанавливается доверенная группа Office 365 глобальной службы.</span><span class="sxs-lookup"><span data-stu-id="84a74-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="84a74-136">Однако правила преобразования выдачи пока не настроены.</span><span class="sxs-lookup"><span data-stu-id="84a74-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="84a74-137">Вы можете использовать [AD FS Help для](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) создания правильных правил преобразования выдачи.</span><span class="sxs-lookup"><span data-stu-id="84a74-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="84a74-138">Созданные правила утверждения, созданные с помощью AD FS Help, можно добавлять вручную через консоль управления AD FS или с Помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84a74-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="84a74-139">AD FS Help будет создавать необходимые скрипты PowerShell, которые необходимо выполнять.</span><span class="sxs-lookup"><span data-stu-id="84a74-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="84a74-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) будет создавать стандартные правила преобразования выдачи, которые отгружаются вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="84a74-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="84a74-141">Однако, если правила преобразования настраиваемой выдачи в Microsoft Cloud Deutschland Relying Party Trust (например, пользовательские URL-адреса эмитента, нестандартные неизменяемые ID или любые другие настройки), правила, созданные службой AD FS, должны быть изменены таким образом, чтобы они вписывались в настраиваемую логику, созданную в настоящее время для доверения сторон Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="84a74-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="84a74-142">Если эти настройки не интегрированы в правила, созданные с помощью [AD FS Help,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)проверка  подлинности в **Microsoft Office 365 Identity Platform WorldWide,** скорее всего, не будет работать для федеративного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="84a74-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="84a74-143">Запустите **создание утверждений** в [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) и скопируйте скрипт PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.</span><span class="sxs-lookup"><span data-stu-id="84a74-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="84a74-144">Следуйте шагам, описанным в справке [AD FS о](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) том, как запустить сценарий PowerShell в ферме AD FS для создания глобального доверяемой группы доверия.</span><span class="sxs-lookup"><span data-stu-id="84a74-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="84a74-145">Перед запуском скрипта замените следующие строки кода в сгенерированной скрипте, как описано ниже:</span><span class="sxs-lookup"><span data-stu-id="84a74-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="84a74-146">Убедитесь, что присутствуют два полагаться partyTtrusts; один для Microsoft Cloud Deutschland и один для Office 365 глобальной службы.</span><span class="sxs-lookup"><span data-stu-id="84a74-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="84a74-147">Для проверки можно использовать следующую команду.</span><span class="sxs-lookup"><span data-stu-id="84a74-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="84a74-148">Он должен возвращать две строки и соответствующие имена и идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="84a74-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="84a74-149">Резервное копирование полной конфигурации миграции, включая оба доверчивых участника, с помощью [этих действий.](#backup)</span><span class="sxs-lookup"><span data-stu-id="84a74-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="84a74-150">Сохраните его с именем **MicrosoftCloudDeutschlandAndWorldwide.**</span><span class="sxs-lookup"><span data-stu-id="84a74-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="84a74-151">В то время как клиент находится в миграции, регулярно убедитесь, что проверка подлинности AD FS работает с облаком Microsoft Cloud Deutschland и Microsoft Global в различных поддерживаемых шагах миграции.</span><span class="sxs-lookup"><span data-stu-id="84a74-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="84a74-152">Аварийное восстановление AD FS (база данных WID)</span><span class="sxs-lookup"><span data-stu-id="84a74-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="84a74-153">Чтобы восстановить ферму AD FS в аварийной ситуации, необходимо использовать средство быстрого восстановления [AD FS.](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool)</span><span class="sxs-lookup"><span data-stu-id="84a74-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="84a74-154">Поэтому необходимо скачать средство и перед началом миграции создать и безопасно хранить резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="84a74-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="84a74-155">В этом примере были запущены следующие команды для обратного запуска фермы в базе данных WID:</span><span class="sxs-lookup"><span data-stu-id="84a74-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="84a74-156">Back up an AD FS Farm</span><span class="sxs-lookup"><span data-stu-id="84a74-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="84a74-157">Установите средство быстрого восстановления AD FS на основном сервере AD FS.</span><span class="sxs-lookup"><span data-stu-id="84a74-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="84a74-158">Импортировать модуль в сеансе PowerShell с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="84a74-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="84a74-159">Запустите команду резервного копирования:</span><span class="sxs-lookup"><span data-stu-id="84a74-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="84a74-160">Безопасно храните резервную копию в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="84a74-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="84a74-161">Восстановление фермы AD FS</span><span class="sxs-lookup"><span data-stu-id="84a74-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="84a74-162">Если ферма полностью сбой и нет способа вернуться к старой ферме, делайте следующее.</span><span class="sxs-lookup"><span data-stu-id="84a74-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="84a74-163">Перемещение ранее сгенерированной и хранимой резервной копии на новый основной сервер AD FS.</span><span class="sxs-lookup"><span data-stu-id="84a74-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="84a74-164">Запустите следующую `Restore-ADFS` команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84a74-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="84a74-165">При необходимости импортировать сертификат SSL AD FS заранее.</span><span class="sxs-lookup"><span data-stu-id="84a74-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="84a74-166">Указать новые записи DNS или балансировку нагрузки на новые серверы AD FS.</span><span class="sxs-lookup"><span data-stu-id="84a74-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="84a74-167">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="84a74-167">More information</span></span>

<span data-ttu-id="84a74-168">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="84a74-168">Getting started:</span></span>

- [<span data-ttu-id="84a74-169">Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="84a74-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="84a74-170">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="84a74-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="84a74-171">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="84a74-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="84a74-172">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="84a74-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="84a74-173">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="84a74-173">Moving through the transition:</span></span>

- [<span data-ttu-id="84a74-174">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="84a74-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="84a74-175">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="84a74-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="84a74-176">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="84a74-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="84a74-177">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="84a74-177">Cloud apps:</span></span>

- [<span data-ttu-id="84a74-178">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="84a74-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="84a74-179">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="84a74-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="84a74-180">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84a74-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
