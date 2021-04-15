---
title: Включить ограниченную функцию периодического сканирования антивирусных программ Microsoft Defender
description: Ограниченное периодическое сканирование позволяет использовать антивирус Microsoft Defender в дополнение к другим установленным поставщикам av
keywords: LPS, ограниченное, периодическое, сканирование, сканирование, совместимость, 3-я сторона, другое av, отключение
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
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764487"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Использование ограниченного периодического сканирования в антивирусной программе в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Ограниченное периодическое сканирование — это особый тип обнаружения и устранения угроз, который можно включить при установке другого антивирусного продукта на устройстве Windows 10.

Его можно включить только в определенных ситуациях. Дополнительные сведения о ограниченном периодичное сканирование и о том, как антивирус Microsoft Defender работает с другими антивирусными продуктами, см. в этой [ссылке.](microsoft-defender-antivirus-compatibility.md)

**Корпорация Майкрософт не рекомендует использовать эту функцию в корпоративных средах. Это функция, предназначенная в первую очередь для потребителей.** Эта функция использует только ограниченный подмножество антивирусных возможностей Microsoft Defender для обнаружения вредоносных программ, и не сможет обнаружить большинство вредоносных программ и потенциально нежелательного программного обеспечения. Кроме того, возможности управления и отчетности будут ограничены. Корпорация Майкрософт рекомендует предприятиям выбирать основное антивирусное решение и использовать его исключительно.

## <a name="how-to-enable-limited-periodic-scanning"></a>Как включить ограниченное периодическое сканирование

Антивирус Microsoft Defender по умолчанию включает себя на устройстве Windows 10, если не установлен другой антивирусный продукт или если другой продукт устарел, истек или не работает правильно.

Если антивирус Microsoft Defender включен, на этом устройстве будут отображаться обычные параметры, настроенные на него:

![Приложение Безопасности Windows, показывающая параметры av Microsoft Defender, включая параметры сканирования, параметры и параметры обновления](images/vtp-wdav.png)

Если другой антивирусный продукт установлен и работает правильно, антивирус Microsoft Defender отключится. Приложение Безопасности Windows изменит раздел защиты **&** вирусов, чтобы показать состояние продукта AV и укажите ссылку на параметры конфигурации продукта.

Под любыми сторонними продуктами AV появится новая ссылка в качестве антивирусных параметров **Microsoft Defender.** Щелкните эту ссылку, чтобы показать перегной, который позволяет ограниченное периодическое сканирование. Обратите внимание, что ограниченный периодический параметр — это переключеть, чтобы включить или отключить периодическое сканирование. 

При сдвижном переходе **на Включен** будет покажите стандартные параметры AV Microsoft Defender под сторонним продуктом AV. Ограниченный вариант периодического сканирования появится в нижней части страницы.

## <a name="related-articles"></a>Статьи по теме

- [Настройка поведенческой, эвристической защиты и защиты в режиме реального времени](configure-protection-features-microsoft-defender-antivirus.md)
- [Антивирус Microsoft Defender в Windows 10](microsoft-defender-antivirus-in-windows-10.md)