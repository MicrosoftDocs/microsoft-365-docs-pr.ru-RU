---
title: Устранение неполадок службы Microsoft Defender для конечных точек
description: Поиск решений и обходных решений известных проблем, таких как ошибки сервера при попытке доступа к службе.
keywords: устранение неполадок Microsoft Defender для конечной точки, ошибка сервера, отказ в доступе, недействительные учетные данные, отсутствие данных, портал панели мониторинга, разрешить, просмотр событий
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 81f1b4154de25f6186679adc5b1f24f78f302415
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933761"
---
# <a name="troubleshoot-service-issues"></a>Устранение неполадок службы

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы расширенных угроз Microsoft Defender.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Ошибка сервера. Доступ отказано из-за недействительных учетных данных
Если при попытке доступа к службе вы столкнулись с ошибкой сервера, необходимо изменить параметры cookie браузера.
Настройте браузер, чтобы разрешить файлы cookie.

## <a name="elements-or-data-missing-on-the-portal"></a>Элементы или данные, отсутствующие на портале
Если в Центре безопасности Microsoft Defender отсутствуют некоторые элементы или данные, возможно, параметры прокси-сервера блокируют его.

Убедитесь, `*.securitycenter.windows.com` что он включен в список прокси-серверов.


> [!NOTE]
> При добавлении следующих конечных точек необходимо использовать протокол HTTPS.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender для службы конечных точек показывает журналы событий или ошибок в viewer событий

Обзор [событий и ошибок](event-error-codes.md) с помощью viewer событий см. в списке ID событий, которые сообщаются службой Microsoft Defender для конечных точек. В статье также содержатся действия по устранению неполадок при ошибках событий.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Служба Microsoft Defender для конечных точек не удается запустить после перезагрузки и показывает ошибку 577

Если бортовые устройства успешно завершатся, но Microsoft Defender для конечной точки не начинается после перезагрузки и показывает ошибку 577, убедитесь, что Защитник Windows не отключена политикой.

Дополнительные сведения см. в [веб-сайте Убедитесь,](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)что антивирус Microsoft Defender не отключен политикой.

## <a name="known-issues-with-regional-formats"></a>Известные проблемы с региональными форматами

**Форматы даты и времени**<br>
Известны некоторые проблемы с форматами времени и даты. 

Поддерживаются следующие форматы дат:
- MM/dd/yyyyy
- dd/MM/yyyy

В настоящее время не поддерживаются следующие форматы даты и времени:
- Формат date yyyy/MM/dd
- Формат даты dd/MM/yyy
- Формат даты с yy. Будет показываться только yyyy.
- Формат времени HH:mm:ss не поддерживается (12-часовой формат AM/PM не поддерживается). Поддерживается только 24-часовой формат.

**Использование запятой, чтобы указать тысячу**<br>
Поддержка использования запятой в качестве сепаратора в числах не поддерживается. Регионы, в которых число разделено запятой, чтобы указать тысячу, будут видеть использование точки только в качестве разделитора. Например, 15,5K отображается как 15,5K.

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Клиент Microsoft Defender для конечной точки был автоматически создан в Европе
При использовании Azure Defender для мониторинга серверов автоматически создается клиент Microsoft Defender для конечных точек. Данные Microsoft Defender для конечных точек хранятся в Европе по умолчанию.





## <a name="related-topics"></a>Похожие темы
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
- [Просмотр событий и ошибок с помощью viewer событий](event-error-codes.md)
