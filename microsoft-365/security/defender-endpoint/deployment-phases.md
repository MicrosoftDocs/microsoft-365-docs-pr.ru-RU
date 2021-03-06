---
title: Этапы развертывания
description: Узнайте, как развернуть конечную точку Microsoft Defender для конечной точки, подготавливая, настраивая и внося конечные точки в эту службу.
keywords: развертывание, подготовка, настройка, бортовая, фаза, развертывание, развертывание, принятие, настройка
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165169"
---
# <a name="deployment-phases"></a>Этапы развертывания

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Узнайте, как развернуть Microsoft Defender для конечной точки, чтобы ваше предприятие воспользовалось профилактической защитой, обнаружением нарушений, автоматическим расследованием и ответом. 


Это руководство помогает вам работать с заинтересованными сторонами для подготовки среды и бортовых устройств методично, переходя от оценки к содержательному пилоту, к полному развертыванию.

Каждый раздел соответствует отдельной статье в этом решении.

![Изображение этапов развертывания с подробными сведениями из таблицы](images/deployment-guide-phases.png)


![Сводка этапов развертывания: подготовка, настройка, бортовой](images/phase-diagrams/deployment-phases.png)

|Этап | Описание | 
|:-------|:-----|
| [Этап 1. Подготовка](prepare-deployment.md)| Узнайте, что необходимо учитывать при развертывании Defender для конечной точки, таких как утверждения заинтересованных сторон, соображения среды, разрешения доступа и порядок принятия возможностей. 
| [Этап 2. Настройка](production-deployment.md)|  Получите инструкции по начальным шагам, которые необходимо предпринять, чтобы получить доступ к порталу, например к проверке лицензирования, завершению мастера установки и конфигурации сети. 
| [Этап 3. Подключение](onboarding.md) | Узнайте, как использовать кольца развертывания, поддерживаемые средства бортового использования в зависимости от типа конечной точки, и настройка доступных возможностей. 


После завершения этого руководства вы будете настроены с нужными разрешениями доступа, конечные точки будут на борту и отчеты о данных датчиков службы, а также возможности, такие как защита следующего поколения и снижение поверхности атаки будут на месте.



Независимо от архитектуры среды и метода развертывания, которые вы выбрали в руководстве по развертыванию [Plan,](deployment-strategy.md) это руководство будет поддерживать вас в конечных точках на борту. 








## <a name="key-capabilities"></a>Ключевые возможности

Несмотря на то, что Microsoft Defender для конечной точки предоставляет множество возможностей, основная цель этого руководства по развертыванию состоит в том, чтобы начать работу с помощью бортовых устройств. В дополнение к onboarding, это руководство начинается со следующими возможностями.



Возможность | Описание 
:---|:---
Обнаружение и устранение угроз на конечных точках | Для обнаружения, расследования и реагирования на попытки вторжения и активных нарушений на месте работают возможности обнаружения конечных точек и реагирования на них.
Защита нового поколения | Чтобы еще больше усилить периметр безопасности сети, Microsoft Defender для конечной точки использует защиту следующего поколения, предназначенную для улавливания всех типов возникающих угроз.
Сокращение направлений атак |  Предоставление первой линии защиты в стеке. Обеспечивая правильное настройку параметров конфигурации и применяя методы смягчения последствий, этот набор возможностей позволяет противостоять атакам и эксплуатации.

Все эти возможности доступны для владельцев лицензий Конечной точки для Microsoft Defender. Дополнительные сведения см. [в сведениях о требованиях к лицензированию.](minimum-requirements.md#licensing-requirements)

## <a name="scope"></a>Область

### <a name="in-scope"></a>В области

-   Использование Microsoft Endpoint Manager и Microsoft Endpoint Manager конечных точек в службе и настройка возможностей

-   Включение функций Defender для обнаружение и нейтрализация атак на конечные точки (EDR)

-   Включение возможностей платформы защиты конечных точек Defender для конечной точки (EPP)

    -   Защита нового поколения

    -   Сокращение направлений атак


### <a name="out-of-scope"></a>Вне области поддержки

Ниже из этого руководства по развертыванию находятся вне сферы действия:

-   Конфигурация сторонних решений, которые могут интегрироваться с Defender для endpoint

-   Тестирование на проникновение в производственной среде




## <a name="see-also"></a>См. также
- [Этап 1. Подготовка](prepare-deployment.md)
- [Этап 2. Настройка](production-deployment.md)
- [Этап 3. Подключение](onboarding.md)
- [Планирование развертывания](deployment-strategy.md)