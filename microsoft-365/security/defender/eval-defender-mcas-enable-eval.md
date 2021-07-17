---
title: Включить среду оценки для Microsoft Cloud App Security
description: Узнайте архитектуру MCAS в Microsoft Defender для Office 365 и узнайте о взаимодействии между Microsoft 365 Defender продуктами.
keywords: Microsoft 365 Defender пробной версии попробуйте Microsoft 365 Defender, оцените Microsoft 365 Defender, Microsoft 365 Defender лаборатории оценки, пилот Microsoft 365 Defender, кибербезопасность, расширенные постоянные угрозы, безопасность предприятия, устройства, устройства, удостоверения, пользователей, данные, приложения, инциденты, автоматическое расследование и исправление, продвинутая охота
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458545"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>Включить среду оценки для Microsoft Cloud App Security


**Область применения:**

- Microsoft 365 Defender

Эта статья [— шаг 2 из 2](eval-defender-mcas-overview.md) в процессе настройки среды оценки для Microsoft Cloud App Security. Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-mcas-overview.md)

В этой статье вы можете получить доступ к порталу Cloud App Security и настроить необходимую интеграцию для сбора данных трафика облачных приложений.

Чтобы найти облачные приложения, используемые в среде, можно сделать одно или оба следующих:

- Быстро встать и работать с cloud Discovery, интегрируясь с Microsoft Defender для конечной точки. Эта нативная интеграция позволяет сразу же приступить к сбору данных по облачному трафику на Windows 10 устройствах, в сети и вне ее.
- Чтобы узнать все облачные приложения, доступ к которые доступны на всех устройствах, подключенных к сети, разместите Cloud App Security журнала на брандмауэрах и других прокси-экранах. Это собирает данные из конечных точек и отправляет их в Cloud App Security для анализа. Cloud App Security интегрируется с некоторыми сторонними прокси для еще большего потенциала.

В этой статье содержатся рекомендации по обоим методам.

Чтобы настроить Microsoft Cloud App Security, используйте следующие действия.

![Действия, позволяющие Microsoft Cloud App Security Microsoft в среде оценки Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Шаг 1. Подключение на портал Cloud App Security](#step-1-connect-to-the-cloud-app-security-portal)
- [Шаг 2. Интеграция с Microsoft Defender для конечной точки](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [Шаг 3. Развертывание Cloud App Security журнала на брандмауэрах и других прокси](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [Шаг 4. Просмотр панели мониторинга облачного обнаружения, чтобы узнать, какие приложения используются в организации](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>Этап 1. Подключение на портал Cloud App Security

Чтобы проверить лицензирование и подключиться к порталу Cloud App Security, см. в обзоре [Quickstart: Начало работы с Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security). 

Если вы не можете сразу подключиться к порталу, может потребоваться добавить IP-адрес в допустимый список брандмауэра. См. [основные настройки для Cloud App Security.](/cloud-app-security/general-setup)

Если у вас по-прежнему возникли проблемы, просмотрите [требования к сети.](/cloud-app-security/network-requirements)

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Этап 2. Интеграция с Microsoft Defender для конечной точки

Microsoft Cloud App Security интегрируется с Microsoft Defender для конечной точки. Интеграция упрощает внедрение cloud Discovery, расширяет возможности cloud Discovery за пределами корпоративной сети и позволяет вести исследование на основе устройств. Эта интеграция показывает облачные приложения и службы, к которым можно получить доступ с ИТ-Windows 10 устройств. 

Если вы уже настроили Microsoft Defender для конечной точки, настройка интеграции с Cloud App Security является Microsoft 365 Defender. После включаемой интеграции можно вернуться на портал Cloud App Security и просмотреть богатые данные на панели мониторинга обнаружения облаков.

Для выполнения этих задач см. [в веб-сайте Microsoft Defender для интеграции](/cloud-app-security/mde-integration)конечных точек с Microsoft Cloud App Security. 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>Этап 3. Развертывание Cloud App Security журнала на брандмауэрах и других прокси

Для покрытия всех устройств, подключенных к сети, разместите Cloud App Security журнала на брандмауэрах и других прокси для сбора данных с конечных точек и отправки их в Cloud App Security для анализа. 

Если вы используете один из следующих безопасных веб-шлюзов (SWG), Cloud App Security обеспечивает бесшовное развертывание и интеграцию:
- Zscaler
- iboss
- Corrata
- Безопасность Menlo

Дополнительные сведения об интеграции с этими сетевыми устройствами см. в [сайте Set up Cloud Discovery.](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Этап 4. Просмотр панели мониторинга облачного обнаружения, чтобы узнать, какие приложения используются в организации

Панель мониторинга обнаружения облаков предназначена для получения дополнительных данных о том, как облачные приложения используются в организации. Он предоставляет краткий обзор используемых приложений, открытых оповещений и уровней риска приложений в организации. 

Чтобы начать работу с панели мониторинга cloud Discovery, см. в странице [Работа с обнаруженными приложениями.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Дальнейшие действия

Шаг 3 из 3. [Пилотный Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

Возвращайся к обзору [для Оценки Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)