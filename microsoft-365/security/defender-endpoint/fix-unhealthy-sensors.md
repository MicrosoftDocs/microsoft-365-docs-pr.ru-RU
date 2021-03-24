---
title: Исправление нездоровых датчиков в Microsoft Defender для конечной точки
description: Исправьте датчики устройств, которые сообщают о неправильном или неактивном устройстве, чтобы служба получала данные с устройства.
keywords: неправильно сконфигурированная, неактивность, исправление датчика, состояние датчика, отсутствие данных датчиков, данных датчиков, нарушенная связь, связь
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a24dc4ef23d32b19de9d2871b7d87aae90d05828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073734"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Исправление нездоровых датчиков в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

Устройства, которые классифицируются как неправильно сконфигурированы или неактивны, могут быть помечены из-за различных причин. В этом разделе приводится ряд объяснений того, что могло привести к тому, что устройство было классифицироваться как неактивное или неправильное.

## <a name="inactive-devices"></a>Неактивные устройства

Неактивное устройство не обязательно помечено из-за проблемы. Следующие действия, принятые на устройстве, могут привести к категоризированию устройства как неактивного:

### <a name="device-is-not-in-use"></a>Устройство не используется

Если устройство по какой-либо причине не используется более семи дней, оно останется в состоянии "Неактивно" на портале.

### <a name="device-was-reinstalled-or-renamed"></a>Устройство было переустановлено или переименовано
Переустановленное или переименованное устройство будет создавать новое устройство в Центре безопасности Microsoft Defender. Предыдущее устройство останется со статусом "Неактивный" на портале. Если вы переустановили устройство и развернули пакет Defender for Endpoint, ищите новое имя устройства, чтобы убедиться, что устройство сообщает нормально.

### <a name="device-was-offboarded"></a>Устройство было отключено
Если устройство было отключено, оно по-прежнему будет отображаться в списке устройств. Через семь дней состояние состояния здоровья устройства должно измениться на неактивное.

### <a name="device-is-not-sending-signals"></a>Устройство не отправляет сигналы
Если устройство не отправляет сигналы в течение более семи дней ни в один из каналов Microsoft Defender для конечных точек по любой причине, включая условия, которые попадают под классификацию неправильного устройства, устройство можно считать неактивным. 

Ожидаете ли вы, что устройство будет в состоянии "Active"? [Откройте билет поддержки.](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)

## <a name="misconfigured-devices"></a>Неправильно сконфигуративные устройства
Неправильное устройство можно далее классифицировать так:
- Нарушение связи
- Нет данных датчика

### <a name="impaired-communications"></a>Нарушение связи
Этот статус указывает, что связь между устройством и службой ограничена.

Следующие предлагаемые действия могут помочь устранить проблемы, связанные с неправильно сконфигурованным устройством с нарушениями связи:

- [Убедитесь, что устройство подключено к Интернету](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Датчик ATP защитника окна требует от Microsoft Windows HTTP (WinHTTP) сообщать данные датчиков и общаться с службой Microsoft Defender для конечных точек.

- [Проверка подключения клиента к URL-адресам службы Microsoft Defender для конечных точек](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  Убедитесь, что конфигурация прокси успешно завершена, что WinHTTP может обнаруживаться и общаться через прокси-сервер в вашей среде, и что прокси-сервер позволяет трафик на URL-адреса службы Microsoft Defender для конечной точки.

Если вы приняли меры по исправлению и состояние устройства по-прежнему неправильно сконфигурировали, [откройте билет поддержки.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

### <a name="no-sensor-data"></a>Нет данных датчика
Неправильное устройство со статусом "Нет данных датчика" имеет связь со службой, но может сообщать только о частичных данных датчика.
Выполните действия по исправлению известных проблем, связанных с неправильно сконфигурованным устройством со статусом "Нет данных датчика":

- [Убедитесь, что устройство подключено к Интернету](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Датчик ATP защитника окна требует от Microsoft Windows HTTP (WinHTTP) сообщать данные датчиков и общаться с службой Microsoft Defender для конечных точек.

- [Проверка подключения клиента к URL-адресам службы Microsoft Defender для конечных точек](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  Убедитесь, что конфигурация прокси успешно завершена, что WinHTTP может обнаруживаться и общаться через прокси-сервер в вашей среде, и что прокси-сервер позволяет трафик на URL-адреса службы Microsoft Defender для конечной точки.

- [Убедитесь, что служба диагностических данных включена](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Если устройства не сообщают правильно, может потребоваться проверить, должна ли служба диагностических данных Windows 10 автоматически запускаться и работать на конечной точке.

- [Убедитесь, что антивирус Microsoft Defender не отключен политикой](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Если на ваших устройствах работает сторонний клиент противомалярийных программ, агенту Defender для конечных точек необходим драйвер раннего запуска антивирусных программ Microsoft Defender (ELAM).

Если вы приняли меры по исправлению и состояние устройства по-прежнему неправильно сконфигурировали, [откройте билет поддержки.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

## <a name="see-also"></a>См. также
- [Проверка состояния состояния датчика в Microsoft Defender для конечной точки](check-sensor-status.md)
