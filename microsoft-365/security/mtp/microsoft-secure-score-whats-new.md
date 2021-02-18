---
title: Новые возможности оценки безопасности (Майкрософт)
description: Описание новых изменений, внесенных в оценку безопасности (Майкрософт) в Центре безопасности Microsoft 365.
keywords: оценка безопасности Майкрософт, оценка безопасности, оценка безопасности Office 365, оценка безопасности Майкрософт, Центр безопасности Microsoft 365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 520a5627d2cd280f28c4e2c3db0e565640a1eace
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289165"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Новые возможности оценки безопасности (Майкрософт)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Чтобы сделать оценку безопасности (Майкрософт) более показательной для вашего положения в области безопасности, мы влияли на некоторые изменения. Чтобы узнать о запланированных изменениях, см. информацию о предстоящих оценках [безопасности (Майкрософт)?](microsoft-secure-score-whats-coming.md)

Оценка безопасности (Майкрософт) находится в Центре https://security.microsoft.com/securescore [безопасности Microsoft 365.](overview-security-center.md)
    
## <a name="february-2021"></a>Февраль 2021 г.

### <a name="compatibility-with-graph-api"></a>Совместимость с API Graph

Рекомендации по оценке безопасности (Майкрософт), которые ставляются с помощью API Graph, будут выглядеть и взвешены так же, как рекомендации, которые вы сейчас видите в Центре безопасности Microsoft 365.

## <a name="january-2021"></a>Январь 2021 г.

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Добавлена первая рекомендация по безопасности для Microsoft Teams

Пользователи Microsoft Teams увидят "Запретить анонимным пользователям присоединяться к собраниям" в качестве нового действия по улучшению в оценке безопасности.

## <a name="december-2020"></a>Декабрь 2020 г.

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Добавлено шесть действий по улучшению, связанных с учетной записью, для Microsoft Defender для конечной точки (ранее ATP в Microsoft Defender):

- Установите "Минимальная длина пароля" в 14 или более символов
- Установите для "Принудительного применения истории паролей" (24 или более паролей)
- Установите для "Максимального возраста пароля" значение "60 или меньше дней, но не 0"
- Установите для "Минимального возраста пароля" (1 или более дней)
- Отключение встроенной учетной записи администратора
- Отключение встроенной гостевой учетной записи

## <a name="november-2020"></a>Ноябрь 2020 г.

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Удалена возможность создавать билеты ServiceNow с помощью оценки безопасности 

Возможность создавать билеты ServiceNow с помощью оценки безопасности с помощью share **> ServiceNow** больше недоступна. Благодарим вас за отзывы и поддержку, пока мы определяем дальнейшие действия.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Добавлены три действия по улучшению, связанные со службами, для Microsoft Defender для конечной точки (ранее ATP в Microsoft Defender):

- Исправление unquoted service path for Windows services
- Изменение пути исполняемого исполняемого пути службы к общей защищенной области
- Изменение учетной записи службы во избежание кэшного пароля в реестре Windows

## <a name="october-2020"></a>Октябрь 2020 г.

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Удаление действия по улучшению, связанного с Microsoft Defender для конечной точки

- Настройка проверки веб-содержимого приложения Магазина Windows smartScreen в Microsoft Defender для предупреждения

## <a name="august-2020"></a>Август 2020 г.

### <a name="updated-improvement-action-for-azure-active-directory"></a>Обновлено действие по улучшению Azure Active Directory

- Включить политику для блокировки устаревшей проверки подлинности

## <a name="incompatibility-with-identity-secure-score"></a>Несовместимость с оценкой безопасности удостоверений

В недавнем выпуске оценки безопасности (Майкрософт) была выпущена улучшенная модель показателей. Эти изменения позволяют более гибко и точно с точки зрения безопасности. Однако эти обновления сделали оценку безопасности (Майкрософт) временно несовместимой с оценкой безопасности удостоверений.

Со временем оценка безопасности удостоверений примет новую модель показателей. До этого момента клиенты будут видеть различия в оценках, относяхся к оценке безопасности (Майкрософт) и оценке безопасности удостоверений. Мы приносим извинения за все неудобства, связанные с этим, и работаем над тем, чтобы обеспечить их совместимость в будущем.

## <a name="updated-improvement-actions"></a>Обновленные действия по улучшению

- Добавлены действия по улучшению Azure Active Directory
- Добавлен Microsoft Defender для действий по улучшению удостоверений
- Поддержка рекомендаций по безопасности управления угрозами & угроз конечной точки в Microsoft [Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Теперь доступны все выпущенные рекомендации по безопасности, предоставленные телевизором

## <a name="updated-interface-and-functionality"></a>Обновленный интерфейс и функциональные возможности

* Все новые метрики и тенденции для обсуждений CISO и на уровне ведущими
* Новые способы отслеживания и оценки показателей
* Улучшение отслеживания и понимания регрессии показателей
* Фильтрация, тег, поиск и группировка действий по улучшению
* Управление будущими целями с помощью проекций показателей и запланированных действий
* И еще!

## <a name="we-want-to-hear-from-you"></a>Мы ждем ваших отзывов!

Если у вас есть какие-либо проблемы, дайте нам знать, опубликовав в сообществе по [безопасности, & соответствия требованиям.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Мы отслеживаем сообщество и предоставляем помощь.

## <a name="related-resources"></a>Связанные ресурсы

- [Оценка уровня безопасности](microsoft-secure-score-improvement-actions.md)
- [Отслеживание истории оценки безопасности (Майкрософт) и достижения целей](microsoft-secure-score-history-metrics-trends.md)
- [Что вскоре появится](microsoft-secure-score-whats-coming.md)
