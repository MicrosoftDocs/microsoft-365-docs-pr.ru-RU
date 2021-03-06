---
title: Onboard devices to the Microsoft Defender for Endpoint service
description: На борту Windows 10, серверов, Windows устройств и узнайте, как выполнить тест обнаружения.
keywords: onboarding, Microsoft Defender for Endpoint onboarding, sccm, group policy, mdm, local script, detection test
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933557"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Onboard devices to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Вам потребуется перейти в раздел onboarding портала Defender для конечной точки на борт любого из поддерживаемых устройств. В зависимости от устройства вы будете руководствоваться соответствующими действиями и предоставлять параметры средств управления и развертывания, подходящие для устройства. 

В общем, для бортовых устройств в службу:

- Убедитесь, что устройство выполняет [минимальные требования](minimum-requirements.md)
- В зависимости от устройства выполните этапы настройки, предусмотренные в разделе onboarding портала Defender for Endpoint.
- Использование соответствующего средства управления и метода развертывания для устройств
- Запустите тест обнаружения, чтобы убедиться, что устройства правильно на борту и отчеты службе

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Параметры onboarding tool
В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.

| Endpoint     | Параметры инструмента                       |
|--------------|------------------------------------------|
| **Windows**  |  [Локальный скрипт (до 10 устройств)](configure-endpoints-script.md) <br>  [Групповая политика](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Диспетчер мобильных устройств](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Скрипты VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Локальные сценарии](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Управление мобильными устройствами](mac-install-with-other-mdm.md) |
| **Linux Server** | [Локальный скрипт](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [На основе приложения](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>В этом разделе
Статья | Описание
:---|:---
[Подключение предыдущих версий Windows](onboard-downlevel.md)| На борту Windows 7 и Windows 8.1 устройств в Defender для конечной точки. 
[Подключение устройств Windows 10](configure-endpoints.md) | Чтобы сообщить об этом службе Defender для конечной точки, необходимо иметь бортовые устройства. Узнайте о средствах и методах, которые можно использовать для настройки устройств в вашем предприятии.
[Серверы на борту](configure-server-endpoints.md) |  Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) версии 1803 и более поздней версии Windows Server 2019 и Windows Server 2019 core edition to Defender for Endpoint.
[Подключение устройствах, отличных от Windows](configure-endpoints-non-windows.md) | Defender for Endpoint предоставляет централизованный опыт операций безопасности для Windows, а также Windows платформ. Вы сможете видеть оповещения из различных поддерживаемых операционных систем (ОС) в Центр безопасности в Microsoft Defender и лучше защищать сеть организации. Этот опыт использует данные датчиков сторонних продуктов безопасности. 
[Запуск теста обнаружения на новом подключенном устройстве](run-detection-test.md) | Запустите скрипт на новом устройстве, чтобы убедиться, что он должным образом сообщается службе Defender для конечных точек.
[Настройка параметров прокси и Интернета](configure-proxy-internet.md)| Включить связь с облачной службой Defender для конечной точки путем настройки параметров прокси-сервера и подключения к Интернету.
[Устранение неполадок с подключением](troubleshoot-onboarding.md) | Узнайте об устранении проблем, которые могут возникнуть во время бортовой платы.

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
