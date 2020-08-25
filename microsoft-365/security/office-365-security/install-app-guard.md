---
title: Application Guard для Office 365 (общедоступная Предварительная версия) для администраторов
keywords: Application Guard, Protection, изоляция, изолированный контейнер, изоляция оборудования
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Получите последнюю версию в разделе изоляция на основе оборудования. Предотвращение текущих и новых атак, таких как эксплойты или вредоносные ссылки, не нарушая продуктивность сотрудников и корпоративную безопасность.
ms.openlocfilehash: d0a89e8f8874c9ad298bf862384019b9e1ace0bf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867504"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="42258-105">Application Guard для Office (общедоступная Предварительная версия) для администраторов</span><span class="sxs-lookup"><span data-stu-id="42258-105">Application Guard for Office (public preview) for admins</span></span>


<span data-ttu-id="42258-106">**Применимо к:** Word, Excel и PowerPoint для Microsoft 365, Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="42258-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

>[!IMPORTANT]
><span data-ttu-id="42258-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="42258-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="42258-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="42258-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="42258-109">Защитник Microsoft Defender Application Guard для Office (Application Guard для Office) помогает предотвратить доступ к доверенным ресурсам для ненадежных файлов, обеспечивая надежную защиту от новых и новых атак.</span><span class="sxs-lookup"><span data-stu-id="42258-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="42258-110">В этой статье администраторы проходят настройку устройств для предварительного просмотра Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="42258-111">Он содержит сведения о требованиях к системе и действиях по установке для включения Application Guard для Office на устройстве.</span><span class="sxs-lookup"><span data-stu-id="42258-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42258-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="42258-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="42258-113">Минимальные требования к оборудованию</span><span class="sxs-lookup"><span data-stu-id="42258-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="42258-114">**ЦП**: 64-разрядный, 4 ядра (физический или виртуальный), расширения виртуализации (Intel VT-x или AMD-V), основной i5 эквивалент или более высокий уровень</span><span class="sxs-lookup"><span data-stu-id="42258-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="42258-115">**Физическая память**: 8 ГБ ОЗУ</span><span class="sxs-lookup"><span data-stu-id="42258-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="42258-116">**Жесткий диск**: 10 ГБ свободного места на системном диске (рекомендуется SSD)</span><span class="sxs-lookup"><span data-stu-id="42258-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="42258-117">Минимальные требования к программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="42258-117">Minimum software requirements</span></span>

