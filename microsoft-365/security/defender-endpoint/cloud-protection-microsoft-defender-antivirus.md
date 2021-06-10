---
title: Облачная защита и антивирусная программа в Microsoft Defender
description: Узнайте о облачной защите и антивирусная программа в Microsoft Defender
keywords: антивирусная программа в Microsoft Defender, технологии следующего поколения, av следующего поколения, машинное обучение, антивирусное программное обеспечение, безопасность, защитник, облако, облачная защита
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: ce54f8205e62b953022fd2518caac058f4f9bab2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788803"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Облачная защита и антивирусная программа в Microsoft Defender

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)
- Антивирусная программа в Microsoft Defender

Технологии следующего поколения в антивирусная программа в Microsoft Defender обеспечивают почти мгновенную автоматизированную защиту от новых и возникающих угроз. Чтобы динамически идентифицировать новые угрозы, технологии нового поколения работают с большими наборами взаимосвязанных данных в системах Microsoft Intelligent Security Graph и мощными системами искусственного интеллекта (AI), управляемыми передовыми моделями машинного обучения. антивирусная программа в Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения точной и интеллектуальной защиты в режиме реального времени. 

> [!TIP]
> Нужны дополнительные сведения? См. в блоге, Узнайте о передовых технологиях в центре [защиты Microsoft Defender для endpoint следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

антивирусная программа в Microsoft Defender работает с облачными службами Майкрософт. Эти службы облачной защиты, также именуемой Службой расширенной защиты Майкрософт (MAPS), повышают стандартную защиту в режиме реального времени, обеспечивая, возможно, лучшую антивирусную защиту. 

> [!NOTE]
> Облачная антивирусная программа в Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки. Как облачная служба это не просто защита файлов, хранимых в облаке; вместо этого облачная служба использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно быстрее, чем традиционные обновления сведении о безопасности.

С помощью облачной защиты технологии следующего поколения обеспечивают быструю идентификацию новых угроз, иногда даже до заражения одной машины. В следующих блогах показано, как работает облачная защита:

- [Почему антивирусная программа в Microsoft Defender является наиболее развернутой на предприятии](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Мониторинг поведения в сочетании с машинным обучением портит масштабную кампанию по добыче монет](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Как искусственный интеллект остановил вспышку "Эмотета"](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Детонация плохой кролик: антивирусная программа в Microsoft Defender и многоуровневые защиты машинного обучения](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [антивирусная программа в Microsoft Defender облачной защиты: расширенные средства защиты в режиме реального времени от неимуторного вредоносного ПО](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Как получить облачную защиту 

Защита с облачной доставкой включена по умолчанию. Однако, возможно, потребуется повторно включить его, если он был отключен в рамках предыдущих организационных политик. Дополнительные дополнительные информации см. в [дополнительных данных, включив облачную защиту.](enable-cloud-protection-microsoft-defender-antivirus.md)

Организации, Windows 10 E5, также могут воспользоваться обновлениями динамической разведки в чрезвычайных ситуациях, которые обеспечивают почти в режиме реального времени защиту от возникающих угроз. При включив облачную защиту, исправления проблем с вредоносными программами можно доставить через облако в течение нескольких минут, а не ждать следующего обновления. Настройте антивирусная программа в Microsoft Defender автоматически получать новые обновления защиты на основе [отчетов из облачной службы.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)

> [!TIP]
> Посетите веб Защитник Windows тестовом сайте demo.wd.microsoft.com, чтобы подтвердить, что функция работает, и узнайте, как она работает. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

## <a name="next-steps"></a>Дальнейшие действия

1. [Включить облачную защиту.](enable-cloud-protection-microsoft-defender-antivirus.md) Вы можете включить облачную защиту с помощью Microsoft Endpoint Manager (которая теперь включает Microsoft Endpoint Configuration Manager и Microsoft Intune), групповые политики или группы PowerShell.

2. [Укажите уровень облачной защиты.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Уровень защиты, предлагаемый облаком, можно указать с помощью Microsoft Endpoint Manager или групповой политики. Уровень защиты влияет на объем сведений, общих с облаком, и на то, насколько агрессивно блокируют новые файлы.

3. [Настройка и проверка сетевых подключений для антивирусная программа в Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md). Существуют определенные URL-адреса Майкрософт, к которые должна быть подключена сеть и конечные точки для эффективной работы облачной защиты. В этой статье перечислены URL-адреса, разрешенные с помощью брандмауэра или правил фильтрации сети, а инструкции по подтверждению правильной регистрации сети в облачной защите.

4. [Настройка функции "блок с первого взгляда".](configure-block-at-first-sight-microsoft-defender-antivirus.md) Функция "блокировка на первый взгляд" может блокировать новые вредоносные программы в течение нескольких секунд, не дожидаясь часов для традиционной разведки безопасности. Вы можете включить и настроить его с помощью Microsoft Endpoint Manager или групповой политики.

5. [Настройка периода ожидания облачного блока](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). антивирусная программа в Microsoft Defender может блокировать запуск подозрительных файлов во время запроса службы защиты облачных служб. Вы можете настроить время, когда файл будет не запущен с помощью Microsoft Endpoint Manager или групповой политики.