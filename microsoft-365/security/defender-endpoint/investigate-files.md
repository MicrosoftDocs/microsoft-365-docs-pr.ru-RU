---
title: Исследование файлов "Защитник Майкрософт" для конечных точек
description: Используйте параметры исследования, чтобы получить сведения о файлах, связанных с оповещениями, поведением или событиями.
keywords: исследование, исследование, файл, вредоносные действия, мотивация атаки, глубокий анализ, отчет о глубоком анализе
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186069"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="a10ea-104">Исследование файла, связанного с оповещением Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10ea-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a10ea-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a10ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="a10ea-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a10ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a10ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a10ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a10ea-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a10ea-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a10ea-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a10ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="a10ea-110">Изучите сведения о файле, связанном с определенным предупреждением, поведением или событием, чтобы определить, есть ли в файле вредоносные действия, определить мотивацию атаки и понять потенциальную область нарушения.</span><span class="sxs-lookup"><span data-stu-id="a10ea-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="a10ea-111">Существует множество способов доступа к подробной странице профиля определенного файла.</span><span class="sxs-lookup"><span data-stu-id="a10ea-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="a10ea-112">Например, можно использовать функцию поиска, щелкнуть ссылку из дерева процесса **оповещения,** графика инцидентов, временной шкалы **артефактов** или выбрать событие, перечисленное в временной шкале **Устройства.**</span><span class="sxs-lookup"><span data-stu-id="a10ea-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="a10ea-113">После на подробной странице профиля можно переключаться между макетами новых и старых страниц, переключая новую страницу **File.**</span><span class="sxs-lookup"><span data-stu-id="a10ea-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="a10ea-114">В остальной части этой статьи описывается более новая схема страницы.</span><span class="sxs-lookup"><span data-stu-id="a10ea-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="a10ea-115">Сведения можно получить из следующих разделов в представлении файла:</span><span class="sxs-lookup"><span data-stu-id="a10ea-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="a10ea-116">Сведения о файлах, обнаружение вредоносных программ, распространенность файлов</span><span class="sxs-lookup"><span data-stu-id="a10ea-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="a10ea-117">Глубокий анализ</span><span class="sxs-lookup"><span data-stu-id="a10ea-117">Deep analysis</span></span>
- <span data-ttu-id="a10ea-118">Оповещения</span><span class="sxs-lookup"><span data-stu-id="a10ea-118">Alerts</span></span>
- <span data-ttu-id="a10ea-119">Наблюдается в организации</span><span class="sxs-lookup"><span data-stu-id="a10ea-119">Observed in organization</span></span>
- <span data-ttu-id="a10ea-120">Глубокий анализ</span><span class="sxs-lookup"><span data-stu-id="a10ea-120">Deep analysis</span></span>
- <span data-ttu-id="a10ea-121">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="a10ea-121">File names</span></span>

<span data-ttu-id="a10ea-122">Вы также можете принять меры к файлу на этой странице.</span><span class="sxs-lookup"><span data-stu-id="a10ea-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="a10ea-123">Действия файла</span><span class="sxs-lookup"><span data-stu-id="a10ea-123">File actions</span></span>

<span data-ttu-id="a10ea-124">В верхней части страницы профиля, над карточками информации о файлах.</span><span class="sxs-lookup"><span data-stu-id="a10ea-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="a10ea-125">Действия, которые можно выполнить здесь, включают:</span><span class="sxs-lookup"><span data-stu-id="a10ea-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="a10ea-126">Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="a10ea-126">Stop and quarantine</span></span>
- <span data-ttu-id="a10ea-127">Индикатор add/edit</span><span class="sxs-lookup"><span data-stu-id="a10ea-127">Add/edit indicator</span></span>
- <span data-ttu-id="a10ea-128">Скачивание файла</span><span class="sxs-lookup"><span data-stu-id="a10ea-128">Download file</span></span>
- <span data-ttu-id="a10ea-129">Обратитесь к эксперту по угрозам</span><span class="sxs-lookup"><span data-stu-id="a10ea-129">Consult a threat expert</span></span>
- <span data-ttu-id="a10ea-130">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="a10ea-130">Action center</span></span>

