---
title: Сбор диагностических данных антивируса Microsoft Defender
description: Используйте средство для сбора данных для устранения неполадок антивируса Microsoft Defender
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender av, объект групповой политики, параметр, диагностические данные
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691094"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="1ca81-104">Сбор диагностических данных Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="1ca81-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1ca81-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1ca81-105">**Applies to:**</span></span>

- [<span data-ttu-id="1ca81-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1ca81-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1ca81-107">В этой статье описывается сбор диагностических данных, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок, с которыми вы можете столкнуться при использовании AV Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1ca81-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca81-108">В рамках процесса расследования или ответа можно собрать пакет исследований с устройства.</span><span class="sxs-lookup"><span data-stu-id="1ca81-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="1ca81-109">Вот как: [сбор пакета исследований с устройств.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="1ca81-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="1ca81-110">По крайней мере на двух устройствах, столкнующихся с одной и той же проблемой, получите диагностический файл .cab, предприняв следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1ca81-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="1ca81-111">Откройте версию командной подсказки на уровне администратора следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1ca81-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="1ca81-112">а.</span><span class="sxs-lookup"><span data-stu-id="1ca81-112">a.</span></span> <span data-ttu-id="1ca81-113">Откройте меню **Пуск.**</span><span class="sxs-lookup"><span data-stu-id="1ca81-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="1ca81-114">б.</span><span class="sxs-lookup"><span data-stu-id="1ca81-114">b.</span></span> <span data-ttu-id="1ca81-115">Введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="1ca81-115">Type **cmd**.</span></span> <span data-ttu-id="1ca81-116">Щелкните правой кнопкой мыши **командный запрос** и нажмите **кнопку Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="1ca81-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="1ca81-117">в.</span><span class="sxs-lookup"><span data-stu-id="1ca81-117">c.</span></span> <span data-ttu-id="1ca81-118">Ввод учетных данных администратора или утверждение запроса.</span><span class="sxs-lookup"><span data-stu-id="1ca81-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="1ca81-119">Перейдите к каталогу Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1ca81-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="1ca81-120">По умолчанию это значение равно `C:\Program Files\Windows Defender`.</span><span class="sxs-lookup"><span data-stu-id="1ca81-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca81-121">Если вы работаете с [обновленной версией платформы Защитника Майкрософт,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)запустите ее в `MpCmdRun` следующем расположении: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="1ca81-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="1ca81-122">Введите следующую команду и нажмите **кнопку Ввод**</span><span class="sxs-lookup"><span data-stu-id="1ca81-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="1ca81-123">Создается файл .cab, содержащий различные диагностические журналы.</span><span class="sxs-lookup"><span data-stu-id="1ca81-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="1ca81-124">Расположение файла будет указано в выходе в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="1ca81-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="1ca81-125">По умолчанию расположение `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` является .</span><span class="sxs-lookup"><span data-stu-id="1ca81-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca81-126">Чтобы перенаправить файл кабины на другой путь или долю UNC, используйте следующую команду: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="1ca81-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="1ca81-127">Дополнительные сведения см. в [раздел Перенаправление диагностических данных в раздел UNC.](#redirect-diagnostic-data-to-a-unc-share)</span><span class="sxs-lookup"><span data-stu-id="1ca81-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="1ca81-128">Скопируйте эти файлы .cab в расположение, к нему можно получить доступ с помощью службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1ca81-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="1ca81-129">Примером может быть защищенная паролем папка OneDrive, которую вы можете поделиться с нами.</span><span class="sxs-lookup"><span data-stu-id="1ca81-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="1ca81-130">Если у вас возникла проблема с соответствием требованиям обновления, отправьте сообщение электронной почты с помощью шаблона поддержки обновления и заполните шаблон следующими сведениями: <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a></span><span class="sxs-lookup"><span data-stu-id="1ca81-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="1ca81-131">Перенаправление диагностических данных на долю UNC</span><span class="sxs-lookup"><span data-stu-id="1ca81-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="1ca81-132">Для сбора диагностических данных в центральном репозитории можно указать параметр SupportLogLocation.</span><span class="sxs-lookup"><span data-stu-id="1ca81-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="1ca81-133">Копирует диагностические данные в указанный путь.</span><span class="sxs-lookup"><span data-stu-id="1ca81-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="1ca81-134">Если путь не указан, диагностические данные будут скопированы в расположение, указанное в конфигурации расположения журнала поддержки.</span><span class="sxs-lookup"><span data-stu-id="1ca81-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="1ca81-135">Когда используется параметр SupportLogLocation, в пути назначения будет создана структура папок, как по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="1ca81-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="1ca81-136">поле</span><span class="sxs-lookup"><span data-stu-id="1ca81-136">field</span></span>  | <span data-ttu-id="1ca81-137">Описание</span><span class="sxs-lookup"><span data-stu-id="1ca81-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="1ca81-138">path</span><span class="sxs-lookup"><span data-stu-id="1ca81-138">path</span></span> | <span data-ttu-id="1ca81-139">Путь, указанный в командной строке или извлеченный из конфигурации</span><span class="sxs-lookup"><span data-stu-id="1ca81-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="1ca81-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="1ca81-140">MMDD</span></span> | <span data-ttu-id="1ca81-141">Месяц и день сбора диагностических данных (например, 0530)</span><span class="sxs-lookup"><span data-stu-id="1ca81-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="1ca81-142">имя хозяйского имени</span><span class="sxs-lookup"><span data-stu-id="1ca81-142">hostname</span></span> | <span data-ttu-id="1ca81-143">Имя хозяина устройства, на котором собирались диагностические данные</span><span class="sxs-lookup"><span data-stu-id="1ca81-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="1ca81-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="1ca81-144">HHMM</span></span> | <span data-ttu-id="1ca81-145">Часы и минуты при сборе диагностических данных (например, 1422)</span><span class="sxs-lookup"><span data-stu-id="1ca81-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="1ca81-146">При использовании файла убедитесь, что учетная запись, используемая для сбора диагностического пакета, имеет доступ к файлу записи.</span><span class="sxs-lookup"><span data-stu-id="1ca81-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="1ca81-147">Укажите расположение, где создаются диагностические данные</span><span class="sxs-lookup"><span data-stu-id="1ca81-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="1ca81-148">Вы также можете указать, где будет создан диагностический файл .cab с помощью объекта групповой политики (GPO).</span><span class="sxs-lookup"><span data-stu-id="1ca81-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="1ca81-149">Откройте редактор локальной групповой политики и найдите GPO SupportLogLocation по: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="1ca81-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="1ca81-150">Выберите **Определение пути каталога для копирования файлов журнала поддержки.**</span><span class="sxs-lookup"><span data-stu-id="1ca81-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Снимок экрана редактора локальной групповой политики](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Снимок экрана определения пути для параметра файлов журналов](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="1ca81-153">В редакторе политики выберите **Включено**.</span><span class="sxs-lookup"><span data-stu-id="1ca81-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="1ca81-154">Укажите путь каталога, в котором необходимо скопировать файлы журнала поддержки в поле **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="1ca81-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="1ca81-155">![Снимок экрана настраиваемого параметра путь к каталогам с включенной поддержкой](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="1ca81-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="1ca81-156">Выберите **ОК** или **Применить**.</span><span class="sxs-lookup"><span data-stu-id="1ca81-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ca81-157">См. также</span><span class="sxs-lookup"><span data-stu-id="1ca81-157">See also</span></span>

- [<span data-ttu-id="1ca81-158">Устранение неполадок в антивирусной отчетности Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1ca81-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)