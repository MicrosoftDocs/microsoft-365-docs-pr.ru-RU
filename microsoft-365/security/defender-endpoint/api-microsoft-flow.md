---
title: Соединители потока конечных точек Microsoft Defender для конечных точек
ms.reviewer: ''
description: Используйте соединители Потока конечных точек Microsoft Defender для автоматизации безопасности и создания потока, который будет запускаться в любое время, когда в клиенте будет возникать новое оповещение.
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
ms.technology: mde
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929303"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (ранее Microsoft Flow) и Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Автоматизация процедур безопасности является стандартным требованием для каждого современного центра операций безопасности. Отсутствие профессиональных киберзащит заставляет SOC работать наиболее эффективно, а автоматизация является обязательным. Microsoft Power Automate поддерживает различные соединители, которые были построены именно для этого. Вы можете создать автоматизацию процедуры в течение нескольких минут.

API Защитника Майкрософт имеет официальный соединителет потока с большим количеством возможностей.

![Изображение учетных данных для редактирования1](images/api-flow-0.png)

> [!NOTE]
> Дополнительные сведения о предварительных условия лицензирования соединителов премиум-класса см. в материале [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)


## <a name="usage-example"></a>Пример использования

В следующем примере показано, как создать поток, который запускается в любое время, когда на клиенте возникает новое оповещение.

1. Войдите в [Microsoft Power Automate](https://flow.microsoft.com).

2. Перейдите к **потоку**  >  **My New**  >  **Automated-from blank**.

    ![Изображение редактирования учетных данных2](images/api-flow-1.png)

3. Выберите имя потока, в качестве триггера выберите триггер "Триггеры ATP Защитника Майкрософт", а затем выберите новый триггер оповещения.

    ![Изображение учетных данных для редактирования3](images/api-flow-2.png)

Теперь у вас есть поток, который запускается каждый раз, когда происходит новое оповещение.

![Изображение редактирования учетных данных4](images/api-flow-3.png)

Все, что вам нужно сделать, это выбрать следующие действия.
Например, вы можете изолировать устройство, если уровень серьезности оповещений является высоким, и отправить сообщение об этом.
Спусковой крючок Alert предоставляет только оповещение и машинный ID. Этот соединитатель можно использовать для расширения этих сущностями.

### <a name="get-the-alert-entity-using-the-connector"></a>Получить объект Alert с помощью соединиттеля

1. Выберите **ATP Защитника Майкрософт** для нового шага.

2. Выбор **оповещений . Получить API единого оповещения**.

3. Установите **ID оповещения на** последнем шаге в качестве **ввода.**

    ![Изображение учетных данных для редактирования5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Изолировать устройство, если степень серьезности оповещений высока

1. Добавьте **Условие** в качестве нового шага.

2. Проверьте, равна ли серьезность оповещения **высокой.**

   Если да, добавьте **atP Защитника Microsoft — изолировать** действие машины с машинным ИД и комментарием.

    ![Изображение редактировать учетные данные6](images/api-flow-5.png)

3. Добавьте новый шаг для отправки сообщений по электронной почте об оповещении и изоляции. Существует несколько соединителов электронной почты, которые очень просты в использовании, например Outlook или Gmail.

4. Сохраните поток.

Вы также можете создать **запланированный** поток, который запускает расширенные запросы на охоту и многое другое!

## <a name="related-topic"></a>Связанная тема
- [Microsoft Defender для API конечных точек](apis-intro.md)
