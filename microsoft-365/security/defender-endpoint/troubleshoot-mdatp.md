---
title: Устранение неполадок в Microsoft Defender для проблем службы конечных точек
description: Поиск решений и работа с известными вопросами, такими как ошибки сервера при попытке получить доступ к службе.
keywords: устранение неполадок защитника Майкрософт для конечной точки, устранение неполадок в Windows ATP, ошибка сервера, отказ в доступе, недействительные учетные данные, отсутствие данных, портал мониторинга, разрешить, просмотр событий
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
ms.openlocfilehash: bd211a56ee9ed6aa871c8d55149247a4755bc863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072902"
---
# <a name="troubleshoot-service-issues"></a>Проблемы службы устранения неполадок

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы расширенных угроз Microsoft Defender.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Ошибка сервера. Доступ отказано из-за недействительных учетных данных
Если при попытке доступа к службе вы столкнулись с ошибкой сервера, необходимо изменить параметры cookie браузера.
Настройте браузер, чтобы разрешить файлы cookie.

## <a name="elements-or-data-missing-on-the-portal"></a>Элементы или данные, отсутствующие на портале
Если некоторые элементы пользовательского интерфейса или данные отсутствуют в Центре безопасности Microsoft Defender, возможно, параметры прокси-сервера блокируют его.

Убедитесь, `*.securitycenter.windows.com` что этот список включен в список прокси-серверов.


> [!NOTE]
> При добавлении следующих конечных точек необходимо использовать протокол HTTPS.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender для службы конечных точек показывает журналы событий или ошибок в viewer событий

В разделе Обзор событий и ошибок с помощью [viewer](event-error-codes.md) событий см. список ID событий, которые сообщаются службой Microsoft Defender для конечных точек. В этой теме также содержатся действия по устранению неполадок при ошибках событий.

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
При использовании Центра безопасности Azure для мониторинга серверов автоматически создается клиент Microsoft Defender для конечных точек. Данные Microsoft Defender для конечных точек хранятся в Европе по умолчанию.





## <a name="related-topics"></a>Статьи по теме
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
- [Просмотр событий и ошибок с помощью viewer событий](event-error-codes.md)
