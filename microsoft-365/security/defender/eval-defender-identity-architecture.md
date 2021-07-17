---
title: Обзор требований к архитектуре и технической базы для Microsoft Defender для удостоверений, схемы архитектуры, MDI
description: Техническая схема для Microsoft Defender для удостоверений в Microsoft 365 Defender поможет вам понять личность в Microsoft 365 перед созданием пробной лаборатории или пилотной среды.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458707"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Обзор требований к архитектуре и ключевых концепций для Microsoft Defender для identity


**Область применения:**
- Microsoft 365 Defender

Эта статья [— шаг 1 из 3](eval-defender-identity-overview.md) в процессе настройки среды оценки для Microsoft Defender для identity. Дополнительные сведения об этом процессе см. в статье [обзор.](eval-defender-identity-overview.md)

Прежде чем включить Microsoft Defender для identity, убедитесь, что вы понимаете архитектуру и можете соответствовать требованиям.

Microsoft Defender for Identity использует машинное обучение и поведенческую аналитику для выявления атак в локальной сети, а также обнаружения и предотвращения рисков, связанных с входом пользователей в облачные идентификаторы. Дополнительные сведения см. [в дополнительных сведениях о том, что такое Microsoft Defender for Identity?](/defender-for-identity/what-is)

Defender for Identity защищает локального пользователя Active Directory и/или пользователей, синхронизированных с Azure Active Directory (Azure AD). Чтобы защитить среду, в которой могут быть только пользователи Azure AD, см. в [примере Azure AD Identity Protection.](/azure/active-directory/identity-protection/overview-identity-protection)

## <a name="understand-the-architecture"></a>Знакомство с архитектурой

Следующая схема иллюстрирует базовую архитектуру defender for Identity. 

![Архитектура для Microsoft Defender для удостоверений](../../media/defender/m365-defender-identity-architecture.png)

В этой иллюстрации:
- Датчики, установленные на контроллерах доменов AD, анализят журналы и сетевой трафик и отправляют их в Microsoft Defender for Identity для анализа и отчетности.
-  Датчики также могут сравнить службы Федерации Active Directory (AD FS), если Azure AD настроена на использование федерарной проверки подлинности (пунктирная строка на иллюстрации). 
- Microsoft Defender for Identity передает сигналы Microsoft 365 Defender для расширенного обнаружения и ответа (XDR).


Датчики Defender for Identity можно установить непосредственно на следующих серверах:

- Контроллеры домена. Датчик непосредственно отслеживает трафик контроллера домена без необходимости выделенного сервера или настройки зеркального зеркального использования порта.
- AD FS. Датчик непосредственно отслеживает события сетевого трафика и проверки подлинности.

Подробнее об архитектуре Defender for Identity, включая интеграцию с Cloud App Security, см. в этой [ссылке.](/defender-for-identity/architecture)


## <a name="understand-key-concepts"></a>Понимание ключевых понятий

В следующей таблице определены ключевые понятия, которые важны для понимания при оценке, настройке и развертывании Microsoft Defender для identity.


|Понятие  |Описание |Дополнительная информация  |
|---------|---------|---------|
| Отслеживаемая деятельность | Defender for Identity отслеживает сигналы, генерируемые внутри организации, для обнаружения подозрительных или вредоносных действий и помогает определить правильность каждой потенциальной угрозы, чтобы эффективно определять и реагировать.  |  [Действия, отслеживаемые в Microsoft Defender для удостоверений](/defender-for-identity/monitored-activities)       |
| Оповещения системы безопасности    | Оповещений защитника безопасности удостоверений объясняют подозрительные действия, обнаруженные датчиками в сети, а также субъектами и компьютерами, вовлеченными в каждую угрозу.   | [Microsoft Defender для оповещений о безопасности удостоверений](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| Профили сущности    | Профили Entity предоставляют комплексное глубоководное исследование пользователей, компьютеров, устройств и ресурсов вместе с историей доступа.   | [Понимание профилей сущности](/defender-for-identity/entity-profiles)  |
| Пути для движения с последующим движением    | Ключевым компонентом анализа безопасности MDI является определение путей, по которым злоумышленник использует нечувствительные учетные записи для получения доступа к конфиденциальным учетным записям или машинам по всей сети.  | [Защитник Майкрософт для путей личных данных (LMP)](/defender-for-identity/use-case-lateral-movement-path)  |
| Разрешение сетевых имен    |  Разрешение имен сети (NNR) — это компонент функции MDI, которая фиксирует действия на основе сетевого трафика, событий Windows, ETW и т. д. и сопоставляет эти необработанные данные с соответствующими компьютерами, участвующими в каждом действии.       | [Что такое разрешение сетевых имен?](/defender-for-identity/nnr-policy)      |
| Отчеты    | Отчеты Defender for Identity позволяют планировать или немедленно создавать и скачивать отчеты, которые предоставляют сведения о состоянии системы и объекта.  Вы можете создавать отчеты о состоянии системы, оповещениях о безопасности и потенциальных путях движения, обнаруженных в вашей среде.   | [Microsoft Defender для отчетов о удостоверениях ](/defender-for-identity/reports)       |
| Группы ролей    | Defender for Identity предлагает группы на основе ролей и делегированную защиту данных в соответствии с конкретными потребностями вашей организации в области безопасности и соответствия требованиям, включая администраторов, пользователей и зрителей.        |  [Группы ролей Microsoft Defender для удостоверений](/defender-for-identity/role-groups)       |
| Портал администрирования    |  Кроме центра Microsoft 365 безопасности, кабина портала Defender for Identity используется для мониторинга и реагирования на подозрительные действия.      | [Работа с порталом Microsoft Defender для удостоверений](/defender-for-identity/workspace-portal)        |
| Microsoft Cloud App Security интеграции   | Microsoft Cloud App Security интегрируется с Microsoft Defender для identity, чтобы обеспечить поведенческую аналитику пользовательского объекта (UEBA) в гибридной среде — как в облачном приложении, так и в локальной среде.   | Microsoft Defender для интеграции удостоверений  |
| | | |


## <a name="review-prerequisites"></a>Просмотр необходимых условий

Defender for Identity требует определенной работы, необходимой для обеспечения того, чтобы локальное удостоверение и сетевые компоненты соответствуют минимальным требованиям. Используйте эту статью в качестве контрольного списка для обеспечения готовности среды: предварительные условия [Microsoft Defender для удостоверений.](/defender-for-identity/prerequisites)


## <a name="next-steps"></a>Дальнейшие действия

Шаг 2 из 3. [Включить среду оценки Defender для identity](eval-defender-identity-enable-eval.md)

Возвращение к обзору [оценки microsoft Defender для удостоверений](eval-defender-identity-overview.md)

Возвращайся к обзору [для оценки и пилотных Microsoft 365 Defender](eval-overview.md) 