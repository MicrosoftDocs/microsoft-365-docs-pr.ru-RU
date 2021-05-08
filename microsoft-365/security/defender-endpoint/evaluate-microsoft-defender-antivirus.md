---
title: Оценка антивирусной программы в Microsoft Defender
description: Предприятия всех размеров могут использовать это руководство для оценки и тестирования защиты, антивирусная программа в Microsoft Defender в Windows 10.
keywords: антивирусная программа в Microsoft Defender, облачная защита, облако, антивирусное программное обеспечение, безопасность, защита, оценка, тестирование, защита, сравнение, защита в режиме реального времени
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274740"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Оценка антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Используйте это руководство, чтобы определить, насколько антивирусная программа в Microsoft Defender защищает вас от вирусов, вредоносных программ и потенциально нежелательных приложений.

>[!TIP]
>Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки в [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить работу следующих функций и посмотреть, как они работают:
>- Облачная защита
>- Быстрое обучение (включая блок с первого взгляда)
>- Блокировка потенциально нежелательных приложений

В нем рассказывается о важных средствах защиты нового поколения антивирусная программа в Microsoft Defender для малых и крупных предприятий, а также о том, как они увеличивают обнаружение и защиту вредоносных программ в сети.

Вы можете настроить и оценить каждый параметр самостоятельно или все сразу. Мы сгруппировали аналогичные параметры на основе типичных сценариев оценки и включили инструкции по использованию PowerShell для параметров.

Руководство доступно в формате PDF для автономного просмотра:

- [Скачайте руководство в формате PDF](https://www.microsoft.com/download/details.aspx?id=54795)

Вы также можете скачать PowerShell, который автоматически включает все параметры, описанные в руководстве. Сценарий можно получить вместе с загрузкой PDF выше или отдельно из PowerShell Gallery:

- [Скачайте скрипт PowerShell, чтобы автоматически настроить параметры](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> Руководство в настоящее время предназначено для одноаммийной оценки антивирусная программа в Microsoft Defender. Включение всех параметров в этом руководстве может оказаться неподходящим для развертывания в реальном мире.
>
> Последние рекомендации по развертыванию и мониторингу антивирусная программа в Microsoft Defender в сети см. в [антивирусная программа в Microsoft Defender.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Статьи по теме

- [антивирусная программа в Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Развертывание антивирусная программа в Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)