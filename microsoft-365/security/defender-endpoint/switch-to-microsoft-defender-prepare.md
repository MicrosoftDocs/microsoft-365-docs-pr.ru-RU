---
title: Переход на Microsoft Defender для конечной точки — подготовка
description: Это этап 1, Подготовка к миграции в Microsoft Defender для конечной точки.
keywords: миграция, Microsoft Defender для конечной точки, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 05/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 265f32f5a24b982933ac6a876b244b10802cdd60
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345817"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Переход на microsoft Defender для конечной точки — этап 1: подготовка

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Этап 1. Подготовка](images/phase-diagrams/prepare.png)<br/>Этап 1. Подготовка | [![Этап 2. Настройка](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Этап 2. Настройка](switch-to-microsoft-defender-setup.md) | [![Этап 3. Подключение](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Этап 3. Подключение](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Вы здесь!*| | |

**Добро пожаловать на этап подготовки перехода [на Microsoft Defender для конечной точки.](switch-to-microsoft-defender-migration.md#the-migration-process)** 

Этот этап миграции включает следующие действия:

1. [Получать и развертывать обновления на устройствах организации](#get-and-deploy-updates-across-your-organizations-devices)

2. [Получите Microsoft Defender для конечной точки](#get-microsoft-defender-for-endpoint).

3. [Предоставление доступа к Центр безопасности в Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).

4. [Настройка параметров прокси-сервера устройства](#configure-device-proxy-and-internet-connectivity-settings)и подключения к Интернету.

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Получать и развертывать обновления на устройствах организации

В качестве наилучшей практики следите за тем, чтобы устройства и конечные точки организации были в курсе. Убедитесь, что существующее решение по защите конечной точки и антивирусу обновлено, а операционные системы и приложения организации также имеют последние обновления. Это поможет предотвратить проблемы позже при переходе в Microsoft Defender для конечной точки и антивирусная программа в Microsoft Defender.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Убедитесь, что существующее решение устарело

Обновляйте существующее решение по защите конечной точки и убедитесь, что на устройствах организации имеются последние обновления безопасности. 

Нужна помощь? См. документацию поставщика решений.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Убедитесь, что устройства организации устарели

Нужна помощь в обновлении устройств организации? См. следующие ресурсы:

|OS | Resource |
|:--|:--|
|Windows |[Центр обновления Майкрософт](https://www.update.microsoft.com) |
|macOS | [Обновление программного обеспечения на компьютере Mac](https://support.apple.com/HT201541)|
|iOS |[Обновление iPhone, iPad или iPod touch](https://support.apple.com/HT204204)|
|Android |[Проверка & обновления версии Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: обновление системы](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Get Microsoft Defender for Endpoint

Теперь, когда вы обновили устройства организации, следующим шагом будет получить Microsoft Defender для конечной точки, назначить лицензии и убедиться, что служба будет предусмотрена.

1. Купить или попробовать Microsoft Defender для конечной точки сегодня. [Начните бесплатную пробную работу или запросить цитату.](https://aka.ms/mdatp) 

2. Убедитесь, что лицензии надлежащим образом подготовить. [Проверьте состояние лицензии.](production-deployment.md#check-license-state)

3. В качестве глобального администратора или администратора безопасности установите специальный облачный экземпляр Microsoft Defender для конечной точки. См. [в веб-сайте Microsoft Defender для установки конечной точки: конфигурация клиента.](production-deployment.md#tenant-configuration)

4. Если конечные точки (например, устройства) в вашей организации используют прокси-сервер для доступа к Интернету, см. в [веб-сайте Microsoft Defender for Endpoint setup: Network configuration.](production-deployment.md#network-configuration)
 
На этом этапе вы готовы предоставить доступ администраторам безопасности и операторам безопасности, которые будут использовать Центр безопасности в Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Иногда Центр безопасности в Microsoft Defender называется порталом Microsoft Defender для конечных точек, к нему можно получить доступ по [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ссылке . 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Предоставление доступа к Центр безопасности в Microsoft Defender

В Центр безопасности в Microsoft Defender () вы можете получить доступ и настроить функции и возможности [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender для конечной точки. Дополнительные сведения [см. в обзоре Центр безопасности в Microsoft Defender.](use.md)

Разрешения для Центр безопасности в Microsoft Defender могут быть предоставлены с помощью базовых разрешений или управления доступом на основе ролей (RBAC). Рекомендуется использовать RBAC для более детального контроля над разрешениями.

1. Планирование ролей и разрешений для администраторов безопасности и операторов безопасности. См. [управление доступом на основе ролей.](prepare-deployment.md#role-based-access-control)

2. Настройка и настройка RBAC. Мы рекомендуем использовать [Intune](/mem/intune/fundamentals/what-is-intune) для настройки RBAC, особенно если в вашей организации используется сочетание устройств Windows 10, macOS, iOS и Android. Настройка [RBAC с помощью Intune](/mem/intune/fundamentals/role-based-access-control).

    Если вашей организации требуется метод, не intune, выберите один из следующих вариантов:

    - [Диспетчер конфигураций](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Расширенное управление групповыми политиками](/microsoft-desktop-optimization-pack/agpm)

    - [Windows Центр администрирования](/windows-server/manage/windows-admin-center/overview)

3. Предоставление доступа к Центр безопасности в Microsoft Defender. (Нужна помощь? См. [в руб. Управление доступом к порталу с помощью RBAC).](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Настройка параметров прокси-сервера устройства и подключения к Интернету

Чтобы включить связь между устройствами и Microsoft Defender для конечной точки, настройте параметры прокси и Интернета. В следующей таблице содержатся ссылки на ресурсы, которые можно использовать для настройки прокси-серверов и параметров Интернета для различных операционных систем и возможностей:

|Возможности  | Операционная система | Ресурсы |
|--|--|--|
|[Обнаружение конечных точек](overview-endpoint-detection-response.md) и ответ (EDR) |[Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Сервер 1803 или более поздний](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Настройка параметров прокси-сервера и подключения к Интернету](configure-proxy-internet.md) |
|EDR |[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 с пакетом обновления 1 (SP1)](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Настройка параметров прокси и подключения к Интернету](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)   |[Microsoft Defender для конечной точки на macOS: сетевые подключения](microsoft-defender-endpoint-mac.md#network-connections)  |
|[Антивирусная программа в Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) |[Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Сервер 1803 или более поздний](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Настройка и проверка сетевого подключения антивирусной программы в Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Защита от вирусов |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave) |[Microsoft Defender для конечной точки на macOS: сетевые подключения](microsoft-defender-endpoint-mac.md#network-connections) |
|Защита от вирусов |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender для конечной точки в Linux: сетевые подключения](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап **подготовки** перехода [на Microsoft Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Приступить к настройкам Microsoft Defender для конечной точки](switch-to-microsoft-defender-setup.md).
