---
title: Анализ исправления возможного почтового цикла
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать анализ возможных почтовых циклов fix на панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям & для определения и исправления почтовых циклов в организации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290565"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Исправление возможной информации о почтовом цикле в Центре & соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Почтовые циклы являются плохими, так как:

- Они тратить системные ресурсы.
- Они потребляют квоту тома почты организации.
- Отправителю исходного сообщения отправляются запутанные отчеты о не доставке (также известные как сообщения о возврате).

Анализ **возможных** почтовых циклов в области "Рекомендуемый для вас" панели мониторинга потока обработки почты в Центре безопасности и соответствия требованиям [&](https://protection.office.com) сообщает вам об обнаружении почтового цикла в организации.  [](mail-flow-insights-v2.md)

Эта информация отображается только после обнаружения условия (если у вас нет почтовых циклов, вы не увидите эти данные).

![Исправление статистики о медленных правилах потока почты в области "Рекомендуемые для вас" панели мониторинга потока почты](../../media/mfi-fix-possible-mail-loop.png)

При **нажатии кнопки "Просмотреть сведения о** виджете" появится элемент с дополнительными сведениями:

- **Домен**
- **Количество сообщений:** вы  можете щелкнуть "Просмотреть образцы сообщений", чтобы просмотреть результаты трассировки сообщений для примера сообщений, на которые повлиял цикл. [](message-trace-scc.md)
- **Тип домена**" Например, "До полномочного" или "Не до полномочного".
- **MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.
- **Причина цикла** **и решение:** мы оденем наиболее распространенные сценарии почтового цикла и предоставляем рекомендуемые действия для исправления цикла.

![Flyout Details that appears after clicking View details on the Fix possible mail loop insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>См. также

Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)
