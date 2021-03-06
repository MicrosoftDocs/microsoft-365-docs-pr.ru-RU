---
title: Устранение проблем с защитой сети
description: Ресурсы и пример кода для устранения неполадок с защитой сети в Microsoft Defender для конечной точки.
keywords: устранение неполадок, ошибка, исправление, защита windows, например, asr, правила, бедра, устранение неполадок, аудит, исключение, ложное срабатыважение, нарушение, блокировка, Microsoft Defender для Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844062"
---
# <a name="troubleshoot-network-protection"></a>Защита сети от неполадок

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
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
> - Конечные точки запускаются Windows 10 Pro или Enterprise версии 1709 или выше.
> - Конечные точки используют антивирусная программа в Microsoft Defender в качестве единственного приложения для защиты от антивирусов. [Узнайте, что происходит при использовании антивирусного решения, не используемого Корпорацией Майкрософт.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [Включена защита в](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) режиме реального времени.
> - [Включена облачная](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) защита.
> - Режим аудита не включен. Используйте [групповую](enable-network-protection.md#group-policy) политику, чтобы установить правило **отключено** (значение: **0).**

## <a name="use-audit-mode"></a>Использовать режим аудита

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

Если вы протестировали эту функцию на демо-сайте и в режиме аудита, а защита сети работает в предварительно настроенных сценариях, но работает не так, как ожидалось, для определенного подключения используйте [веб-форму](https://www.microsoft.com/wdsi/filesubmission) отправки Защитник Windows Security Intelligence, чтобы сообщить о ложном отрицательном или ложном срабатывке для защиты сети. С подпиской на E5 вы также можете предоставить ссылку на любое [связанное оповещение.](alerts-queue.md)

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

3. Прикрепить файл к форме отправки. По умолчанию диагностические журналы сохраняются на `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` уровне . 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Устранение проблем с подключением с помощью защиты сети (для клиентов E5)

Из-за среды, в которой выполняется защита сети, Корпорация Майкрософт не может видеть параметры прокси-сервера операционной системы. В некоторых случаях клиенты сетевой защиты не могут добраться до облачной службы. Чтобы устранить проблемы с подключением с помощью сетевой защиты, настройте один из следующих ключей реестра, чтобы защита сети знала о конфигурации прокси:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

Ключ реестра можно настроить с помощью PowerShell, Microsoft Endpoint Manager или групповой политики. Вот некоторые ресурсы, которые помогут:
- [Работа с ключами реестра](/powershell/scripting/samples/working-with-registry-keys)
- [Настройка настраиваемых параметров клиента для Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Используйте параметры групповой политики для управления Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>См. также

- [Защита сети](network-protection.md)
- [Оценка защиты сети](evaluate-network-protection.md)
- [Включить защиту сети](enable-network-protection.md)
- [Адрес ложных срабатыва-срабатыва-](defender-endpoint-false-positives-negatives.md)
