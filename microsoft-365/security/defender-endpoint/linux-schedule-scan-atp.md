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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845370"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Расписание сканирования с помощью Microsoft Defender для конечной точки (Linux)

Чтобы выполнить сканирование для Linux, см. [в руб. Поддерживаемые команды.](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux (и Unix) имеют средство **crontab** (аналогично планиру задач) для выполнения запланированных задач.

## <a name="pre-requisite"></a>Предварительное требование

> [!NOTE]
> Чтобы получить список всех часовых поясов, запустите следующую команду: `timedatectl list-timezones`<br>
> Примеры для зоны времени:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Настройка задания Cron
Используйте следующие команды:

**Резервное копирование записей crontab**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Где 200919 == YRMMDD

> [!TIP]
> Сделайте это перед изменением или удалением. <br>

Чтобы изменить crontab и добавить новую работу в качестве корневого пользователя: <br>
`sudo crontab -e`

> [!NOTE]
> Редактор по умолчанию — VIM.

Вы можете увидеть:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Нажмите кнопку "Вставить"

Добавьте следующие записи:

CRON_TZ=Америка/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>В этом примере мы установили его до 00 минут в 2 часа утра. (час в 24-часовом формате), в любой день месяца, в любой месяц по субботам. Это означает, что он будет работать по субботам в 2:00. Pacific (UTC —8).

Нажмите кнопку "Esc"

Введите ":wq" без двойных кавычках.

> [!NOTE]
> w == write, q == quit

Чтобы просмотреть задания cron, введите `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="Linux mdatp":::

**Проверка запусков задания cron**

`sudo grep mdatp /var/log/cron`

**Проверка mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

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

+—————- минуты (значения: 0 — 59) (специальные символы: — * /)  <br>
| +————- (значения: 0 — 23) (специальные символы: , — * /) <br>
| | +———- месяца (значения: 1 — 31) (специальные символы: , — * / L W C)  <br>
| | | +——- (значения: 1 — 12) (специальные символы: ,- * / )  <br>
| | | | +-- день недели (значения: 0 — 6) (воскресенье=0 или 7) (специальные символы: , — * / L W C) <br>
| | | | |******команда, которая будет выполнена


