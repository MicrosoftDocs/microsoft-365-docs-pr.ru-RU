---
title: Сбор диагностических данных для обновления соответствия требованиям и Защитник Windows антивирусная программа в Microsoft Defender
description: Используйте средство для сбора данных для устранения неполадок с обновлением соответствия требованиям при использовании добавления антивирусная программа в Microsoft Defender оценки
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903736"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a><span data-ttu-id="f22fa-104">Сбор диагностических данных о соответствии требованиям для антивирусная программа в Microsoft Defender оценки</span><span class="sxs-lookup"><span data-stu-id="f22fa-104">Collect update compliance diagnostic data for Microsoft Defender Antivirus assessment</span></span>


<span data-ttu-id="f22fa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f22fa-105">**Applies to:**</span></span>

- [<span data-ttu-id="f22fa-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f22fa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f22fa-107">В этой статье описывается сбор диагностических данных, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения проблем, с которыми вы можете столкнуться при использовании раздела антивирусная программа в Microsoft Defender оценки в надстройки Update Compliance.</span><span class="sxs-lookup"><span data-stu-id="f22fa-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender Antivirus Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="f22fa-108">Перед попыткой этого процесса убедитесь, что вы читали отчеты антивирусная программа в Microsoft Defender устранения неполадок, [](troubleshoot-reporting.md)выполнили все необходимые условия и предприняли любые другие предложенные действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="f22fa-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="f22fa-109">По крайней мере на двух устройствах, которые не сообщают или не отображаются в соответствии с обновлением, .cab диагностический файл, предприняв следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f22fa-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="f22fa-110">Откройте версию командной подсказки на уровне администратора следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f22fa-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="f22fa-111">а.</span><span class="sxs-lookup"><span data-stu-id="f22fa-111">a.</span></span> <span data-ttu-id="f22fa-112">Откройте меню **Пуск.**</span><span class="sxs-lookup"><span data-stu-id="f22fa-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="f22fa-113">б.</span><span class="sxs-lookup"><span data-stu-id="f22fa-113">b.</span></span> <span data-ttu-id="f22fa-114">Введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="f22fa-114">Type **cmd**.</span></span> <span data-ttu-id="f22fa-115">Щелкните правой кнопкой мыши **командную подсказку** и выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="f22fa-115">Right-click on **Command Prompt** and then select **Run as administrator**.</span></span>

    <span data-ttu-id="f22fa-116">в.</span><span class="sxs-lookup"><span data-stu-id="f22fa-116">c.</span></span> <span data-ttu-id="f22fa-117">Укажите учетные данные администратора или одобрить запрос.</span><span class="sxs-lookup"><span data-stu-id="f22fa-117">Specify administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="f22fa-118">Перейдите к Защитник Windows каталогу.</span><span class="sxs-lookup"><span data-stu-id="f22fa-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="f22fa-119">По умолчанию это значение равно `C:\Program Files\Windows Defender`.</span><span class="sxs-lookup"><span data-stu-id="f22fa-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="f22fa-120">Введите следующую команду и нажмите **кнопку Ввод**</span><span class="sxs-lookup"><span data-stu-id="f22fa-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="f22fa-121">Будет .cab файл, содержащий различные диагностические журналы.</span><span class="sxs-lookup"><span data-stu-id="f22fa-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="f22fa-122">Расположение файла будет указано в выходе в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="f22fa-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="f22fa-123">По умолчанию расположение `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` является .</span><span class="sxs-lookup"><span data-stu-id="f22fa-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="f22fa-124">Скопируйте .cab файлы в расположение, к нему можно получить доступ с помощью службы поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f22fa-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="f22fa-125">Примером может быть защищенная паролем папка OneDrive которую вы можете поделиться с нами.</span><span class="sxs-lookup"><span data-stu-id="f22fa-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="f22fa-126">Отправьте сообщение электронной почты <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">с</a>помощью шаблона поддержки обновления и заполните шаблон следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="f22fa-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">update compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="f22fa-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f22fa-127">See also</span></span>

- [<span data-ttu-id="f22fa-128">Устранение Защитник Windows антивирусная программа в Microsoft Defender отчетов</span><span class="sxs-lookup"><span data-stu-id="f22fa-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)