---
title: Оценка безопасности (Майкрософт) для устройств
description: В вашей оценке для устройств показано общее состояние конфигурации устройств в приложениях, операционной системе, сети, учетных записях и средствах управления безопасностью.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, контроль угроз и уязвимостей, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13307d3205818d41e7b2219b4e3a4ed6e9f2d5bb
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454790"
---
# <a name="microsoft-secure-score-for-devices"></a>Оценка безопасности (Майкрософт) для устройств

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Контроль угроз и уязвимостей](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> Оценка конфигурации теперь является частью контроль угроз и уязвимостей microsoft Secure Score для устройств.

Ваша оценка для устройств отображается на контроль угроз и уязвимостей панели [мониторинга](tvm-dashboard-insights.md) Microsoft 365 Defender портала. Более высокий показатель microsoft Secure Score для устройств означает, что конечные точки более устойчивы к атакам угроз кибербезопасности. Он отражает состояние конфигурации коллективной безопасности устройств в следующих категориях:

- Приложение
- Операционная система
- Сеть
- Учетные записи
- Средства контроля безопасности

Выберите категорию, чтобы перейти на страницу [**Рекомендации безопасности**](tvm-security-recommendation.md) и просмотреть соответствующие рекомендации.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Включив соединители microsoft Secure Score

Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture. Переададные данные хранятся и обрабатываются в том же месте, что и данные Microsoft Secure Score.

На отражение изменений на панели мониторинга может потребоваться до нескольких часов.

1. В области навигации перейдите **к Параметры**  >  **Конечные точки**  >  **Общие**  >  **расширенные функции** 

2. Прокрутите **вниз до Microsoft Secure Score** и перейдите к параметру **On**.

3. Выберите **Параметры Сохранить**.

## <a name="how-it-works"></a>Принципы работы

>[!NOTE]
> Microsoft Secure Score для устройств в настоящее время поддерживает конфигурации, заданная с помощью групповой политики. Из-за текущей частичной поддержки Intune конфигурации, которые могли быть настроены через Intune, могут быть неправильно настроены. Обратитесь к ИТ-администратору, чтобы проверить фактическое состояние конфигурации в случае, если ваша организация использует Intune для безопасного управления конфигурацией.

Данные в карточке Microsoft Secure Score for Devices — это продукт тщательного и непрерывного процесса обнаружения уязвимости. Она агрегируется с оценками обнаружения конфигурации, которые непрерывно:

- Сравнение собранных конфигураций с собранными тестами, чтобы обнаружить неправильное расположение активов
- Конфигурации карт для уязвимостей, которые можно устранять или частично устранять (снижение риска)
- Сбор и обслуживание контрольных показателей конфигурации (поставщики, каналы безопасности, внутренние исследовательские группы)
- Сбор и мониторинг изменений состояния конфигурации управления безопасностью из всех активов

## <a name="improve-your-security-configuration"></a>Улучшение конфигурации безопасности

Улучшение конфигурации безопасности путем устранения проблем из списка рекомендаций по безопасности. По мере этого ваша оценка microsoft Secure Для устройств улучшается, а ваша организация становится более устойчивой к угрозам и уязвимостям кибербезопасности.

1. Из карты Microsoft Secure Score for Devices в контроль угроз и уязвимостей панели мониторинга выберите одну из категорий. Вы увидите список рекомендаций, связанных с этой категорией. Он будет принимать вас на [**страницу рекомендации безопасности.**](tvm-security-recommendation.md) Если вы хотите увидеть все рекомендации по безопасности, как только вы доберетсяе до страницы Рекомендации безопасности, очистить поле поиска.

2. Выберите элемент в списке. Панель вылетов откроется с подробными сведениями, связанными с рекомендацией. Выберите **параметры исправлений.**

   :::image type="content" alt-text="Рекомендации по контролю безопасности, связанные с безопасностью." source="images/security-controls.png":::

3. Ознакомьтесь с описанием, чтобы понять контекст проблемы и что делать дальше. Выберите дату, добавить заметки и экспортировать все данные о деятельности по исправлению в **CSV,** чтобы можно было прикрепить их к электронной почте для последующей работы.

4. **Отправка запроса**. Вы увидите сообщение подтверждения о том, что задача по исправлению была создана.

   :::image type="content" alt-text="Подтверждение создания задач по исправлению." source="images/remediation-task-created.png":::

5. Сохраните CSV-файл.

   :::image type="content" alt-text="Сохранение csv-файла." source="images/tvm_save_csv_file.png":::

6. Отправьте ИТ-администратору по электронной почте последующее письмо и дайте время, отведенное для распространения исправлений в системе.

7. Снова **просмотрите карту Microsoft Secure Score для устройств** на панели мониторинга. Количество рекомендаций по контролю безопасности будет уменьшаться. Когда вы выберите элементы управления  **безопасностью,** чтобы вернуться на страницу рекомендации по безопасности, элемент, который вы рассмотрели, больше не будет перечислены там. Необходимо увеличить оценку microsoft Secure Для устройств.

>[!IMPORTANT]
>Чтобы повысить уровень обнаружения уязвимости, скачайте следующие обязательные обновления безопасности и разместите их в сети:
>- Клиенты 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- Клиенты RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- Клиенты RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- Клиенты RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>Чтобы скачать обновления безопасности:
>1. Перейдите [в каталог обновлений Майкрософт](https://www.catalog.update.microsoft.com/home.aspx).
>2. Вйдите в номер КБ обновления безопасности, который необходимо скачать, а затем нажмите **кнопку Поиск**.  

## <a name="related-topics"></a>Связанные статьи

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Панель мониторинга](tvm-dashboard-insights.md)
- [Показатель уязвимости](tvm-exposure-score.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
