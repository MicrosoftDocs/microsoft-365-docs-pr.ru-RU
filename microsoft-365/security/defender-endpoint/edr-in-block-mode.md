---
title: Обнаружение конечных точек и реагирование в режиме блокировки
description: Узнайте о обнаружение и нейтрализация атак на конечные точки в режиме блокировки
keywords: Microsoft Defender для конечной точки, mde, EDR в режиме блокирования, блокировка пассивного режима
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415603"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Обнаружение конечных точек и ответ (EDR) в режиме блокировки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Что EDR в режиме блокировки?

[Обнаружение и](overview-endpoint-detection-response.md) ответ конечной точки (EDR) в режиме блокировки обеспечивает добавленную защиту от вредоносных артефактов, антивирусная программа в Microsoft Defender не является основным антивирусным продуктом и работает в пассивном режиме. EDR режиме блокировки устраняет вредоносные артефакты, обнаруженные с помощью EDR. Такие артефакты могли быть пропущены основным антивирусным продуктом, не от microsoft. EDR в режиме блокировки работает за кулисами для устранения обнаруженных вредоносных артефактов, после нарушения на устройстве. 

> [!IMPORTANT]
> EDR режиме блокировки не обеспечивает всю защиту, доступную при антивирусная программа в Microsoft Defender включена защита в режиме реального времени. Все функции, которые антивирусная программа в Microsoft Defender быть активным антивирусным решением, не будут работать, включая следующие ключевые примеры: 
> 
> - Защита в режиме реального времени, включая сканирование в режиме реального времени, недоступна, антивирусная программа в Microsoft Defender в пассивном режиме. Дополнительные новости о параметрах политики защиты в режиме реального времени см. в антивирусная программа в Microsoft Defender в режиме **[реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md)**
> - Такие **[функции,](network-protection.md)** как защита сети и правила уменьшения поверхности атаки, доступны только при антивирусная программа в Microsoft Defender в активном режиме. **[](attack-surface-reduction.md)** 
> 
> Ожидается, что антивирусное решение, не в microsoft, предоставляет эти возможности. 

EDR в режиме блокировки интегрирована с угрозами [& управление уязвимостями](next-gen-threat-and-vuln-mgt.md). Команда безопасности организации получит рекомендации [](tvm-security-recommendation.md) по безопасности, чтобы включить EDR в режиме блокировки, если она еще не включена. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="рекомендация включить EDR в режиме блокировки":::

