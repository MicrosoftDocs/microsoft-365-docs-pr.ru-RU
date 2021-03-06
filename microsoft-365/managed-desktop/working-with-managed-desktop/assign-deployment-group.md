---
title: Назначение устройств группе развертывания
description: Как указать группу развертывания, в которой должны быть устройства
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985640"
---
# <a name="assign-devices-to-a-deployment-group"></a>Назначение устройств группе развертывания

компьютеры, управляемые Майкрософт назначит устройства различным группам развертывания, но можно указать или изменить группу, назначенную устройству с помощью портала Admin. Назначение меняется после регистрации устройства или после регистрации пользователя.

> [!IMPORTANT]
> При изменении назначения к устройству будут применены политики, определенные для этой группы. Изменение может установить последнюю версию Windows 10 (включая любые новые функции или обновления качества). Сначала лучше переместить несколько устройств, а затем проверить результат работы пользователя. Следует помнить, что некоторые обновления перезапустят устройство. Дважды убедитесь, что вы выбрали нужные устройства для назначения. Выполнение назначения может занять до 24 часов.

Чтобы назначить устройства группе развертывания, выполните следующие действия. Если необходимо переместить отдельные устройства в разные группы, повторите эти действия для каждой группы.

1. В Microsoft Endpoint Manager выберите **Устройства** в левой области. В разделе **компьютеры, управляемые Майкрософт** выберите **Устройства**.
2. Выберите устройства, которые необходимо назначить. Все выбранные устройства будут назначены в указанную группу.
3. Выберите **действия устройства** из меню.
4. Выберите **Назначение устройства в группу.** Откроется флайер.
5. Используйте выпадаемое меню, чтобы выбрать группу для перемещения устройств, а затем выберите **Сохранить**. Назначенная **группа будет** изменяться на **Pending**.

Когда назначение выполнено, **группа,** назначенная  администратором (указано, что вы сделали это изменение), и столбец **Group** покажет новое групповое назначение.

> [!NOTE]
> Нельзя перемещать устройства в другие группы, если они находятся в состоянии "ошибка" или "ожидание" регистрации.
>
>Если устройство не было правильно удалено, оно может показать состояние "готово". Если переместить такое устройство, не исключено, что перемещение не будет завершено. Если вы не  видите группу, назначенную изменением на **Ожидающееся** в шаге 5, убедитесь, что устройство доступно, ища его в Intune. Дополнительные сведения см. в разделе[Сведения об устройстве в Intune](/mem/intune/remote-actions/device-inventory).