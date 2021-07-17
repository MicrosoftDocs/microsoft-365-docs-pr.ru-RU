---
title: Пилотные Microsoft Cloud App Security с Microsoft 365 Defender, создание пилотных групп, настройка условного управления доступом, опробовка возможностей, установка в Microsoft 365 Defender
description: Настройка пробной Microsoft 365 Defender или пилотной среды для тестирования и тестирования решения безопасности, предназначенного для защиты устройств, удостоверений, данных и приложений.
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
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458544"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>Пилотный Microsoft Cloud App Security с Microsoft 365 Defender


**Область применения:**
- Microsoft 365 Defender

Эта статья [— шаг 3 из 3](eval-defender-mcas-overview.md) в процессе настройки среды оценки для Microsoft Cloud App Security. Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-mcas-overview.md)

Чтобы настроить пилотный пилот для Microsoft Cloud App Security, используйте следующие действия.


![Этапы пилотирования Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- Этап 1. [Создание пилотной группы — область развертывания пилотного развертывания для определенных групп пользователей](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [Шаг 2. Настройка защиты — управление приложениями условного доступа](#step-2-configure-protection--conditional-access-app-control)
- [Шаг 3. Опробуйте возможности — пройдитесь по учебникам по защите среды](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>Этап 1. Создание пилотной группы — область развертывания пилотного развертывания для определенных групп пользователей

Microsoft Cloud App Security позволяет расширить область развертывания. Scoping позволяет выбрать определенные группы пользователей, которые будут отслеживаться для приложений или исключены из мониторинга. Можно включить или исключить группы пользователей. Чтобы расширить область развертывания пилотного развертывания, см. [в поле Scoped Deployment.](/cloud-app-security/scoped-deployment)


## <a name="step-2-configure-protection--conditional-access-app-control"></a>Этап 2. Настройка защиты — управление приложениями условного доступа

Одной из самых мощных средств защиты, которые можно настроить, является управление приложениями условного доступа. Это требует интеграции с Azure Active Directory (Azure AD). Это позволяет применять политики условного доступа, в том числе связанные политики (например, требующие здоровых устройств), для облачных приложений, которые вы санкционировали. 

Первым шагом к использованию Microsoft Cloud App Security для управления приложениями SaaS является обнаружение этих приложений и добавление их в клиент Azure AD. Если вам нужна помощь в обнаружении, см. [в справке Откройте и управляйте приложениями SaaS в сети.](/cloud-app-security/tutorial-shadow-it) После обнаружения приложений добавьте их в клиент [Azure AD.](/azure/active-directory/manage-apps/add-application-portal)

Вы можете начать управлять этими данными, делая следующее:

- Сначала в Azure AD создайте новую политику условного доступа и настройте ее на "Управление приложениями условного доступа". Это перенаправляет запрос на Cloud App Security. Вы можете создать одну политику и добавить все приложения SaaS в эту политику.
- Далее в Cloud App Security создайте политики сеанса. Создайте по одной политике для каждого необходимого управления.

Дополнительные сведения, в том числе поддерживаемые приложения и клиенты, см. в Microsoft Cloud App Security с управлением приложениями [условного доступа.](/cloud-app-security/proxy-intro-aad) 

Например, политики см. [в Microsoft Cloud App Security для приложений SaaS.](../office-365-security/mcas-saas-access-policies.md) Эти политики строятся на [](../office-365-security/microsoft-365-policies-configurations.md) наборе общих политик доступа к удостоверениям и устройствам, которые рекомендуется использовать в качестве отправной точки для всех клиентов. 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>Этап 3. Опробуйте возможности — пройдитесь по учебникам по защите среды 

В Microsoft Cloud App Security документации содержится ряд учебных пособий, которые помогут вам обнаружить риски и защитить окружающую среду. 

Попробуйте Cloud App Security руководства:

- [Обнаружение подозрительных действий пользователей](/cloud-app-security/tutorial-suspicious-activity)
- [Исследование рискованных пользователей](/cloud-app-security/tutorial-ueba)
- [Исследование рискованных приложений OAuth](/cloud-app-security/investigate-risky-oauth)
- [Обнаружение и защита конфиденциальной информации](/cloud-app-security/tutorial-dlp)
- [Защита любого приложения в организации в режиме реального времени](/cloud-app-security/tutorial-proxy)
- [Блокировка скачивания конфиденциальной информации](/cloud-app-security/use-case-proxy-block-session-aad)
- [Защита файлов с помощью карантина администратора](/cloud-app-security/use-case-admin-quarantine)
- [Требуются дополнительные проверки подлинности при рискованных действиях](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a>Дальнейшие действия

[Исследование и реагирование с Microsoft 365 Defender в пилотной среде](eval-defender-investigate-respond.md)

Возвращайся к обзору [для Оценки Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md)