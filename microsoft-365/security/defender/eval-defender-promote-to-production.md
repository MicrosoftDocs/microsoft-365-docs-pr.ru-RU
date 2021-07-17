---
title: Продвижение среды Microsoft 365 Defender в производственную, Microsoft 365 Defender оценку, попробуйте оценку, сохраняйте оценку, производственную оценку
description: Используйте эту статью для продвижения эквивалентов MDI, MDO, MDE и MCAS в живую среду в Microsoft 365 Defender или M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458747"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Продвижение среды Microsoft 365 Defender в производство

**Область применения:**
- Microsoft 365 Defender

Чтобы повысить Microsoft 365 Defender среды оценки до производства, сначала приобретите необходимую лицензию. Следуйте шагам в Создании среды [eval](eval-create-eval-environment.md) и приобретайте лицензию Office 365 E5 (вместо выбора бесплатной пробной пробной части Start).

Затем выполните любую дополнительную конфигурацию и расширите пилотные группы, пока они не достигнут полного производства. 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender для удостоверений
Defender for Identity не требует дополнительной конфигурации. Просто убедитесь, что вы приобрели необходимые лицензии и установили датчик на всех контроллерах домена Active Directory и серверах федерации Active Directory (AD FS). 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender для Office 365
После успешной оценки или пилотирования MDO он может быть повышен до всей производственной среды.
1. Приобретение и предоставление необходимых лицензий и назначение их пользователям производства.
2. Повторно запустите рекомендуемые базовые конфигурации политики (стандартные или строгие) для производственного домена электронной почты или определенных групп пользователей.
3. Необязательно создавать и настраивать настраиваемые политики MDO в отношении производственного домена электронной почты или групп пользователей.  Однако помните, что все назначенные базовые политики всегда будут иметь приоритет над настраиваемой политикой.
4. Обновите публичную запись MX для вашего домена электронной почты для решения непосредственно в EOP.
5. Отключите все сторонние шлюзы SMTP и отключите или удалите все соединители EXO, связанные с этим ретранслятором.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender для конечной точки
Чтобы повысить среду оценки Microsoft Defender для конечных точек с пилотного до производственного, просто на борту дополнительных конечных точек службы с помощью любых поддерживаемых средств [и методов.](/defender-endpoint/onboard-configure)

Используйте следующие общие рекомендации, чтобы использовать дополнительные устройства в Microsoft Defender для конечной точки. 

1. Убедитесь, что устройство выполняет [минимальные требования.](/defender-endpoint/minimum-requirements)
2. В зависимости от устройства следуйте шагам конфигурации, предусмотренным в разделе onboarding портала Defender for Endpoint.
3. Используйте соответствующий инструмент управления и метод развертывания для устройств.
4.  Запустите тест обнаружения, чтобы убедиться, что устройства правильно на борту и отчеты службе.

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security не требует дополнительной конфигурации. Просто убедитесь, что вы приобрели необходимые лицензии. Если развертывание было развернуто в определенных группах пользователей, необходимо увеличить область действия этих групп до достижения производственного масштаба. 

