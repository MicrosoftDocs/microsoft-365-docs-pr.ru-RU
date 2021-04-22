---
title: Расписание сканирования с помощью Microsoft Defender для конечной точки (Linux)
description: Узнайте, как запланировать автоматическое время сканирования для Microsoft Defender для конечной точки (Linux), чтобы лучше защитить активы организации.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, scans, antivirus, microsoft defender for endpoint (Linux)
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
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933137"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="f3a71-104">Расписание сканирования с помощью Microsoft Defender для конечной точки (Linux)</span><span class="sxs-lookup"><span data-stu-id="f3a71-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="f3a71-105">Чтобы выполнить сканирование для Linux, см. [в руб. Поддерживаемые команды.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="f3a71-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="f3a71-106">Linux (и Unix) имеют средство **crontab** (аналогично планиру задач) для выполнения запланированных задач.</span><span class="sxs-lookup"><span data-stu-id="f3a71-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="f3a71-107">Предварительное требование</span><span class="sxs-lookup"><span data-stu-id="f3a71-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="f3a71-108">Чтобы получить список всех часовых поясов, запустите следующую команду: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="f3a71-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="f3a71-109">Примеры для зоны времени:</span><span class="sxs-lookup"><span data-stu-id="f3a71-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="f3a71-110">Настройка задания Cron</span><span class="sxs-lookup"><span data-stu-id="f3a71-110">To set the Cron job</span></span>
<span data-ttu-id="f3a71-111">Используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f3a71-111">Use the following commands:</span></span>

<span data-ttu-id="f3a71-112">**Резервное копирование записей crontab**</span><span class="sxs-lookup"><span data-stu-id="f3a71-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="f3a71-113">Где 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="f3a71-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="f3a71-114">Сделайте это перед изменением или удалением.</span><span class="sxs-lookup"><span data-stu-id="f3a71-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="f3a71-115">Чтобы изменить crontab и добавить новую работу в качестве корневого пользователя:</span><span class="sxs-lookup"><span data-stu-id="f3a71-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="f3a71-116">Редактор по умолчанию — VIM.</span><span class="sxs-lookup"><span data-stu-id="f3a71-116">The default editor is VIM.</span></span>

<span data-ttu-id="f3a71-117">Вы можете увидеть:</span><span class="sxs-lookup"><span data-stu-id="f3a71-117">You might see:</span></span>

<span data-ttu-id="f3a71-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="f3a71-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="f3a71-119">Нажмите кнопку "Вставить"</span><span class="sxs-lookup"><span data-stu-id="f3a71-119">Press “Insert”</span></span>

<span data-ttu-id="f3a71-120">Добавьте следующие записи:</span><span class="sxs-lookup"><span data-stu-id="f3a71-120">Add the following entries:</span></span>

<span data-ttu-id="f3a71-121">CRON_TZ=Америка/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="f3a71-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="f3a71-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="f3a71-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="f3a71-123">В этом примере мы установили его до 00 минут в 2 часа утра.</span><span class="sxs-lookup"><span data-stu-id="f3a71-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="f3a71-124">(час в 24-часовом формате), в любой день месяца, в любой месяц по субботам.</span><span class="sxs-lookup"><span data-stu-id="f3a71-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="f3a71-125">Это означает, что он будет работать по субботам в 2:00.</span><span class="sxs-lookup"><span data-stu-id="f3a71-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="f3a71-126">Pacific (UTC —8).</span><span class="sxs-lookup"><span data-stu-id="f3a71-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="f3a71-127">Нажмите кнопку "Esc"</span><span class="sxs-lookup"><span data-stu-id="f3a71-127">Press “Esc”</span></span>

<span data-ttu-id="f3a71-128">Введите ":wq" без двойных кавычках.</span><span class="sxs-lookup"><span data-stu-id="f3a71-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="f3a71-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="f3a71-129">w == write, q == quit</span></span>

<span data-ttu-id="f3a71-130">Чтобы просмотреть задания cron, введите `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="f3a71-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="Linux mdatp":::

<span data-ttu-id="f3a71-132">**Проверка запусков задания cron**</span><span class="sxs-lookup"><span data-stu-id="f3a71-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="f3a71-133">**Проверка mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="f3a71-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="f3a71-134">Для тех, кто использует Ansible, Chef или Puppet</span><span class="sxs-lookup"><span data-stu-id="f3a71-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="f3a71-135">Используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f3a71-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="f3a71-136">Настройка заданий cron в Ansible</span><span class="sxs-lookup"><span data-stu-id="f3a71-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="f3a71-137">Дополнительные сведения см. в статье [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="f3a71-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="f3a71-138">Настройка crontabs в Chef</span><span class="sxs-lookup"><span data-stu-id="f3a71-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="f3a71-139">Дополнительные сведения см. в статье [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="f3a71-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="f3a71-140">Настройка заданий cron в Puppet</span><span class="sxs-lookup"><span data-stu-id="f3a71-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="f3a71-141">Тип ресурса: cron</span><span class="sxs-lookup"><span data-stu-id="f3a71-141">Resource Type: cron</span></span>

<span data-ttu-id="f3a71-142">Дополнительные сведения см. в статье [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="f3a71-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="f3a71-143">Автоматизация с помощью puppet: cron jobs and scheduled tasks</span><span class="sxs-lookup"><span data-stu-id="f3a71-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="f3a71-144">Дополнительные сведения см. в статье [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="f3a71-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="f3a71-145">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f3a71-145">Additional information</span></span>

<span data-ttu-id="f3a71-146">**Чтобы получить помощь с crontab**</span><span class="sxs-lookup"><span data-stu-id="f3a71-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="f3a71-147">**Чтобы получить список файла crontab текущего пользователя**</span><span class="sxs-lookup"><span data-stu-id="f3a71-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="f3a71-148">**Чтобы получить список файла crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="f3a71-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="f3a71-149">**Резервное копирование записей crontab**</span><span class="sxs-lookup"><span data-stu-id="f3a71-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="f3a71-150">Сделайте это перед изменением или удалением.</span><span class="sxs-lookup"><span data-stu-id="f3a71-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="f3a71-151">**Восстановление записей crontab**</span><span class="sxs-lookup"><span data-stu-id="f3a71-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="f3a71-152">**Изменение crontab и добавление новой работы в качестве корневого пользователя**</span><span class="sxs-lookup"><span data-stu-id="f3a71-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="f3a71-153">**Изменение crontab и добавление новой работы**</span><span class="sxs-lookup"><span data-stu-id="f3a71-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="f3a71-154">**Редактирование записей crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="f3a71-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="f3a71-155">**Удаление всех записей crontab**</span><span class="sxs-lookup"><span data-stu-id="f3a71-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="f3a71-156">**Удаление записей crontab другого пользователя**</span><span class="sxs-lookup"><span data-stu-id="f3a71-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="f3a71-157">**Пояснение**</span><span class="sxs-lookup"><span data-stu-id="f3a71-157">**Explanation**</span></span>

<span data-ttu-id="f3a71-158">+—————- минуты (значения: 0 — 59) (специальные символы: — \* /)</span><span class="sxs-lookup"><span data-stu-id="f3a71-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="f3a71-159">| +————- (значения: 0 — 23) (специальные символы: , — \* /)</span><span class="sxs-lookup"><span data-stu-id="f3a71-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="f3a71-160">| | +———- месяца (значения: 1 — 31) (специальные символы: , — \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="f3a71-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="f3a71-161">| | | +——- (значения: 1 — 12) (специальные символы: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="f3a71-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="f3a71-162">| | | | +-- день недели (значения: 0 — 6) (воскресенье=0 или 7) (специальные символы: , — \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="f3a71-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="f3a71-163">| | | | |\*\*\*\*\*\*команда, которая будет выполнена</span><span class="sxs-lookup"><span data-stu-id="f3a71-163">| | | | |\*\*\*\*\*command to be executed</span></span>


