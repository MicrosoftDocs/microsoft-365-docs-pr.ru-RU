---
title: Новые возможности в Microsoft Secure Score
description: Описывает, какие изменения произошли с Microsoft Secure Score в центре Microsoft 365 безопасности.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: b3f86dfbc1ae89eff61c680737061b01998a527b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933869"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Новые возможности в Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Чтобы сделать Microsoft Secure Score лучшим представителем вашей позиции в области безопасности, мы внося некоторые изменения. Чтобы узнать о запланированных изменениях, см. в записи "Что [будет в Microsoft Secure Score"?](microsoft-secure-score-whats-coming.md)

Microsoft Secure Score можно найти в центре Microsoft 365 https://security.microsoft.com/securescore [безопасности.](overview-security-center.md)
    
## <a name="february-2021"></a>Февраль 2021 г.

### <a name="compatibility-with-graph-api"></a>Совместимость с Graph API

Рекомендации Microsoft Secure Score, Graph API, будут выглядеть и взвешить так же, как рекомендации, которые в настоящее время Microsoft 365 центре безопасности.

## <a name="january-2021"></a>Январь 2021 г.

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Добавлена наша первая рекомендация по безопасности для Microsoft Teams

Microsoft Teams пользователи увидят "Ограничение анонимных пользователей от присоединения к собраниям" в качестве нового действия по улучшению в Secure Score.

## <a name="december-2020"></a>Декабрь 2020 г.

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Добавлено шесть действий по улучшению учетных записей для Microsoft Defender для конечной точки:

- Установите "Минимальная длина пароля" до "14 или более символов"
- Установите "Принудить историю паролей" к '24 или более паролей (s)'
- Установите "Максимальный возраст пароля" до "60 или меньше дней, но не 0"
- Установите "Минимальный возраст пароля" до "1 или более дней(ы)"
- Отключение встроенной учетной записи администратора
- Отключение встроенной гостевой учетной записи

## <a name="november-2020"></a>Ноябрь 2020 г.

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Удалена возможность создания билетов ServiceNow с помощью secure Score 

Возможность создания билетов ServiceNow с помощью secure Score с **помощью share > ServiceNow** больше недоступна. Благодарим вас за отзывы и поддержку, пока мы определяем дальнейшие действия.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Добавлены три действия по улучшению, связанные с службами, для Microsoft Defender для конечной точки:

- Исправление незакавратного пути службы для Windows служб
- Изменение исполняемого пути службы в общее защищенное расположение
- Изменение учетной записи службы, чтобы избежать кэшного пароля в реестре Windows

## <a name="october-2020"></a>Октябрь 2020 г.

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Удаление действия по улучшению, связанного с Microsoft Defender для конечной точки

- Установите фильтр SmartScreen в Microsoft Defender Windows для проверки веб-контента приложения Store, чтобы предупредить

## <a name="august-2020"></a>Август 2020 г.

### <a name="updated-improvement-action-for-azure-active-directory"></a>Обновленное действие по улучшению Azure Active Directory

- Включить политику для блокировки устаревшей проверки подлинности

## <a name="incompatibility-with-identity-secure-score"></a>Несовместимость с показателем безопасности удостоверений

В недавнем выпуске Microsoft Secure Score была выпущена улучшенная модель оценки. Эти изменения позволяют обеспечить более гибкое и точное представление о вашей позиции безопасности. Однако эти обновления сделали Microsoft Secure Score временно несовместимой с показателем безопасности удостоверений.

Со временем, identity Secure Score примет новую модель скоринга. До этого времени клиенты будут видеть различия в оценках, отчитающихся в Microsoft Secure Score и Показателе безопасности удостоверений. Мы приносим свои извинения за все неудобства, которые это вызывает, и работаем над тем, чтобы обеспечить более совместимость этих опытом в будущем.

## <a name="updated-improvement-actions"></a>Обновленные действия по улучшению

- Добавлены Azure Active Directory действий по улучшению
- Добавлены действия по улучшению удостоверений в Microsoft Defender
- Поддержка рекомендаций по безопасности управления & [угрозы конечной](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) точки Microsoft Defender
    - Все выпущенные рекомендации по безопасности, предоставленные TVM, теперь доступны

## <a name="updated-interface-and-functionality"></a>Обновленный интерфейс и функциональные возможности

* Все новые представления показателей и тенденций для ciSO и обсуждений на уровне свинца
* Новые способы отслеживания и оценки результатов
* Улучшение отслеживания и понимания регрессий показателей
* Фильтрация, теги, поиск и группа действий по улучшению
* Управление будущими целями с помощью проекций показателей и запланированных действий
* И еще!

## <a name="we-want-to-hear-from-you"></a>Мы ждем ваших отзывов!

Если у вас есть какие-либо проблемы, дайте нам знать, разместив в сообществе [безопасность, конфиденциальность & соответствия](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) требованиям. Мы отслеживаем сообщество и предоставляем помощь.

## <a name="related-resources"></a>Связанные ресурсы

- [Доступ к состоянию безопасности](microsoft-secure-score-improvement-actions.md)
- [Отслеживание истории microsoft Secure Score и достижения целей](microsoft-secure-score-history-metrics-trends.md)
- [Что вскоре появится](microsoft-secure-score-whats-coming.md)