---
title: Самостоятельная регистрация новых устройств
description: Самостоятельное регистрация устройств для управления настольными компьютерами, управляемыми Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557557"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="aedf5-103">Самостоятельная регистрация новых устройств</span><span class="sxs-lookup"><span data-stu-id="aedf5-103">Register new devices yourself</span></span>

<span data-ttu-id="aedf5-104">Рабочий стол, управляемый Майкрософт, может работать с новыми устройствами или можно повторно использовать уже имеющиеся устройства (которые потребуют их повторного создания образа).</span><span class="sxs-lookup"><span data-stu-id="aedf5-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="aedf5-105">Вы можете зарегистрировать устройства с помощью управляемого рабочего стола Майкрософт на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="aedf5-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="aedf5-106">Работаете с партнером для получения устройств?</span><span class="sxs-lookup"><span data-stu-id="aedf5-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="aedf5-107">Если это так, вам не придется беспокоиться о том, чтобы получить хеш оборудования; они позаботится о них.</span><span class="sxs-lookup"><span data-stu-id="aedf5-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="aedf5-108">Убедитесь, что ваш партнер устанавливает связь с вами в [центре партнеров](https://partner.microsoft.com/dashboard) и включает делегированные права администратора для Azure Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="aedf5-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard) and that they include delegated administration privileges for Azure Active Directory and Office 365.</span></span> <span data-ttu-id="aedf5-109">Ваш партнер может узнать больше в [справке центра партнеров](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="aedf5-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="aedf5-110">После установления этого отношения ваш партнер просто зарегистрирует устройства от вашего имени — никакие дополнительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="aedf5-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="aedf5-111">Если вы хотите просмотреть сведения, или у вашего партнера есть вопросы, ознакомьтесь [с инструкциями для регистрации устройств для партнеров](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="aedf5-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="aedf5-112">После регистрации устройств вы можете продолжить [проверку изображения](#check-the-image) и [доставки устройств](#deliver-the-device) пользователям.</span><span class="sxs-lookup"><span data-stu-id="aedf5-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="aedf5-113">Подготовка к регистрации фирменной символики новых устройств</span><span class="sxs-lookup"><span data-stu-id="aedf5-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="aedf5-114">Получив новые устройства, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aedf5-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="aedf5-115">Получите хеш оборудования для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="aedf5-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="aedf5-116">Объединение хэш-данных</span><span class="sxs-lookup"><span data-stu-id="aedf5-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="aedf5-117">[Зарегистрируйте устройства на настольном компьютере, управляемом Майкрософт](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="aedf5-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="aedf5-118">Дважды проверьте правильность изображения.</span><span class="sxs-lookup"><span data-stu-id="aedf5-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="aedf5-119">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="aedf5-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="aedf5-120">Получение хэш-кода оборудования</span><span class="sxs-lookup"><span data-stu-id="aedf5-120">Obtain the hardware hash</span></span>

<span data-ttu-id="aedf5-121">Рабочий стол, управляемый Майкрософт, определяет каждое устройство уникальным образом, ссылаясь на хэш оборудования.</span><span class="sxs-lookup"><span data-stu-id="aedf5-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="aedf5-122">Вы можете получить эту информацию тремя способами:</span><span class="sxs-lookup"><span data-stu-id="aedf5-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="aedf5-123">Обратитесь к поставщику поставщика вычислительной техники для файла регистрации для автопилота, в котором будут содержаться хэши оборудования.</span><span class="sxs-lookup"><span data-stu-id="aedf5-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="aedf5-124">Запустите [сценарий Windows PowerShell](#powershell-script-method) на каждом устройстве и соберите результаты в файле.</span><span class="sxs-lookup"><span data-stu-id="aedf5-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="aedf5-125">Запустите каждое устройство, но не завершите работу с программой установки Windows, и [Соберите хэши на съемном носителе флэш-памяти](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="aedf5-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="aedf5-126">Метод скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="aedf5-126">PowerShell script method</span></span>

1.  <span data-ttu-id="aedf5-127">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="aedf5-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="aedf5-128">Выполняем`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="aedf5-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="aedf5-129">Выполняем`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="aedf5-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="aedf5-130">Метод флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="aedf5-130">Flash drive method</span></span>

1. <span data-ttu-id="aedf5-131">На устройстве, отличном от регистрируемого, вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="aedf5-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="aedf5-132">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="aedf5-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="aedf5-133">Выполняем`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="aedf5-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="aedf5-134">Включите регистрируемое устройство, но не *запускайте процесс установки*.</span><span class="sxs-lookup"><span data-stu-id="aedf5-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="aedf5-135">Если вы случайно запустили программу установки, вам потребуется сбросить или переобразировать устройство.</span><span class="sxs-lookup"><span data-stu-id="aedf5-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="aedf5-136">Вставьте USB-накопитель, а затем нажмите клавиши SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="aedf5-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="aedf5-137">Откройте командную строку PowerShell с правами администратора и запустите `cd <pathToUsb>`.</span><span class="sxs-lookup"><span data-stu-id="aedf5-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="aedf5-138">Выполняем`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="aedf5-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="aedf5-139">Выполняем`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="aedf5-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="aedf5-140">Удалите USB-накопитель, а затем завершите работу устройства, выполнив`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="aedf5-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="aedf5-141">Не выключайте устройство, которое вы регистрируете повторно, пока не завершите его регистрацию.</span><span class="sxs-lookup"><span data-stu-id="aedf5-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="aedf5-142">Слияние хэш-данных</span><span class="sxs-lookup"><span data-stu-id="aedf5-142">Merge hash data</span></span>

<span data-ttu-id="aedf5-143">Для завершения регистрации необходимо объединить данные CSV-файлов в один файл.</span><span class="sxs-lookup"><span data-stu-id="aedf5-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="aedf5-144">Вот пример сценария PowerShell для упрощения:</span><span class="sxs-lookup"><span data-stu-id="aedf5-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="aedf5-145">Регистрация устройств</span><span class="sxs-lookup"><span data-stu-id="aedf5-145">Register devices</span></span>

<span data-ttu-id="aedf5-146">Для регистрации CSV-файл должен быть в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="aedf5-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="aedf5-147">Если вы собрали данные самостоятельно на предыдущих шагах, файл должен быть уже в правильном формате; Если вы получаете файл от поставщика, может потребоваться изменить формат.</span><span class="sxs-lookup"><span data-stu-id="aedf5-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="aedf5-148">Для удобства вы можете скачать [пример CSV-файла](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span><span class="sxs-lookup"><span data-stu-id="aedf5-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="aedf5-149">Ваш файл должен включать в себя те **же заголовки столбцов** , что и один образец (Manufacturer, Model и т. д.), но собственные данные для других строк.</span><span class="sxs-lookup"><span data-stu-id="aedf5-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="aedf5-150">Если вы используете шаблон, откройте его в средстве редактирования текста (например, в Блокноте) и продумайте все данные только в строке 1, вводя данные в строки 2 и ниже.</span><span class="sxs-lookup"><span data-stu-id="aedf5-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="aedf5-151">Если вы забыли изменить какой – либо образец данных, регистрация завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="aedf5-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="aedf5-152">Регистрация устройств с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="aedf5-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="aedf5-153">На [портале Azure](https://aka.ms/mmdportal)с настольным управлением Microsoft выберите **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="aedf5-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="aedf5-154">Выберите **+ Регистрация устройств**; Откроется вспомогательная надстройка:</span><span class="sxs-lookup"><span data-stu-id="aedf5-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="aedf5-155">[![Вскрывающийся после выбора параметра Регистрация устройств, перечисление устройств со столбцами для назначенных пользователей, серийного номера, состояния, даты последнего рассмотрения и срока хранения](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="aedf5-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (К сожалению, это не так. Мы можем удалить эту заметку, но оставив ее сейчас, пока не сможете поговорить с этой заметкой.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="aedf5-157">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aedf5-157">Follow these steps:</span></span>

1. <span data-ttu-id="aedf5-158">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="aedf5-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="aedf5-159">При необходимости вы можете добавить **идентификатор заказа** или **идентификатор покупки** для собственных целей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="aedf5-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="aedf5-160">Для этих значений не предусмотрены требования к формату.</span><span class="sxs-lookup"><span data-stu-id="aedf5-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="aedf5-161">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="aedf5-161">Select **Register devices**.</span></span> <span data-ttu-id="aedf5-162">Система добавит устройства в список устройств в **колонке устройств**, помеченных как **ожидающие регистрации**.</span><span class="sxs-lookup"><span data-stu-id="aedf5-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="aedf5-163">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов и ждет, пока конечный пользователь начнет использовать.</span><span class="sxs-lookup"><span data-stu-id="aedf5-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="aedf5-164">Вы можете отслеживать ход регистрации устройств на главной странице " **управляемые настольные устройства Майкрософт** ".</span><span class="sxs-lookup"><span data-stu-id="aedf5-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="aedf5-165">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="aedf5-165">Possible states reported there include:</span></span>

| <span data-ttu-id="aedf5-166">Состояние</span><span class="sxs-lookup"><span data-stu-id="aedf5-166">State</span></span> | <span data-ttu-id="aedf5-167">Описание</span><span class="sxs-lookup"><span data-stu-id="aedf5-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="aedf5-168">Ожидается регистрация</span><span class="sxs-lookup"><span data-stu-id="aedf5-168">Registration pending</span></span> | <span data-ttu-id="aedf5-169">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="aedf5-169">Registration is not done yet.</span></span> <span data-ttu-id="aedf5-170">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="aedf5-170">Check back later.</span></span> |
| <span data-ttu-id="aedf5-171">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="aedf5-171">Registration failed</span></span> | <span data-ttu-id="aedf5-172">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="aedf5-172">Registration could not be completed.</span></span> <span data-ttu-id="aedf5-173">Для получения дополнительных сведений обратитесь к разделу [Устранение неполадок Device Registration](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="aedf5-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="aedf5-174">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="aedf5-174">Ready for user</span></span> | <span data-ttu-id="aedf5-175">Регистрация выполнена успешно, и теперь устройство готово к доставке конечному пользователю.</span><span class="sxs-lookup"><span data-stu-id="aedf5-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="aedf5-176">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="aedf5-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="aedf5-177">Активное</span><span class="sxs-lookup"><span data-stu-id="aedf5-177">Active</span></span> | <span data-ttu-id="aedf5-178">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="aedf5-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="aedf5-179">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="aedf5-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="aedf5-180">Отсутств</span><span class="sxs-lookup"><span data-stu-id="aedf5-180">Inactive</span></span> | <span data-ttu-id="aedf5-181">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="aedf5-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="aedf5-182">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="aedf5-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="aedf5-183">Устранение неполадок при регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="aedf5-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="aedf5-184">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="aedf5-184">Error message</span></span> | <span data-ttu-id="aedf5-185">Сведения</span><span class="sxs-lookup"><span data-stu-id="aedf5-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="aedf5-186">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="aedf5-186">Device not found</span></span> | <span data-ttu-id="aedf5-187">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="aedf5-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="aedf5-188">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="aedf5-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="aedf5-189">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="aedf5-189">Hardware hash not valid</span></span> | <span data-ttu-id="aedf5-190">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="aedf5-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="aedf5-191">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="aedf5-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="aedf5-192">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="aedf5-192">Device already registered</span></span> | <span data-ttu-id="aedf5-193">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aedf5-193">This device is already registered to your organization.</span></span> <span data-ttu-id="aedf5-194">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="aedf5-194">No further action required.</span></span> |
| <span data-ttu-id="aedf5-195">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="aedf5-195">Device claimed by another organization</span></span> | <span data-ttu-id="aedf5-196">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="aedf5-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="aedf5-197">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="aedf5-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="aedf5-198">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="aedf5-198">Unexpected error</span></span> | <span data-ttu-id="aedf5-199">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="aedf5-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="aedf5-200">Обратитесь в службу поддержки и введите идентификатор запроса:<requestId></span><span class="sxs-lookup"><span data-stu-id="aedf5-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="aedf5-201">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="aedf5-201">Check the image</span></span>

<span data-ttu-id="aedf5-202">Если ваше устройство поступило от поставщика управляемого партнера Майкрософт для настольных ПК, изображение должно быть правильным.</span><span class="sxs-lookup"><span data-stu-id="aedf5-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="aedf5-203">Вы также можете применить образ самостоятельно, если хотите.</span><span class="sxs-lookup"><span data-stu-id="aedf5-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="aedf5-204">Чтобы приступить к работе, обратитесь к представителю Майкрософт, с которым вы работаете, и укажите расположение и действия по применению образа.</span><span class="sxs-lookup"><span data-stu-id="aedf5-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="aedf5-205">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="aedf5-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aedf5-206">Прежде чем вы перейдете на устройство для пользователя, убедитесь, что вы получили и применили [соответствующие лицензии](../get-ready/prerequisites.md) для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="aedf5-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="aedf5-207">Если все лицензии применяются, вы можете [приступить к работе с устройствами](get-started-devices.md), а затем, когда пользователь сможет запустить устройство и выполнить установку Windows.</span><span class="sxs-lookup"><span data-stu-id="aedf5-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






