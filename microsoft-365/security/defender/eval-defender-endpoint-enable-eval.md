---
title: Включить microsoft Defender для оценки конечной точки, активировать оценку для MDE
description: Включите Microsoft 365 Defender пробную или пилотную среду, включая проверку состояния лицензии и onboarding enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458581"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Включить среду оценки конечных точек Microsoft Defender


В этой статье вы сможете с помощью производственных устройств принять меры по настройке среды оценки для Microsoft Defender для конечной точки. 


>[!TIP]
>Microsoft Defender для endpoint также поставляется с лабораторией оценки в продукте, где можно добавить предварительно настроенные устройства и запустить моделирование для оценки возможностей платформы. В лаборатории имеется упрощенная настройка, которая поможет быстро продемонстрировать значение Microsoft Defender для enpdoint, включая рекомендации по многим функциям, таким как расширенный анализ охоты и аналитика угроз. Дополнительные сведения см. в [дополнительных сведениях о возможностях Оценки.](/defender-endpoint/evaluation-lab.md) <br> Основное отличие руководства, представленного в этой статье, от лаборатории оценки состоит в том, что среда оценки использует производственные устройства, в то время как лаборатория оценки использует непроизводимые устройства. 

Чтобы включить оценку для Microsoft Defender для конечной точки, используйте следующие действия.

![Действия, направленные на то, чтобы включить Microsoft Defender для конечной точки в среде оценки Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [Шаг 1. Проверка состояния лицензии](#step-1-check-license-state)
- [Шаг 2. Конечные точки на борту](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Этап 1. Проверка состояния лицензии

Сначала необходимо проверить состояние лицензии, чтобы убедиться, что оно было правильно заложено. Это можно сделать через центр администрирования или через **портал Microsoft Azure.**


1. Чтобы просмотреть лицензии, перейдите на портал **Microsoft Azure и** перейдите в раздел лицензии Microsoft Azure [портала](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).

   ![Изображение страницы лицензирования Azure](../../media/defender/atp-licensing-azure-portal.png)

1. Поочередно в центре администрирования перейдите к **подпискам на**  >  **биллинг.**

    На экране вы увидите все предварительные лицензии и их текущее **состояние.**

    ![Изображение лицензий на выставление счета](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Этап 2. Конечные точки на борту с использованием любого из поддерживаемых средств управления

После проверки правильного состояния лицензии можно запустить бортовые устройства в службу. 

Для оценки Microsoft Defender для конечной точки рекомендуется выбрать несколько Windows 10 для проведения оценки. 

В [разделе Развертывание](../defender-endpoint/deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.  

Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Параметры onboarding tool

В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.

Конечная точка | Параметры инструмента
:---|:---
**Windows** | [Локальный скрипт (до 10 устройств),](../defender-endpoint/configure-endpoints-script.md)групповой политики [,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/](../defender-endpoint/configure-endpoints-mdm.md)Диспетчер мобильных устройств , [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [сценарии VDI](../defender-endpoint/configure-endpoints-vdi.md), [интеграция](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) с Azure Defender
**macOS** | [Локальные сценарии](../defender-endpoint/mac-install-manually.md) [, Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), управление [мобильными устройствами](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux Server** | [Локальный](../defender-endpoint/linux-install-manually.md)  [сценарий](../defender-endpoint/linux-install-with-puppet.md), Кукольный ,  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [На основе приложения](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>Следующее действие
[Настройка пилотного проекта для Microsoft Defender для конечной точки](eval-defender-endpoint-pilot.md)
 
Возвращение к обзору [оценки Microsoft Defender для конечной точки](eval-defender-endpoint-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)