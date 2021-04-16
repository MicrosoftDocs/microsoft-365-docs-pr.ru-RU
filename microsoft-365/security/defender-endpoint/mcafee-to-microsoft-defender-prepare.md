---
title: McAfee в Microsoft Defender для конечной точки — подготовка
description: Это этап 1, Подготовка к миграции из McAfee в Microsoft Defender для конечной точки.
keywords: миграция, защита от угроз защитника Windows, atp, edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 45b22d0066496e40bb8f2e17d9f82de860d73ea4
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861427"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Миграция из McAfee — этап 1. Подготовка к миграции

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Этап 1. Подготовка](images/phase-diagrams/prepare.png)<br/>Этап 1. Подготовка |[![Этап 2. Настройка](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Этап 2. Настройка](mcafee-to-microsoft-defender-setup.md) |[![Этап 3. Подключение](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Этап 3. Подключение](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Вы здесь!*| | |


Добро пожаловать на этап Подготовки к переходу из **[McAfee Endpoint Security (McAfee) в Microsoft Defender для конечной точки](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. 

Этот этап миграции включает следующие действия:
1. [Получать и развертывать обновления на устройствах организации](#get-and-deploy-updates-across-your-organizations-devices)
2. [Получите Microsoft Defender для конечной точки](#get-microsoft-defender-for-endpoint).
3. [Предоставление доступа к Центру безопасности Защитника Майкрософт.](#grant-access-to-the-microsoft-defender-security-center)
4. [Настройка параметров прокси-сервера устройства](#configure-device-proxy-and-internet-connectivity-settings)и подключения к Интернету.

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Получать и развертывать обновления на устройствах организации

В качестве наилучшей практики следите за тем, чтобы устройства и конечные точки организации были в курсе. Убедитесь, что решение McAfee Endpoint Security (McAfee) обновлено, а операционные системы и приложения организации также имеют последние обновления. Это поможет предотвратить проблемы позже при переходе на антивирус Microsoft Defender для конечной точки и Microsoft Defender.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Убедитесь, что решение McAfee устарело

Следите за обновлениями McAfee и убедитесь, что на устройствах организации имеются последние обновления безопасности. Нужна помощь? Вот некоторые ресурсы McAfee:

- [Документация по корпоративным продуктам McAfee: как работает безопасность конечных точек](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [Техническая статья Центра знаний McAfee: Центр безопасности Windows периодически неправильно сообщает о том, что при работе с Windows 10 безопасность конечных точек отключена.](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [Техническая статья Центра знаний McAfee: Центр безопасности Windows сообщает, что при запуске endpoint Security отключается служба безопасности конечных точек.](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- Поддержка службы McAfee ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Убедитесь, что устройства организации устарели

Нужна помощь в обновлении устройств организации? См. следующие ресурсы:

|OS | Ресурс |
|:--|:--|
|Windows |[Центр обновления Майкрософт](https://www.update.microsoft.com) |
|macOS | [Обновление программного обеспечения на компьютере Mac](https://support.apple.com/HT201541)|
|iOS |[Обновление iPhone, iPad или iPod touch](https://support.apple.com/HT204204)|
|Android |[Проверка & обновления версии Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: обновление системы](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Get Microsoft Defender for Endpoint

Теперь, когда вы обновили устройства организации, следующим шагом будет получить Microsoft Defender для конечной точки, назначить лицензии и убедиться, что служба будет предусмотрена.

1. Купить или попробовать Microsoft Defender для конечной точки сегодня. [Начните бесплатную пробную работу или запросить цитату.](https://aka.ms/mdatp) 

2. Убедитесь, что лицензии надлежащим образом подготовить. [Проверьте состояние лицензии.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)

3. В качестве глобального администратора или администратора безопасности установите специальный облачный экземпляр Microsoft Defender для конечной точки. См. [в веб-сайте Microsoft Defender для установки конечной точки: конфигурация клиента.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)

4. Если конечные точки (например, устройства) в вашей организации используют прокси-сервер для доступа к Интернету, см. в [веб-сайте Microsoft Defender for Endpoint setup: Network configuration.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)
 
На этом этапе вы готовы предоставить доступ администраторам безопасности и операторам безопасности, которые будут использовать Центр безопасности Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Центр безопасности защитника Майкрософт иногда называют порталом Microsoft Defender для конечных точек. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Предоставление доступа к Центру безопасности защитника Майкрософт

Центр безопасности Защитника Майкрософт () — это место, где вы можете получить доступ и настроить функции и возможности [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender для конечной точки. Дополнительные сведения см. в обзоре Центра безопасности [защитника Майкрософт.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

Разрешения центру безопасности Microsoft Defender можно предоставить с помощью базовых разрешений или управления доступом на основе ролей (RBAC). Рекомендуется использовать RBAC для более детального контроля над разрешениями.

1. Планирование ролей и разрешений для администраторов безопасности и операторов безопасности. См. [управление доступом на основе ролей.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)

2. Настройка и настройка RBAC. Мы рекомендуем использовать [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) для настройки RBAC, особенно если ваша организация использует сочетание устройств с Windows 10, macOS, iOS и Android. Настройка [RBAC с помощью Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

    Если вашей организации требуется метод, не intune, выберите один из следующих вариантов:
    - [Диспетчер конфигураций](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Расширенное управление групповыми политиками](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Центр администрирования Windows](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Предоставление доступа к Центру безопасности Защитника Майкрософт. (Нужна помощь? См. [в руб. Управление доступом к порталу с помощью RBAC).](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Настройка параметров прокси-сервера устройства и подключения к Интернету

Чтобы включить связь между устройствами и Microsoft Defender для конечной точки, настройте параметры прокси и Интернета. В следующей таблице содержатся ссылки на ресурсы, которые можно использовать для настройки прокси-серверов и параметров Интернета для различных операционных систем и возможностей:

|Возможности  | Операционная система | Ресурсы |
|--|--|--|
|[Обнаружение конечных точек и ответ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 или более поздней версии](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Настройка параметров прокси-сервера и подключения к Интернету](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Настройка параметров прокси и подключения к Интернету](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave) <br/>- 10.13 (Высокая сьерра)  |[Microsoft Defender для конечной точки на macOS: сетевые подключения](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Антивирусная программа в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 или более поздней версии](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Настройка и проверка сетевого подключения антивирусной программы в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Защита от вирусов |macOS: <br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave) <br/>- 10.13 (Высокая сьерра) |[Microsoft Defender для конечной точки на macOS: сетевые подключения](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Защита от вирусов |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender для конечной точки в Linux: сетевые подключения](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап **подготовки** перехода из [McAfee в Microsoft Defender для конечной точки!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Приступить к настройкам Microsoft Defender для конечной точки](mcafee-to-microsoft-defender-setup.md).
