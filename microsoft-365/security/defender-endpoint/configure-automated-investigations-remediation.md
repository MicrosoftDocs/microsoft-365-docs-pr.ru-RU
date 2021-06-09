---
title: Настройка возможностей автоматического расследования и устранения последствий
description: Настройка возможностей автоматического расследования и исправлений в Microsoft Defender для конечной точки.
keywords: настройка, настройка, автоматизация, исследование, обнаружение, оповещения, исправление, ответ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841352"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Настройка возможностей автоматического расследования и исправлений в Microsoft Defender для endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Если ваша организация использует [Microsoft Defender для конечной](/windows/security/threat-protection/) точки (Defender для конечной точки), [](/microsoft-365/security/defender-endpoint/automated-investigations) возможности автоматического расследования и восстановления могут сэкономить время и усилия группы операций безопасности. Как описано в [этом](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)блоге, эти возможности имитируют идеальные действия аналитика безопасности для расследования и устранения угроз. [Узнайте больше об автоматическом расследовании и исправлении.](/microsoft-365/security/defender-endpoint/automated-investigations) 

Чтобы настроить автоматическое расследование и исправление,
1. [Включаем функции;](#turn-on-automated-investigation-and-remediation) и 
2. [Настройка групп устройств.](#set-up-device-groups)

## <a name="turn-on-automated-investigation-and-remediation"></a>Включаем автоматическое расследование и исправление

1. В качестве глобального администратора или администратора безопасности перейдите в Центр безопасности в Microsoft Defender () и [https://securitycenter.windows.com](https://securitycenter.windows.com) войдите.
2. В области навигации **выберите** Параметры .
3. В разделе **Общие** выберите **расширенные функции**.
4. Включаем **автоматическое расследование** **и автоматически разрешаем оповещения.**

## <a name="set-up-device-groups"></a>Настройка групп устройств

1. В Центр безопасности в Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) ( ), на странице **Параметры,** в **соответствии с разрешениями,** выберите **группы устройств**.
2. Выберите **+ Добавить группу устройств.**
3. Создайте по крайней мере одну группу устройств следующим образом:
   - Укажите имя и описание группы устройств.
   - В **списке уровень автоматизации** выберите уровень, например Full — автоматически устраняйте **угрозы.** Уровень автоматизации определяет, принимаются ли действия по исправлению автоматически или только после утверждения. Дополнительные статьи см. в [статьи Уровни автоматизации в автоматизированном расследовании и исправлении.](automation-levels.md)
   - В разделе **Члены** используйте одно или несколько условий для идентификации и включаем устройства.
   - На **вкладке Доступ** пользователя выберите Azure Active Directory [группы,](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) которые должны иметь доступ к создаемой группе устройств.
4. Выберите **Готово,** когда вы закончите настройку группы устройств.

## <a name="next-steps"></a>Дальнейшие действия

- [Посетите Центр действий, чтобы просмотреть ожидающих и завершенных действий по исправлению](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Просмотр и утверждение ожидающих действий](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>См. также

- [Устранение ложных положительных/отрицательных срабатываний в Microsoft Defender для конечной точки](defender-endpoint-false-positives-negatives.md)
