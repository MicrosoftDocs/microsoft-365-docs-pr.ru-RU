---
title: Расписание обновления конечной точки Microsoft Defender (Linux)
description: Узнайте, как запланировать обновление конечной точки Microsoft Defender (Linux), чтобы лучше защитить активы организации.
keywords: Microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (Linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a967333a58f74938ea70e32e0c48d2decb597e98
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688805"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="63741-104">Планирование обновления Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="63741-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="63741-105">Чтобы запустить обновление в Microsoft Defender для конечной точки в Linux, см. в статью Развертывание обновлений для [Microsoft Defender для конечной](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)точки в Linux.</span><span class="sxs-lookup"><span data-stu-id="63741-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="63741-106">Linux (и Unix) имеют средство **crontab** (аналогично планиру задач) для выполнения запланированных задач.</span><span class="sxs-lookup"><span data-stu-id="63741-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="63741-107">Предварительное требование</span><span class="sxs-lookup"><span data-stu-id="63741-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="63741-108">Чтобы получить список всех часовых поясов, запустите следующую команду: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="63741-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="63741-109">Примеры для зоны времени:</span><span class="sxs-lookup"><span data-stu-id="63741-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="63741-110">Настройка задания Cron</span><span class="sxs-lookup"><span data-stu-id="63741-110">To set the Cron job</span></span>
<span data-ttu-id="63741-111">Используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="63741-111">Use the following commands:</span></span>

<span data-ttu-id="63741-112">**Резервное копирование записей crontab**</span><span class="sxs-lookup"><span data-stu-id="63741-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="63741-113">Где 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="63741-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="63741-114">Сделайте это перед изменением или удалением.</span><span class="sxs-lookup"><span data-stu-id="63741-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="63741-115">Чтобы изменить crontab и добавить новую работу в качестве корневого пользователя:</span><span class="sxs-lookup"><span data-stu-id="63741-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="63741-116">Редактор по умолчанию — VIM.</span><span class="sxs-lookup"><span data-stu-id="63741-116">The default editor is VIM.</span></span>

<span data-ttu-id="63741-117">Вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="63741-117">You might see:</span></span>

<span data-ttu-id="63741-118">0\*\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="63741-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="63741-119">And</span><span class="sxs-lookup"><span data-stu-id="63741-119">And</span></span>

<span data-ttu-id="63741-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="63741-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="63741-121">См. [расписание сканирования с помощью Microsoft Defender для конечной точки (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="63741-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="63741-122">Нажмите кнопку "Вставить"</span><span class="sxs-lookup"><span data-stu-id="63741-122">Press “Insert”</span></span>

<span data-ttu-id="63741-123">Добавьте следующие записи:</span><span class="sxs-lookup"><span data-stu-id="63741-123">Add the following entries:</span></span>

<span data-ttu-id="63741-124">CRON_TZ=Америка/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="63741-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="63741-125">! RHEL и варианты (CentOS и Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="63741-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="63741-126">! SLES и варианты</span><span class="sxs-lookup"><span data-stu-id="63741-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="63741-127">! Системы Ubuntu и Debian</span><span class="sxs-lookup"><span data-stu-id="63741-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="63741-128">В вышеперечисленных примерах мы устанавливаем его до 00 минут 6 утра (час в 24-часовом формате), в любой день месяца, в любой месяц, по воскресеньям. [$(date + d) -le 15] == Не будет работать, если он не равен или меньше \% 15-го дня (3-я неделя).</span><span class="sxs-lookup"><span data-stu-id="63741-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="63741-129">Это означает, что он будет работать каждые 3 воскресенья (7) месяца в 6:00.</span><span class="sxs-lookup"><span data-stu-id="63741-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="63741-130">Pacific (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="63741-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="63741-131">Нажмите кнопку "Esc"</span><span class="sxs-lookup"><span data-stu-id="63741-131">Press “Esc”</span></span>

<span data-ttu-id="63741-132">Введите ":wq" w/o двойные кавычка.</span><span class="sxs-lookup"><span data-stu-id="63741-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="63741-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="63741-133">w == write, q == quit</span></span>

<span data-ttu-id="63741-134">Чтобы просмотреть задания cron, введите `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="63741-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="обновление linux MDE":::

<span data-ttu-id="63741-136">Чтобы проверить, выполняется ли задание cron: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="63741-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="63741-137">Проверка mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="63741-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="63741-138">Для тех, кто использует Ansible, Chef или Puppet</span><span class="sxs-lookup"><span data-stu-id="63741-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="63741-139">Используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="63741-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="63741-140">Настройка заданий cron в Ansible</span><span class="sxs-lookup"><span data-stu-id="63741-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="63741-141">Дополнительные сведения см. в статье [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="63741-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="63741-142">Настройка crontabs в Chef</span><span class="sxs-lookup"><span data-stu-id="63741-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="63741-143">Дополнительные сведения см. в статье [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="63741-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="63741-144">Настройка заданий cron в Puppet</span><span class="sxs-lookup"><span data-stu-id="63741-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="63741-145">Тип ресурса: cron</span><span class="sxs-lookup"><span data-stu-id="63741-145">Resource Type: cron</span></span>

<span data-ttu-id="63741-146">Дополнительные сведения см. в статье [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="63741-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="63741-147">Автоматизация с помощью puppet: cron jobs and scheduled tasks</span><span class="sxs-lookup"><span data-stu-id="63741-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="63741-148">Дополнительные сведения см. в статье [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="63741-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="63741-149">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="63741-149">Additional information</span></span>

<span data-ttu-id="63741-150">**Чтобы получить помощь с crontab**</span><span class="sxs-lookup"><span data-stu-id="63741-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="63741-151">**Чтобы получить список файла crontab текущего пользователя**</span><span class="sxs-lookup"><span data-stu-id="63741-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="63741-152">**Чтобы получить список файла crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="63741-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="63741-153">**Резервное копирование записей crontab**</span><span class="sxs-lookup"><span data-stu-id="63741-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="63741-154">Сделайте это перед изменением или удалением.</span><span class="sxs-lookup"><span data-stu-id="63741-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="63741-155">**Восстановление записей crontab**</span><span class="sxs-lookup"><span data-stu-id="63741-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="63741-156">**Изменение crontab и добавление новой работы в качестве корневого пользователя**</span><span class="sxs-lookup"><span data-stu-id="63741-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="63741-157">**Изменение crontab и добавление новой работы**</span><span class="sxs-lookup"><span data-stu-id="63741-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="63741-158">**Редактирование записей crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="63741-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="63741-159">**Удаление всех записей crontab**</span><span class="sxs-lookup"><span data-stu-id="63741-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="63741-160">**Удаление записей crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="63741-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="63741-161">**Пояснение**</span><span class="sxs-lookup"><span data-stu-id="63741-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

