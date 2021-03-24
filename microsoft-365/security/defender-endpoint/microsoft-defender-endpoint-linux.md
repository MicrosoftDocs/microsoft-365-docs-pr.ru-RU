---
title: AtP Защитника Майкрософт для Linux
ms.reviewer: ''
description: Описывает установку и использование ATP Microsoft Defender для Linux.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072998"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender для конечной точки для Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе описывается установка, настройка, обновление и использование Microsoft Defender для конечной точки для Linux.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечных точек наряду с Microsoft Defender для конечной точки для Linux может привести к проблемам с производительностью и непредсказуемым системным ошибкам.

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>Установка Microsoft Defender для конечной точки для Linux

### <a name="prerequisites"></a>Предварительные требования

- Доступ к порталу Центра безопасности Защитника Майкрософт
- Дистрибуция Linux с [помощью системного системного](https://systemd.io/) диспетчера
- Опыт начального уровня в скриптах Linux и BASH
- Административные привилегии на устройстве (в случае ручного развертывания)

### <a name="installation-instructions"></a>Инструкции по установке

Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Microsoft Defender для конечной точки для Linux.

В общем, необходимо предпринять следующие действия:

- Убедитесь, что у вас есть подписка Microsoft Defender для конечной точки и доступ к порталу [Microsoft Defender для конечных точек.](microsoft-defender-security-center.md)
- Развертывание Microsoft Defender для конечной точки для Linux с помощью одного из следующих методов развертывания:
  - Средство командной строки:
    - [Ручное развертывание](linux-install-manually.md)
  - Средства управления сторонними средствами управления:
    - [Развертывание с помощью средства управления конфигурацией Puppet](linux-install-with-puppet.md)
    - [Развертывание с помощью средства управления конфигурацией Ansible](linux-install-with-ansible.md)

Если вы испытываете какие-либо сбои в установке, обратитесь к устранению неполадок установки в [Microsoft Defender для конечной точки для Linux](linux-support-install.md).

### <a name="system-requirements"></a>Требования к системе

- Поддерживаемые дистрибутивы и версии серверов Linux:

  - Red Hat Enterprise Linux 7.2 или более
  - CentOS 7.2 или более
  - Ubuntu 16.04 LTS или более высокий LTS
  - Debian 9 или более
  - SUSE Linux Enterprise Server 12 или более
  - Oracle Linux 7.2 или более

- Минимальная версия ядра 3.10.0-327
- Параметр `fanotify` ядра должен быть включен
  > [!CAUTION]
  > Запуск Defender для конечной точки для Linux бок о бок с другими решениями безопасности на основе не `fanotify` поддерживается. Это может привести к непредсказуемым результатам, в том числе к висячим операционной системе.

- Пространство диска: 1 ГБ
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
  >[!NOTE]
  > События системы, запечатленные в правилах, добавляются в журналы аудита и могут повлиять на аудит хостов `audit.logs` и коллекцию upstream. События, добавленные Microsoft Defender для Endopoint для Linux, будут помечены `mdatp` ключом.

### <a name="network-connections"></a>Сетевые соединения.

В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть. Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы отказывали в доступе к этим URL-адресам. Если они есть, может потребоваться создать правило разрешить специально для них. 

|**Таблица списка доменов**|**Описание**|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС. <br><br>[Скачайте таблицу здесь.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Более конкретный список URL-адресов см. в [перечне Настройка параметров](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)прокси-сервера и подключения к Интернету.

Defender for Endpoint может открыть прокси-сервер с помощью следующих методов обнаружения:
- Прозрачный прокси
- Ручная статическая конфигурация прокси

Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах. Для прозрачных прокси-прокси не требуется дополнительная конфигурация для Defender для конечной точки. Для статического прокси-сервера выполните действия в [ручной статической конфигурации прокси.](linux-static-proxy-configuration.md)

> [!WARNING]
> Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются. Убедитесь, что используется только статичный прокси или прозрачный прокси.
>
> Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности. Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender for Endpoint для Linux в соответствующие URL-адреса без перехвата. Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.

О действиях по устранению неполадок см. в выпуске Устранение неполадок с облачными подключениями [для Microsoft Defender для конечной точки для Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>Обновление Microsoft Defender для конечной точки для Linux

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций. Чтобы обновить Microsoft Defender для конечной точки для Linux, обратитесь к развертыванию обновлений [для Microsoft Defender для конечной](linux-updates.md)точки для Linux.

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>Настройка Microsoft Defender для конечной точки для Linux

Инструкции по настройке продукта в корпоративных средах доступны в наборе предпочтений [для Microsoft Defender для конечной](linux-preferences.md)точки для Linux.

## <a name="resources"></a>Ресурсы

- Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы.](linux-resources.md)
