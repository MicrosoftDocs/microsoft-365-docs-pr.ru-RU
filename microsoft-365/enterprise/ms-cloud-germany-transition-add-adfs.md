---
title: Этапы миграции AD FS для миграции с Microsoft Cloud записей
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
description: 'Сводка: этапы миграции служб федерации Active Directory (AD FS) для миграции с Microsoft Cloud записей.'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554814"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="289dd-103">Этапы миграции AD FS для миграции с Microsoft Cloud записей</span><span class="sxs-lookup"><span data-stu-id="289dd-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="289dd-104">Чтобы перенести ферму служб федерации Active Directory (AD FS) из Microsoft Cloud записей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="289dd-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="289dd-105">Выполните резервное копирование параметров AD FS, в том числе FF Trust со сведениями об [этих действиях](#backup).</span><span class="sxs-lookup"><span data-stu-id="289dd-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="289dd-106">Назовите резервную копию **Microsoft cloud Deutschland_Only** , чтобы указать, что у нее есть только сведения о клиенте Microsoft Cloud записей.</span><span class="sxs-lookup"><span data-stu-id="289dd-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="289dd-107">Протестируйте восстановление с помощью Microsoft Cloud Deutschland_Only резервную копию, ферма AD FS должна продолжать работать как записей в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="289dd-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="289dd-108">Создайте новое отношение доверия с проверяющей стороной из **AD FS > служб Office 365**.</span><span class="sxs-lookup"><span data-stu-id="289dd-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="289dd-109">В разделе **отношения доверия с проверяющей стороной** в консоли управления AD FS выберите **Добавить отношение доверия с проверяющей** стороной.</span><span class="sxs-lookup"><span data-stu-id="289dd-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="289dd-110">Нажмите кнопку **Далее** на странице **приветствия** мастера добавления отношения доверия с проверяющей стороной.</span><span class="sxs-lookup"><span data-stu-id="289dd-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="289dd-111">На странице **Выбор источника данных** выберите **Импорт данных о проверяющей стороне, опубликованных в Интернете или в локальной сети**.</span><span class="sxs-lookup"><span data-stu-id="289dd-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="289dd-112">Для параметра **адрес метаданных федерации (имя узла или URL-адрес)** задано значение `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="289dd-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="289dd-113">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="289dd-113">Click **Next**.</span></span>
7. <span data-ttu-id="289dd-114">На странице **Выбор источника данных** введите отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="289dd-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="289dd-115">Корпорация Майкрософт рекомендует использовать **платформу идентификации Microsoft Office 365 по всему миру**.</span><span class="sxs-lookup"><span data-stu-id="289dd-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="289dd-116">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="289dd-116">Click **Next**.</span></span>
8. <span data-ttu-id="289dd-117">Нажмите кнопку **Далее** в **разделе Настройка многофакторной проверки подлинности сейчас?**, **Выберите правила авторизации выдачи** и **все готово к добавлению страниц доверия** .</span><span class="sxs-lookup"><span data-stu-id="289dd-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="289dd-118">Нажмите кнопку **Закрыть** на странице **Готово** .</span><span class="sxs-lookup"><span data-stu-id="289dd-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="289dd-119">После закрытия мастера устанавливается отношение доверия с проверяющей стороной Естс служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="289dd-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="289dd-120">Однако правила преобразования выдачи не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="289dd-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="289dd-121">Вы можете использовать [справку по AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) для создания правильных правил преобразования выдачи.</span><span class="sxs-lookup"><span data-stu-id="289dd-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="289dd-122">Созданные правила утверждений, созданные с помощью справки AD FS, можно либо добавить вручную через консоль управления AD FS, либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289dd-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="289dd-123">Справка по AD FS создаст необходимые сценарии PowerShell, которые необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="289dd-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="289dd-124">Запустите **Создание утверждений** в СПРАВКЕ AD FS и скопируйте сценарий преобразования утверждений PowerShell с помощью параметра **Copy** в правом верхнем углу скрипта.</span><span class="sxs-lookup"><span data-stu-id="289dd-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="289dd-125">Вставьте созданную оболочку PowerShell в следующее:</span><span class="sxs-lookup"><span data-stu-id="289dd-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="289dd-126">Выполнение завершенного скрипта.</span><span class="sxs-lookup"><span data-stu-id="289dd-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="289dd-127">Убедитесь, что имеются два отношения доверия проверяющей стороны; один для всего мира и один для БФ.</span><span class="sxs-lookup"><span data-stu-id="289dd-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="289dd-128">Выполните резервное копирование отношений доверия, выполнив [указанные ниже действия](#backup).</span><span class="sxs-lookup"><span data-stu-id="289dd-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="289dd-129">Сохраните файл с именем **ффандворлдвиде**.</span><span class="sxs-lookup"><span data-stu-id="289dd-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="289dd-130">Выполните внутреннюю миграцию и убедитесь, что служба AD FS все еще работает во время процесса миграции.</span><span class="sxs-lookup"><span data-stu-id="289dd-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="289dd-131">Аварийное восстановление AD FS (база данных WID)</span><span class="sxs-lookup"><span data-stu-id="289dd-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="289dd-132">Чтобы восстановить ферму AD FS в [средстве аварийного восстановления служб федерации Active Directory](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) , необходимо использовать его.</span><span class="sxs-lookup"><span data-stu-id="289dd-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="289dd-133">Таким образом, перед началом миграции необходимо скачать и сохранить средство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="289dd-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="289dd-134">В этом примере (средах ТАТ) для резервного копирования фермы были выполнены следующие команды:</span><span class="sxs-lookup"><span data-stu-id="289dd-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="289dd-135">Резервное копирование фермы AD FS</span><span class="sxs-lookup"><span data-stu-id="289dd-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="289dd-136">Установите средство быстрого восстановления служб федерации Active Directory на основном сервере AD FS.</span><span class="sxs-lookup"><span data-stu-id="289dd-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="289dd-137">Импортируйте модуль в сеансе PowerShell с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="289dd-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="289dd-138">Выполните команду резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="289dd-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="289dd-139">Безопасно храните резервную копию в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="289dd-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="289dd-140">Восстановление фермы AD FS</span><span class="sxs-lookup"><span data-stu-id="289dd-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="289dd-141">Если ферма закончилась неудачно и нет способа вернуться на старую ферму, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="289dd-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="289dd-142">Переместите ранее созданный и сохраненный архив на новый основной сервер AD FS.</span><span class="sxs-lookup"><span data-stu-id="289dd-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="289dd-143">Выполните следующую `Restore-ADFS` команду PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289dd-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="289dd-144">При необходимости импортируйте SSL-сертификат AD FS заранее.</span><span class="sxs-lookup"><span data-stu-id="289dd-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="289dd-145">Укажите новые записи DNS или подсистему балансировки нагрузки для новых серверов AD FS.</span><span class="sxs-lookup"><span data-stu-id="289dd-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="289dd-146">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="289dd-146">More information</span></span>

<span data-ttu-id="289dd-147">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="289dd-147">Getting started:</span></span>

- [<span data-ttu-id="289dd-148">Миграция из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке</span><span class="sxs-lookup"><span data-stu-id="289dd-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="289dd-149">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="289dd-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="289dd-150">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="289dd-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="289dd-151">Взаимодействие с пользователем во время миграции</span><span class="sxs-lookup"><span data-stu-id="289dd-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="289dd-152">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="289dd-152">Moving through the transition:</span></span>

- [<span data-ttu-id="289dd-153">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="289dd-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="289dd-154">Дополнительные предварительные действия</span><span class="sxs-lookup"><span data-stu-id="289dd-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="289dd-155">Дополнительные сведения о [службах](ms-cloud-germany-transition-add-general.md), [устройствах](ms-cloud-germany-transition-add-devices.md), [опыте](ms-cloud-germany-transition-add-experience.md)и службах [федерации Active Directory](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="289dd-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="289dd-156">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="289dd-156">Cloud apps:</span></span>

- [<span data-ttu-id="289dd-157">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="289dd-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="289dd-158">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="289dd-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="289dd-159">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="289dd-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