> [!TIP]
> Чтобы получить лучшую защиту, убедитесь в развертывании базовых показателей **[Microsoft Defender для конечных точек.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Что происходит при обнаружении чего-либо?

Когда EDR в режиме блокировки и обнаружен вредоносный артефакт, Microsoft Defender для конечных точек блокирует и устраняет этот артефакт. Ваша группа операций безопасности будет  видеть  состояние обнаружения заблокированным или предотвращенным в центре действий, [](respond-machine-alerts.md#check-activity-details-in-action-center)указанным в качестве завершенных действий.

На следующем изображении показан экземпляр нежелательного программного обеспечения, которое было обнаружено и заблокировано EDR режиме блокировки:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR в режиме блокировки обнаружил что-то":::


## <a name="enable-edr-in-block-mode"></a>Включить EDR в режиме блокировки

> [!TIP]
> Убедитесь, [что требования](#requirements-for-edr-in-block-mode) будут выполнены перед включением EDR в режиме блокировки.

1. Перейдите на портал Microsoft 365 Defender [https://security.microsoft.com/](https://security.microsoft.com/) () и войдите. 

2. Выберите **Параметры**  >  **конечных точек**  >  **Общие**  >  **расширенные функции**.

3. Прокрутите вниз, а затем урну на **включить EDR в режиме блокировки**.

> [!NOTE]
> EDR режиме блокировки можно включить только на портале Microsoft 365 Defender () или в Центр безопасности в Microsoft Defender [https://security.microsoft.com](https://security.microsoft.com) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). Вы не можете использовать клавиши реестра, Microsoft Intune или групповой политики, чтобы включить или отключить EDR в режиме блокировки.

## <a name="requirements-for-edr-in-block-mode"></a>Требования к EDR в режиме блокировки

| Требования  | Сведения  |
|---------|---------|
| Разрешения | Роль глобального администратора или администратора безопасности должна быть назначена в [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Дополнительные сведения см. в [элементе Basic permissions.](basic-permissions.md) |
| Операционная система     | Устройства должны запускать одну из следующих версий Windows: <br/>- Windows 10 (все выпуски) <br/>- Windows Server, версия 1803 или более новая <br/>- Windows Server 2019 <br/>- Windows Server 2016 (только если антивирусная программа в Microsoft Defender находится в активном режиме)     |
| Microsoft Defender для конечной точки     | Устройства должны быть на борту в Defender для конечной точки. См. [минимальные требования к Microsoft Defender для конечной точки.](minimum-requirements.md)       |
| Антивирусная программа в Microsoft Defender  | Устройства должны антивирусная программа в Microsoft Defender и работать в активном или пассивном режиме. [Подтвердим антивирусная программа в Microsoft Defender находится в активном или пассивном режиме.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
| Облачная защита | антивирусная программа в Microsoft Defender необходимо настроить так, чтобы включена [облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md) |
| антивирусная программа в Microsoft Defender платформа | Устройства должны быть в курсе. Чтобы подтвердить, используя PowerShell, запустите в качестве администратора групплет [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMProductVersion** необходимо увидеть **4.18.2001.10** или выше. <p> Дополнительные данные см. в разделе [Управление обновлениями антивирусной программы в Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md). |
| антивирусная программа в Microsoft Defender | Устройства должны быть в курсе. Чтобы подтвердить, используя PowerShell, запустите в качестве администратора групплет [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus) В **строке AMEngineVersion** вы должны увидеть **1.1.16700.2** или выше. <p> Дополнительные данные см. в разделе [Управление обновлениями антивирусной программы в Microsoft Defender и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md). |

> [!IMPORTANT]
> Чтобы получить наилучшее значение защиты, убедитесь, что антивирусное решение настроено для получения регулярных обновлений и основных функций, а также настройки [исключений.](configure-exclusions-microsoft-defender-antivirus.md) EDR режиме блокировки касается исключений, определенных для антивирусная программа в Microsoft Defender, [](manage-indicators.md) но не индикаторов, определенных для Microsoft Defender для конечной точки.

## <a name="frequently-asked-questions"></a>Вопросы и ответы 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>Нужно ли включить EDR в режиме блокировки, если антивирусная программа в Microsoft Defender работает на устройствах?

Основная цель EDR в режиме блокировки — исправление обнаружения после нарушения, пропущенных антивирусным продуктом, не относяжимся к Майкрософт. Однако рекомендуется сохранять EDR в режиме блокировки, независимо от того, антивирусная программа в Microsoft Defender работает в пассивном режиме или в активном режиме. 

- Когда антивирусная программа в Microsoft Defender находится в пассивном режиме, EDR режиме блокировки обеспечивает другой уровень защиты вместе с Microsoft Defender для конечной точки. 
- Если антивирусная программа в Microsoft Defender находится в активном режиме, EDR режиме блокировки не предоставляет дополнительного сканирования, но позволяет Defender для конечной точки выполнять автоматические действия при обнаружении EDR нарушений.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>Повлияет ли EDR режим блокировки на антивирусную защиту пользователя? 

EDR режиме блокировки не влияет на сторонную антивирусную защиту, запущенную на устройствах пользователей. EDR в режиме блокировки работает, если основное антивирусное решение что-то пропускает или если обнаружено сообщение о нарушении. EDR режиме блокировки работает так же, как антивирусная программа в Microsoft Defender в пассивном режиме, за исключением того, что EDR в режиме блокировки также блокирует и устраняет обнаруженные вредоносные артефакты или поведение.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Почему мне нужно поддерживать антивирусная программа в Microsoft Defender в курсе? 

Поскольку антивирусная программа в Microsoft Defender обнаруживает и устраняет вредоносные элементы, важно поддерживать его в курсе. Чтобы EDR режиме блокировки был эффективным, он использует новейшие модели обучения устройств, поведенческие обнаружения и heuristics. Пакет [возможностей Defender для конечной](microsoft-defender-endpoint.md) точки работает комплексно. Чтобы получить наилучшее значение защиты, антивирусная программа в Microsoft Defender быть в курсе. См. [антивирусная программа в Microsoft Defender управление обновлениями и применение базовых показателей.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>Зачем нужна облачная защита (MAPS)? 

Чтобы включить функцию на устройстве, требуется облачная защита. Облачная защита позволяет [Defender for Endpoint](microsoft-defender-endpoint.md) предоставлять последнюю и наибольшую защиту с учетом широты и глубины сведений о безопасности, а также моделей обучения поведения и устройств.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>В чем разница между активным и пассивным режимом?

Для конечных точек Windows 10, Windows Server, версии 1803 или более поздней версии или Windows Server 2019, когда антивирусная программа в Microsoft Defender находится в активном режиме, он используется в качестве основного антивируса на устройстве. При работе в пассивном режиме антивирусная программа в Microsoft Defender не является основным антивирусным продуктом. В этом случае угрозы не устраняются антивирусная программа в Microsoft Defender в режиме реального времени.

> [!NOTE]
> антивирусная программа в Microsoft Defender может работать в пассивном режиме только в том случае, если устройство находится на борту в Microsoft Defender для конечной точки.

Дополнительные сведения см. [в антивирусная программа в Microsoft Defender совместимости.](microsoft-defender-antivirus-compatibility.md)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Как подтвердить, что антивирусная программа в Microsoft Defender находится в активном или пассивном режиме?

Чтобы подтвердить, антивирусная программа в Microsoft Defender работает в активном или пассивном режиме, можно использовать командную подсказку или PowerShell на устройстве с Windows.

|Метод  |Procedure  |
|---------|---------|
| PowerShell     | 1. Выберите меню , начните вводить, а затем `PowerShell` откройте Windows PowerShell в результатах. <p>2. Введите `Get-MpComputerStatus` . <p>3. В списке результатов в строке **AMRunningMode** посмотрите одно из следующих значений: <br/>- `Normal` <br/>- `Passive Mode` <p>Дополнительные данные см. в дополнительных данных [get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Командная строка     | 1. Выберите меню , начните вводить, а затем `Command Prompt` откройте Windows командную подсказку в результатах. <p>2. Введите `sc query windefend` . <p>3. В списке результатов в строке **STATE** подтвердим, что служба запущена.         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Как подтвердить, что EDR в режиме блокировки включена с антивирусная программа в Microsoft Defender в пассивном режиме?

С помощью PowerShell можно подтвердить, что EDR в режиме блокировки включена с антивирусная программа в Microsoft Defender в пассивном режиме.

1. Выберите меню , начните вводить, а `PowerShell` затем откройте Windows PowerShell в результатах. 

2. Тип `Get-MPComputerStatus | select AMRunningMode`.

3. Подтверди, что `EDR Block Mode` результат отображается.

   > [!TIP]
   > Если антивирусная программа в Microsoft Defender находится в активном режиме, вместо `Normal` `EDR Block Mode` . Дополнительные данные см. в дополнительных данных [get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Поддерживается EDR в режиме блокировки в Windows Server 2016?

Если антивирусная программа в Microsoft Defender работает в активном или пассивном режиме, EDR в режиме блокировки поддерживается следующие версии Windows:

- Windows 10 (все выпуски)
- Windows Сервер, версия 1803 или более новая 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>Как насчет Windows Server 2016? 

Если Windows Server 2016 работает антивирусная программа в Microsoft Defender активном режиме, а конечная точка находится на борту в Defender для конечной точки, EDR в режиме блокировки технически поддерживается. Однако EDR в режиме блокировки предназначен для дополнительной защиты, антивирусная программа в Microsoft Defender не является основным антивирусным решением на конечной точке. В этих случаях антивирусная программа в Microsoft Defender в пассивном режиме. 

В настоящее время антивирусная программа в Microsoft Defender в пассивном режиме не поддерживается Windows Server 2016. Дополнительные новости см. [в антивирусная программа в Microsoft Defender антивирусных](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)и антивирусных решениях, не в microsoft.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Сколько времени необходимо для отключения EDR в режиме блокировки?

Если вы решите отключить EDR в режиме блокировки, для отключения этой возможности может занять до 30 минут.

## <a name="see-also"></a>См. также

- [Блог Community технологий: введение EDR в режиме блокировки: остановка атак в их треках](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Блокировка с учетом поведения и автономность](behavioral-blocking-containment.md)

