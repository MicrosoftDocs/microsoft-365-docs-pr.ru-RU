---
title: Понимание профилей устройств
description: Различные профили, которые администраторы могут назначать устройствам
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842006"
---
# <a name="device-profiles"></a>Профили устройств

Можно назначить устройствам различные предустроинные конфигурации ("профили устройств"), каждый из которых оптимизирован для потребностей определенных типов пользователей. Доступны три профиля устройств:

- Стандартный
- Конфиденциальные данные
- Power user

Профили устройств можно использовать как часть иерархии параметров конфигурации устройств.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Конфигурации устройств, показанные как пирамида. Описание следует":::

В принципе каждое компьютеры, управляемые Майкрософт имеет основу, которая включает стандартный базовый уровень безопасности, политики соответствия требованиям, Windows параметры обновления и группы. Чтобы работать с компьютеры, управляемые Майкрософт, каждое устройство должно включать все эти элементы, которые не могут быть изменены администраторами без запроса на компьютеры, управляемые Майкрософт.

Профили устройств отображаются на следующем более высоком уровне. Каждое компьютеры, управляемые Майкрософт должно иметь один (и только один) профиль. Администраторы могут выбрать, какой профиль назначен устройству.

На еще более высоком уровне находятся [дополнительные настройки.](customizing.md) Каждое устройство может иметь одно или несколько (или нет) настроек. Они могут изменять нижний уровень (профили устройств или фундаментальная конфигурация), либо быть совершенно новым запросом, который будет слоистым поверх стандартной конфигурации.

В верхней части находятся собственные изменения, такие как сетевые сведения или приложения. Устройство может иметь любое количество этих изменений, которые не управляются или блокируются компьютеры, управляемые Майкрософт.


## <a name="device-profile-details"></a>Сведения о профиле устройства

В следующей таблице подводятся итоги параметров и их значений по умолчанию для каждого параметра, настроенного профилями устройств. (За кулисами эти параметры настраиваются OMA-URIs с помощью настраиваемых профилей конфигурации в Microsoft Endpoint Manager.)

<br>

****

|Возможность|Конфиденциальные данные|Power User|Стандартный|
|---|:---:|:---:|:---:|
|**Блок внешних служба хранилища**|Да|Да|Нет|
|**[Уровень облачного блока](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|Фишинговое сообщение с|Фишинговое сообщение с|Фишинговое сообщение с|
|**Отключение учетных записей Майкрософт**|Да|Да|Нет|
|**Отключение личных OneDrive**|Да|Да|Нет|
|**Переключение на безопасный рабочий стол для высоты**|Нет|Да|Нет|
|**Microsoft Defender для тега конечного устройства**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**Администратор на устройстве?**|Нет|Да|Нет|
|**Профиль автопилота**|Стандарт MMD|MMD Power User|Стандарт MMD|
|**AppLocker**|Да|Нет|Нет|
|**Блокировка общедоступных магазинов**|Да|Да|Нет|
|

Каждый профиль устройства также включает в себя эти элементы:

- Динамическая группа устройств Azure Active Directory (AAD)
- Группа устройств AAD для статического членства
- Профиль Microsoft Endpoint Manager конфигурации

> [!IMPORTANT]
> Не изменять членство этих групп напрямую. Используйте интерфейс, как описано в [профилях Reassign](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Ограничения

Вы можете запросить исключения для профилей устройств и их сведений, как это было бы с любой другой политикой. Имейте в виду, что в организации Azure Active Directory (клиент) может быть только один профиль каждого устройства. Например, нельзя запрашивать отключение профиля устройства "Конфиденциальные данные" для некоторых пользователей. Все устройства с профилем конфиденциальных данных должны иметь ту же конфигурацию.

Каждое устройство может иметь только один профиль. Если заданное устройство используется более чем одним пользователем, все пользователи на этом устройстве будут иметь ту же конфигурацию.
