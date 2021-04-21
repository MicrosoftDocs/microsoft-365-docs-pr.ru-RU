---
title: Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux
keywords: Microsoft, defender, atp, linux, installation
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
ms.openlocfilehash: 270ad1145308aaa2af703cda84307a4a96097a53
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903134"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Проверка успешной установки

Ошибка при установке может привести или не привести к содержательному сообщению об ошибке диспетчером пакетов. Чтобы проверить, удалось ли установить установку, получите и проверьте журналы установки с помощью:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Выход из предыдущей команды с правильной датой и временем установки указывает на успех.

Кроме того, [проверьте конфигурацию клиента,](linux-install-manually.md#client-configuration) чтобы проверить состояние продукта и обнаружить текстовый файл EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Убедитесь, что у вас есть правильный пакет

Обратите внимание, что пакет, который вы устанавливаете, соответствует распределению и версии хостов.

| package                       | распространение                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL и CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL и CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian и Ubuntu 16.04, 18.04 и 20.04 |

Для [ручного развертывания](linux-install-manually.md)убедитесь, что выбран правильный дистро и версия.

## <a name="installation-failed"></a>Сбой установки

Проверьте, запущена ли служба mdatp:

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Действия по устранению неполадок, если служба mdatp не запущена

1. Проверьте, существует ли пользователь "mdatp":

    ```bash
    id "mdatp"
    ```

    Если нет вывода, запустите

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Попробуйте включить и перезапустить службу с помощью:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Если mdatp.service не найден при запуске предыдущей команды, запустите:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    где ```<systemd_path>``` для ```/lib/systemd/system``` дистрибутивов Ubuntu и Debian, а также для ```/usr/lib/systemd/system``` Rhel, CentOS, Oracle и SLES.
   Затем повторно повторяем шаг 2.

4. Если вышеперечисленные действия не работают, проверьте, установлен ли SELinux в режиме принудительного действия. Если это так, попробуйте установить его в разрешительном (предпочтительно) или отключенном режиме. Это можно сделать, задав параметр `SELINUX` "допустимый" или "отключенный" в файле, а затем `/etc/selinux/config` перезагружается. Дополнительные сведения ознакомьтесь с man-page selinux.
Теперь попробуйте перезапустить службу mdatp с помощью шага 2. Немедленно измените конфигурацию, хотя по соображениям безопасности после ее перезагрузки и перезагрузки.

5. Если `/opt` каталог является символической ссылкой, создайте крепление привязки `/opt/microsoft` для .

6. Убедитесь, что у деймона есть исполняемое разрешение.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Если у деймона нет исполняемых разрешений, сделайте его исполняемым с помощью:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    и повторное запуск шага 2.

7. Убедитесь, что файловая система, содержащая wdavdaemon, не установлена с помощью "noexec".

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Если служба mdatp запущена, но обнаружение текстовых файлов EICAR не работает

1. Проверьте тип файловой системы с помощью:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    В настоящее время поддерживаемые файловые системы для действий в доступе перечислены [здесь.](microsoft-defender-endpoint-linux.md#system-requirements) Любые файлы вне этих файлов не будут отсканированы.

## <a name="command-line-tool-mdatp-isnt-working"></a>Средство командной строки "mdatp" не работает

1. Если при запуске средства командной `mdatp` строки будет допущена `command not found` ошибка, запустите следующую команду:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    и попробуйте еще раз.

    Если ни один из вышеуказанных действий не поможет, соберйте диагностические журналы:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Путь к почтовому файлу, содержащий журналы, будет отображаться в качестве вывода. С помощью этих журналов можно связаться с нашими службами поддержки клиентов.
