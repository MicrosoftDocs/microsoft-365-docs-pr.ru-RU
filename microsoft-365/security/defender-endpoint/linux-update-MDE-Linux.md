---
title: Расписание обновления конечной точки Microsoft Defender (Linux)
description: Узнайте, как запланировать обновление конечной точки Microsoft Defender (Linux), чтобы лучше защитить активы организации.
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
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730874"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Планирование обновления Microsoft Defender для конечной точки для Linux

Чтобы запустить обновление в Microsoft Defender для конечной точки в Linux, см. в статью Развертывание обновлений для [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/linux-updates)точки в Linux.

Linux (и Unix) имеют средство **crontab** (аналогично планиру задач) для выполнения запланированных задач.

## <a name="pre-requisite"></a>Предварительное требование

> [!NOTE]
> Чтобы получить список всех часовых поясов, запустите следующую команду: `timedatectl list-timezones`<br>
> Примеры для зоны времени: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Настройка задания Cron
Используйте следующие команды:

**Резервное копирование записей crontab**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Где 201118 == YYMMDD

> [!TIP]
> Сделайте это перед изменением или удалением. <br>

Чтобы изменить crontab и добавить новую работу в качестве корневого пользователя: <br>
`sudo crontab -e`

> [!NOTE]
> Редактор по умолчанию — VIM.

Вы можете увидеть:

0*****/etc/opt/microsoft/mdatp/logrorate.sh

And

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

См. [расписание сканирования с помощью Microsoft Defender для конечной точки (Linux)](linux-schedule-scan-atp.md)

Нажмите кнопку "Вставить"

Добавьте следующие записи:

CRON_TZ=Америка/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL и варианты (CentOS и Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES и варианты

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Системы Ubuntu и Debian

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> В вышеперечисленных примерах мы устанавливаем его до 00 минут 6 утра (час в 24-часовом формате), в любой день месяца, в любой месяц, по воскресеньям. [$(date + d) -le 15] == Не будет работать, если он не равен или меньше \% 15-го дня (3-я неделя). Это означает, что он будет работать каждые 3 воскресенья (7) месяца в 6:00. Pacific (UTC -8).

Нажмите кнопку "Esc"

Введите ":wq" w/o двойные кавычка.

> [!NOTE]
> w == write, q == quit

Чтобы просмотреть задания cron, введите `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="обновление linux MDE":::

Чтобы проверить, выполняется ли задание cron: `sudo grep mdatp /var/log/cron`

Проверка mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Для тех, кто использует Ansible, Chef или Puppet

Используйте следующие команды:
### <a name="to-set-cron-jobs-in-ansible"></a>Настройка заданий cron в Ansible

`cron – Manage cron.d and crontab entries`

Дополнительные сведения см. в статье [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).

### <a name="to-set-crontabs-in-chef"></a>Настройка crontabs в Chef
`cron resource`

Дополнительные сведения см. в статье [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).

### <a name="to-set-cron-jobs-in-puppet"></a>Настройка заданий cron в Puppet
Тип ресурса: cron

Дополнительные сведения см. в статье [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).

Автоматизация с помощью puppet: cron jobs and scheduled tasks

Дополнительные сведения см. в статье [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).

## <a name="additional-information"></a>Дополнительные сведения

**Чтобы получить помощь с crontab**

`man crontab`

**Чтобы получить список файла crontab текущего пользователя**

`crontab -l`

**Чтобы получить список файла crontab другого пользователя**

`crontab -u username -l`

**Резервное копирование записей crontab**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Сделайте это перед изменением или удалением. <br>

**Восстановление записей crontab**

`crontab /var/tmp/cron_backup.dat`

**Изменение crontab и добавление новой работы в качестве корневого пользователя**

`sudo crontab -e`

**Изменение crontab и добавление новой работы**

`crontab -e`

**Редактирование записей crontab другого пользователя**

`crontab -u username -e`

**Удаление всех записей crontab**

`crontab -r`

**Удаление записей crontab другого пользователя**

`crontab -u username -r`

**Пояснение**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

