---
title: Пилотный защитник для оценки конечной точки
description: Внося Microsoft 365 Defender пробную или пилотную среду.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458640"
---
# <a name="pilot-mde-evaluation"></a>Пилотная оценка MDE

>[!NOTE]
>Для того, чтобы направлять вас через типичное развертывание, этот сценарий будет охватывать только использование Microsoft Endpoint Configuration Manager. Defender for Endpoint поддерживает использование других средств бортового использования, но не покрывает эти сценарии в руководстве по развертыванию. Дополнительные сведения см. в таблице [Onboard devices to Microsoft Defender for Endpoint.](onboard-configure.md)

## <a name="step-1-check-license-state"></a>Этап 1. Проверка состояния лицензии

Проверка состояния лицензии и правильного ее состояния можно сделать через центр администрирования или на **портале Microsoft Azure.**

1. Чтобы просмотреть лицензии, перейдите на портал **Microsoft Azure и** перейдите в раздел лицензии Microsoft Azure [портала](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).

   ![Изображение страницы лицензирования Azure](images/atp-licensing-azure-portal.png)

1. Поочередно в центре администрирования перейдите к **подпискам на**  >  **биллинг.**

    На экране вы увидите все предварительные лицензии и их текущее **состояние.**

    ![Изображение лицензий на выставление счета](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Этап 2. Конечные точки на борту с использованием любого из поддерживаемых средств управления

В [разделе Развертывание](deployment-strategy.md) Plan описаны общие действия, которые необходимо предпринять для развертывания Defender для конечной точки.  

Просмотрите это видео, чтобы получить краткий обзор процесса работы с бортовой частью и узнать о доступных средствах и методах.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

После определения архитектуры необходимо решить, какой метод развертывания использовать. Инструмент развертывания, который вы выбираете, влияет на то, как вы работаете с конечными точками на борту службы.

### <a name="onboarding-tool-options"></a>Параметры onboarding tool

В следующей таблице перечислены доступные средства, основанные на конечной точке, которую необходимо использовать на борту.

| Конечная точка     | Параметры инструмента                       |
|--------------|------------------------------------------|
| **Windows**  |  [Локальный скрипт (до 10 устройств)](../defender-endpoint/configure-endpoints-script.md) <br> [Групповая политика](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/ Диспетчер мобильных устройств](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [Скрипты VDI](../defender-endpoint/configure-endpoints-vdi.md) <br> [Интеграция с Защитником Azure](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [Местные сценарии](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [Управление мобильными устройствами](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [Локальный скрипт](../defender-endpoint/linux-install-manually.md) <br> [Puppet](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [На основе приложения](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)               |
