---
title: Устранение проблем с защитой сети
description: Ресурсы и пример кода для устранения неполадок с защитой сети в Microsoft Defender для конечной точки.
keywords: устранение неполадок, ошибка, исправление, защитник Windows, например, asr, правила, бедра, устранение неполадок, аудит, исключение, ложное срабатывательство, нарушение, блокировка, защитник Майкрософт для конечной точки, защита от угроз microsoft defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 165c17bc820403ebfbbe5cdfe3ca856e8416c593
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074078"
---
# <a name="troubleshoot-network-protection"></a>Защита сети от неполадок

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


При использовании [сетевой защиты](network-protection.md) могут возникнуть проблемы, такие как:

- Защита сети блокирует безопасный веб-сайт (ложное срабатывательство)
- Защита сети не блокирует подозрительный или известный вредоносный веб-сайт (ложный отрицательный)

Для устранения этих проблем необходимо четыре шага:

1. Подтверждение необходимых условий
2. Чтобы проверить правило, используйте режим аудита
3. Добавление исключений для указанного правила (для ложных срабатыва-
4. Отправка журналов поддержки

## <a name="confirm-prerequisites"></a>Подтверждение необходимых условий

Защита сети будет работать только на устройствах со следующими условиями:

>[!div class="checklist"]
> - Конечные точки работают в выпуске Windows 10 Pro или Enterprise версии 1709 или выше.
> - Конечные точки используют антивирус Microsoft Defender в качестве единственного приложения для защиты от антивирусов. [Узнайте, что происходит при использовании антивирусного решения, не используемого Корпорацией Майкрософт.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [Включена защита в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) режиме реального времени.
> - [Включена облачная](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) защита.
> - Режим аудита не включен. Используйте [групповую](enable-network-protection.md#group-policy) политику, чтобы установить правило **отключено** (значение: **0).**

## <a name="use-audit-mode"></a>Использование режима аудита

Вы можете включить защиту сети в режиме аудита, а затем посетить веб-сайт, созданный для демонстрации этой функции. Все подключения к веб-сайту будут разрешены с помощью сетевой защиты, но событие будет включено в журнал, чтобы указать любое подключение, которое было бы заблокировано, если бы была включена защита сети.

1. Настройка сетевой защиты в **режиме аудита.**

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Выполните действия подключения, которые вызывают проблему (например, попытка посетить сайт или подключиться к IP-адресу, который вы делаете или не хотите блокировать).

3. [Просмотрите журналы событий защиты](network-protection.md#review-network-protection-events-in-windows-event-viewer) сети, чтобы узнать, заблокировала ли бы эта функция подключение, если бы оно было установлено для **включения.**
   
   Если защита сети не блокирует подключение, которое, как вы ожидаете, должно блокироваться, в включить эту функцию.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Сообщение о ложном срабатыве или ложном отрицательном

Если вы протестировали эту функцию на демо-сайте и в режиме аудита, а защита сети работает в предварительно настроенных сценариях, но работает не так, как ожидалось для определенного подключения, используйте [веб-форму](https://www.microsoft.com/wdsi/filesubmission) отправки Защитник Windows Security Intelligence, чтобы сообщить о ложном отрицательном или ложном срабатывке для защиты сети. С подпиской на E5 вы также можете предоставить ссылку на любое [связанное оповещение.](alerts-queue.md)

См. [адрес ложных срабатыва-срабатыва-минусов в Microsoft Defender для конечной точки.](defender-endpoint-false-positives-negatives.md)

## <a name="exclude-website-from-network-protection-scope"></a>Исключение веб-сайта из области защиты сети

Чтобы разрешить заблокированный веб-сайт (ложное срабатываний), добавьте ЕГО URL-адрес в [список доверенных сайтов.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/) Веб-ресурсы из этого списка обходят проверку защиты сети.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Сбор диагностических данных для отправки файлов

Когда вы сообщаете о проблеме с сетевой защитой, вам будет предложено собирать и отправлять диагностические данные, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок.

1. Откройте повышенную командную подсказку и измените каталог Защитник Windows:

   ```console
   cd c:\program files\windows defender
   ```

2. Запустите эту команду для создания диагностических журналов:

   ```console
   mpcmdrun -getfiles
   ```

3. По умолчанию они сохраняются в C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab. Прикрепить файл к форме отправки.

## <a name="related-topics"></a>Статьи по теме

- [Защита сети](network-protection.md)
- [Оценка защиты сети](evaluate-network-protection.md)
- [Включить защиту сети](enable-network-protection.md)
- [Адрес ложных срабатыва-срабатыва-](defender-endpoint-false-positives-negatives.md)
