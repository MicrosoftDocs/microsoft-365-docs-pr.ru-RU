---
title: Самостоятельное регистрация устройств в управляемом Майкрософт рабочем столе
description: Самостоятельное регистрация устройств для управления наСтольными компьютерами, управляемыми Майкрософт
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289140"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="07a21-103">Регистрация устройств на наСтольных компьютерах, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="07a21-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="07a21-104">В этом разделе описываются действия, которые необходимо выполнить для самостоятельной регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="07a21-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="07a21-105">Процесс для партнеров описан в разделе [Register Devices на НастольНых компьютерах, управляемых Майкрософт для партнеров](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="07a21-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="07a21-106">Рабочий стол, управляемый Майкрософт, может работать с новыми устройствами или можно повторно использовать уже имеющиеся устройства (которые потребуют их повторного создания образа).</span><span class="sxs-lookup"><span data-stu-id="07a21-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="07a21-107">Вы можете зарегистрировать устройства с помощью управляемого рабочего стола Майкрософт на портале Azure или повысить гибкость с помощью API.</span><span class="sxs-lookup"><span data-stu-id="07a21-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="07a21-108">Подготовка к регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="07a21-108">Prepare to register devices</span></span>

<span data-ttu-id="07a21-109">Если вы еще не приобрели нужные устройства, проверьте устройства, [управляемые Майкрософт](../service-description/device-list.md) , и работайте с партнером по устройствам, чтобы приобрести Поддерживаемые устройства.</span><span class="sxs-lookup"><span data-stu-id="07a21-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="07a21-110">Независимо от того, используете ли вы полностью новые устройства или повторно используете существующие, для их регистрации с помощью управляемого рабочего стола Майкрософт необходимо подготовить **CSV-файл**.</span><span class="sxs-lookup"><span data-stu-id="07a21-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="07a21-111">Этот файл должен содержать следующие сведения для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="07a21-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="07a21-112">Этот формат предназначен только для самостоятельной регистрации.</span><span class="sxs-lookup"><span data-stu-id="07a21-112">This format is for self-service registration only.</span></span> <span data-ttu-id="07a21-113">Партнеры по формату, которые следует использовать, задокументированы в разделе [Register Devices in Office Managed Desktop for партнеры](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="07a21-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="07a21-114">Эти значения используются в целях отображения и не должны точно совпадать со свойствами устройства.</span><span class="sxs-lookup"><span data-stu-id="07a21-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="07a21-115">Производитель устройства (например: Спиралорбит)</span><span class="sxs-lookup"><span data-stu-id="07a21-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="07a21-116">Модель устройства (пример: Контосоабк)</span><span class="sxs-lookup"><span data-stu-id="07a21-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="07a21-117">Серийный номер устройства</span><span class="sxs-lookup"><span data-stu-id="07a21-117">Device serial number</span></span>

<span data-ttu-id="07a21-118">Аппаратный хеш должен быть точным совпадением.</span><span class="sxs-lookup"><span data-stu-id="07a21-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="07a21-119">Аппаратный хэш</span><span class="sxs-lookup"><span data-stu-id="07a21-119">Hardware hash</span></span>

