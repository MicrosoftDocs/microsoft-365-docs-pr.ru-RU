---
title: Совместимость антивируса Microsoft Defender с другими продуктами безопасности
description: Что следует ожидать от антивируса Microsoft Defender с другими продуктами безопасности и операционными системами, которые вы используете.
keywords: защитник windows, следующего поколения, антивирус, совместимость, пассивный режим
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8eb52e277f7987477114db9333c3f90bb581ebb5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690974"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Совместимость антивируса Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Обзор

Антивирус Microsoft Defender автоматически включен и установлен на конечных точках и устройствах с Windows 10. Но что происходит, когда используется другое решение антивирусного и антивирусного обеспечения? Это зависит от того, используете ли вы [Microsoft Defender для конечной точки](microsoft-defender-endpoint.md) вместе с антивирусной защитой.
- Если конечные точки и устройства вашей организации защищены решением антивируса и антивируса, не относящиться к Microsoft, а Microsoft Defender для конечной точки не используется, антивирус Microsoft Defender автоматически переходит в отключенный режим.
- Если ваша организация использует Microsoft Defender для конечной точки вместе с решением, не использующим антивирусное или антивирусное программное обеспечение, антивирус Microsoft Defender автоматически переходит в пассивный режим. (Защита и угрозы в режиме реального времени не устраняются антивирусом Microsoft Defender.)
- Если ваша организация использует Microsoft Defender для конечной точки вместе с решением, не использующим антивирусное или антивирусное программное обеспечение, и у вас включен [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) в режиме блокировки, то всякий раз, когда обнаружен вредоносный артефакт, Microsoft Defender for Endpoint принимает меры для блокировки и устранения артефакта.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Антивирус и microsoft Defender для конечной точки

В следующей таблице кратко излагается, что происходит с антивирусом Microsoft Defender, когда сторонние антивирусные продукты используются вместе или без Microsoft Defender для endpoint. 


