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
description: Сводка. Этапы миграции служб федерации Active Directory (AD FS) для миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688669"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="8f174-103">Этапы миграции AD FS для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="8f174-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="8f174-104">Чтобы перенести ферму служб федерации Active Directory (AD FS) из Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="8f174-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="8f174-105">С помощью этих действий можно создать параметров [](#backup)AD FS, включая сведения о доверии FF.</span><span class="sxs-lookup"><span data-stu-id="8f174-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="8f174-106">Назовем резервную **копию microsoft Cloud Deutschland_Only** указать, что у нее есть только сведения о клиенте Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="8f174-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="8f174-107">Проверьте восстановление с помощью резервной копии Microsoft Cloud Deutschland_Only, ферма AD FS должна продолжать работать только как Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="8f174-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="8f174-108">Создайте новое отношения доверия с отношениями доверия с > Службы **AD FS в Office 365.**</span><span class="sxs-lookup"><span data-stu-id="8f174-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="8f174-109">В **окнах доверия с отношениями** доверия с этой стороной в консоли управления AD FS выберите "Добавить отношения доверия с этой **стороной".**</span><span class="sxs-lookup"><span data-stu-id="8f174-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="8f174-110">Выберите **"Далее"** на странице приветствия мастера добавления отношения доверия с подстройки. </span><span class="sxs-lookup"><span data-stu-id="8f174-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="8f174-111">На странице **"Выбор источника данных"** выберите "Импорт данных о стороне, опубликованной в Интернете или **в локальной сети".**</span><span class="sxs-lookup"><span data-stu-id="8f174-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="8f174-112">Для **адреса метаданных федерации (имя или URL-адрес)** федерации установлено значение `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="8f174-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="8f174-113">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8f174-113">Click **Next**.</span></span>
7. <span data-ttu-id="8f174-114">На странице **"Выбор источника данных"** введите отображаемого имени.</span><span class="sxs-lookup"><span data-stu-id="8f174-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="8f174-115">Корпорация Майкрософт рекомендует **Microsoft Office 365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="8f174-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="8f174-116">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8f174-116">Click **Next**.</span></span>
8. <span data-ttu-id="8f174-117">Нажмите **кнопку** "Далее" в области "Настройка многофакторной проверки подлинности"? **Выберите**"Правила авторизации выдачи" и "Готово **к добавлению** страниц доверия". </span><span class="sxs-lookup"><span data-stu-id="8f174-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="8f174-118">Нажмите **кнопку "Закрыть"** на **странице "Готово".**</span><span class="sxs-lookup"><span data-stu-id="8f174-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="8f174-119">Закрыв мастер, устанавливается отношения доверия с отношениями доверия с службами Office 365 eSTS.</span><span class="sxs-lookup"><span data-stu-id="8f174-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="8f174-120">Однако правила преобразования выдачи не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="8f174-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="8f174-121">Справку [AD FS можно использовать](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) для создания правильных правил преобразования выдачи.</span><span class="sxs-lookup"><span data-stu-id="8f174-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="8f174-122">Созданные правила утверждений, созданные с помощью справки AD FS, можно добавить вручную с помощью консоли управления AD FS или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f174-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="8f174-123">Справка AD FS создает необходимые сценарии PowerShell, которые необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="8f174-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="8f174-124">Запустите **справку "Создание** утверждений" в AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **"Копировать"** в правом верхнем углу сценария.</span><span class="sxs-lookup"><span data-stu-id="8f174-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="8f174-125">В paste the generated PowerShell into the following:</span><span class="sxs-lookup"><span data-stu-id="8f174-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="8f174-126">Выполните завершенный сценарий.</span><span class="sxs-lookup"><span data-stu-id="8f174-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="8f174-127">Убедитесь, что имеются два отношения доверия с проверяемой стороной; один для всемирного и второй для BF.</span><span class="sxs-lookup"><span data-stu-id="8f174-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="8f174-128">Резервное копирование доверия с помощью [этих действий.](#backup)</span><span class="sxs-lookup"><span data-stu-id="8f174-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="8f174-129">Сохраните его с именем **FFAndWorldwide.**</span><span class="sxs-lookup"><span data-stu-id="8f174-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="8f174-130">Завершите миграцию на тыл и убедитесь, что службы AD FS по-прежнему работают в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="8f174-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="8f174-131">Аварийное восстановление AD FS (база данных WID)</span><span class="sxs-lookup"><span data-stu-id="8f174-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="8f174-132">Для восстановления фермы AD FS в аварийном средстве быстрого восстановления [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) необходимо использовать средство быстрого восстановления.</span><span class="sxs-lookup"><span data-stu-id="8f174-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="8f174-133">Поэтому необходимо скачать средство и перед началом миграции создать резервную копию и безопасно сохранить ее.</span><span class="sxs-lookup"><span data-stu-id="8f174-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="8f174-134">В этом примере (средах СДВИБ) для работы с фермой были выполнить следующие команды:</span><span class="sxs-lookup"><span data-stu-id="8f174-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="8f174-135">Back up an AD FS Farm</span><span class="sxs-lookup"><span data-stu-id="8f174-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="8f174-136">Установите средство быстрого восстановления AD FS на основном сервере AD FS.</span><span class="sxs-lookup"><span data-stu-id="8f174-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="8f174-137">Импортировать модуль в сеансе PowerShell с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="8f174-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="8f174-138">Запустите команду резервного копирования:</span><span class="sxs-lookup"><span data-stu-id="8f174-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="8f174-139">Безопасно храните резервную копию в нужном месте назначения.</span><span class="sxs-lookup"><span data-stu-id="8f174-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="8f174-140">Восстановление фермы AD FS</span><span class="sxs-lookup"><span data-stu-id="8f174-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="8f174-141">Если в ферме полностью сбой и возврат к старой ферме не удастся, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="8f174-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="8f174-142">Переместим ранее созданную и сохраненную резервную копию на новый основной сервер AD FS.</span><span class="sxs-lookup"><span data-stu-id="8f174-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="8f174-143">Запустите следующую `Restore-ADFS` команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f174-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="8f174-144">При необходимости импортировать SSL-сертификат AD FS заранее.</span><span class="sxs-lookup"><span data-stu-id="8f174-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="8f174-145">Указать новые записи DNS или балансировку нагрузки на новые серверы AD FS.</span><span class="sxs-lookup"><span data-stu-id="8f174-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="8f174-146">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="8f174-146">More information</span></span>

<span data-ttu-id="8f174-147">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="8f174-147">Getting started:</span></span>

- [<span data-ttu-id="8f174-148">Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии</span><span class="sxs-lookup"><span data-stu-id="8f174-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="8f174-149">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="8f174-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="8f174-150">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="8f174-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="8f174-151">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="8f174-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="8f174-152">Переход:</span><span class="sxs-lookup"><span data-stu-id="8f174-152">Moving through the transition:</span></span>

- [<span data-ttu-id="8f174-153">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="8f174-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="8f174-154">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="8f174-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="8f174-155">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [функций](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="8f174-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="8f174-156">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="8f174-156">Cloud apps:</span></span>

- [<span data-ttu-id="8f174-157">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8f174-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="8f174-158">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="8f174-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="8f174-159">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f174-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