<span data-ttu-id="07a21-120">Чтобы получить хэш оборудования, можно обратиться за помощью к ПОСТАВЩИКу или партнеру или выполнить следующие действия для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="07a21-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="07a21-121">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="07a21-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="07a21-122">Выполняем`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="07a21-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="07a21-123">Выполняем`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="07a21-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="07a21-124">Кроме того, вы можете выполнить указанные ниже действия на новом устройстве (перед первым переходом к OOBE):</span><span class="sxs-lookup"><span data-stu-id="07a21-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="07a21-125">На другом устройстве Вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="07a21-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="07a21-126">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="07a21-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="07a21-127">Выполняем`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="07a21-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="07a21-128">Включите целевое устройство, но не запускайте процесс установки.</span><span class="sxs-lookup"><span data-stu-id="07a21-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="07a21-129">Если вы случайно запустили программу установки, вам потребуется сбросить или переобразировать устройство.</span><span class="sxs-lookup"><span data-stu-id="07a21-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="07a21-130">Вставьте USB-накопитель, а затем нажмите клавиши SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="07a21-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="07a21-131">Откройте командную строку PowerShell с правами администратора и запустите `cd <pathToUsb>`.</span><span class="sxs-lookup"><span data-stu-id="07a21-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="07a21-132">Выполняем`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="07a21-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="07a21-133">Выполняем`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="07a21-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="07a21-134">Удалите USB-накопитель, а затем завершите работу устройства, выполнив`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="07a21-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="07a21-135">Не выключайте оконечное устройство еще раз, пока не завершите регистрацию.</span><span class="sxs-lookup"><span data-stu-id="07a21-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="07a21-136">Для удобства вы можете скачать [шаблон](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) для этого CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="07a21-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this CSV file.</span></span>

<span data-ttu-id="07a21-137">Ваш файл должен включать в себя те **же заголовки столбцов** , что и один образец (Manufacturer, Model и т. д.), но собственные данные для других строк.</span><span class="sxs-lookup"><span data-stu-id="07a21-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="07a21-138">Если вы используете шаблон, откройте его в средстве редактирования текста (например, в Блокноте) и продумайте все данные только в строке 1, вводя данные в строки 2 и ниже.</span><span class="sxs-lookup"><span data-stu-id="07a21-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="07a21-139">Если вы забыли изменить какой – либо образец данных, регистрация завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="07a21-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="07a21-140">Регистрация устройств с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="07a21-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="07a21-141">На [портале Azure](https://aka.ms/mmdportal)с наСтольным управлением Microsoft выберите **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="07a21-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="07a21-142">Выберите **+ Регистрация устройств**; Откроется вспомогательная надстройка:</span><span class="sxs-lookup"><span data-stu-id="07a21-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="07a21-143">[![Вылет после выбора параметра Регистрация устройств](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="07a21-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (К сожалению, это не так. Мы можем удалить эту заметку, но оставив ее сейчас, пока не сможете поговорить с этой заметкой.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="07a21-145">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="07a21-145">Follow these steps:</span></span>

1. <span data-ttu-id="07a21-146">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="07a21-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="07a21-147">При необходимости вы можете добавить **идентификатор заказа** или **идентификатор покупки** для собственных целей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="07a21-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="07a21-148">Для этих значений не предусмотрены требования к формату.</span><span class="sxs-lookup"><span data-stu-id="07a21-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="07a21-149">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="07a21-149">Select **Register devices**.</span></span> <span data-ttu-id="07a21-150">Система добавит устройства в список устройств в **колонке устройств**, помеченных как **ожидающие регистрации**.</span><span class="sxs-lookup"><span data-stu-id="07a21-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="07a21-151">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов и ждет, пока конечный пользователь начнет использовать.</span><span class="sxs-lookup"><span data-stu-id="07a21-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="07a21-152">Вы можете отслеживать ход регистрации устройств на главной странице " **управляемые НастольНые устройства Майкрософт** ".</span><span class="sxs-lookup"><span data-stu-id="07a21-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="07a21-153">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="07a21-153">Possible states reported there include:</span></span>

| <span data-ttu-id="07a21-154">Состояние</span><span class="sxs-lookup"><span data-stu-id="07a21-154">State</span></span> | <span data-ttu-id="07a21-155">Описание</span><span class="sxs-lookup"><span data-stu-id="07a21-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="07a21-156">Ожидается регистрация</span><span class="sxs-lookup"><span data-stu-id="07a21-156">Registration pending</span></span> | <span data-ttu-id="07a21-157">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="07a21-157">Registration is not done yet.</span></span> <span data-ttu-id="07a21-158">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="07a21-158">Check back later.</span></span> |
| <span data-ttu-id="07a21-159">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="07a21-159">Registration failed</span></span> | <span data-ttu-id="07a21-160">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="07a21-160">Registration could not be completed.</span></span> <span data-ttu-id="07a21-161">Для получения дополнительных сведений обратитесь к разделу [устраненИе неполадок](register-devices-self.md#troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="07a21-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="07a21-162">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="07a21-162">Ready for user</span></span> | <span data-ttu-id="07a21-163">Регистрация выполнена успешно, и теперь устройство готово к доставке конечному пользователю.</span><span class="sxs-lookup"><span data-stu-id="07a21-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="07a21-164">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="07a21-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="07a21-165">Активное</span><span class="sxs-lookup"><span data-stu-id="07a21-165">Active</span></span> | <span data-ttu-id="07a21-166">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="07a21-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="07a21-167">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="07a21-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="07a21-168">Отсутств</span><span class="sxs-lookup"><span data-stu-id="07a21-168">Inactive</span></span> | <span data-ttu-id="07a21-169">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="07a21-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="07a21-170">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="07a21-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="07a21-171">Регистрация устройств с помощью API</span><span class="sxs-lookup"><span data-stu-id="07a21-171">Register devices by using an API</span></span>

<span data-ttu-id="07a21-172">Доступ к REST API обеспечивает большую гибкость и повторяемость с частыми отдельными регистрациями устройств.</span><span class="sxs-lookup"><span data-stu-id="07a21-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="07a21-173">В настоящее время, чтобы использовать API, обратитесь за помощью к своему контакту Майкрософт, чтобы присоединиться к предварительной версии этой возможности.</span><span class="sxs-lookup"><span data-stu-id="07a21-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="07a21-174">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="07a21-174">Troubleshooting</span></span>

| <span data-ttu-id="07a21-175">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="07a21-175">Error message</span></span> | <span data-ttu-id="07a21-176">Подробно</span><span class="sxs-lookup"><span data-stu-id="07a21-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="07a21-177">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="07a21-177">Device not found</span></span> | <span data-ttu-id="07a21-178">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="07a21-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="07a21-179">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="07a21-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="07a21-180">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="07a21-180">Device not found</span></span> | <span data-ttu-id="07a21-181">Не удалось отменить регистрацию этого устройства, так как он не существует в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="07a21-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="07a21-182">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="07a21-182">No further action required.</span></span> |
| <span data-ttu-id="07a21-183">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="07a21-183">Hardware hash not valid</span></span> | <span data-ttu-id="07a21-184">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="07a21-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="07a21-185">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="07a21-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="07a21-186">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="07a21-186">Device already registered</span></span> | <span data-ttu-id="07a21-187">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="07a21-187">This device is already registered to your organization.</span></span> <span data-ttu-id="07a21-188">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="07a21-188">No further action required.</span></span> |
| <span data-ttu-id="07a21-189">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="07a21-189">Device claimed by another organization</span></span> | <span data-ttu-id="07a21-190">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="07a21-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="07a21-191">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="07a21-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="07a21-192">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="07a21-192">Unexpected error</span></span> | <span data-ttu-id="07a21-193">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="07a21-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="07a21-194">Обратитесь в службу поддержки и введите идентификатор запроса:<requestId></span><span class="sxs-lookup"><span data-stu-id="07a21-194">Contact Support and provide the Request ID: <requestId></span></span> |




