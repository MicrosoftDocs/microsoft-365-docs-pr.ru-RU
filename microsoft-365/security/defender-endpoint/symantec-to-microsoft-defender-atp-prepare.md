---
title: Symantec в Microsoft Defender для конечной точки — этап 1, подготовка
description: Это этап 1 , Подготовка, миграции из Symantec в Microsoft Defender для конечной точки.
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: bba48803863cd330b371c24600239462b1ca9250
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327418"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Миграция из Symantec — этап 1. Подготовка к миграции

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Этап 1. Подготовка](images/phase-diagrams/prepare.png)<br/>Этап 1. Подготовка |[![Этап 2. Настройка](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Этап 2. Настройка](symantec-to-microsoft-defender-atp-setup.md) |[![Этап 3. Подключение](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Этап 3. Подключение](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Вы здесь!*| | |


**Добро пожаловать на этап Подготовки к [переходу из Symantec в Microsoft Defender для конечной точки.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

Этот этап миграции включает следующие действия:
1. [Получите Microsoft Defender для конечной точки](#get-microsoft-defender-for-endpoint).
2. [Предоставление доступа к Центру безопасности Защитника Майкрософт.](#grant-access-to-the-microsoft-defender-security-center)
3. [Настройка параметров прокси-сервера устройства](#configure-device-proxy-and-internet-connectivity-settings)и подключения к Интернету.

## <a name="get-microsoft-defender-for-endpoint"></a>Get Microsoft Defender for Endpoint

Чтобы начать работу, необходимо иметь Microsoft Defender для конечной точки с присвоением и подготовкаю лицензий.

1. Купить или попробовать Microsoft Defender для конечной точки сегодня. [Посетите Microsoft Defender для конечной точки, чтобы начать бесплатную пробную запись или запросить цитату.](https://aka.ms/mdatp) 
2. Убедитесь, что лицензии надлежащим образом подготовить. [Проверьте состояние лицензии.](production-deployment.md#check-license-state)
3. В качестве глобального администратора или администратора безопасности установите специальный облачный экземпляр Microsoft Defender для конечной точки. См. [в веб-сайте Microsoft Defender для установки конечной точки: конфигурация клиента.](production-deployment.md#tenant-configuration)
4. Если конечные точки (например, устройства) в вашей организации используют прокси-сервер для доступа к Интернету, см. в [веб-сайте Microsoft Defender for Endpoint setup: Network configuration.](production-deployment.md#network-configuration)
 
На этом этапе вы готовы предоставить доступ администраторам безопасности и операторам безопасности, которые будут использовать Центр безопасности Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Центр безопасности защитника Майкрософт иногда называют порталом Microsoft Defender для конечных точек. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Предоставление доступа к Центру безопасности защитника Майкрософт

Центр безопасности Защитника Майкрософт () — это место, где вы можете получить доступ и настроить функции и возможности [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender для конечной точки. Дополнительные сведения см. в обзоре Центра безопасности [защитника Майкрософт.](use.md)

Разрешения центру безопасности Microsoft Defender можно предоставить с помощью базовых разрешений или управления доступом на основе ролей (RBAC). Рекомендуется использовать RBAC для более детального контроля над разрешениями.

1. Планирование ролей и разрешений для администраторов безопасности и операторов безопасности. См. [управление доступом на основе ролей.](prepare-deployment.md#role-based-access-control)
2. Настройка и настройка RBAC. Мы рекомендуем использовать [Intune](/mem/intune/fundamentals/what-is-intune) для настройки RBAC, особенно если ваша организация использует сочетание устройств с Windows 10, macOS, iOS и Android. Настройка [RBAC с помощью Intune](/mem/intune/fundamentals/role-based-access-control).<br/>
   Если вашей организации требуется метод, не intune, выберите один из следующих вариантов:
    - [Диспетчер конфигураций](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Расширенное управление групповыми политиками](/microsoft-desktop-optimization-pack/agpm)
    - [Центр администрирования Windows](/windows-server/manage/windows-admin-center/overview)
3. Предоставление доступа к Центру безопасности Защитника Майкрософт. (Нужна помощь? См. [в руб. Управление доступом к порталу с помощью RBAC).](rbac.md)

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Настройка параметров прокси-сервера устройства и подключения к Интернету

Чтобы включить связь между устройствами и Microsoft Defender для конечной точки, настройте параметры прокси и Интернета. В следующей таблице содержатся ссылки на ресурсы, которые можно использовать для настройки прокси-серверов и параметров Интернета для различных операционных систем и возможностей:

|Возможности  | Операционная система | Ресурсы |
|:----|:----|:---|
|[Обнаружение конечных точек и ответ](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 или более поздней версии](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Настройка параметров прокси-сервера и подключения к Интернету](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Настройка параметров прокси и подключения к Интернету](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave) <br/>- 10.13 (Высокая сьерра)  |[Microsoft Defender для конечной точки на macOS: сетевые подключения](microsoft-defender-endpoint-mac.md#network-connections) |
|[Антивирусная программа в Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 или более поздней версии](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Настройка и проверка сетевого подключения антивирусной программы в Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Защита от вирусов |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Каталина)<br/>- 10.14 (Mojave)  |[Microsoft Defender для конечной точки на Mac: сетевые подключения](microsoft-defender-endpoint-mac.md#network-connections) |
|Защита от вирусов |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS или более высокий LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender для конечной точки в Linux: сетевые подключения](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Следующий шаг

**Поздравляем!** Вы завершили этап **подготовки** перехода из [Symantec в Microsoft Defender для конечной точки!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Приступить к настройкам Microsoft Defender для конечной точки](symantec-to-microsoft-defender-atp-setup.md).
