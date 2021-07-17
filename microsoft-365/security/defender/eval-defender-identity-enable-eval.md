---
title: Включить среду оценки для Microsoft Defender для identity, настроить экземпляр MDI, установить и настроить датчик MDI, чтобы датчик MDI обнаруживать локальных администраторов
description: Настройка Microsoft Defender для удостоверений в Microsoft 365 Defender пробной лаборатории или пилотной среде путем & настройки датчика и обнаружения локальных администраторов на других компьютерах.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458563"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Включить среду оценки для Microsoft Defender для удостоверений

**Область применения:**
- Microsoft 365 Defender

Эта статья — [шаг 2 из 2 в](eval-defender-identity-overview.md) процессе настройки среды оценки для Microsoft Defender для identity. Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-identity-overview.md)

Чтобы настроить среду Microsoft Defender для удостоверений, используйте следующие действия. 

![Действия, направленные на то, чтобы включить Microsoft Defender для удостоверений в среде оценки Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [Шаг 1. Настройка экземпляра Defender для удостоверения](#step-1-set-up-the-defender-for-identity-instance)
- [Шаг 2. Установка и настройка датчика](#step-2-install-and-configure-the-sensor)
- [Шаг 3. Настройка параметров журнала событий и прокси на компьютерах с помощью датчика](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Шаг 4. Разрешить defender for Identity для идентификации локальных администраторов на других компьютерах](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Этап 1. Настройка экземпляра Defender для удостоверения

Во входе на портал Defender for Identity для создания экземпляра и подключения этого экземпляра к среде Active Directory. 

|  |Шаг     |Дополнительная информация  |
|---------|---------|---------|
|1     | Создание экземпляра Defender для удостоверения        | [Quickstart: создание экземпляра Microsoft Defender для удостоверений](/defender-for-identity/install-step1)        |
|2     | Подключение экземпляр Defender for Identity в лесу Active Directory   | [Quickstart: Подключение в ваш лес Active Directory](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>Этап 2. Установка и настройка датчика

Затем скачайте, установите и настройте датчик Defender for Identity на контроллерах домена и серверах AD FS в локальной среде.

|  |Шаг     |Дополнительная информация  |
|---------|---------|---------|
|1     | Определите количество необходимых датчиков Microsoft Defender для удостоверений.        | [Планирование емкости для Microsoft Defender для удостоверений](/defender-for-identity/capacity-planning)   |
|2     | Скачайте пакет установки датчика  |  [Quickstart: Скачайте пакет установки датчика идентификации Microsoft Defender для идентификации](/defender-for-identity/install-step3)   |
|3     | Установка датчика Defender для удостоверений    |  [Quickstart: Установите датчик Microsoft Defender для удостоверений](/defender-for-identity/install-step4)       |
|4      | Настройка датчика       |  [Настройка параметров датчика удостоверений Для защитника Майкрософт ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Этап 3. Настройка параметров журнала событий и прокси на компьютерах с помощью датчика

На компьютерах, на которые установлен датчик, настройте Windows журнал событий и параметры прокси-сервера в Интернете, чтобы включить и повысить возможности обнаружения.

|  |Шаг     |Дополнительная информация  |
|---------|---------|---------|
|1     | Настройка Windows журнала событий         | [Настройка коллекции Windows событий](/defender-for-identity/configure-windows-event-collection)        |
|2     | Настройка параметров прокси-сервера в Интернете        | [Настройка параметров прокси-сервера конечной точки и подключения к Интернету для датчика удостоверений Microsoft Defender](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Этап 4. Разрешить defender for Identity для идентификации локальных администраторов на других компьютерах

Обнаружение путей с последующим движением в Microsoft Defender для удостоверений зависит от запросов, определяющих локальных администраторов на определенных машинах. Эти запросы выполняются с помощью протокола SAM-R с помощью учетной записи Defender для службы удостоверений. 

Чтобы Windows клиенты и серверы позволяли учетной записи Defender for Identity выполнять SAM-R, необходимо внести изменения в групповую политику, чтобы добавить учетную запись службы Defender для удостоверений в дополнение к настроенным учетным записям, указанным в политике доступа к сети. Не забудьте применить групповые политики на всех компьютерах, **кроме контроллеров домена.**

Инструкции по этому делать см. в инструкции [Configure Microsoft Defender for Identity, чтобы сделать удаленные вызовы в SAM.](/defender-for-identity/install-step8-samr) 

## <a name="next-steps"></a>Дальнейшие действия

Шаг 3 из 3: [пилотный microsoft Defender для удостоверений](eval-defender-identity-pilot.md)

Возвращение к обзору [оценки microsoft Defender для удостоверений](eval-defender-identity-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)