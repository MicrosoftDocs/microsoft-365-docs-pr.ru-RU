---
title: Запись устройств в Microsoft Defender для конечной точки
description: Отслеживайте учет устройств, управляемых intune, в Microsoft Defender для конечной точки и увеличение скорости в составе.
keywords: на борту, управление Intune, Microsoft Defender для конечной точки, Microsoft Defender, Защитник Windows, управление конфигурацией
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841574"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Запись устройств в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Каждое бортовом устройстве добавляет дополнительный датчик обнаружение и нейтрализация атак на конечные точки (EDR) и повышает видимость по поводу активности нарушения в сети. Онбординг также обеспечивает проверку устройства на наличие уязвимых компонентов, а также проблемы с конфигурацией безопасности и получение критически важных действий по исправлению ситуации во время атак.

Перед отслеживанием и управлением на борту устройств:
- [Регистрация устройств в управление Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Убедитесь, что у вас есть необходимые разрешения](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Обнаружение и отслеживание незащищенных устройств

Карта **onboarding** предоставляет высококачественный обзор скорости на борту, сравнивая количество устройств Windows 10, которые фактически были на борту с Defender для конечной точки, и общее число устройств, управляемых intune Windows 10.

![Карта onboarding управления конфигурацией устройств](images/secconmgmt_onboarding_card.png)<br>
*Карта, показывающая бортовые устройства по сравнению с общее число управляемых intune устройств Windows 10*

>[!NOTE]
>Если вы использовали диспетчер конфигурации Центра безопасности, сценарий бортовой обработки или другие методы бортовой обработки, которые не используют профили Intune, вы можете столкнуться с несоответствиями данных. Чтобы устранить эти несоответствия, создайте соответствующий профиль конфигурации Intune для onboarding Defender для конечной точки и назначьте этот профиль устройствам.

## <a name="onboard-more-devices-with-intune-profiles"></a>На борту больше устройств с профилями Intune

Defender for Endpoint предоставляет несколько удобных вариантов для Windows 10 [устройств.](onboard-configure.md) Однако для устройств с управляемым intune можно использовать профили Intune для удобного развертывания датчика Defender для конечных точек для выбора устройств, эффективно вовсю перенаправив эти устройства в службу.

С **бортовой карты** выберите  дополнительные устройства для создания и назначения профиля в Intune. Ссылка приводит вас на страницу соответствия требованиям устройств в Intune, которая предоставляет аналогичный обзор состояния бортового устройства.

![Страница Microsoft Defender для соответствия требованиям для конечных устройств в управлении устройствами Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Страница Microsoft Defender для соответствия требованиям для конечных устройств в управлении устройствами Intune*

>[!TIP]
>Кроме того, вы можете перейти на страницу соответствия требованиям для конечной точки Defender для конечной точки на портале [Microsoft Azure](https://portal.azure.com/) из всех служб **> Intune >** устройства > ATP в Защитнике Microsoft .

>[!NOTE]
> Если вы хотите просмотреть самые последние данные устройства, нажмите кнопку Список устройств **без датчика ATP**.

На странице соответствия требованиям устройства создайте профиль конфигурации специально для развертывания датчика Defender для конечной точки и назначьте этот профиль устройствам, которые необходимо на борту. Для этого можно либо:

- Выберите **Создать профиль конфигурации устройства, чтобы настроить датчик ATP,** чтобы начать с предварительного профиля конфигурации устройства.
- Создайте профиль конфигурации устройства с нуля.

Дополнительные сведения см. в материале Об использовании профилей конфигурации устройств Intune на бортовых устройствах [в Defender для конечной точки.](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Статьи по теме
- [Убедитесь, что ваши устройства настроены правильно](configure-machines.md)
- [Повышение соответствия базовому стандарту безопасности Defender для конечной точки](configure-machines-security-baseline.md)
- [Оптимизация развертывания и обнаружений правил сокращения направлений атак](configure-machines-asr.md)