| Версия Windows   | Защита от вредоносных программ  | Microsoft Defender для регистрации конечной точки | Состояние антивируса Microsoft Defender     |
|------|------|-------|-------|
| Windows 10  | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Да  | Пассивный режим  |
| Windows 10  | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Нет   | Автоматически отключенный режим     |
| Windows 10  | Антивирус Microsoft Defender | Да  | Активный режим | 
| Windows 10  | Антивирус Microsoft Defender | Нет   | Активный режим |
| Windows Server, версия 1803 или более новая или Windows Server 2019 | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Да  | Необходимо настроить пассивный режим (вручную) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, версия 1803 или более новая или Windows Server 2019 | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Нет  | Необходимо отключить (вручную) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, версия 1803 или более новая или Windows Server 2019 | Антивирус Microsoft Defender  | Да |         Активный режим  |
| Windows Server, версия 1803 или более новая или Windows Server 2019 | Антивирус Microsoft Defender | Нет  | Активный режим |
| Windows Server 2016 | Антивирус Microsoft Defender | Да | Активный режим |
| Windows Server 2016 | Антивирус Microsoft Defender | Нет | Активный режим |
| Windows Server 2016 | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Да | Необходимо отключить (вручную) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Сторонний продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт | Нет | Необходимо отключить (вручную) <sup> [[2](#fn2)]<sup> |

<a id="fn1">(1)</a>На Windows Server версии 1803 или более новой версии или Windows Server 2019 антивирус Microsoft Defender автоматически не вступает в пассивный режим при установке антивирусного продукта, не включаемого в Microsoft. В этих случаях установите [антивирус Microsoft Defender в](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) пассивный режим, чтобы предотвратить проблемы, вызванные установкой на сервер нескольких антивирусных продуктов.

Если вы используете Windows Server, версию 1803 или более новую версию или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим, установив следующий ключ реестра:
- Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Имя: `ForcePassiveMode`
- Тип: `REG_DWORD`
- Значение: `1`

> [!NOTE]
> Ключ `ForcePassiveMode` реестра не поддерживается на Windows Server 2016.

<a id="fn2">(2)</a>На Windows Server 2016 антивирус Microsoft Defender автоматически не вступает в пассивный режим при установке антивирусного продукта, не входя в Microsoft. Кроме того, антивирус Microsoft Defender не поддерживается в пассивном режиме. В этих случаях [отключать или](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) отключать антивирус Microsoft Defender вручную, чтобы предотвратить проблемы, вызванные установкой на сервер нескольких антивирусных продуктов.

Для [ключевых](microsoft-defender-antivirus-on-windows-server.md) отличий и параметров управления для установок Windows Server см. антивирус Microsoft Defender на Windows Server.

> [!IMPORTANT]
> Антивирус Microsoft Defender доступен только на устройствах под управлением Windows 10, Windows Server 2016, Windows Server, версии 1803 или более поздней версии и Windows Server 2019.
>
> В Windows 8.1 и Windows Server 2012 антивирусная защита конечной точки корпоративного уровня предлагается в качестве защиты конечных точек System [Center,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))которая управляется с помощью Microsoft Endpoint Configuration Manager.
>
> Защитник Windows также предлагается для потребительских устройств [на Windows 8.1 и Windows Server 2012,](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)хотя она не обеспечивает управление на уровне предприятия (или интерфейс для установок Windows Server 2012 Server Core).

## <a name="functionality-and-features-available-in-each-state"></a>Функциональные возможности и функции, доступные в каждом состоянии

В таблице в этом разделе представлены функциональность и функции, доступные в каждом состоянии. Таблица предназначена только для информационных данных. Он предназначен для описания функций &, которые активно работают или нет, в зависимости от того, находится ли антивирус Microsoft Defender в активном режиме, в пассивном режиме или отключен или отключен. 

> [!IMPORTANT]
> Не отключите возможности, такие как защита в режиме реального времени, облачная защита или ограниченное периодическое сканирование, если вы используете антивирус Microsoft Defender в пассивном режиме или используете EDR в режиме блокировки. 

|Защита |Активный режим |Пассивный режим |EDR в режиме блокировки |Отключено или неустановлено |
|:---|:---|:---|:---|:---|
| [Защита в режиме реального времени](./configure-real-time-protection-microsoft-defender-antivirus.md) [и облачная защита](./enable-cloud-protection-microsoft-defender-antivirus.md) | Да | Нет <sup> [[3](#fn3)]<sup> | Нет | Нет |
| [Ограниченная доступность периодического сканирования](./limited-periodic-scanning-microsoft-defender-antivirus.md) | Нет | Нет | Нет | Да |
| [Сведения о проверке и обнаружении файлов](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Да | Да | Да | Нет |
|  [Устранение угроз](./configure-remediation-microsoft-defender-antivirus.md) | Да | См. <sup> примечание [[4](#fn4)]<sup> | Да | Нет |
| [Обновления аналитики безопасности](./manage-updates-baselines-microsoft-defender-antivirus.md) | Да | Да | Да | Нет |

<a id="fn3">(3)</a>В целом, когда антивирус Microsoft Defender находится в пассивном режиме, защита в режиме реального времени не обеспечивает блокировку или принудительный доступ, даже если она включена и находится в пассивном режиме. 

(<a id="fn4">4)</a>Когда антивирус Microsoft Defender находится в пассивном режиме, функции устранения угроз активны только во время запланированных или по требованию сканов.

> [!NOTE]
> Защита от потери данных конечной точки [Майкрософт 365](/microsoft-365/compliance/endpoint-dlp-learn-about) продолжает работать в обычном режиме, когда антивирус Microsoft Defender находится в активном или пассивном режиме.

## <a name="keep-the-following-points-in-mind"></a>Имейте в виду следующие точки

- В активном режиме антивирус Microsoft Defender используется в качестве антивирусного приложения на компьютере. Вся конфигурация, выполненная с помощью диспетчера конфигурации, групповой политики, intune или других продуктов управления, будет применяться. Файлы отсканированы и устраняются угрозы, а сведения об обнаружении сообщаются в средстве конфигурации (например, в диспетчере конфигурации или антивирусе Microsoft Defender на самом компьютере).

- В пассивном режиме антивирус Microsoft Defender не используется в качестве антивирусного приложения, а угрозы не устраняются антивирусом Microsoft Defender. Файлы отсканированы и отчеты предоставляются для обнаружения угроз, которые совместно с службой Microsoft Defender для конечных точек. Поэтому в консоли Центра безопасности могут возникнуть оповещения с антивирусом Microsoft Defender в качестве источника, даже если антивирус Microsoft Defender находится в пассивном режиме.

- Когда [EDR в](/microsoft-365/security/defender-endpoint/edr-in-block-mode) режиме блокировки включен, а антивирус Microsoft Defender не является основным антивирусным решением, он по-прежнему может обнаруживать и устранять вредоносные элементы.

- При отключении антивирус Microsoft Defender не используется в качестве антивирусного приложения. Файлы не сканированы и угрозы не устраняются. Отключение и отключение антивируса Microsoft Defender в целом не рекомендуется; Если это возможно, держите антивирус Microsoft Defender в пассивном режиме, если вы используете решение для антивирусных программ, не в microsoft.

- Если вы зарегистрированы в Microsoft Defender для конечной точки и используете сторонний продукт противомалярийных программ, то включен пассивный режим. [Служба требует общего обмена](/microsoft-365/security/defender-endpoint/defender-compatibility) информацией из антивирусной службы Microsoft Defender, чтобы правильно отслеживать ваши устройства и сеть для попыток вторжения и атак.

- При автоматическом отключении антивируса Microsoft Defender его можно автоматически включить, если истекает срок защиты, предоставляемой антивирусным продуктом, не относяшимся к Майкрософт, или иным образом перестает обеспечивать защиту в режиме реального времени от вирусов, вредоносных программ или других угроз. Автоматическое повторное включение помогает обеспечить сохранение антивирусной защиты на устройствах. Это также позволяет включить ограниченное периодическое [сканирование,](limited-periodic-scanning-microsoft-defender-antivirus.md)которое использует антивирусный двигатель Microsoft Defender, чтобы периодически проверять угрозы в дополнение к основному антивирусного приложения.

- Когда антивирус Microsoft Defender находится в пассивном режиме, вы можете управлять обновлениями для [антивируса Microsoft Defender;](manage-updates-baselines-microsoft-defender-antivirus.md) Однако вы не можете переместить антивирус Microsoft Defender в активный режим, если на ваших устройствах есть антивирусный продукт, не относяющийся к Корпорации Майкрософт, обеспечивающий защиту от вредоносных программ в режиме реального времени. Для оптимальной эффективности защиты и обнаружения на уровне безопасности убедитесь, что вы обновляете антивирусную защиту [Microsoft Defender (обновление](./manage-updates-baselines-microsoft-defender-antivirus.md) аналитики безопасности, двигатель и платформа), даже если антивирус Microsoft Defender работает в пассивном режиме.

   Если удалить антивирусный продукт, не включаемый в Microsoft, и использовать антивирус Microsoft Defender для защиты устройств, антивирус Microsoft Defender автоматически вернется в обычный активный режим.

> [!WARNING]
> Не отключать, останавливать или изменять связанные службы, используемые антивирусом Microsoft Defender, Microsoft Defender для конечной точки или приложением Безопасности Windows. Эта рекомендация включает службы и процессы *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* или *MsMpEng.* Ручное изменение этих служб может привести к серьезной нестабильности на устройствах и сделать вашу сеть уязвимой. Отключение, остановка или изменение этих служб также могут привести к проблемам при использовании антивирусных решений, не связанных с Microsoft, и отображения их сведений в [приложении Безопасности Windows.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>См. также

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Антивирус Microsoft Defender на Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR в режиме блокировки](edr-in-block-mode.md)
- [Настройка защиты конечных точек](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Устранение ложных положительных/отрицательных срабатываний в Microsoft Defender для конечной точки](defender-endpoint-false-positives-negatives.md)
- [Сведения о защите от потери данных в конечной точке Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)