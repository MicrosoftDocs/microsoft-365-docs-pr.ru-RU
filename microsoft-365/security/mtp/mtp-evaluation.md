---
title: Оценка защиты от угроз Майкрософт
description: Настройте пробную среду лаборатории Майкрософт по защите от угроз, чтобы проверить, как согласованное решение для защиты от угроз предназначено для защиты устройств, удостоверений, данных и приложений, которые могут помочь вашей организации
keywords: Пробная версия системы защиты от угроз Майкрософт, пробная защита от угроз Майкрософт, Лаборатория Microsoft Threat Protection, Лаборатория Microsoft Threat Protection, Лаборатория оценки безопасности кибератак, повышенная постоянная угроза, Корпоративная защита, устройства, устройства, удостоверения, пользователи, данные, приложения, происшествия, автоматизированное исследование и исправление, расширенное Поиск
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049643"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Создание пробной лабораторной среды Майкрософт для защиты от угроз 

**Область применения:**
- Защита от угроз (Майкрософт)

Цель создания пробной лабораторной среды — продемонстрировать комплексные, интегрированные и интеллектуальные возможности защиты от угроз Майкрософт для обнаружения, защиты, расследования и ответа, которые можно использовать в вашей организации. 

В этом руководстве описано, как начать оценку системы защиты от угроз Майкрософт на основе рекомендуемых путей развертывания. Цель состоит в том, чтобы помочь вам настроить интегрированные службы защиты от угроз Майкрософт в лабораторной среде или в качестве эксперимента при предоставлении решений по обеспечению безопасности в Организации. Когда вы закончите работу с имитацией атак, автоматическим исследованием и ответом и удовлетворенными результатами, вы можете развернуть его в рабочей среде с помощью технических специалистов по продажам и экспертов Майкрософт в Организации. 

Это руководство поможет вам:
- Настройка сервера лаборатории и компьютеров
- Настройка Active Directory для пользователей и групп
- Настройка и настройка Azure ATP, Office ATP, Microsoft Defender ATP и Microsoft Cloud App Security
- Настройка локальных политик для сервера и компьютеров
- Имитирует атаку угроз для создания тестового инцидента или оповещения в Microsoft Threat protection

>[!IMPORTANT]
>Для достижения оптимальных результатов выполните инструкции по настройке лаборатории, насколько это возможно.


## <a name="deployment-phases"></a>Этапы развертывания

Создание пробной лабораторной среды Майкрософт по защите от угроз и ее развертывание выполняется в три этапа:

|Этап | Описание | 
|:-------|:-----|
| ![Этап 1: подготовка](../../media/prepare.png)<br>[Этап 1: подготовка](prepare-mtpeval.md)| Сведения о том, что необходимо учитывать при развертывании защиты от угроз Майкрософт в испытательной лабораторной среде: <br><br>— Заинтересованные стороны и подпись <br> Аспекты среды <br>Доступ <br>— Установка Azure Active Directory <br> — Порядок настройки
|  ![Этап 2: Настройка](../../media/setup.png) <br>[Этап 2: Настройка](setup-mtpeval.md)|  Выполните начальные действия для доступа к центру безопасности Microsoft 365, чтобы настроить лабораторную среду пробной системы защиты от угроз Майкрософт. Вы будете переработаны в следующих руководствах:<br><br>— Подписаться на пробную версию Microsoft 365 <br>  — Настройка домена<br>— Назначение лицензий Microsoft 365<br>— Завершите работу мастера установки на портале.|
|  ![Этап 3: Настройка встроенного &](../../media/config-onboard.png) <br>[Этап 3: Настройка встроенного &](config-mtpeval.md) | Настройте каждый из принципов и встроенных конечных точек защиты от угроз Майкрософт. Вы будете переработаны в следующих руководствах:<br><br>— Настройка Office 365 Advanced Threat protection<br>— Настройка Microsoft Cloud App Security<br>— Настройка службы Advanced Threat Protection в Azure<br>— Настройка Advanced Threat Protection в защитнике Майкрософт 


## <a name="in-scope"></a>В области

В этом руководстве для пробной лабораторной лаборатории приведена следующая область:
-   Настройка Azure Active Directory
-   Настройка защиты от угроз Майкрософт
    -   Подписка на пробную версию Microsoft 365
    -   Настройка домена
    -   Назначение лицензий на Microsoft 365
    -   Завершение работы мастера установки на портале
-   Настройка всех принципов защиты от угроз Майкрософт на основе рекомендаций
    -   Office 365 Advanced Threat Protection
    -   Расширенная защита от угроз Azure
    -   Microsoft Cloud App Security
    -   Advanced Threat Protection в Microsoft Defender

## <a name="out-of-scope"></a>Вне области предоставляемых услуг

Ниже приведены рекомендации по развертыванию.

-   Конфигурация сторонних решений, которые могут интегрироваться с защитником Майкрософт ATP
-   Тестирование уязвимости в рабочей среде

## <a name="next-step"></a>Следующий этап
|||
|:-------|:-----|
|![Этап 1: подготовка](../../media/prepare.png) <br>[Этап 1: подготовка](prepare-mtpeval.md) | Подготовка лабораторной среды оценки Microsoft Threat protection