---
title: Узнайте о локальном сканере для защиты от потери данных Microsoft 365 (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Локальный сканер для защиты от потери данных Microsoft 365 расширяет возможности отслеживания действий и защитных мер для файлов на локальных файловых ресурсах, и в папках и библиотеках документов SharePoint. Сканер Azure Information Protection (AIP) сканирует и защищает файлы
ms.openlocfilehash: 996de5ea640a16ef2a250830d7167aa316b54a21
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417391"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="00fac-104">Узнайте о локальном сканере для защиты от потери данных Microsoft 365 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="00fac-104">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="00fac-105">Сканер для защиты от потери данных Microsoft является частью набора функций защиты от потери данных Microsoft 365 (DLP), которые можно использовать для обнаружения и защиты конфиденциальных элементов в службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00fac-105">Microsoft data loss prevention on-premises scanner is part of the Microsoft 365 data loss prevention (DLP) suite of features that you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="00fac-106">Дополнительные сведения обо всех предложениях Майкрософт по защите от потери данных см. в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="00fac-106">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="00fac-107">**Локальный сканер для защиты от потери данных** выполняет обход локальных неактивных данных в общих папках, а также в библиотеках документов и папках SharePoint в поисках конфиденциальных элементов, которые в случае утечки представляют риск для вашей организации или могут нарушить политику соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="00fac-107">The **DLP on-premises scanner** crawls on-premises data-at-rest in file shares and SharePoint document libraries and folders for sensitive items that, if leaked, would pose a risk to your organization or pose a risk of compliance policy violation.</span></span> <span data-ttu-id="00fac-108">Это обеспечивает необходимый уровень контроля и видимости для правильного использования и защиты конфиденциальных элементов, а также для предотвращения рискованного поведения, которое может поставить их под угрозу.</span><span class="sxs-lookup"><span data-stu-id="00fac-108">This gives you the visibility and control you need to ensure that sensitive items are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span> <span data-ttu-id="00fac-109">Локальный сканер защиты от потери данных обнаруживает конфиденциальную информацию с помощью [встроенных](sensitive-information-type-entity-definitions.md) или [настраиваемых типов конфиденциальной информации](create-a-custom-sensitive-information-type.md), [меток конфиденциальности](sensitivity-labels.md) или свойств файлов.</span><span class="sxs-lookup"><span data-stu-id="00fac-109">The DLP on-premises scanner detects sensitive information by using [built-in](sensitive-information-type-entity-definitions.md) or [custom sensitive information](create-a-custom-sensitive-information-type.md) types, [sensitivity labels](sensitivity-labels.md) or file properties.</span></span> <span data-ttu-id="00fac-110">Сведения о действиях пользователей с конфиденциальными элементами отображаются в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [Политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="00fac-110">The information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a><span data-ttu-id="00fac-111">В основе локального сканера защиты от потери данных — сканер Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="00fac-111">The DLP on-premises scanner relies on Azure Information Protection scanner</span></span>

<span data-ttu-id="00fac-112">Локальный сканер защиты от потери данных основан на полной реализации сканера Azure Information Protection (AIP) для мониторинга, маркировки и защиты конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="00fac-112">The DLP on-premises scanner relies on a full implementation of the Azure Information Protection (AIP) scanner to monitor, label and protect sensitive items.</span></span> <span data-ttu-id="00fac-113">Если вы не знакомы со сканером AIP, настоятельно рекомендуем ознакомиться с ним.</span><span class="sxs-lookup"><span data-stu-id="00fac-113">If you aren't familiar with the AIP scanner, we strongly recommend familiarizing yourself with it.</span></span> <span data-ttu-id="00fac-114">См. эти статьи:</span><span class="sxs-lookup"><span data-stu-id="00fac-114">See these articles:</span></span>

- [<span data-ttu-id="00fac-115">Что такое Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="00fac-115">What is Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [<span data-ttu-id="00fac-116">Что такое сканер унифицированных меток Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="00fac-116">What is the Azure Information Protection unified labeling scanner</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="00fac-117">Требования к установке и развертыванию сканера унифицированных меток Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="00fac-117">Requirements for installing and deploying the Azure Information Protection unified labeling scanner</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-prereqs)
- [<span data-ttu-id="00fac-118">Руководство. Установка сканера унифицированных меток Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="00fac-118">Tutorial: Installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](https://docs.microsoft.com/azure/information-protection/tutorial-install-scanner)
- [<span data-ttu-id="00fac-119">Настройка и установка сканера унифицированных меток Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="00fac-119">Configuring and installing the Azure Information Protection unified labeling scanner</span></span>](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)
- [<span data-ttu-id="00fac-120">Клиент унифицированных меток Azure Information Protection — журнал выпусков и политика поддержки</span><span class="sxs-lookup"><span data-stu-id="00fac-120">Azure Information Protection unified labeling client - Version release history and support policy</span></span>](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a><span data-ttu-id="00fac-121">Действия локального сканера защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-121">DLP on-premises scanner actions</span></span>

<span data-ttu-id="00fac-122">Локальный сканер защиты от потери данных обнаруживает файлы одним из следующих четырех методов:</span><span class="sxs-lookup"><span data-stu-id="00fac-122">DLP on-premises scanner detects files by one of these four methods:</span></span>

- <span data-ttu-id="00fac-123">типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="00fac-123">sensitive information types</span></span>
- <span data-ttu-id="00fac-124">метки конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="00fac-124">sensitivity labels</span></span>
- <span data-ttu-id="00fac-125">расширение файла</span><span class="sxs-lookup"><span data-stu-id="00fac-125">file extension</span></span>
- <span data-ttu-id="00fac-126">настраиваемые свойства документа только для файлов Office</span><span class="sxs-lookup"><span data-stu-id="00fac-126">custom document properties on Office files only</span></span> 

<span data-ttu-id="00fac-127">Когда обнаруженный файл представляет потенциальную угрозу утечки или нарушения политики соответствия требованиям, локальный сканер защиты от потери данных предпринимает одно из следующих четырех действий.</span><span class="sxs-lookup"><span data-stu-id="00fac-127">When a detected file poses a potential risk if leaked or a compliance policy violation, the DLP on-premises scanner can take one of these four actions.</span></span>

|<span data-ttu-id="00fac-128">Действие</span><span class="sxs-lookup"><span data-stu-id="00fac-128">Action</span></span> |<span data-ttu-id="00fac-129">Описание</span><span class="sxs-lookup"><span data-stu-id="00fac-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="00fac-130">**Блокировка доступа данных пользователей к файлам, хранимых в локальном сканере — для всех**</span><span class="sxs-lookup"><span data-stu-id="00fac-130">**Block these people from accessing file stored in  on-premises scanner - Everyone**</span></span> | <span data-ttu-id="00fac-131">Это действие блокирует доступ для всех учетных записей, кроме владельца содержимого, последней учетной записи, изменившей элемент, и администратора.</span><span class="sxs-lookup"><span data-stu-id="00fac-131">When enforced, this action blocks access to all accounts except the content owner, the last account that modified the item and the administrator.</span></span> <span data-ttu-id="00fac-132">Для этого удаляются все учетные записи из разрешений NTFS и SharePoint на уровне файла, за исключением владельца файла, владельца репозитория (установленного настройкой [Установить владельца репозитория](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) в задании сканирования содержимого), последнего пользователя, вносившего изменения (может быть определен только в SharePoint) и администратора. Учетной записи сканера также предоставляются права FC на файл.</span><span class="sxs-lookup"><span data-stu-id="00fac-132">It does this by removing all accounts from NTFS/SharePoint permissions at the file level except the file owner, repository owner (set in the [Set repository owner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) setting in content scan job), last modifier (can be identified in SharePoint only) and admin. The scanner account is also granted FC rights on the file.</span></span>|
|<span data-ttu-id="00fac-133">**Блокировка доступа данных пользователей к файлам, хранимых в локальном сканере — блокировать доступ в пределах организации (общедоступный)**</span><span class="sxs-lookup"><span data-stu-id="00fac-133">**Block these people from accessing file stored in  on-premises scanner - block org-wide (public) access**</span></span>    |<span data-ttu-id="00fac-134">Это действие удаляет идентификаторы безопасности категорий **_Все пользователи_*_, _*_NT AUTHORITY\пользователи, прошедшие проверку подлинности_*_ и _*_Пользователи домена_** из списка управления доступом (ACL) к файлам.</span><span class="sxs-lookup"><span data-stu-id="00fac-134">When enforced, this action removes the **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SIDs from the file access control list (ACL).</span></span> <span data-ttu-id="00fac-135">Только пользователи и группы, для которых явным образом предоставлены права на доступ к файлу или родительской папке, смогут открыть файл.</span><span class="sxs-lookup"><span data-stu-id="00fac-135">Only users and groups that have been explicitly granted rights to the file or parent folder will be able to access the file.</span></span>|
|<span data-ttu-id="00fac-136">**Настройка разрешений для файла**</span><span class="sxs-lookup"><span data-stu-id="00fac-136">**Set permissions on the file**</span></span>|<span data-ttu-id="00fac-137">Это действие заставляет файл наследовать разрешения родительской папки.</span><span class="sxs-lookup"><span data-stu-id="00fac-137">When enforced, this action forces the file to inherit the permissions of its parent folder.</span></span> <span data-ttu-id="00fac-138">По умолчанию это действие выполняется только в том случае, если разрешения для родительской папки более строгие, чем разрешения, которые уже имеются для файла.</span><span class="sxs-lookup"><span data-stu-id="00fac-138">Be default, this action will only be enforced if the permissions on the parent folder are more restrictive than the permissions that are already on the file.</span></span> <span data-ttu-id="00fac-139">Например, если ACL для файла настроен так, чтобы разрешать только \**_определенных пользователей_*_, а родительская папка настроена для разрешения группы _\*_Пользователи домена_*_, разрешения родительской папки не будут унаследованы файлом. Вы можете переопределить это поведение, выбрав параметр _* Наследовать, даже если родительские разрешения менее строгие\*\*.</span><span class="sxs-lookup"><span data-stu-id="00fac-139">For example, if the ACL on the file is set to only allow **_specific users_*_ and the parent folder is configured to allow _*_Domain Users_*_ group, the parent folder permissions would not be inherited by the file. You can override this behavior by selecting the _\* Inherit even if parent permissions are less restrictive*\* option.</span></span>|
|<span data-ttu-id="00fac-140">**Удаление файла из неправильного расположения**</span><span class="sxs-lookup"><span data-stu-id="00fac-140">**Remove the file from improper location**</span></span>|<span data-ttu-id="00fac-141">Это действие заменяет исходный файл на файл-заглушку с расширением .txt и помещает копию исходного файла в папку карантина.</span><span class="sxs-lookup"><span data-stu-id="00fac-141">When enforced, this action replaces the original file with a stub file with .txt extension and places a copy of the original file in a quarantine folder.</span></span> 

## <a name="whats-different-in-the-on-premises-scanner"></a><span data-ttu-id="00fac-142">Отличие локального сканера</span><span class="sxs-lookup"><span data-stu-id="00fac-142">What's different in the on-premises scanner</span></span>

<span data-ttu-id="00fac-143">Перед началом глубокой работы с локальным сканером необходимо учитывать ряд дополнительных понятий.</span><span class="sxs-lookup"><span data-stu-id="00fac-143">There are a few extra concepts that you need to be aware of before you dig into the on-premises scanner.</span></span>

### <a name="aip-repositories-and-content-scan-jobs"></a><span data-ttu-id="00fac-144">Репозитории AIP и задания сканирования содержимого</span><span class="sxs-lookup"><span data-stu-id="00fac-144">AIP repositories and content scan jobs</span></span>

<span data-ttu-id="00fac-145">Необходимо создать задание сканирования содержимого AIP и определить репозитории, хранящие файлы, которые должны оцениваться подсистемой защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="00fac-145">You must create an AIP content scan jobs and identify the repositories that host the files that you want to be evaluated by DLP engine.</span></span> <span data-ttu-id="00fac-146">Убедитесь, что правила DLP включены в созданном задании сканирования содержимого AIP.</span><span class="sxs-lookup"><span data-stu-id="00fac-146">Make sure you enable DLP rules in the created AIP content scan job.</span></span>

### <a name="policy-tips"></a><span data-ttu-id="00fac-147">Подсказки политики</span><span class="sxs-lookup"><span data-stu-id="00fac-147">Policy tips</span></span>

<span data-ttu-id="00fac-148">[Подсказки политики](use-notifications-and-policy-tips.md) недоступны в локальном сканере.</span><span class="sxs-lookup"><span data-stu-id="00fac-148">[Policy tips](use-notifications-and-policy-tips.md) are not available in on-premises scanner.</span></span>


### <a name="viewing-dlp-on-premises-scanner-events"></a><span data-ttu-id="00fac-149">Просмотр событий локального сканера защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-149">Viewing DLP on-premises scanner events</span></span>

<span data-ttu-id="00fac-150">Данные локального сканера защиты от потери данных можно просмотреть в [обозревателе действий](data-classification-activity-explorer.md) Центра соответствия требованиям M365.</span><span class="sxs-lookup"><span data-stu-id="00fac-150">You view DLP on-premises scanner data in the M365 Compliance Center [activity explorer](data-classification-activity-explorer.md).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="00fac-151">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="00fac-151">Next steps</span></span>

<span data-ttu-id="00fac-152">Теперь, когда вы узнали о локальном сканере защиты от потери данных, ознакомьтесь со следующим:</span><span class="sxs-lookup"><span data-stu-id="00fac-152">Now that you've learned about DLP on-premises scanner, your next steps are:</span></span>

1. [<span data-ttu-id="00fac-153">Начало работы с локальной сканером защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-153">Get started with the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
2. [<span data-ttu-id="00fac-154">Использование локального сканера защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-154">Use the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="00fac-155">См. также</span><span class="sxs-lookup"><span data-stu-id="00fac-155">See also</span></span>

- [<span data-ttu-id="00fac-156">Начало работы с локальной сканером защиты от потери данных Microsoft</span><span class="sxs-lookup"><span data-stu-id="00fac-156">Getting started with the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="00fac-157">Использование локального сканера защиты от потери данных Microsoft </span><span class="sxs-lookup"><span data-stu-id="00fac-157">Use the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="00fac-158">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-158">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="00fac-159">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="00fac-159">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="00fac-160">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="00fac-160">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)