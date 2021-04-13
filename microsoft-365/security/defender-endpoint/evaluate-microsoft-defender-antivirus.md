---
title: Оценка антивируса Microsoft Defender
description: Предприятия всех размеров могут использовать это руководство для оценки и тестирования защиты, предложенной антивирусом Microsoft Defender в Windows 10.
keywords: Антивирус Microsoft Defender, облачная защита, облачные, антивирусные программы, безопасность, защита, оценка, тестирование, защита, сравнение, защита в режиме реального времени
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de9c7e845188f47ab5b8e1f9d97871ea36340d19
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691470"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Оценка антивируса Microsoft Defender

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

## <a name="related-topics"></a>Статьи по теме

- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Развертывание антивируса Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)