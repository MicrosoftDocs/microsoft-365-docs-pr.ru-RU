---
title: Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"
description: Настройка и проверка подключения к облачной службе защиты от антивирусных программ Microsoft Defender.
keywords: антивирус, антивирус Microsoft Defender, антивирусные программы, безопасность, защитник, облако, агрессивность, уровень защиты
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6218bc32690ca42c06b5606d8a3922f6fc5c7307
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765159"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="86760-104">Настройка и проверка сетевого подключения антивирусной программы "Защитник Windows"</span><span class="sxs-lookup"><span data-stu-id="86760-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="86760-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="86760-105">**Applies to:**</span></span>

- [<span data-ttu-id="86760-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="86760-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="86760-107">Чтобы обеспечить надстройку облачной защиты от антивируса Microsoft Defender, необходимо настроить сеть, чтобы разрешить подключение между конечными точками и определенными серверами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="86760-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="86760-108">В этой статье перечислены подключения, которые необходимо разрешить, например с помощью правил брандмауэра, и перечислены инструкции по проверке подключения.</span><span class="sxs-lookup"><span data-stu-id="86760-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="86760-109">Правильная настройка защиты позволяет получить наилучшее значение от облачных служб защиты.</span><span class="sxs-lookup"><span data-stu-id="86760-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="86760-110">Некоторые сведения о подключении к сети см. в публикации "Важные изменения в конечной точке [Службы](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) активной защиты Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="86760-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="86760-111">Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки [в demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что работают следующие функции:</span><span class="sxs-lookup"><span data-stu-id="86760-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="86760-112">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="86760-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="86760-113">Быстрое обучение (включая блок с первого взгляда)</span><span class="sxs-lookup"><span data-stu-id="86760-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="86760-114">Блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="86760-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="86760-115">Разрешить подключение к облачной облачной службе Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="86760-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="86760-116">Облачная служба антивирусной защиты Microsoft Defender обеспечивает быструю и мощную защиту конечных точек.</span><span class="sxs-lookup"><span data-stu-id="86760-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="86760-117">Включение облачной службы защиты является необязательным, однако она настоятельно рекомендуется, так как обеспечивает важную защиту от вредоносных программ в конечных точках и в сети.</span><span class="sxs-lookup"><span data-stu-id="86760-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="86760-118">Облачная служба антивирусной защиты Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки.</span><span class="sxs-lookup"><span data-stu-id="86760-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="86760-119">Несмотря на то, что она называется облачной службой, она не просто обеспечивает защиту файлов, хранимых в облаке, а использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="86760-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="86760-120">Сведения о включив службу в intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell или отдельных клиентах в приложении Windows Security, см. в материале Enable [cloud-delivered protection.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="86760-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="86760-121">После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключение между ней и конечными точками.</span><span class="sxs-lookup"><span data-stu-id="86760-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="86760-122">Поскольку ваша защита является облачной службой, компьютеры должны иметь доступ к Интернету и получать доступ к службам машинного обучения Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="86760-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="86760-123">Не исключайте URL-адрес `*.blob.core.windows.net` любого вида сетевой проверки.</span><span class="sxs-lookup"><span data-stu-id="86760-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="86760-124">В таблице ниже перечислены службы и связанные с ними URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="86760-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="86760-125">Убедитесь, что нет брандмауэра или правил фильтрации сети, отказывающих в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них (за исключением `*.blob.core.windows.net` URL-адреса).</span><span class="sxs-lookup"><span data-stu-id="86760-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="86760-126">Ниже приведены URL-адреса, использующие порт 443 для связи.</span><span class="sxs-lookup"><span data-stu-id="86760-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="86760-127">**Служба**</span><span class="sxs-lookup"><span data-stu-id="86760-127">**Service**</span></span>| <span data-ttu-id="86760-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="86760-128">**Description**</span></span> |<span data-ttu-id="86760-129">**URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="86760-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="86760-130">Облачная служба защиты от антивируса Microsoft Defender, также именуемая Службой активной защиты Microsoft (MAPS)</span><span class="sxs-lookup"><span data-stu-id="86760-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="86760-131">Используется антивирусом Microsoft Defender для обеспечения облачной защиты</span><span class="sxs-lookup"><span data-stu-id="86760-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="86760-132">Служба обновления Майкрософт (MU)</span><span class="sxs-lookup"><span data-stu-id="86760-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="86760-133">Служба обновления Windows (WU)</span><span class="sxs-lookup"><span data-stu-id="86760-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="86760-134">Сведения о безопасности и обновления продуктов</span><span class="sxs-lookup"><span data-stu-id="86760-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="86760-135">Подробные сведения [см. в материале Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="86760-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="86760-136">Сведения о безопасности обновляют альтернативное расположение загрузки (ADL)</span><span class="sxs-lookup"><span data-stu-id="86760-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="86760-137">Альтернативное расположение для обновлений антивирусной безопасности Microsoft Defender, если установленная разведка безопасности устарела (7 или более дней)</span><span class="sxs-lookup"><span data-stu-id="86760-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="86760-138">Хранение отправки вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="86760-138">Malware submission storage</span></span>|<span data-ttu-id="86760-139">Отправка расположения для файлов, отправленных в Корпорацию Майкрософт с помощью формы отправки или автоматической отправки образца</span><span class="sxs-lookup"><span data-stu-id="86760-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="86760-140">Список отзыва сертификатов (CRL)</span><span class="sxs-lookup"><span data-stu-id="86760-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="86760-141">Используется Windows при создании подключения SSL к MAPS для обновления CRL</span><span class="sxs-lookup"><span data-stu-id="86760-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="86760-142">Магазин символов</span><span class="sxs-lookup"><span data-stu-id="86760-142">Symbol Store</span></span>|<span data-ttu-id="86760-143">Используется антивирусом Microsoft Defender для восстановления определенных критически важных файлов во время потоков исправлений</span><span class="sxs-lookup"><span data-stu-id="86760-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="86760-144">Клиент универсальной телеметрии</span><span class="sxs-lookup"><span data-stu-id="86760-144">Universal Telemetry Client</span></span>| <span data-ttu-id="86760-145">Используется Windows для отправки диагностических данных клиента; Антивирус Microsoft Defender использует телеметрию для мониторинга качества продуктов</span><span class="sxs-lookup"><span data-stu-id="86760-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="86760-146">Обновление использует SSL (TCP Port 443) для скачивания манифестов и отправки диагностических данных в Корпорацию Майкрософт, которая использует следующие конечные точки DNS:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="86760-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="86760-147">Проверка подключений между сетью и облаком</span><span class="sxs-lookup"><span data-stu-id="86760-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="86760-148">Разрешив указанные выше URL-адреса, вы можете проверить, подключены ли вы к облачной службе антивируса Microsoft Defender и правильно отчитываться и получать сведения, чтобы обеспечить полную защиту.</span><span class="sxs-lookup"><span data-stu-id="86760-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="86760-149">**Используйте средство cmdline для проверки облачной защиты:**</span><span class="sxs-lookup"><span data-stu-id="86760-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="86760-150">Чтобы убедиться, что ваша сеть может взаимодействовать с облачной службой антивирусных программ Microsoft Defender, используйте следующий `mpcmdrun.exe` аргумент:</span><span class="sxs-lookup"><span data-stu-id="86760-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="86760-151">Необходимо открыть версию командной подсказки на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="86760-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="86760-152">Щелкните правой кнопкой мыши элемент в меню "Пуск", нажмите кнопку **Запустить** в качестве администратора и нажмите **кнопку Да** по запросу разрешений.</span><span class="sxs-lookup"><span data-stu-id="86760-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="86760-153">Эта команда будет работать только в Windows 10, версии 1703 или выше.</span><span class="sxs-lookup"><span data-stu-id="86760-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="86760-154">Дополнительные сведения см. в [веб-сайте Управление](command-line-arguments-microsoft-defender-antivirus.md)антивирусом Microsoft Defender с помощью средства mpcmdrun.exe командной линии.</span><span class="sxs-lookup"><span data-stu-id="86760-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="86760-155">**Попытка скачать поддельный файл вредоносных программ из Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="86760-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="86760-156">Вы можете скачать пример файла, который антивирус Microsoft Defender будет обнаруживать и блокировать, если вы правильно подключены к облаку.</span><span class="sxs-lookup"><span data-stu-id="86760-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="86760-157">Скачайте файл, посетив [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="86760-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="86760-158">Этот файл не является фактическим вредоносным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="86760-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="86760-159">Это поддельный файл, который предназначен для проверки правильного подключения к облаку.</span><span class="sxs-lookup"><span data-stu-id="86760-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="86760-160">Если вы подключены должным образом, вы увидите предупреждение о антивирусном оповещении Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="86760-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="86760-161">Если вы используете Microsoft Edge, вы также увидите сообщение уведомления:</span><span class="sxs-lookup"><span data-stu-id="86760-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge информирует пользователя о обнаружении вредоносных программ](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="86760-163">Аналогичное сообщение возникает, если вы используете Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="86760-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Антивирусное уведомление Microsoft Defender, информирующие пользователя о обнаружении вредоносных программ](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="86760-165">Кроме того, в разделе  История сканирования в приложении Windows Security вы также увидите обнаружение под карантинными угрозами: </span><span class="sxs-lookup"><span data-stu-id="86760-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="86760-166">Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="86760-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="86760-167">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем метку **истории сканирования:**</span><span class="sxs-lookup"><span data-stu-id="86760-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Снимок экрана метки истории сканирования в приложении Безопасности Windows](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="86760-169">В разделе **Карантин** угроз выберите **См.** полную историю обнаружения поддельных вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="86760-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="86760-170">Версии Windows 10 до версии 1703 имеют другой пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="86760-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="86760-171">См. [антивирус Microsoft Defender в приложении Windows Security.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="86760-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="86760-172">В журнале событий Windows также будет Защитник Windows [ИД события клиента 1116](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="86760-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="86760-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="86760-173">Related articles</span></span>

- [<span data-ttu-id="86760-174">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="86760-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="86760-175">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="86760-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="86760-176">Аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="86760-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="86760-177">Важные изменения конечной точки Службы активной защиты Майкрософт</span><span class="sxs-lookup"><span data-stu-id="86760-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)