---
title: Оценка Microsoft 365 Defender
description: Установите пробную лабораторию или пилотную среду Microsoft 365 Defender, чтобы опробовыть и испытать решение безопасности, предназначенное для защиты устройств, удостоверений, данных и приложений в организации.
keywords: Microsoft Threat Protection trial, try Microsoft Threat Protection, assessment Microsoft Threat Protection, Microsoft Threat Protection assessment lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076654"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Создание пробной лаборатории или пилотной среды Для Защитника Microsoft 365 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


В этом руководстве помогают настраивать лабораторную среду с пользователями и группами, а затем помогают определить конфигурацию возможностей в Microsoft 365 Defender, чтобы можно было имитировать угрозу и получить значимый пробный результат. 

Целью создания этой пробной лаборатории или пилотной среды является демонстрация комплексных и интегрированных возможностей Microsoft 365 Defender. Изучите, как это интеллектуальное решение безопасности обнаруживает, предотвращает, автоматически расследует и реагирует на расширенные угрозы вашей организации. 


Вы будете руководствоваться действиями по началу оценки Защитника Microsoft 365 на основе рекомендуемых путей развертывания. Цель состоит в том, чтобы помочь вам настроить решение безопасности либо в лаборатории с пробной учетной записью, либо в пилотной среде в производстве с полной лицензией. Подготовка пробной лаборатории или пилотной среды может помочь вам представить случаи использования операций безопасности для лиц, принимающих решения в вашей организации. После запуска имитации атак и удовлетворенных результатами вы можете полностью развернуть и использовать его в организации с помощью специалистов по техническим продажам Майкрософт или экспертов в вашей организации. 

Это руководство поможет вам:
- Настройка лабораторного сервера и компьютеров
- Настройка Active Directory с пользователями и группами
- Настройка и настройка Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и microsoft Cloud App Security
- Настройка локальных политик для сервера и компьютеров
- Имитация атаки угрозы для создания тестового инцидента или оповещения в Microsoft 365 Defender

>[!IMPORTANT]
>Для достижения оптимальных результатов выполните инструкции по настройке лаборатории как можно ближе.


## <a name="deployment-phases"></a>Этапы развертывания

Создание среды пробной лаборатории Microsoft 365 Defender имеет три этапа.

![Этапы развертывания: подготовка, настройка, бортовой](../../media/evaluation-guide-phases.png)

|Этап | Описание | 
|:-------|:-----|
|[Этап 1. Подготовка](prepare-m365d-eval.md)| Узнайте, что необходимо учитывать при развертывании Microsoft 365 Defender в пробной лаборатории или пилотной среде: <br><br>- Заинтересованные лица и вход <br> - Соображения среды <br>- Доступ <br>- Установка Azure Active Directory <br> - Порядок конфигурации
|[Этап 2. Установка](setup-m365deval.md)|  Сначала необходимо получить доступ к Центру безопасности Microsoft 365, чтобы настроить пробную лабораторию или пилотную среду Microsoft 365 Defender. Вы будете руководствоваться:<br><br>- Зарегистриройся на microsoft 365 E5 Trial <br>  - Настройка домена<br>- Назначение лицензий Microsoft 365 E5<br>- Завершите мастер установки на портале|
|[Этап 3. Настройка & на борту](config-m365d-eval.md) | Настройка каждого столба и конечных точек Microsoft 365 Defender. Вы будете руководствоваться:<br><br>- Настройка Microsoft Defender для Office 365<br>- Настройка безопасности облачных приложений Майкрософт<br>- Настройка Microsoft Defender для удостоверений<br>- Настройка Microsoft Defender для конечной точки


После завершения этого руководства вы бы определили заинтересованных лиц и необходимые разрешения, получили бы соответствующие разрешения доступа, подписались на пробные, настроенные домены и каждый из столбов Microsoft 365 Defender, а конечные точки будут присоединены к службе.

## <a name="key-capabilities"></a>Ключевые возможности

Несмотря на то, что Microsoft 365 Defender предоставляет множество возможностей, основная цель этого руководства по развертыванию состоит в том, чтобы начать работу с помощью бортовых устройств. В дополнение к onboarding, это руководство начинается со следующими возможностями.


Возможность | Описание 
:---|:---
Microsoft Defender для Office 365 | Защита всей инврионации Office 365 от сегодняшних угроз
Microsoft Defender для удостоверений | Определяет и обнаруживает угрозы в отношении скомпрометированных удостоверений и вредоносных действий инсайдеров.
Microsoft Cloud App Security | Обеспечивает богатую видимость, управление перемещениями данных и обнаружение киберугроз в облачных службах.
Microsoft Defender для конечной точки | Предотвращает, обнаруживает и предоставляет возможности реагирования на расширенные угрозы с комплексной безопасностью конечных точек.


## <a name="in-scope"></a>В области

В этом руководстве находятся следующие задачи:
-   Настройка Azure Active Directory
-   Настройка защитника Microsoft 365
    -   Зарегистрируйся в Microsoft 365 E5 Trial или используйте полную лицензию, если запущен пилотный
    -   Настройка домена
    -   Назначение лицензий Microsoft 365 E5
    -   Завершение мастера установки на портале
-   Настройка всех столпов Microsoft 365 Defender на основе практических методов
    -   Microsoft Defender для Office 365
    -   Microsoft Defender для удостоверений
    -   Microsoft Cloud App Security
    -   Microsoft Defender для конечной точки

## <a name="out-of-scope"></a>Вне области поддержки

Ниже из этого руководства по развертыванию находятся вне сферы действия:

-   Конфигурация сторонних решений, которые могут интегрироваться с Microsoft 365 Defender
-   Тестирование на проникновение в производственной среде

## <a name="next-step"></a>Следующий шаг
[Этап 1. Подготовка](prepare-m365d-eval.md) 
<br> Подготовка пробной лаборатории или пилотной среды Microsoft 365 Defender
