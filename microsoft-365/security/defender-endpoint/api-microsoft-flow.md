---
title: Соединитетор Microsoft Defender для Flow конечных точек
ms.reviewer: ''
description: Используйте соединители Microsoft Defender для Flow конечной точки, чтобы автоматизировать безопасность и создать поток, который будет активироваться в любое время, когда на клиенте будет возникать новое оповещение.
keywords: поток, поддерживаемые api, api, поток Майкрософт, запрос, автоматизация
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
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769711"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (ранее Microsoft Flow) и Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Автоматизация процедур безопасности является стандартным требованием для каждого современного центра операций безопасности. Отсутствие профессиональных киберзащит заставляет SOC работать наиболее эффективно, а автоматизация является обязательным. Microsoft Power Automate поддерживает различные соединители, которые были построены именно для этого. Вы можете создать автоматизацию процедуры в течение нескольких минут.

API Защитника Майкрософт имеет официальный Flow со многими возможностями.

![Изображение учетных данных для редактирования1](images/api-flow-0.png)

> [!NOTE]
> Дополнительные сведения о предварительных условия лицензирования соединителов премиум-класса см. в материале [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)


## <a name="usage-example"></a>Пример использования

В следующем примере показано, как создать Flow, который запускается в любое время, когда на клиенте возникает новое оповещение.

1. Войдите в [Microsoft Power Automate.](https://flow.microsoft.com)

2. Перейдите к **потоку**  >  **My New**  >  **Automated-from blank**.

    ![Изображение редактирования учетных данных2](images/api-flow-1.png)

3. Выберите имя для Flow, найди в качестве триггера ATP в Защитнике Microsoft триггер, а затем выберите новый триггер оповещения.

    ![Изображение учетных данных для редактирования3](images/api-flow-2.png)

Теперь у вас есть Flow, который запускается каждый раз при новом оповещении.

![Изображение редактирования учетных данных4](images/api-flow-3.png)

Все, что вам нужно сделать, это выбрать следующие действия.
Например, вы можете изолировать устройство, если уровень серьезности оповещений является высоким, и отправить сообщение об этом.
Спусковой крючок Alert предоставляет только оповещение и машинный ID. Этот соединитатель можно использовать для расширения этих сущностями.

### <a name="get-the-alert-entity-using-the-connector"></a>Получить объект Alert с помощью соединиттеля

1. Выберите **ATP в Защитнике Microsoft** для нового шага.

2. Выбор **оповещений . Получить API единого оповещения**.

3. Установите **ID оповещения на** последнем шаге в качестве **ввода.**

    ![Изображение учетных данных для редактирования5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Изолировать устройство, если степень серьезности оповещений высока

1. Добавьте **Условие** в качестве нового шага.

2. Проверьте, равна ли серьезность оповещения **высокой.**

   Если да, добавьте **ATP в Защитнике Microsoft — изолировать** действие машины с машинным ИД и комментарием.

    ![Изображение редактировать учетные данные6](images/api-flow-5.png)

3. Добавьте новый шаг для отправки сообщений по электронной почте об оповещении и изоляции. Существует несколько соединителов электронной почты, которые очень просты в использовании, например Outlook или Gmail.

4. Сохраните поток.

Вы также можете создать **запланированный** поток, который запускает расширенные запросы на охоту и многое другое!

## <a name="related-topic"></a>Связанная тема
- [Microsoft Defender для API конечных точек](apis-intro.md)
