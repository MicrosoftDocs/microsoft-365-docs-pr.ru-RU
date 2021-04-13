---
title: На борту службы Microsoft Defender для конечных точек
description: Узнайте, как переназначить конечные точки в службу Microsoft Defender для конечных точек
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689537"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>На борту службы Microsoft Defender для конечных точек

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Узнайте о различных этапах развертывания Microsoft Defender для конечной точки и о настройке возможностей решения. 

Развертывание Defender для конечной точки — это трех этапный процесс:

| [![этап развертывания — подготовка](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Этап 1. Подготовка](prepare-deployment.md) | [![этап развертывания — установка](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Этап 2. Настройка](production-deployment.md) | ![этап развертывания — на борту](images/phase-diagrams/onboard.png)<br>Этап 3. Подключение |
| ----- | ----- | ----- |
| | |*Вы здесь!*|

В настоящее время вы находитесь на этапе вмеяния.

Вот шаги, которые необходимо предпринять для развертывания Defender для конечной точки:

- Шаг 1. Конечные точки на борту службы 
- Шаг 2. Настройка возможностей 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Шаг 1. Конечные точки на борту с помощью любого из поддерживаемых средств управления
В [разделе Развертывание](deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.  


Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



После определения архитектуры необходимо решить, какой метод развертывания использовать. Инструмент развертывания, который вы выбираете, влияет на то, как вы работаете с конечными точками на борту службы. 

### <a name="onboarding-tool-options"></a>Параметры onboarding tool

В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.

| Endpoint     | Параметры инструмента                       |
|--------------|------------------------------------------|
| **Windows**  |  [Локальный скрипт (до 10 устройств)](configure-endpoints-script.md) <br>  [Групповая политика](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Скрипты VDI](configure-endpoints-vdi.md) <br> [Центр безопасности Azure](configure-server-endpoints.md#integration-with-azure-security-center) |
| **macOS**    | [Локальные сценарии](mac-install-manually.md) <br> [Менеджер конечных точек Майкрософт](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Управление мобильными устройствами](mac-install-with-other-mdm.md) |
| **Linux Server** | [Локальный скрипт](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [На основе приложения](ios-install.md)                                |
| **Android**  | [Менеджер конечных точек Майкрософт](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Шаг 2. Настройка возможностей
После настроя конечных точек вы настроите различные возможности, такие как обнаружение конечной точки и реагирование, защита следующего поколения и уменьшение поверхности атаки. 


## <a name="example-deployments"></a>Пример развертывания
В этом руководстве по развертыванию мы назначим вам использование двух средств развертывания для конечных точек на борту и настройку возможностей.

Средства в примере развертывания:
- [Подключение с помощью Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Подключение с помощью Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Используя указанные выше средства развертывания, вы будете руководствоваться настройкой следующих возможностей Defender для конечных точек:
- Конфигурация обнаружения конечных точек и ответов
- Конфигурация защиты следующего поколения
- Конфигурация уменьшения поверхности атаки

## <a name="related-topics"></a>Статьи по теме
- [Подключение с помощью Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Подключение с помощью Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Безопасные документы в Microsoft 365 E5](../office-365-security/safe-docs.md)
