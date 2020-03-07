---
title: Этапы регистрации устройств для партнеров
description: Как партнеры могут регистрировать устройства, чтобы они могли управляться с помощью Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557567"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="a81b4-103">Этапы регистрации устройств для партнеров</span><span class="sxs-lookup"><span data-stu-id="a81b4-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="a81b4-104">В этом разделе описываются действия, которые необходимо выполнить партнерам для регистрации устройств.</span><span class="sxs-lookup"><span data-stu-id="a81b4-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="a81b4-105">Процесс регистрации устройств самостоятельно описывается в разделе [Регистрация устройств на рабочем столе, управляемом Майкрософт](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="a81b4-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="a81b4-106">Подготовка к регистрации</span><span class="sxs-lookup"><span data-stu-id="a81b4-106">Prepare for registration</span></span> 
<span data-ttu-id="a81b4-107">Прежде чем завершить регистрацию клиента, необходимо сначала установить связь с ними в [центре партнеров](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="a81b4-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="a81b4-108">Установите флажок **включить делегированные права администрирования для Azure Active Directory и Office 365**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="a81b4-109">Дополнительные сведения см. в [справке центра партнеров](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="a81b4-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="a81b4-110">Чтобы завершить регистрацию клиента, сначала создайте CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a81b4-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="a81b4-111">Для удобства вы можете скачать [пример CSV-файла](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) для этой *версии партнера*.</span><span class="sxs-lookup"><span data-stu-id="a81b4-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) for this *Partner version*.</span></span>

<span data-ttu-id="a81b4-112">Ваш файл должен включать в себя те **же заголовки столбцов** , что и один образец (Manufacturer, Model и т. д.), но собственные данные для других строк.</span><span class="sxs-lookup"><span data-stu-id="a81b4-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="a81b4-113">Если вы используете шаблон, откройте его в средстве редактирования текста (например, в Блокноте) и продумайте все данные только в строке 1, вводя данные в строки 2 и ниже.</span><span class="sxs-lookup"><span data-stu-id="a81b4-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="a81b4-114">Этот формат предназначен только для процесса партнера.</span><span class="sxs-lookup"><span data-stu-id="a81b4-114">This format is only for the Partner process.</span></span> <span data-ttu-id="a81b4-115">Процесс самостоятельной регистрации описан в разделе [Register Devices на рабочем столе, управляемом Майкрософт](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="a81b4-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="a81b4-116">Эти значения должны точно совпадать со значениями производителя из SMBIOS, в том числе с помощью прописных и специальных символов.</span><span class="sxs-lookup"><span data-stu-id="a81b4-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="a81b4-117">Производитель устройства (например: Спиралорбит)</span><span class="sxs-lookup"><span data-stu-id="a81b4-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="a81b4-118">Модель устройства (пример: Контосоабк)</span><span class="sxs-lookup"><span data-stu-id="a81b4-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="a81b4-119">Серийный номер устройства</span><span class="sxs-lookup"><span data-stu-id="a81b4-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="a81b4-120">Регистрация устройств с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="a81b4-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="a81b4-121">Регистрация с помощью портала Azure выполняется так же, как и для самообслуживания, за исключением того, что вы обращаетесь к порталу по-другому.</span><span class="sxs-lookup"><span data-stu-id="a81b4-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="a81b4-122">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a81b4-122">Follow these steps:</span></span>

1. <span data-ttu-id="a81b4-123">Переход в [Центр партнеров](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="a81b4-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="a81b4-124">Выберите **Customers (клиенты**).</span><span class="sxs-lookup"><span data-stu-id="a81b4-124">Select **Customers**.</span></span>
3. <span data-ttu-id="a81b4-125">Выберите клиента, которого вы хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="a81b4-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="a81b4-126">Выберите **Администрирование службы**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="a81b4-127">Выберите **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-127">Select **Intune**.</span></span>
6. <span data-ttu-id="a81b4-128">Выполните поиск по запросу "ММД" в верхнем поле поиска на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="a81b4-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="a81b4-129">Выберите пункт **устройства**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-129">Select **Devices**.</span></span>
8. <span data-ttu-id="a81b4-130">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="a81b4-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="a81b4-131">При необходимости вы можете добавить **идентификатор заказа** или **идентификатор покупки** для собственных целей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a81b4-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="a81b4-132">Для этих значений не предусмотрены требования к формату.</span><span class="sxs-lookup"><span data-stu-id="a81b4-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="a81b4-133">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-133">Select **Register devices**.</span></span> <span data-ttu-id="a81b4-134">Система добавит устройства в список устройств в **колонке устройств**, помеченных как **ожидающие регистрации**.</span><span class="sxs-lookup"><span data-stu-id="a81b4-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="a81b4-135">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов и ждет, пока конечный пользователь начнет использовать.</span><span class="sxs-lookup"><span data-stu-id="a81b4-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="a81b4-136">Вы можете отслеживать ход регистрации устройств на главной странице " **управляемые настольные устройства Майкрософт** ".</span><span class="sxs-lookup"><span data-stu-id="a81b4-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="a81b4-137">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a81b4-137">Possible states reported there include:</span></span>

| <span data-ttu-id="a81b4-138">Состояние</span><span class="sxs-lookup"><span data-stu-id="a81b4-138">State</span></span> | <span data-ttu-id="a81b4-139">Описание</span><span class="sxs-lookup"><span data-stu-id="a81b4-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="a81b4-140">Ожидается регистрация</span><span class="sxs-lookup"><span data-stu-id="a81b4-140">Registration pending</span></span> | <span data-ttu-id="a81b4-141">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a81b4-141">Registration is not done yet.</span></span> <span data-ttu-id="a81b4-142">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="a81b4-142">Check back later.</span></span> |
| <span data-ttu-id="a81b4-143">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="a81b4-143">Registration failed</span></span> | <span data-ttu-id="a81b4-144">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="a81b4-144">Registration could not be completed.</span></span> <span data-ttu-id="a81b4-145">Для получения дополнительных сведений обратитесь к разделу [Устранение неполадок Device Registration](register-devices-self.md#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="a81b4-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="a81b4-146">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="a81b4-146">Ready for user</span></span> | <span data-ttu-id="a81b4-147">Регистрация выполнена успешно, и теперь устройство готово к доставке конечному пользователю.</span><span class="sxs-lookup"><span data-stu-id="a81b4-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="a81b4-148">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="a81b4-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="a81b4-149">Активное</span><span class="sxs-lookup"><span data-stu-id="a81b4-149">Active</span></span> | <span data-ttu-id="a81b4-150">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a81b4-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="a81b4-151">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="a81b4-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="a81b4-152">Отсутств</span><span class="sxs-lookup"><span data-stu-id="a81b4-152">Inactive</span></span> | <span data-ttu-id="a81b4-153">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a81b4-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="a81b4-154">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="a81b4-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="a81b4-155">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a81b4-155">Troubleshooting</span></span>

| <span data-ttu-id="a81b4-156">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="a81b4-156">Error message</span></span> | <span data-ttu-id="a81b4-157">Сведения</span><span class="sxs-lookup"><span data-stu-id="a81b4-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="a81b4-158">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="a81b4-158">Device not found</span></span> | <span data-ttu-id="a81b4-159">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="a81b4-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="a81b4-160">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="a81b4-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="a81b4-161">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="a81b4-161">Hardware hash not valid</span></span> | <span data-ttu-id="a81b4-162">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="a81b4-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="a81b4-163">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="a81b4-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="a81b4-164">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="a81b4-164">Device already registered</span></span> | <span data-ttu-id="a81b4-165">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a81b4-165">This device is already registered to your organization.</span></span> <span data-ttu-id="a81b4-166">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="a81b4-166">No further action required.</span></span> |
| <span data-ttu-id="a81b4-167">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="a81b4-167">Device claimed by another organization</span></span> | <span data-ttu-id="a81b4-168">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="a81b4-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="a81b4-169">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="a81b4-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="a81b4-170">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="a81b4-170">Unexpected error</span></span> | <span data-ttu-id="a81b4-171">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="a81b4-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="a81b4-172">Обратитесь в службу<support link>поддержки () и укажите идентификатор запроса:<requestId></span><span class="sxs-lookup"><span data-stu-id="a81b4-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
