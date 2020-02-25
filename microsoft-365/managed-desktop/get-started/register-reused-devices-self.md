---
title: Самостоятельная регистрация существующих устройств
description: Регистрация повторно используемых устройств. возможно, у вас уже есть права для управления на настольном компьютере, управляемом Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250449"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="08ff8-103">Самостоятельная регистрация существующих устройств</span><span class="sxs-lookup"><span data-stu-id="08ff8-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="08ff8-104">В этом разделе описываются действия, которые необходимо выполнить, чтобы повторно использовать уже имеющиеся устройства и зарегистрировать их в системе, управляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08ff8-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="08ff8-105">Если вы работаете с новыми устройствами, выполните действия, описанные в статье [Регистрация новых устройств на компьютере, управляемом Майкрософт](register-devices-self.md) , вместо этого.</span><span class="sxs-lookup"><span data-stu-id="08ff8-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="08ff8-106">Процесс для партнеров описан в [статье действия для партнеров по регистрации устройств](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="08ff8-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="08ff8-107">Рабочий стол, управляемый Майкрософт, может работать с новыми устройствами или можно повторно использовать уже имеющиеся устройства (которые потребуют их повторного создания образа).</span><span class="sxs-lookup"><span data-stu-id="08ff8-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="08ff8-108">Вы можете зарегистрировать устройства с помощью управляемого рабочего стола Майкрософт на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="08ff8-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="08ff8-109">Подготовка к регистрации существующих устройств</span><span class="sxs-lookup"><span data-stu-id="08ff8-109">Prepare to register existing devices</span></span>