* <span data-ttu-id="42258-118">**Windows 10**: Windows 10 Enterprise Edition, Клиентская сборка версии 2004 (20H1) Build 19041</span><span class="sxs-lookup"><span data-stu-id="42258-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="42258-119">**Office**: сборка канала Office Beta версии 2008 16.0.13212 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="42258-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="42258-120">**Пакет обновления**: Windows 10 накопительных обновлений для системы безопасности ( [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782) )</span><span class="sxs-lookup"><span data-stu-id="42258-120">**Update package**: Windows 10 cumulative monthly security updates [KB4566782](https://support.microsoft.com/help/4566782/windows-10-update-kb4566782)</span></span> 

<span data-ttu-id="42258-121">Для получения подробных сведений о требованиях к системе обратитесь к разделу [требования к системе для Application Guard в защитнике Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span><span class="sxs-lookup"><span data-stu-id="42258-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="42258-122">Чтобы узнать больше о сборках Insider Preview для Office, ознакомьтесь со статьей [Начало работы по развертыванию сборок для участников программы предварительной оценки Office](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="42258-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="42258-123">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="42258-123">Licensing requirements</span></span>
* <span data-ttu-id="42258-124">Microsoft 365 в ~ или Microsoft 365 в систему безопасности</span><span class="sxs-lookup"><span data-stu-id="42258-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="42258-125">Развертывание Application Guard для Office</span><span class="sxs-lookup"><span data-stu-id="42258-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="42258-126">Включение Application Guard для Office</span><span class="sxs-lookup"><span data-stu-id="42258-126">Enable Application Guard for Office</span></span>

1.  <span data-ttu-id="42258-127">Загрузите и установите **накопительные пакеты обновления для системы безопасности KB4566782 для Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="42258-127">Download and install **Windows 10 cumulative monthly security updates KB4566782**.</span></span> 

2. <span data-ttu-id="42258-128">Скачайте и установите [**пакет включения Application Guard для Office**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi).</span><span class="sxs-lookup"><span data-stu-id="42258-128">Download and install [**Application Guard for Office Feature enablement package**](https://download.microsoft.com/download/e/4/c/e4c1180a-fcff-462a-8324-4151c44973a8/Windows%20Preview%20-%20WDAG%20Office%20070920%2001.msi).</span></span> <span data-ttu-id="42258-129">Этот пакет устанавливает групповую политику с именем "KB4559004 Issue 001 Preview" в разделе **Конфигурация компьютера \ административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="42258-129">This package installs a group policy called "KB4559004 Issue 001 Preview" under **Computer Configuration\Administrative Templates**.</span></span> <span data-ttu-id="42258-130">Установите для этой групповой политики значение **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="42258-130">Set this group policy  to **Enabled**.</span></span>
     <span data-ttu-id="42258-131">![Редактор локальных групповых политик](../../media/ag01-deploy.png)</span><span class="sxs-lookup"><span data-stu-id="42258-131">![Local Group Policy Editor](../../media/ag01-deploy.png)</span></span>

     ![KB4559004ная ошибка 001 Preview](../../media/ag02-deploy.png)

    <span data-ttu-id="42258-133">Вы также можете напрямую задать следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="42258-133">You can also directly set the following reg keys:</span></span> 
    
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 3457697930 /t REG_DWORD /d 1 
    ```
    ```
    reg add HKLM\SYSTEM\CurrentControlSet\Policies\Microsoft\FeatureManagement\Overrides /v 94539402 /t REG_DWORD /d 1 
    ```
    <span data-ttu-id="42258-134">Затем выполните следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42258-134">Then, run this PowerShell command:</span></span> 
    
    ```powershell
    Get-ScheduledTask -TaskName "ReconcileFeatures" -TaskPath "\Microsoft\Windows\Flighting\FeatureConfig\" | Start-ScheduledTask 
    ```

3.  <span data-ttu-id="42258-135">Выберите **Application Guard в защитнике Microsoft** в разделе Компоненты Windows и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="42258-135">Select **Microsoft Defender Application Guard** under Windows Features and select **OK**.</span></span> <span data-ttu-id="42258-136">При использовании функции Application Guard будет выдаваться запрос на перезагрузку системы.</span><span class="sxs-lookup"><span data-stu-id="42258-136">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="42258-137">Вы можете выполнить перезагрузку сейчас или после шага 4.</span><span class="sxs-lookup"><span data-stu-id="42258-137">You can choose to reboot now or after step 4.</span></span>

    ![Диалоговое окно "компоненты Windows", в котором отображается AG](../../media/ag03-deploy.png)
    
    <span data-ttu-id="42258-139">Кроме того, можно включить эту функцию, выполнив следующую команду PowerShell от имени администратора:</span><span class="sxs-lookup"><span data-stu-id="42258-139">The feature can also be enabled by running the following PowerShell command as administrator:</span></span> 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

4.  <span data-ttu-id="42258-140">Найдите Application Guard в защитнике Майкрософт в групповой политике управляемого режима, расположенном в разделе **Конфигурация компьютера \\ Административные шаблоны \\ Windows компоненты \\ Application Guard в защитнике Microsoft Application Guard**.</span><span class="sxs-lookup"><span data-stu-id="42258-140">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="42258-141">Включите эту политику, задав значение в разделе параметры как **2** или **3** нажмите **кнопку ОК** или **Применить**.</span><span class="sxs-lookup"><span data-stu-id="42258-141">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

    ![Включение AG в управляемом режиме](../../media/ag04-deploy.png)
  
    <span data-ttu-id="42258-143">Кроме того, можно настроить соответствующую политику CSP:</span><span class="sxs-lookup"><span data-stu-id="42258-143">Alternatively, you can set the corresponding CSP policy:</span></span> 

    <span data-ttu-id="42258-144">OMA — URI: **./девице/вендор/мсфт/виндовсдефендераппликатионгуард/Сеттингс/алловвиндовсдефендераппликатионгуард** 
    </span><span class="sxs-lookup"><span data-stu-id="42258-144">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span></span><br><span data-ttu-id="42258-145">Тип данных: **целое число** 
</span><span class="sxs-lookup"><span data-stu-id="42258-145">Data type: **Integer** 
</span></span><br><span data-ttu-id="42258-146">Значение: **2**</span><span class="sxs-lookup"><span data-stu-id="42258-146">Value: **2**</span></span>


5.  <span data-ttu-id="42258-147">Перезагрузите систему.</span><span class="sxs-lookup"><span data-stu-id="42258-147">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="42258-148">Настройка диагностики & обратной связи для отправки полных данных</span><span class="sxs-lookup"><span data-stu-id="42258-148">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="42258-149">Этот шаг гарантирует, что данные, необходимые для определения и устранения проблем, достигнут корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="42258-149">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="42258-150">Выполните следующие действия, чтобы включить диагностику на устройстве с Windows:</span><span class="sxs-lookup"><span data-stu-id="42258-150">Follow these steps to enable diagnostics on your Windows device:</span></span>

1.  <span data-ttu-id="42258-151">Откройте **Параметры** из меню "Пуск".</span><span class="sxs-lookup"><span data-stu-id="42258-151">Open **Settings** from the Start menu.</span></span>

    ![Меню "Пуск"](../../media/ag05-diagnostic.png)

2.  <span data-ttu-id="42258-153">В меню **Параметры Windows**выберите **Конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="42258-153">On **Windows Settings**, select **Privacy**.</span></span>

    ![Меню "Параметры Windows"](../../media/ag06-diagnostic.png)

3.  <span data-ttu-id="42258-155">В разделе Конфиденциальность выберите пункт **диагностика & отзывов** и выберите **дополнительные диагностические данные**.</span><span class="sxs-lookup"><span data-stu-id="42258-155">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

    ![Меню диагностики и обратной связи](../../media/ag07a-diagnostic.png)

<span data-ttu-id="42258-157">Для получения дополнительных сведений о настройке параметров диагностики Windows, обратитесь к разделу [Настройка диагностических данных Windows в Организации](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span><span class="sxs-lookup"><span data-stu-id="42258-157">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="42258-158">Убедитесь, что Application Guard для Office включено и работает.</span><span class="sxs-lookup"><span data-stu-id="42258-158">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="42258-159">Перед подтверждением того, что Application Guard для Office включено, запустите Word, Excel или PowerPoint на устройстве с развернутыми политиками.</span><span class="sxs-lookup"><span data-stu-id="42258-159">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="42258-160">Убедитесь, что приложение Office активировано.</span><span class="sxs-lookup"><span data-stu-id="42258-160">Make sure Office is activated.</span></span> <span data-ttu-id="42258-161">Для активации продукта Office может потребоваться использовать рабочий идентификатор.</span><span class="sxs-lookup"><span data-stu-id="42258-161">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="42258-162">Чтобы убедиться, что Application Guard для Office теперь включено, запустите Word, Excel или PowerPoint и откройте документ, не являющийся доверенным.</span><span class="sxs-lookup"><span data-stu-id="42258-162">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="42258-163">Например, можно открыть документ, загруженный из Интернета или из вложения в сообщение электронной почты от кого-либо из пользователей, не входящих в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="42258-163">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="42258-164">При первом запуске ненадежного файла вы можете увидеть экран-заставку Office, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42258-164">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="42258-165">Он может отображаться некоторое время, пока не будет активирован Application Guard для Office и открыт файл.</span><span class="sxs-lookup"><span data-stu-id="42258-165">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="42258-166">Последующие запуска недоверенных файлов должны выполняться быстрее.</span><span class="sxs-lookup"><span data-stu-id="42258-166">Subsequent launches of untrusted files should be faster.</span></span>

![Экран-заставка приложения Office](../../media/ag08-confirm.png)


<span data-ttu-id="42258-168">После открытия файл должен отображать несколько визуальных индикаторов, которые файл был открыт в Application Guard для Office:</span><span class="sxs-lookup"><span data-stu-id="42258-168">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="42258-169">Выноска на ленте</span><span class="sxs-lookup"><span data-stu-id="42258-169">A callout in the ribbon</span></span>

    ![Файл doc с примечанием для небольшой защиты приложений](../../media/ag09-confirm.png)
* <span data-ttu-id="42258-171">Значок приложения с защитой на панели задач</span><span class="sxs-lookup"><span data-stu-id="42258-171">The application icon with a shield in the taskbar</span></span> 

    ![Значок на панели задач](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a><span data-ttu-id="42258-173">Настройка Application Guard для Office</span><span class="sxs-lookup"><span data-stu-id="42258-173">Configure Application Guard for Office</span></span>
<span data-ttu-id="42258-174">В Office поддерживаются следующие политики, позволяющие настроить возможности Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-174">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="42258-175">Эти политики можно настроить с помощью групповых политик или через службу Microsoft Cloud Policy.</span><span class="sxs-lookup"><span data-stu-id="42258-175">These policies can be configured through Group policies or through the Office cloud policy service.</span></span> 

>[!NOTE] 
> <span data-ttu-id="42258-176">Эти политики скоро станут доступны.</span><span class="sxs-lookup"><span data-stu-id="42258-176">These policies will become available soon.</span></span>
><span data-ttu-id="42258-177">Кроме того, Настройка этих политик может отключить некоторые функциональные возможности для файлов, открытых в Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-177">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

| <span data-ttu-id="42258-178">Политика</span><span class="sxs-lookup"><span data-stu-id="42258-178">Policy</span></span>                                                                          | <span data-ttu-id="42258-179">Описание</span><span class="sxs-lookup"><span data-stu-id="42258-179">Description</span></span>                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="42258-180">Отключение Application Guard для Office</span><span class="sxs-lookup"><span data-stu-id="42258-180">Disable Application Guard for Office</span></span>                                            | <span data-ttu-id="42258-181">При включении этой политики в Word, Excel и PowerPoint будет использоваться защищенный контейнер изоляции просмотра вместо Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-181">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="42258-182">С помощью этой политики можно временно отключить Application Guard для Office при наличии проблем, связанных с выходом из пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="42258-182">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>                                  |
| <span data-ttu-id="42258-183">Отключение копирования и вставки для документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-183">Disable copy/paste for documents opened in Application Guard</span></span>                    | <span data-ttu-id="42258-184">Включение этой политики не позволит пользователю копировать и вставлять контент из документа, открытого в Application Guard для Office, в документ, Открытый за пределами приложения.</span><span class="sxs-lookup"><span data-stu-id="42258-184">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>                                                                                                                                   |
| <span data-ttu-id="42258-185">Запретить пользователям удалять защиту Application Guard для файлов</span><span class="sxs-lookup"><span data-stu-id="42258-185">Prevent users from removing Application Guard protection on files</span></span>               | <span data-ttu-id="42258-186">Включение этой политики удалит параметр (в интерфейсе приложений Office), чтобы отключить защиту Application Guard или открыть файл за пределами Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-186">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <br><br><span data-ttu-id="42258-187">**Примечание:** Пользователи по-прежнему могут обойти эту политику, вручную удалив свойство метки веб-сайта из файла или переместив документ в надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="42258-187">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span> |
| <span data-ttu-id="42258-188">Ограничение печати документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-188">Restrict printing from documents opened in Application Guard</span></span>                    | <span data-ttu-id="42258-189">Включение этой политики ограничит принтеры, на которых пользователь может выполнять печать, из файла, открытого в Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-189">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="42258-190">Например, вы можете использовать эту политику, чтобы ограничить пользователям печать только в PDF-файл.</span><span class="sxs-lookup"><span data-stu-id="42258-190">For example, you can use this policy to restrict users to only print to PDF.</span></span>                              |
| <span data-ttu-id="42258-191">Отключение доступа к камере и микрофону для документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-191">Turn off camera and microphone access for documents opened in Application Guard</span></span> | <span data-ttu-id="42258-192">Включение этой политики приведет к удалению доступа Office к камере и микрофону внутри Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-192">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>                                                                                                                                                                                                     |
>[!NOTE] 
><span data-ttu-id="42258-193">Для вступления в силу следующих политик необходимо выйти из системы и повторно войти в Windows.</span><span class="sxs-lookup"><span data-stu-id="42258-193">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
> 
> *  <span data-ttu-id="42258-194">Отключение копирования и вставки для документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-194">Disable copy/paste for documents opened in Application Guard</span></span>
>*  <span data-ttu-id="42258-195">Ограничение печати документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-195">Restrict printing for documents opened in Application Guard</span></span>
> *  <span data-ttu-id="42258-196">Отключение доступа к камерам и микрофонам для документов, открытых в Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-196">Turn off camera and mic access to documents opened in Application Guard</span></span>


## <a name="submit-feedback"></a><span data-ttu-id="42258-197">Отправить отзыв</span><span class="sxs-lookup"><span data-stu-id="42258-197">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="42258-198">Отправка отзывов через центр отзывов</span><span class="sxs-lookup"><span data-stu-id="42258-198">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="42258-199">Если при запуске Application Guard для Office возникли проблемы, рекомендуется отправить отзыв через центр отзывов:</span><span class="sxs-lookup"><span data-stu-id="42258-199">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1.  <span data-ttu-id="42258-200">Откройте **приложение центра отзывов** и войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="42258-200">Open the **Feedback Hub app** and sign in.</span></span>

2.  <span data-ttu-id="42258-201">Если при запуске Application Guard выводится диалоговое окно с сообщением об ошибке, выберите в диалоговом окне сообщения об ошибке пункт **Report** , чтобы начать новую отправку отзывов.</span><span class="sxs-lookup"><span data-stu-id="42258-201">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="42258-202">В противном случае перейдите к <https://aka.ms/wdagoffice-fb> разделу, чтобы выбрать правильную категорию Application Guard, а затем нажмите кнопку **+ Добавить новую обратную связь** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="42258-202">Otherwise, navigate to <https://aka.ms/wdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3.  <span data-ttu-id="42258-203">Заполните поле **сводка отзыва** , если оно еще не заполнено.</span><span class="sxs-lookup"><span data-stu-id="42258-203">Fill in the **Summarize your feedback** box if it isn’t already filled in for you.</span></span>

4.  <span data-ttu-id="42258-204">Заполните поле **Подробнее в подробном подробностях** , указав подробное описание возникшей вами ситуации и действия, которые вы сделали, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42258-204">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5.  <span data-ttu-id="42258-205">Выберите всплывающее сообщение рядом с элементом проблема.</span><span class="sxs-lookup"><span data-stu-id="42258-205">Select the bubble next to Problem.</span></span> <span data-ttu-id="42258-206">Убедитесь, что выбрана категория **безопасность и конфиденциальность \> защитник Microsoft Defender Application Guard — Office**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42258-206">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6.  <span data-ttu-id="42258-207">Выберите **создать отзыв**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="42258-207">Select **New feedback**, then **Next**.</span></span>

7.  <span data-ttu-id="42258-208">Сбор трассировок о возникшей ошибке:</span><span class="sxs-lookup"><span data-stu-id="42258-208">Collect traces about the issue:</span></span>

    1. <span data-ttu-id="42258-209">Разверните элемент **повторно создать** плитку с проблемой.</span><span class="sxs-lookup"><span data-stu-id="42258-209">Expand the **Recreate my problem** tile.</span></span>

    2.  <span data-ttu-id="42258-210">Если проблема возникает во время выполнения Application Guard, откройте экземпляр Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-210">If the issue you’re experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="42258-211">Это позволяет собирать дополнительные трассировки в контейнере Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-211">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

    3.  <span data-ttu-id="42258-212">Выберите **начать запись** и дождитесь, пока плитка не перестанет вращаться, а затем *остановите запись*.</span><span class="sxs-lookup"><span data-stu-id="42258-212">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

    4.  <span data-ttu-id="42258-213">Полное воспроизведение проблемы с Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-213">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="42258-214">Это может быть попытка запустить экземпляр Application Guard и подождать, пока она не будет пройдена, или воссоздать ошибку в работающем экземпляре Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-214">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

    5.  <span data-ttu-id="42258-215">Выберите плитку **остановить запись** .</span><span class="sxs-lookup"><span data-stu-id="42258-215">Select the **Stop recording** tile.</span></span>

    6.  <span data-ttu-id="42258-216">Сохраните все запущенные экземпляры Application Guard в любом открытом экземпляре (даже до нескольких минут после отправки), чтобы также можно было собрать диагностические сведения о контейнере.</span><span class="sxs-lookup"><span data-stu-id="42258-216">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8.  <span data-ttu-id="42258-217">Присоедините все соответствующие снимки экрана или файлы, связанные с проблемой.</span><span class="sxs-lookup"><span data-stu-id="42258-217">Attach any relevant screenshots or files related to the problem.</span></span>

9.  <span data-ttu-id="42258-218">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="42258-218">Select **Submit**.</span></span>



### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="42258-219">Отправка отзывов с помощью голосовых вызовов пользователей Office</span><span class="sxs-lookup"><span data-stu-id="42258-219">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="42258-220">Вы также можете отправить отзыв в Office, если проблема возникает при открытии документов Office в Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-220">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="42258-221">Сведения о том, как отправить отзыв, можно найти в [руководстве по предварительной работе Office](https://insider.office.com/handbook) .</span><span class="sxs-lookup"><span data-stu-id="42258-221">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a><span data-ttu-id="42258-222">Интеграция с защитником Майкрософт и пакетом Office ATP</span><span class="sxs-lookup"><span data-stu-id="42258-222">Integration with Microsoft Defender ATP and Office ATP</span></span>

<span data-ttu-id="42258-223">Application Guard для Office интегрировано с авансовым защитником Майкрософт (ATP), чтобы обеспечить мониторинг и оповещение о вредоносных действиях, происходящих в изолированной среде.</span><span class="sxs-lookup"><span data-stu-id="42258-223">Application Guard for Office is integrated with Microsoft Defender Advance Threat Protection (ATP) to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="42258-224">Пакет ATP для защитника Майкрософт — это платформа безопасности, позволяющая корпоративным сетям предотвращать, обнаруживать и отвечать на дополнительные угрозы.</span><span class="sxs-lookup"><span data-stu-id="42258-224">Microsoft Defender ATP is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="42258-225">Для получения дополнительных сведений об этой платформе посетите страницу [Advanced Threat Protection в защитнике Майкрософт](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) .</span><span class="sxs-lookup"><span data-stu-id="42258-225">For more details about this platform, visit the [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="42258-226">Узнайте больше о переносе устройств на эту платформу на [встроенных устройствах в службу Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span><span class="sxs-lookup"><span data-stu-id="42258-226">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender ATP service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="42258-227">Вы также можете настроить Office 365 ATP для работы с пакетом ATP для защитника Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42258-227">You can also configure Office 365 ATP to work with Microsoft Defender ATP.</span></span> <span data-ttu-id="42258-228">Обратитесь к разделу [Интеграция Office 365 ATP с защитником Microsoft для пакета ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="42258-228">Refer to [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="42258-229">Ограничения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="42258-229">Limitations and considerations</span></span>

* <span data-ttu-id="42258-230">Application Guard для Office — это ограниченный режим, который изолирует недоверенные документы от доступа к доверенным корпоративным ресурсам, интрасети, удостоверению пользователя и произвольным файлам, присутствующим на компьютере.</span><span class="sxs-lookup"><span data-stu-id="42258-230">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="42258-231">В результате, если пользователь пытается получить доступ к компоненту, который имеет зависимость от такого доступа, например, при вставке изображения из локального файла на диске произойдет ошибка, и будет выдаваться запрос, подобный показанному ниже.</span><span class="sxs-lookup"><span data-stu-id="42258-231">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="42258-232">Чтобы разрешить недоверенному документу доступ к доверенным ресурсам, пользователи должны удалить защиту Application Guard из документа.</span><span class="sxs-lookup"><span data-stu-id="42258-232">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

    ![Диалоговое окно с сообщением о том, что для обеспечения безопасности эта функция недоступна](../../media/ag10-limitations.png)

    >[!NOTE]    
    ><span data-ttu-id="42258-234">Посоветуйте пользователям удалить защиту только в том случае, если они доверяют файлу и источнику или откуда он поступил.</span><span class="sxs-lookup"><span data-stu-id="42258-234">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="42258-235">Активное содержимое документов, таких как макросы и элементы управления ActiveX, отключено в Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-235">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="42258-236">Для включения активного содержимого пользователям необходимо удалить защиту Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-236">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="42258-237">Недоверенные файлы, открытые из общих сетевых ресурсов или файлов, предоставленных из OneDrive, OneDrive для бизнеса или SharePoint Online из другой организации, открываются в Application Guard только для чтения.</span><span class="sxs-lookup"><span data-stu-id="42258-237">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="42258-238">Пользователи могут сохранить локальную копию таких файлов, чтобы продолжить работу в контейнере, или отключить защиту для непосредственной работы с исходным файлом.</span><span class="sxs-lookup"><span data-stu-id="42258-238">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="42258-239">Файлы, защищенные службой управления правами на доступ к данным (IRM), продолжают открываться в режиме защищенного просмотра.</span><span class="sxs-lookup"><span data-stu-id="42258-239">Files that are protected by Information Rights Management (IRM) continue to   open in Protected View.</span></span>
* <span data-ttu-id="42258-240">Все настройки приложений Office в Application Guard для Office не будут сохранены после выхода пользователя из системы и повторного входа в систему или перезагрузки устройства.</span><span class="sxs-lookup"><span data-stu-id="42258-240">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span> 

* <span data-ttu-id="42258-241">Специальные возможности для файлов, открытых в Application Guard для Office, доступны только в средствах специальных возможностей, которые используют модель UIA Framework.</span><span class="sxs-lookup"><span data-stu-id="42258-241">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="42258-242">Сетевое подключение необходимо для первого запуска Application Guard после установки.</span><span class="sxs-lookup"><span data-stu-id="42258-242">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="42258-243">Это необходимо для проверки лицензии приложением Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-243">This is required for Application Guard to validate the license.</span></span>
* <span data-ttu-id="42258-244">В разделе сведения о документе *Последнее изменение* свойства может отображать вдагутилитяккаунт в качестве пользователя.</span><span class="sxs-lookup"><span data-stu-id="42258-244">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="42258-245">Это анонимный пользователь, настроенный в Application Guard в соответствии с тем, что удостоверение пользователя на рабочем столе не предоставляется в контейнере Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-245">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span> 

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="42258-246">Оптимизация производительности для Application Guard</span><span class="sxs-lookup"><span data-stu-id="42258-246">Performance optimizations for Application Guard</span></span> 

<span data-ttu-id="42258-247">В этом разделе представлен обзор оптимизации производительности, используемой в Application Guard для Office.</span><span class="sxs-lookup"><span data-stu-id="42258-247">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="42258-248">Эта информация поможет администраторам диагностировать отчеты от пользователей, связанных с производительностью Office или всей системы, когда включено Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-248">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span> 

<span data-ttu-id="42258-249">Application Guard использует виртуализованный контейнер для изоляции документов, не заслуживающих доверия, от системы.</span><span class="sxs-lookup"><span data-stu-id="42258-249">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="42258-250">Процесс создания контейнера и настройки контейнера Application Guard для открытия документов Office влияет на производительность, что может негативно повлиять на работу пользователей, когда пользователи открывают ненадежный документ.</span><span class="sxs-lookup"><span data-stu-id="42258-250">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span> 


<span data-ttu-id="42258-251">Чтобы предоставить пользователям доступ к ожидаемому открытому файлу, Application Guard использует логику для предварительного создания контейнера, если в системе выполняется следующий эвристический процесс: пользователь открыл файл в режиме защищенного просмотра или Application Guard за прошедшие 28 дней.</span><span class="sxs-lookup"><span data-stu-id="42258-251">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span> 

<span data-ttu-id="42258-252">При достижении этого эвристического алгоритма Office будет предварительно создать контейнер Application Guard для пользователя после входа в Windows.</span><span class="sxs-lookup"><span data-stu-id="42258-252">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="42258-253">При выполнении этой операции, выполняемой перед созданием, может наблюдаться снижение производительности системы.</span><span class="sxs-lookup"><span data-stu-id="42258-253">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="42258-254">Это будет устранено, как только завершится операция.</span><span class="sxs-lookup"><span data-stu-id="42258-254">This will resolve as soon as the operation completes.</span></span> 


>[!NOTE] 
><span data-ttu-id="42258-255">Рекомендации, необходимые для применения эвристического алгоритма для предварительного создания контейнера, создаются приложениями Office по мере их использования пользователями.</span><span class="sxs-lookup"><span data-stu-id="42258-255">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="42258-256">Если пользователь устанавливает Office в новой системе, где включено Application Guard, Office не будет предварительно создавать контейнер до тех пор, пока пользователь не откроет ненадежный документ в системе.</span><span class="sxs-lookup"><span data-stu-id="42258-256">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="42258-257">Пользователь будет видеть, что этот первый файл занимает больше времени, чем открытие в Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-257">The user will observe that this first file takes longer to open in Application Guard.</span></span> 

## <a name="known-issues-in-preview"></a><span data-ttu-id="42258-258">Известные проблемы в предварительной версии</span><span class="sxs-lookup"><span data-stu-id="42258-258">Known issues in preview</span></span>

* <span data-ttu-id="42258-259">Щелчок по веб-ссылкам ( ```http``` или ```https``` ) не открывает браузер.</span><span class="sxs-lookup"><span data-stu-id="42258-259">Clicking on web links (```http``` or ```https```) does not open the browser.</span></span> 
* <span data-ttu-id="42258-260">Обновления .NET приводят к сбою открытия файлов в Application Guard.</span><span class="sxs-lookup"><span data-stu-id="42258-260">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="42258-261">В качестве обходного пути пользователи могут выполнить перезагрузку устройства при обнаружении этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="42258-261">As a workaround, users can reboot their device when this issue is encountered.</span></span>
    <span data-ttu-id="42258-262">Узнайте больше об этой проблемы [при получении сообщения об ошибке при попытке открыть Application Guard в Защитнике Windows или в песочнице Windows](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span><span class="sxs-lookup"><span data-stu-id="42258-262">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
