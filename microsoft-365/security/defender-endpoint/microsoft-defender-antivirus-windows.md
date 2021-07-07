---
title: Антивирусная программа в Microsoft Defender
description: Узнайте, как настраивать и использовать антивирусную программу в Microsoft Defender (встроенная защита от вредоносных программ и вирусов), а также управлять ею.
keywords: Антивирусная программа в Microsoft Defender, Защитник Windows, защита от вредоносных программ, scep, system center endpoint protection, system center configuration manager, вирус, вредоносная программа, угроза, обнаружение, защита, безопасность
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323052"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Антивирусная программа в Microsoft Defender в Windows

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирусная программа в Microsoft Defender — это основной компонент защиты нового поколения в Microsoft Defender для конечной точки. Эта защита сочетает машинное обучение, анализ больших данных, углубленные исследования устойчивости к угрозам и облачную инфраструктуру Майкрософт для защиты устройств (или конечных точек) в организации. Антивирусная программа в Microsoft Defender встроена в Windows и работает с Microsoft Defender для конечной точки для обеспечения защиты на вашем устройстве и в облаке. 

## <a name="compatibility-with-other-antivirus-products"></a>Совместимость с другими антивирусными продуктами

Если на вашем устройстве используется антивирусная или антивредоносная программа стороннего поставщика, возможно, вы можете запустить антивирусную программу в Microsoft Defender в пассивном режиме вместе с антивирусным решением стороннего поставщика. Это зависит от используемой операционной системы и от того, подключено ли ваше устройство к Defender для конечной точки. Дополнительные сведения см. в статье [Совместимость Антивирусной программы в Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Сравнение активного, пассивного и отключенного режимов

В следующей таблице описано, чего следует ожидать, когда антивирусная программа в Microsoft Defender находится в активном, пассивном или отключенном режимах.

| Режим  | Что происходит  |
|---------|---------|
| Активный режим | В активном режиме антивирусная программа в Microsoft Defender используется в качестве основного антивирусного приложения на устройстве. Файлы проверяются, угрозы устраняются, а обнаруженные угрозы перечислены в отчетах о безопасности вашей организации и в приложении "Безопасность Windows". |
| Пассивный режим | В пассивном режиме антивирусная программа в Microsoft Defender не используется в качестве основного антивирусного приложения на устройстве. Файлы проверяются, и об обнаруженных угрозах сообщается, но угрозы не устраняются антивирусной программой в Microsoft Defender.   |
| Отключено или удалено  | При отключении или удалении антивирусная программа в Microsoft Defender не используется. Файлы не проверяются, угрозы не устраняются. Как правило, не рекомендуется отключать и удалять антивирусную программу в Microsoft Defender.  |

Дополнительные сведения см. в статье [Совместимость Антивирусной программы в Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Проверка состояния антивирусной программы в Microsoft Defender на вашем устройстве

Если вы хотите проверить состояние антивирусной программы в Microsoft Defender на вашем устройстве, можно использовать один из нескольких методов, таких как приложение "Безопасность Windows" или Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Используйте приложение "Безопасность Windows" для проверки состояния антивирусной программы в Microsoft Defender 

1. На устройстве с Windows выберите меню "Пуск" и начните ввод `Security`. Затем откройте приложение "Безопасность Windows" в результатах.

2. Выберите **Защита от вирусов и угроз**.

3. В разделе **Защита от вирусов и угроз** выберите **Управление параметрами**.

На странице параметров вы увидите название антивирусного или антивредоносного решения.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Используйте PowerShell для проверки состояния антивирусной программы в Microsoft Defender 

1. Выберите меню "Пуск" и начните ввод `PowerShell`. Затем откройте Windows PowerShell в результатах.

2. Тип `Get-MpComputerStatus`.

3. В списке результатов посмотрите на строку **AMRunningMode**.

   - **Обычный** означает, что антивирусная программа в Microsoft Defender работает в активном режиме.
   - **Пассивный режим** означает, что антивирусная программа в Microsoft Defender запущена, но не является основным антивирусным или антивредоносным продуктом на вашем устройстве.
   - **Режим блокировки EDR** означает, что антивирусная программа в Microsoft Defender запущена и в Microsoft Defender для конечной точки включена функция, которая называется "EDR в режиме блокировки". (См. раздел [Обнаружение и нейтрализация атак на конечные точки в режиме блокировки](edr-in-block-mode.md).)
   - **Пассивный режим SxS** означает, что антивирусная программа в Microsoft Defender работает в пассивном режиме наряду с другим антивирусным или антивредоносным продуктом, а ваше устройство не подключено к Microsoft Defender для конечной точки. В этом случае ограниченное периодическое сканирование используется в антивирусной программе в Microsoft Defender. Дополнительные сведения см. в разделе [Использование ограниченного периодического сканирования в антивирусной программе в Microsoft Defender](limited-periodic-scanning-microsoft-defender-antivirus.md).

Дополнительные информацию о командлете Get-MpComputerStatus PowerShell см. в справочной статье [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Получите обновления для антивирусной и антивредоносной платформ

Важно постоянно обновлять антивирусную программу в Microsoft Defender или любое антивирусное или антивредоносное решение. Корпорация Майкрософт выпускает регулярные обновления, чтобы убедиться, что ваши устройства оснащены новейшими технологиями для защиты от новых вредоносных программ и методов атак. Дополнительные данные см. в разделе [Управление обновлениями антивирусной программы в Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>См. также

- [Антивирусная программа в Microsoft Defender в Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Управление антивирусной программой в Microsoft Defender и ее настройка](configuration-management-reference-microsoft-defender-antivirus.md)
- [Оценка защиты антивирусной программы в Microsoft Defender](evaluate-microsoft-defender-antivirus.md)