<span data-ttu-id="08ff8-110">Чтобы зарегистрировать существующие устройства, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="08ff8-111">Получите хеш оборудования для каждого устройства.</span><span class="sxs-lookup"><span data-stu-id="08ff8-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="08ff8-112">Объединение хэш-данных</span><span class="sxs-lookup"><span data-stu-id="08ff8-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="08ff8-113">[Зарегистрируйте устройства на настольном компьютере, управляемом Майкрософт](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="08ff8-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="08ff8-114">Дважды проверьте правильность изображения.</span><span class="sxs-lookup"><span data-stu-id="08ff8-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="08ff8-115">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="08ff8-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="08ff8-116">Получение хэш-кода оборудования</span><span class="sxs-lookup"><span data-stu-id="08ff8-116">Obtain the hardware hash</span></span>

<span data-ttu-id="08ff8-117">Рабочий стол, управляемый Майкрософт, определяет каждое устройство уникальным образом, ссылаясь на хэш оборудования.</span><span class="sxs-lookup"><span data-stu-id="08ff8-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="08ff8-118">Существует четыре способа получения этой информации с устройств, которые вы уже используете:</span><span class="sxs-lookup"><span data-stu-id="08ff8-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="08ff8-119">Обратитесь к поставщику поставщика вычислительной техники для файла регистрации для автопилота, в котором будут содержаться хэши оборудования.</span><span class="sxs-lookup"><span data-stu-id="08ff8-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="08ff8-120">Создание настраиваемого отчета в [диспетчере конфигураций](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="08ff8-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="08ff8-121">Запустите сценарий Windows PowerShell, используя [Active Directory](#active-directory-powershell-script-method) или [вручную](#manual-powershell-script-method) на каждом устройстве, и соберите результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="08ff8-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="08ff8-122">Запустите каждое устройство, но не завершите работу с программой установки Windows, и [Соберите хэши на съемном носителе флэш-памяти](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="08ff8-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="08ff8-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="08ff8-123">Configuration Manager</span></span>

<span data-ttu-id="08ff8-124">С помощью диспетчера конфигураций конечных точек Майкрософт можно собирать аппаратные хэши с существующих устройств, которые вы хотите зарегистрировать с помощью управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08ff8-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08ff8-125">Все устройства, для которых вы хотите получить эту информацию, должны работать под управлением Windows 10 версии 1703 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="08ff8-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="08ff8-126">Кроме того, вам потребуется устройство, которое является клиентом Configuration Manager, подключенным к сайту Configuration Manager (текущей ветви).</span><span class="sxs-lookup"><span data-stu-id="08ff8-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="08ff8-127">Кроме того, необходимо настроить роль системы сайта точки формирования отчетов в среде с включенными службами SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="08ff8-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="08ff8-128">Если вы удовлетворены всеми необходимыми компонентами, вы готовы собрать эти сведения, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="08ff8-129">В консоли диспетчера конфигураций выберите пункт **мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="08ff8-130">В рабочей области мониторинга разверните узел **отчеты**, а затем выберите пункт **отчеты**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="08ff8-131">На вкладке **Главная** , в разделе **создать** , выберите **создать отчет** , чтобы открыть мастер создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="08ff8-132">На странице **сведения** задайте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="08ff8-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="08ff8-133">**Имя:** Укажите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="08ff8-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="08ff8-134">**Description:** Укажите описание отчета.</span><span class="sxs-lookup"><span data-stu-id="08ff8-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="08ff8-135">**Сервер:** Отображает имя сервера отчетов, на котором создается этот отчет.</span><span class="sxs-lookup"><span data-stu-id="08ff8-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="08ff8-136">**Путь:** Нажмите кнопку **Обзор** , чтобы указать папку, в которой будет храниться отчет.</span><span class="sxs-lookup"><span data-stu-id="08ff8-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="08ff8-137">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-137">Select **Next**.</span></span> 
6. <span data-ttu-id="08ff8-138">На странице **Сводка** проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="08ff8-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="08ff8-139">Нажмите кнопку **назад** , чтобы изменить параметры или нажмите кнопку **Далее** , чтобы создать отчет в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="08ff8-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="08ff8-140">На странице **Завершение** нажмите кнопку **Закрыть** , чтобы завершить работу мастера и открыть **Построитель отчетов** , чтобы ввести параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="08ff8-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="08ff8-141">При появлении запроса введите учетную запись пользователя и пароль, а затем нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="08ff8-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="08ff8-142">Если на устройстве не установлен построитель отчетов, вам будет предложено установить его.</span><span class="sxs-lookup"><span data-stu-id="08ff8-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="08ff8-143">Выберите **выполнить, чтобы установить построитель отчетов**, который требуется для изменения и создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="08ff8-144">**В построителе отчетов Майкрософт**введите инструкцию SQL для отчета и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="08ff8-145">В левой области выберите **наборы**данных, а затем щелкните правой кнопкой мыши, чтобы **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="08ff8-146">Перейдите на вкладку **запрос** и введите имя в формате *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="08ff8-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="08ff8-147">Выберите **использовать набор данных, внедренный в отчет**; Откроется построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="08ff8-148">В **построителе отчетов**выберите **источник данных:**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="08ff8-149">Выберите источник данных по умолчанию, который должен начинаться с "Аутожен".</span><span class="sxs-lookup"><span data-stu-id="08ff8-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="08ff8-150">Выберите **тип запроса в текстовом поле**, а затем введите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="08ff8-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="08ff8-151">Перейдите на вкладку **поле** , значения Вехре для **имени поля** и **Источник поля** уже должны быть заполнены.</span><span class="sxs-lookup"><span data-stu-id="08ff8-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="08ff8-152">Если это не так, нажмите кнопку **Добавить**, а затем выберите **поле запрос**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="08ff8-153">Введите **имя поля** и **Источник поля**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="08ff8-154">Повторите эти значения для каждого из этих значений:</span><span class="sxs-lookup"><span data-stu-id="08ff8-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="08ff8-155">Вычислитель</span><span class="sxs-lookup"><span data-stu-id="08ff8-155">Manufacturer</span></span> 
    - <span data-ttu-id="08ff8-156">Модель</span><span class="sxs-lookup"><span data-stu-id="08ff8-156">Model</span></span> 
    - <span data-ttu-id="08ff8-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="08ff8-157">Serial_Number</span></span> 
    - <span data-ttu-id="08ff8-158">хардварехаш</span><span class="sxs-lookup"><span data-stu-id="08ff8-158">HardwareHash</span></span>
7. <span data-ttu-id="08ff8-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-159">Select **OK**.</span></span>

<span data-ttu-id="08ff8-160">**Затем определите отображение отчета и создайте отчет** , выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="08ff8-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="08ff8-161">Выберите **Таблица или матрицу**; Откроется новый мастер.</span><span class="sxs-lookup"><span data-stu-id="08ff8-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="08ff8-162">В окне **Выбор набора данных**выберите **выбрать существующий набор данных в этом отчете или в общем наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="08ff8-163">Выберите **DataSet0** (по умолчанию), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="08ff8-164">Перетащите **производителя**, **модель**и **серийный номер** в поле **группы строк** .</span><span class="sxs-lookup"><span data-stu-id="08ff8-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="08ff8-165">Перетащите **хардварехаш** в поле **значения** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="08ff8-166">Снимите флажки для отображения промежуточных **и общих итогов** , а также **развертывания и свертывания групп**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="08ff8-167">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-167">Select **Next**.</span></span>
6. <span data-ttu-id="08ff8-168">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-168">Select **Finish**.</span></span>
7. <span data-ttu-id="08ff8-169">Выберите **выполнить** , чтобы запустить отчет.</span><span class="sxs-lookup"><span data-stu-id="08ff8-169">Select **Run** to run your report.</span></span> <span data-ttu-id="08ff8-170">Убедитесь, что отчет содержит ожидаемые сведения.</span><span class="sxs-lookup"><span data-stu-id="08ff8-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="08ff8-171">При необходимости выберите **проект** , чтобы вернуться в режим конструктора, чтобы изменить отчет.</span><span class="sxs-lookup"><span data-stu-id="08ff8-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="08ff8-172">Нажмите кнопку **сохранить** , чтобы сохранить отчет на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="08ff8-173">Новый отчет можно запустить в узле "отчеты" в рабочей области "Мониторинг".</span><span class="sxs-lookup"><span data-stu-id="08ff8-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="08ff8-174">**Наконец, экспортируйте отчет и используйте его для регистрации устройств** , выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="08ff8-175">(Вам необходимо выполнить действия 1 и 2 этого раздела, если вы выполнили переход с предыдущих шагов.):</span><span class="sxs-lookup"><span data-stu-id="08ff8-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="08ff8-176">В консоли диспетчера конфигураций выберите пункт **мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="08ff8-177">В **мониторинге**разверните узел **отчеты**, а затем выберите пункт **отчеты**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="08ff8-178">Найдите отчет с помощью созданного ранее имени.</span><span class="sxs-lookup"><span data-stu-id="08ff8-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="08ff8-179">Щелкните этот отчет правой кнопкой мыши и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="08ff8-180">В открывшемся диалоговом окне выберите пункт **Экспорт** , а затем — **Сохранить как CSV**-файл.</span><span class="sxs-lookup"><span data-stu-id="08ff8-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="08ff8-181">Эта версия отчета извлекает хэши со всех устройств с Windows 10, с которыми работает Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="08ff8-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="08ff8-182">Вам потребуется фильтровать результаты только на тех устройствах, которые планируется зарегистрировать с помощью управляемого рабочего стола Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08ff8-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="08ff8-183">В запросе в диспетчере конфигурации не допускаются пробелы в именах экспортированных столбцов; Вот почему вы вводили пункты "Serial_Number" и "Хардварехаш".</span><span class="sxs-lookup"><span data-stu-id="08ff8-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="08ff8-184">Теперь, когда у вас есть экспортированный CSV-файл, необходимо изменить заголовки отчетов для чтения *серийного номера* и *аппаратного хеша* , как показано ниже, прежде чем переходить к регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="08ff8-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="08ff8-185">Теперь вы можете перейти к [регистрации устройств с помощью портала Azure](#register-devices-by-using-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="08ff8-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="08ff8-186">Метод сценария PowerShell Active Directory</span><span class="sxs-lookup"><span data-stu-id="08ff8-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="08ff8-187">В среде Active Directory вы можете использовать командлет `Get-MMDRegistrationInfo` PowerShell для удаленного сбора сведений от устройств в группах Active Directory с помощью WinRM.</span><span class="sxs-lookup"><span data-stu-id="08ff8-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="08ff8-188">Кроме того, можно использовать `Get-AD Computer` командлеты и получать отфильтрованные результаты для определенных аппаратных имен моделей, включенных в каталог.</span><span class="sxs-lookup"><span data-stu-id="08ff8-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="08ff8-189">Для этого сначала подтвердите необходимые условия, а затем выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="08ff8-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="08ff8-190">Служба WinRM включена.</span><span class="sxs-lookup"><span data-stu-id="08ff8-190">WinRM is enabled.</span></span>
- <span data-ttu-id="08ff8-191">Устройства, которые вы хотите зарегистрировать, активны в сети (то есть они не отключены и не отключены).</span><span class="sxs-lookup"><span data-stu-id="08ff8-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="08ff8-192">Убедитесь, что у вас есть параметр учетных данных домена, у которого есть разрешение на удаленное выполнение на устройствах.</span><span class="sxs-lookup"><span data-stu-id="08ff8-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="08ff8-193">Убедитесь, что брандмауэр Windows предоставляет доступ к WMI.</span><span class="sxs-lookup"><span data-stu-id="08ff8-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="08ff8-194">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="08ff8-195">Откройте панель управления **брандмауэром защитника Windows** и выберите пункт **Разрешить приложение или компонент через брандмауэр защитника Windows**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="08ff8-196">Найдите в списке **инструментарий управления Windows (WMI)** , включите как частный, так и **общедоступный**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="08ff8-197">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="08ff8-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="08ff8-198">Выполните *один* из следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="08ff8-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="08ff8-199">Доступ к каталогам, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="08ff8-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="08ff8-200">Удалите записи для каждого устройства из *всех* каталогов, включая доменные службы Windows Server Active Directory и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08ff8-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="08ff8-201">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="08ff8-202">Доступ к службам управления, в которых могут быть записи для устройств.</span><span class="sxs-lookup"><span data-stu-id="08ff8-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="08ff8-203">Удалите записи для каждого устройства из *всех* служб управления, включая диспетчер конфигураций конечных точек Майкрософт, Microsoft Intune и Windows автопилот.</span><span class="sxs-lookup"><span data-stu-id="08ff8-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="08ff8-204">Обратите внимание, что для полного выполнения этого процесса может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="08ff8-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="08ff8-205">Теперь вы можете перейти к разделу [Регистрация устройств](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="08ff8-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="08ff8-206">Метод сценария PowerShell вручную</span><span class="sxs-lookup"><span data-stu-id="08ff8-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="08ff8-207">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="08ff8-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="08ff8-208">Выполняем`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="08ff8-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="08ff8-209">Выполняем`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="08ff8-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="08ff8-210">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="08ff8-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="08ff8-211">Метод флэш-накопителя</span><span class="sxs-lookup"><span data-stu-id="08ff8-211">Flash drive method</span></span>

1. <span data-ttu-id="08ff8-212">На устройстве, отличном от регистрируемого, вставьте USB-накопитель.</span><span class="sxs-lookup"><span data-stu-id="08ff8-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="08ff8-213">Откройте командную строку PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="08ff8-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="08ff8-214">Выполняем`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="08ff8-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="08ff8-215">Включите регистрируемое устройство, но не *запускайте процесс установки*.</span><span class="sxs-lookup"><span data-stu-id="08ff8-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="08ff8-216">Если вы случайно запустили программу установки, вам потребуется сбросить или переобразировать устройство.</span><span class="sxs-lookup"><span data-stu-id="08ff8-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="08ff8-217">Вставьте USB-накопитель, а затем нажмите клавиши SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="08ff8-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="08ff8-218">Откройте командную строку PowerShell с правами администратора и запустите `cd <pathToUsb>`.</span><span class="sxs-lookup"><span data-stu-id="08ff8-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="08ff8-219">Выполняем`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="08ff8-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="08ff8-220">Выполняем`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="08ff8-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="08ff8-221">Удалите USB-накопитель, а затем завершите работу устройства, выполнив`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="08ff8-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="08ff8-222">Объединение хэш-данных.</span><span class="sxs-lookup"><span data-stu-id="08ff8-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="08ff8-223">Не выключайте устройство, которое вы регистрируете повторно, пока не завершите его регистрацию.</span><span class="sxs-lookup"><span data-stu-id="08ff8-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="08ff8-224">Слияние хэш-данных</span><span class="sxs-lookup"><span data-stu-id="08ff8-224">Merge hash data</span></span>

<span data-ttu-id="08ff8-225">Если вы собрали хэш-данные оборудования вручную с помощью методов PowerShell или устройства флэш-памяти, то теперь необходимо объединить данные CSV-файлов в один файл для завершения регистрации.</span><span class="sxs-lookup"><span data-stu-id="08ff8-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="08ff8-226">Вот пример сценария PowerShell для упрощения:</span><span class="sxs-lookup"><span data-stu-id="08ff8-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="08ff8-227">После объединения хэш-данных в один CSV-файл можно приступить к [регистрации устройств](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="08ff8-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="08ff8-228">Регистрация устройств</span><span class="sxs-lookup"><span data-stu-id="08ff8-228">Register devices</span></span>

<span data-ttu-id="08ff8-229">Для регистрации CSV-файл должен быть в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="08ff8-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="08ff8-230">Если вы собрали данные самостоятельно на предыдущих шагах, файл должен быть уже в правильном формате; Если вы получаете файл от поставщика, может потребоваться изменить формат.</span><span class="sxs-lookup"><span data-stu-id="08ff8-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="08ff8-231">Для удобства вы можете скачать [шаблон](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) для этого CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="08ff8-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="08ff8-232">Ваш файл должен включать в себя те **же заголовки столбцов** , что и один образец (Manufacturer, Model и т. д.), но собственные данные для других строк.</span><span class="sxs-lookup"><span data-stu-id="08ff8-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="08ff8-233">Если вы используете шаблон, откройте его в средстве редактирования текста (например, в Блокноте) и продумайте все данные только в строке 1, вводя данные в строки 2 и ниже.</span><span class="sxs-lookup"><span data-stu-id="08ff8-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="08ff8-234">Если вы забыли изменить какой – либо образец данных, регистрация завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="08ff8-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="08ff8-235">Регистрация устройств с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="08ff8-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="08ff8-236">На [портале Azure](https://aka.ms/mmdportal)с настольным управлением Microsoft выберите **устройства** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="08ff8-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="08ff8-237">Выберите **+ Регистрация устройств**; Откроется вспомогательная надстройка:</span><span class="sxs-lookup"><span data-stu-id="08ff8-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="08ff8-238">[![Вскрывающийся после выбора параметра Регистрация устройств, перечисление устройств со столбцами для назначенных пользователей, серийного номера, состояния, даты последнего рассмотрения и срока хранения](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="08ff8-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (К сожалению, это не так. Мы можем удалить эту заметку, но оставив ее сейчас, пока не сможете поговорить с этой заметкой.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="08ff8-240">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="08ff8-240">Follow these steps:</span></span>

1. <span data-ttu-id="08ff8-241">В поле **Отправка файла**укажите путь к созданному ранее CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="08ff8-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="08ff8-242">При необходимости вы можете добавить **идентификатор заказа** или **идентификатор покупки** для собственных целей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="08ff8-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="08ff8-243">Для этих значений не предусмотрены требования к формату.</span><span class="sxs-lookup"><span data-stu-id="08ff8-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="08ff8-244">Выберите пункт **зарегистрировать устройства**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-244">Select **Register devices**.</span></span> <span data-ttu-id="08ff8-245">Система добавит устройства в список устройств в **колонке устройств**, помеченных как **ожидающие регистрации**.</span><span class="sxs-lookup"><span data-stu-id="08ff8-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="08ff8-246">Регистрация обычно занимает менее 10 минут, и при успешном завершении работы устройство отображается как **готовое для пользователя** , что означает, что он готов и ждет, пока конечный пользователь начнет использовать.</span><span class="sxs-lookup"><span data-stu-id="08ff8-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="08ff8-247">Вы можете отслеживать ход регистрации устройств на главной странице " **управляемые настольные устройства Майкрософт** ".</span><span class="sxs-lookup"><span data-stu-id="08ff8-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="08ff8-248">В отчет могут воздержаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="08ff8-248">Possible states reported there include:</span></span>

| <span data-ttu-id="08ff8-249">Состояние</span><span class="sxs-lookup"><span data-stu-id="08ff8-249">State</span></span> | <span data-ttu-id="08ff8-250">Описание</span><span class="sxs-lookup"><span data-stu-id="08ff8-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="08ff8-251">Ожидается регистрация</span><span class="sxs-lookup"><span data-stu-id="08ff8-251">Registration pending</span></span> | <span data-ttu-id="08ff8-252">Регистрация еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="08ff8-252">Registration is not done yet.</span></span> <span data-ttu-id="08ff8-253">Вернитесь позже.</span><span class="sxs-lookup"><span data-stu-id="08ff8-253">Check back later.</span></span> |
| <span data-ttu-id="08ff8-254">Сбой регистрации</span><span class="sxs-lookup"><span data-stu-id="08ff8-254">Registration failed</span></span> | <span data-ttu-id="08ff8-255">Не удалось выполнить регистрацию.</span><span class="sxs-lookup"><span data-stu-id="08ff8-255">Registration could not be completed.</span></span> <span data-ttu-id="08ff8-256">Для получения дополнительных сведений обратитесь к разделу [Устранение неполадок Device Registration](#troubleshooting-device-registration) .</span><span class="sxs-lookup"><span data-stu-id="08ff8-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="08ff8-257">Готово для пользователя</span><span class="sxs-lookup"><span data-stu-id="08ff8-257">Ready for user</span></span> | <span data-ttu-id="08ff8-258">Регистрация выполнена успешно, и теперь устройство готово к доставке конечному пользователю.</span><span class="sxs-lookup"><span data-stu-id="08ff8-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="08ff8-259">Рабочий стол, управляемый Майкрософт, будет самостоятельно настраиваться, поэтому дальнейшие подготовительные действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="08ff8-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="08ff8-260">Активное</span><span class="sxs-lookup"><span data-stu-id="08ff8-260">Active</span></span> | <span data-ttu-id="08ff8-261">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="08ff8-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="08ff8-262">Это также означает, что они регулярно используют устройство.</span><span class="sxs-lookup"><span data-stu-id="08ff8-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="08ff8-263">Отсутств</span><span class="sxs-lookup"><span data-stu-id="08ff8-263">Inactive</span></span> | <span data-ttu-id="08ff8-264">Устройство было доставлено конечному пользователю и зарегистрировано в клиенте.</span><span class="sxs-lookup"><span data-stu-id="08ff8-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="08ff8-265">Однако они не использовали устройство недавно (за последние 7 дней).</span><span class="sxs-lookup"><span data-stu-id="08ff8-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="08ff8-266">Устранение неполадок при регистрации устройств</span><span class="sxs-lookup"><span data-stu-id="08ff8-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="08ff8-267">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="08ff8-267">Error message</span></span> | <span data-ttu-id="08ff8-268">Сведения</span><span class="sxs-lookup"><span data-stu-id="08ff8-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="08ff8-269">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="08ff8-269">Device not found</span></span> | <span data-ttu-id="08ff8-270">Не удалось зарегистрировать это устройство, так как не удалось найти соответствующее значение для указанного производителя, модели или серийного номера.</span><span class="sxs-lookup"><span data-stu-id="08ff8-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="08ff8-271">Подтвердите эти значения с помощью поставщика устройств.</span><span class="sxs-lookup"><span data-stu-id="08ff8-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="08ff8-272">Недопустимый хеш оборудования</span><span class="sxs-lookup"><span data-stu-id="08ff8-272">Hardware hash not valid</span></span> | <span data-ttu-id="08ff8-273">Аппаратный хеш, указанный для этого устройства, отформатирован неправильно.</span><span class="sxs-lookup"><span data-stu-id="08ff8-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="08ff8-274">Дважды проверьте хэш оборудования, а затем повторите отправляются.</span><span class="sxs-lookup"><span data-stu-id="08ff8-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="08ff8-275">Устройство уже зарегистрировано</span><span class="sxs-lookup"><span data-stu-id="08ff8-275">Device already registered</span></span> | <span data-ttu-id="08ff8-276">Это устройство уже зарегистрировано в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="08ff8-276">This device is already registered to your organization.</span></span> <span data-ttu-id="08ff8-277">Дальнейшие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="08ff8-277">No further action required.</span></span> |
| <span data-ttu-id="08ff8-278">Устройство заявлено другой организацией</span><span class="sxs-lookup"><span data-stu-id="08ff8-278">Device claimed by another organization</span></span> | <span data-ttu-id="08ff8-279">Это устройство уже заявлено другой организацией.</span><span class="sxs-lookup"><span data-stu-id="08ff8-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="08ff8-280">Обратитесь к поставщику устройства.</span><span class="sxs-lookup"><span data-stu-id="08ff8-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="08ff8-281">Непредвиденная ошибка</span><span class="sxs-lookup"><span data-stu-id="08ff8-281">Unexpected error</span></span> | <span data-ttu-id="08ff8-282">Не удалось автоматически обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="08ff8-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="08ff8-283">Обратитесь в службу поддержки и введите идентификатор запроса:<requestId></span><span class="sxs-lookup"><span data-stu-id="08ff8-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="08ff8-284">Проверка изображения</span><span class="sxs-lookup"><span data-stu-id="08ff8-284">Check the image</span></span>

<span data-ttu-id="08ff8-285">Если ваше устройство поступило от поставщика управляемого партнера Майкрософт для настольных ПК, изображение должно быть правильным.</span><span class="sxs-lookup"><span data-stu-id="08ff8-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="08ff8-286">Вы также можете применить образ самостоятельно, если хотите.</span><span class="sxs-lookup"><span data-stu-id="08ff8-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="08ff8-287">Чтобы приступить к работе, обратитесь к представителю Майкрософт, с которым вы работаете, и укажите расположение и действия по применению образа.</span><span class="sxs-lookup"><span data-stu-id="08ff8-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="08ff8-288">Доставка устройства</span><span class="sxs-lookup"><span data-stu-id="08ff8-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08ff8-289">Прежде чем вы перейдете на устройство для пользователя, убедитесь, что вы получили и применили [соответствующие лицензии](../get-ready/prerequisites.md) для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="08ff8-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="08ff8-290">Если все лицензии применяются, вы можете [приступить к работе с устройствами](get-started-devices.md), а затем, когда пользователь сможет запустить устройство и выполнить установку Windows.</span><span class="sxs-lookup"><span data-stu-id="08ff8-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









