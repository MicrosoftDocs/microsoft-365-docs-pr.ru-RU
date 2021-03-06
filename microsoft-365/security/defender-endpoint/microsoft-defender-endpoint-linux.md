---
title: Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Описывает, как установить и использовать Microsoft Defender для конечной точки на Linux.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 008263bfb948d1a2c52031635d074aca323e6764
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256895"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе описывается установка, настройка, обновление и использование Microsoft Defender для конечной точки в Linux.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечной точки наряду с Microsoft Defender для конечной точки на Linux может привести к проблемам с производительностью и непредсказуемым побочным эффектам. Если защита конечной точки не microsoft является абсолютным требованием в вашей среде, вы можете безопасно использовать функции Defender для конечной точки на Linux EDR после настройки функции антивируса для запуска в пассивном [режиме.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Установка Microsoft Defender для конечной точки на Linux

### <a name="prerequisites"></a>Необходимые условия

- Доступ к порталу Центр безопасности в Microsoft Defender
- Дистрибуция Linux с [помощью системного системного](https://systemd.io/) диспетчера
- Опыт начального уровня в скриптах Linux и BASH
- Административные привилегии на устройстве (в случае ручного развертывания)

> [!NOTE]
>  Microsoft Defender для конечной точки на агенте Linux не зависит от [агента OMS.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent) Microsoft Defender для Конечной точки использует собственный независимый конвейер телеметрии.
> 
> Microsoft Defender для конечной точки в Linux еще не интегрирована в Центр безопасности Azure.



### <a name="installation-instructions"></a>Инструкции по установке

Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Microsoft Defender для конечной точки на Linux.

В общем, необходимо предпринять следующие действия:

- Убедитесь, что у вас есть подписка Microsoft Defender для конечной точки и доступ к порталу [Microsoft Defender для конечных точек.](microsoft-defender-security-center.md)
- Развертывание Microsoft Defender для конечной точки на Linux с помощью одного из следующих методов развертывания:
  - Средство командной строки:
    - [Ручное развертывание](linux-install-manually.md)
  - Средства управления сторонними средствами управления:
    - [Развертывание с помощью средства управления конфигурацией Puppet](linux-install-with-puppet.md)
    - [Развертывание с помощью средства управления конфигурацией Ansible](linux-install-with-ansible.md)
    - [Развертывание с помощью средства управления конфигурацией Chef](linux-deploy-defender-for-endpoint-with-chef.md)
    
Если вы испытываете какие-либо сбои в установке, обратитесь к устранению неполадок установки в [Microsoft Defender для конечной точки на Linux](linux-support-install.md).



### <a name="system-requirements"></a>Требования к системе

- Поддерживаемые дистрибутивы серверов Linux и версии x64 (AMD64/EM64T):

  - Red Hat Enterprise Linux 7.2 или более
  - CentOS 7.2 или более
  - Ubuntu 16.04 LTS или более высокий LTS
  - Debian 9 или более
  - SUSE Linux Enterprise Server 12 или более
  - Oracle Linux 7.2 или более

    > [!NOTE]
    > Дистрибутивы и версии, не указанные в явном списке, не поддерживаются (даже если они получены из официально поддерживаемых дистрибутивов).


- Минимальная версия ядра 3.10.0-327

- Параметр `fanotify` ядра должен быть включен

  > [!CAUTION]
  > Запуск Defender для конечной точки на Linux бок о бок с другими решениями безопасности на основе данных `fanotify` не поддерживается. Это может привести к непредсказуемым результатам, в том числе к висячим операционной системе.

- Пространство диска: 1 ГБ

- /opt/microsoft/mdatp/sbin/wdavdaemon требует исполняемого разрешения. Дополнительные сведения см. в рублях "Убедитесь, что у daemon есть исполняемые разрешения" в проблемах с установкой неполадок для [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/linux-support-install)точки в Linux.

- Основные: 2 минимальных, 4 предпочтительных

- Память: минимум 1 ГБ, 4 предпочитаемых

    > [!NOTE]
    > Убедитесь, что у вас есть свободное пространство диска в /var.

- В настоящее время решение обеспечивает защиту в режиме реального времени для следующих типов файловой системы:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить исходящие подключения между ней и конечными точками.

- Необходимо включить структуру `auditd` аудита ().
  > [!NOTE]
  > События системы, запечатленные правилами, добавлены в (s) и могут повлиять на аудит хостов `/etc/audit/rules.d/` `audit.log` и коллекцию upstream. События, добавленные Microsoft Defender для конечной точки в Linux, будут помечены `mdatp` ключом.

### <a name="network-connections"></a>Сетевые подключения

В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть. Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы отказывали в доступе к этим URL-адресам. Если они есть, может потребоваться создать правило разрешить специально для них. 

| Таблица списка доменов | Описание |
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС. <br><br>[Скачайте таблицу здесь.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Более конкретный список URL-адресов см. в [перечне Настройка параметров](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)прокси-сервера и подключения к Интернету.

Defender for Endpoint может открыть прокси-сервер с помощью следующих методов обнаружения:
- Прозрачный прокси
- Ручная статическая конфигурация прокси

Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах. Для прозрачных прокси-прокси не требуется дополнительная конфигурация для Defender для конечной точки. Для статического прокси-сервера выполните действия в [ручной статической конфигурации прокси.](linux-static-proxy-configuration.md)

> [!WARNING]
> Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются. Убедитесь, что используется только статичный прокси или прозрачный прокси.
>
> Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности. Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender для конечной точки на Linux в соответствующие URL-адреса без перехвата. Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.

О действиях по устранению неполадок см. в выпуске Устранение неполадок с облачными подключениями [для Microsoft Defender для конечной точки в Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Обновление Microsoft Defender для конечной точки в Linux

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций. Чтобы обновить Microsoft Defender для конечной точки в Linux, обратитесь к развертыванию обновлений [для Microsoft Defender для конечной точки в Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Настройка Microsoft Defender для конечной точки в Linux

Инструкции по настройке продукта в корпоративных средах доступны в [set preferences for Microsoft Defender for Endpoint на Linux.](linux-preferences.md)

## <a name="resources"></a>Ресурсы

- Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы.](linux-resources.md)
