---
title: Microsoft Defender для конечной точки на Mac
ms.reviewer: ''
description: Узнайте, как установить, настроить, обновить и использовать Microsoft Defender для конечной точки на Mac.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301780"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender для конечной точки на Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе описывается установка, настройка, обновление и использование Defender для конечной точки на Mac.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечной точки наряду с Microsoft Defender для конечной точки на Mac может привести к проблемам с производительностью и непредсказуемым побочным эффектам. Если защита конечной точки от Microsoft является абсолютным требованием в вашей среде, вы можете безопасно использовать функции Defender для конечной [](mac-preferences.md#enable--disable-passive-mode)точки на Mac EDR после настройки функции антивируса для запуска в пассивном режиме.

## <a name="whats-new-in-the-latest-release"></a>Новые возможности последнего выпуска

[Новые возможности Microsoft Defender для конечной точки](whats-new-in-microsoft-defender-atp.md)

[Новые возможности в Microsoft Defender для конечной точки на Mac](mac-whatsnew.md)

> [!TIP]
> Если у вас есть какие-либо отзывы, которые вы хотели бы поделиться, отправьте его, открыв Microsoft Defender для конечной точки на Mac на устройстве и навигации, чтобы **помочь**  >  **отправить обратную связь**.

Чтобы получить последние функции, в том числе возможности предварительного просмотра (например, обнаружение и нейтрализация атак на конечные точки для устройств Mac), настройте устройство macOS под управлением Microsoft Defender для Конечной точки как устройство "Insider".

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Установка Microsoft Defender для конечной точки на Mac

### <a name="prerequisites"></a>Предварительные условия

- Подписка на конечную точку Defender и доступ к Центр безопасности в Microsoft Defender порталу
- Опыт начального уровня в скриптах macOS и BASH
- Административные привилегии на устройстве (в случае ручного развертывания)

### <a name="installation-instructions"></a>Инструкции по установке

Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Defender для конечной точки на Mac.

- Средства управления сторонними средствами управления:
    - [Развертывание на основе Microsoft Intune](mac-install-with-intune.md)
    - [Развертывание на основе JAMF](mac-install-with-jamf.md)
    - [Другие продукты MDM](mac-install-with-other-mdm.md)

- Средство командной строки:
    - [Ручное развертывание](mac-install-manually.md)

### <a name="system-requirements"></a>Требования к системе

Поддерживаются три последних основных выпуска macOS.

> [!IMPORTANT]
> В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации. Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные в новых профилях конфигурации для [macOS Catalina](mac-sysext-policies.md)и более новых версиях macOS.

> [!IMPORTANT]
> Поддержка macOS 10.13 (High Sierra) прекращена с 15 февраля 2021 г.

- 11 (Big Sur), 10.15 (Каталина), 10.14 (Mojave)
- Пространство диска: 1 ГБ

Бета-версии macOS не поддерживаются.

устройства macOS с процессорами M1 не поддерживаются.

После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить исходящие подключения между ней и конечными точками.

### <a name="licensing-requirements"></a>Требования к лицензированию

Microsoft Defender для конечной точки на Mac требует одно из следующих предложений по лицензированию объемов Microsoft:

- Microsoft 365 E5 (M365 E5)
- Безопасность Microsoft 365 E5
- Microsoft 365 A5 (M365 A5)
- Windows 10 Корпоративная E5
- Microsoft Defender для конечной точки

> [!NOTE]
> Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.
> Microsoft Defender для конечной точки также доступен для покупки в поставщик облачных решений (CSP). При покупке через CSP не требуется перечисление предложений microsoft Volume Licensing.

### <a name="network-connections"></a>Сетевые подключения

В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть. Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы  отказывали в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них.



|**Таблица списка доменов**|**Описание**|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС. <br><br>Скачайте таблицу здесь: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

Microsoft Defender для конечной точки может открыть прокси-сервер с помощью следующих методов обнаружения:
- Прокси-автоконфиг (PAC)
- Протокол автообнаружия веб-прокси (WPAD)
- Ручная статическая конфигурация прокси

Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.

> [!WARNING]
> Прокси-прокси с проверкой подлинности не поддерживаются. Убедитесь, что используется только PAC, WPAD или статический прокси.
>
> Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности. Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Microsoft Defender для конечной точки на macOS в соответствующие URL-адреса без перехвата. Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.

Чтобы проверить, не заблокировано ли подключение, откройте [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) и [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) в браузере.

Если вы предпочитаете командную строку, вы также можете проверить подключение, задав следующую команду в терминале:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Выход из этой команды должен быть похож на следующие:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Рекомендуется поддерживать [включенную](https://support.apple.com/en-us/HT204899) защиту целостности системы (SIP) на клиентских устройствах. SIP — это встроенная функция безопасности macOS, которая предотвращает низкоуровневые взломы ОС и включена по умолчанию.

После установки Microsoft Defender для конечной точки подключение можно проверить, заверив следующую команду в терминале:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Обновление Microsoft Defender для конечной точки на Mac

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций. Для обновления Microsoft Defender для конечной точки на Mac используется программа с именем Microsoft AutoUpdate (MAU). Дополнительные новости см. в дополнительных подробной информации о развертывании обновлений [для Microsoft Defender для конечной точки на Mac.](mac-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Настройка Microsoft Defender для конечной точки на Mac

Инструкции по настройке продукта в корпоративных средах доступны в наборе предпочтений [Для Microsoft Defender для конечной](mac-preferences.md)точки на Mac .

## <a name="macos-kernel-and-system-extensions"></a>ядра macOS и расширения системы

В соответствии с эволюцией macOS мы готовим обновление Microsoft Defender для конечной точки на Mac, которое использует расширения системы вместо расширений ядра. Соответствующие сведения см. [в материале "Что нового в Microsoft Defender для конечной точки на Mac".](mac-whatsnew.md)

## <a name="resources"></a>Ресурсы

- Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы для Microsoft Defender для конечной](mac-resources.md)точки на Mac.

- [Конфиденциальность для Microsoft Defender для конечной точки на Mac](mac-privacy.md).