<span data-ttu-id="a10ea-131">Дополнительные сведения об этих действиях см. в [материалах Take response action on a file.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="a10ea-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="a10ea-132">Сведения о файлах, обнаружение вредоносных программ и распространенность файлов</span><span class="sxs-lookup"><span data-stu-id="a10ea-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="a10ea-133">Сведения о файлах, инциденты, обнаружение вредоносных программ и карты распространения файлов отображают различные атрибуты о файле.</span><span class="sxs-lookup"><span data-stu-id="a10ea-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="a10ea-134">Вы увидите такие сведения, как MD5 файла, коэффициент обнаружения общего числа вирусов и обнаружение AV Microsoft Defender, а также распространенность файла.</span><span class="sxs-lookup"><span data-stu-id="a10ea-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="a10ea-135">Карта распространенности файлов показывает, где файл был замечен на устройствах в организации и во всем мире.</span><span class="sxs-lookup"><span data-stu-id="a10ea-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="a10ea-136">Различные пользователи могут видеть разные значения на устройствах в *разделе организации* карты распространения файлов.</span><span class="sxs-lookup"><span data-stu-id="a10ea-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="a10ea-137">Это происходит из-за того, что на карте отображаются сведения, основанные на области RBAC, которую имеет пользователь.</span><span class="sxs-lookup"><span data-stu-id="a10ea-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="a10ea-138">Это означает, что если пользователю была предоставлена видимость на определенном наборе устройств, он будет видеть только преобладание файлов на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="a10ea-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Изображение сведений о файлах](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="a10ea-140">Оповещения</span><span class="sxs-lookup"><span data-stu-id="a10ea-140">Alerts</span></span>

<span data-ttu-id="a10ea-141">Вкладка **Alerts** содержит список оповещений, связанных с файлом.</span><span class="sxs-lookup"><span data-stu-id="a10ea-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="a10ea-142">Этот список охватывает большую часть той же информации, что и очередь оповещений, за исключением группы устройств, если она имеется, к которой относится затронутное устройство.</span><span class="sxs-lookup"><span data-stu-id="a10ea-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="a10ea-143">Вы можете выбрать, какие сведения показаны, выбрав настраивать столбцы из панели инструментов над загонами столбцов. </span><span class="sxs-lookup"><span data-stu-id="a10ea-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Изображение оповещений, связанных с разделом файлов](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="a10ea-145">Наблюдается в организации</span><span class="sxs-lookup"><span data-stu-id="a10ea-145">Observed in organization</span></span>

<span data-ttu-id="a10ea-146">Вкладка **Observed в организации** позволяет указать диапазон дат, чтобы увидеть, какие устройства были замечены с файлом.</span><span class="sxs-lookup"><span data-stu-id="a10ea-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="a10ea-147">Эта вкладка будет показывать максимальное число 100 устройств.</span><span class="sxs-lookup"><span data-stu-id="a10ea-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="a10ea-148">Чтобы увидеть _все_ устройства с файлом, экспортировать вкладку в  CSV-файл, выбрав экспорт из меню действий над столбцами столбцов вкладки.</span><span class="sxs-lookup"><span data-stu-id="a10ea-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Изображение последнего наблюдаемого устройства с файлом](images/atp-observed-machines.png)

<span data-ttu-id="a10ea-150">Используйте ползунок или селектор диапазона, чтобы быстро указать период времени, который необходимо проверить на события, связанные с файлом.</span><span class="sxs-lookup"><span data-stu-id="a10ea-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="a10ea-151">Вы можете указать окно времени размером с один день.</span><span class="sxs-lookup"><span data-stu-id="a10ea-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="a10ea-152">Это позволит вам видеть только файлы, которые связывались с этим IP-адресом в то время, резко сокращая ненужные прокрутки и поиск.</span><span class="sxs-lookup"><span data-stu-id="a10ea-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="a10ea-153">Глубокий анализ</span><span class="sxs-lookup"><span data-stu-id="a10ea-153">Deep analysis</span></span>

<span data-ttu-id="a10ea-154">Вкладка **Deep analysis** позволяет отправлять файл для глубокого [анализа,](respond-file-alerts.md#deep-analysis)чтобы узнать больше сведений о поведении файла, а также о его последствиях в организациях.</span><span class="sxs-lookup"><span data-stu-id="a10ea-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="a10ea-155">После отправки файла отчет о глубоком анализе появится на этой вкладке после появления результатов.</span><span class="sxs-lookup"><span data-stu-id="a10ea-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="a10ea-156">Если глубокий анализ ничего не нашел, отчет будет пустым, а пространство результатов останется пустым.</span><span class="sxs-lookup"><span data-stu-id="a10ea-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Изображение вкладки глубокого анализа](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="a10ea-158">Имена файлов</span><span class="sxs-lookup"><span data-stu-id="a10ea-158">File names</span></span>

<span data-ttu-id="a10ea-159">На **вкладке Имена** файлов перечислены все имена, которые были замечены в вашем файле, в организациях.</span><span class="sxs-lookup"><span data-stu-id="a10ea-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Изображение вкладки имен файлов](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="a10ea-161">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a10ea-161">Related topics</span></span>

- [<span data-ttu-id="a10ea-162">Просмотр и организация очереди Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10ea-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="a10ea-163">Управление оповещениями Защитника Майкрософт для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10ea-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="a10ea-164">Исследование оповещений Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10ea-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="a10ea-165">Исследование устройств в списке Устройств конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="a10ea-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="a10ea-166">Исследование IP-адреса, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a10ea-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="a10ea-167">Исследование домена, связанного с оповещением Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a10ea-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="a10ea-168">Исследование учетной записи пользователя в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a10ea-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="a10ea-169">Действия отклика в файле</span><span class="sxs-lookup"><span data-stu-id="a10ea-169">Take response actions on a file</span></span>](respond-file-alerts.md)
