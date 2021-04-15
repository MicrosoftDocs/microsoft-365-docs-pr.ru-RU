---
title: Оценка антивирусной программы в Microsoft Defender
description: Предприятия всех размеров могут использовать это руководство для оценки и тестирования защиты, предложенной антивирусом Microsoft Defender в Windows 10.
keywords: Антивирус Microsoft Defender, облачная защита, облачные, антивирусные программы, безопасность, защита, оценка, тестирование, защита, сравнение, защита в режиме реального времени
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764835"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Оценка антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Используйте это руководство, чтобы определить, насколько хорошо антивирус Microsoft Defender защищает вас от вирусов, вредоносных программ и потенциально нежелательных приложений.

>[!TIP]
>Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки в [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить работу следующих функций и посмотреть, как они работают:
>- Защита с облачным доставкой
>- Быстрое обучение (включая блок с первого взгляда)
>- Блокировка потенциально нежелательных приложений

В нем рассказывается о важных средствах защиты нового поколения антивируса Microsoft Defender, доступных как для малых, так и для крупных предприятий, а также о том, как они увеличивают обнаружение и защиту вредоносных программ по всей сети.

Вы можете настроить и оценить каждый параметр самостоятельно или все сразу. Мы сгруппировали аналогичные параметры на основе типичных сценариев оценки и включили инструкции по использованию PowerShell для параметров.

Руководство доступно в формате PDF для автономного просмотра:

- [Скачайте руководство в формате PDF](https://www.microsoft.com/download/details.aspx?id=54795)

Вы также можете скачать PowerShell, который автоматически включает все параметры, описанные в руководстве. Сценарий можно получить вместе с загрузкой PDF выше или отдельно из PowerShell Gallery:

- [Скачайте скрипт PowerShell, чтобы автоматически настроить параметры](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Руководство в настоящее время предназначено для одноамперной оценки антивируса Microsoft Defender. Включение всех параметров в этом руководстве может оказаться неподходящим для развертывания в реальном мире.
>
> Последние рекомендации по развертыванию и мониторингу антивируса Microsoft Defender в сети см. в выпуске [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).

## <a name="related-topics"></a>Связанные статьи

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)