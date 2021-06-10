---
title: Оценка Microsoft 365 Defender
description: Настройка пробной Microsoft 365 или пилотной среды Defender, чтобы опробовыть и испытать решение безопасности, предназначенное для защиты устройств, удостоверений, данных и приложений в организации.
keywords: Microsoft 365 Defender trial, try Microsoft 365 Defender, evaluate Microsoft 365 Defender, Microsoft 365 Defender assessment lab, Microsoft 365 Defender pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933173"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Создание пробной Microsoft 365 Defender или пилотной среды 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


В этом руководстве помогают настраивать лабораторную среду с пользователями и группами, а затем проходить настройку возможностей в Microsoft 365 Defender, чтобы можно было имитировать угрозу и получить значимый пробный результат. 

Цель создания этой пробной лаборатории или пилотной среды заключается в том, чтобы проиллюстрировать комплексные и интегрированные возможности Microsoft 365 Defender. Изучите, как это интеллектуальное решение безопасности обнаруживает, предотвращает, автоматически расследует и реагирует на расширенные угрозы вашей организации. 


Вы будете руководствоваться действиями, чтобы начать оценку Microsoft 365 Defender на основе рекомендуемых путей развертывания. Цель состоит в том, чтобы помочь вам настроить решение безопасности либо в лаборатории с пробной учетной записью, либо в пилотной среде в производстве с полной лицензией. Подготовка пробной лаборатории или пилотной среды может помочь вам представить случаи использования операций безопасности для лиц, принимающих решения в вашей организации. После запуска имитации атак и удовлетворенных результатами вы можете полностью развернуть и использовать его в организации с помощью специалистов по техническим продажам Майкрософт или экспертов в вашей организации. 

Это руководство поможет вам:
- Настройка лабораторного сервера и компьютеров
- Настройка Active Directory с пользователями и группами
- Настройка и настройка Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и Microsoft Cloud App Security
- Настройка локальных политик для сервера и компьютеров
- Имитация атаки угрозы для создания тестового инцидента или оповещения в Microsoft 365 Defender

>[!IMPORTANT]
>Для достижения оптимальных результатов выполните инструкции по настройке лаборатории как можно ближе.


## <a name="deployment-phases"></a>Этапы развертывания

Создание среды пробной лаборатории defender Microsoft 365 трех этапов.

![Этапы развертывания: подготовка, настройка, бортовой](../../media/evaluation-guide-phases.png)

|Этап | Описание | 
|:-------|:-----|
|[Этап 1. Подготовка](prepare-m365d-eval.md)| Узнайте, что необходимо учитывать при развертывании Microsoft 365 Defender в пробной лаборатории или пилотной среде: <br><br>- Заинтересованные лица и вход <br> - Соображения среды <br>- Доступ <br>- Azure Active Directory установки <br> - Порядок конфигурации
|[Этап 2. Настройка](setup-m365deval.md)|  Сначала необходимо получить доступ к центру Microsoft 365 безопасности, чтобы настроить пробную лабораторию Microsoft 365 Defender или пилотную среду. Вы будете руководствоваться:<br><br>- Подпишитесь на Microsoft 365 E5 пробную <br>  - Настройка домена<br>- Назначение Microsoft 365 E5 лицензий<br>- Завершите мастер установки на портале|
|[Этап 3. Настройка & на борту](config-m365d-eval.md) | Настройте каждый столб Microsoft 365 Defender и конечные точки на борту. Вы будете руководствоваться:<br><br>- Настройка Microsoft Defender для Office 365<br>- Настройка Microsoft Cloud App Security<br>- Настройка Microsoft Defender для удостоверений<br>- Настройка Microsoft Defender для конечной точки


После завершения этого руководства вы бы определили заинтересованных лиц и необходимые утверждения, получили бы нужные разрешения доступа, подписались на пробные, настроенные домены и каждый из столбов Microsoft 365 Defender, а конечные точки будут присоединены к службе.

## <a name="key-capabilities"></a>Ключевые возможности

Хотя Microsoft 365 Defender предоставляет множество возможностей, основная цель этого руководства по развертыванию состоит в том, чтобы начать работу с помощью бортовых устройств. В дополнение к onboarding, это руководство начинается со следующими возможностями.


Возможность | Описание 
:---|:---
Microsoft Defender для Office 365 | Помогает защитить всю Office 365 от сегодняшних угроз
Microsoft Defender для удостоверений | Определяет и обнаруживает угрозы в отношении скомпрометированных удостоверений и вредоносных действий инсайдеров.
Microsoft Cloud App Security | Обеспечивает богатую видимость, управление перемещениями данных и обнаружение киберугроз в облачных службах.
Microsoft Defender для конечной точки | Предотвращает, обнаруживает и предоставляет возможности реагирования на расширенные угрозы с комплексной безопасностью конечных точек.


## <a name="in-scope"></a>В области

В этом руководстве находятся следующие задачи:
-   Настройка Azure Active Directory
-   Настройка Microsoft 365 Defender
    -   Зарегистрируйся Microsoft 365 E5 пробную версию или используйте полную лицензию, если запущен пилот
    -   Настройка домена
    -   Назначение Microsoft 365 E5 лицензий
    -   Завершение мастера установки на портале
-   Настройка всех столбов Microsoft 365 Defender на основе лучших практик
    -   Microsoft Defender для Office 365
    -   Microsoft Defender для удостоверений
    -   Microsoft Cloud App Security
    -   Microsoft Defender для конечной точки

## <a name="out-of-scope"></a>Вне области поддержки

Ниже из этого руководства по развертыванию находятся вне сферы действия:

-   Конфигурация сторонних решений, которые могут интегрироваться с Microsoft 365 Defender
-   Тестирование на проникновение в производственной среде

## <a name="next-step"></a>Следующий этап
[Этап 1. Подготовка](prepare-m365d-eval.md) 
<br> Подготовка пробной лаборатории Microsoft 365 Defender или пилотной среды
