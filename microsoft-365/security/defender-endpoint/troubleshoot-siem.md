---
title: Устранение неполадок с интеграцией средств SIEM в ATP Защитника Майкрософт
description: Устранение неполадок, которые могут возникнуть при использовании инструментов SIEM с atP Microsoft Defender.
keywords: устранение неполадок, siem, секрет клиента, секрет
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
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072877"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Устранение неполадок в интеграции инструментов SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Возможно, вам потребуется устранить неполадки при обнаружении обнаружения в средствах SIEM.

На этой странице подробно описаны действия по устранению проблем, с которыми вы можете столкнуться.


## <a name="learn-how-to-get-a-new-client-secret"></a>Узнайте, как получить новый секрет клиента
Если срок действия секрета клиента истекает или если вы неправильно предоставили копию при включите приложение-инструмент SIEM, вам потребуется получить новый секрет.

1. Вход на портал [управления Azure.](https://portal.azure.com)

2. Выберите **Azure Active Directory**.

3. Выберите клиента.

4. Нажмите **кнопку Регистрация приложений**. Затем в списке приложений выберите приложение.

5. Выберите **раздел Клавиши,** затем укажите описание ключа и укажите длительность действия ключа.

6. Нажмите кнопку **Сохранить**. Отображается ключевое значение.

7. Скопируйте значение и сохраните его в безопасном месте.


## <a name="error-when-getting-a-refresh-access-token"></a>Ошибка при получении маркера доступа к обновлению
Если вы столкнулись с ошибкой при попытке получить маркер обновления при использовании API-API или средств SIEM-аналитики, необходимо добавить URL-адрес ответа для соответствующего приложения в Azure Active Directory.

1. Вход на портал [управления Azure.](https://ms.portal.azure.com)

2. Выберите **Azure Active Directory**.

3. Выберите клиента.

4. Нажмите **кнопку Регистрация приложений**. Затем в списке приложений выберите приложение.

5. Добавьте следующий URL-адрес:
   - Для Европейского Союза: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Для Соединенного Королевства: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Для Соединенных Штатов:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Нажмите кнопку **Сохранить**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Ошибка при включении приложения соединиттеля SIEM
Если вы столкнулись с ошибкой при попытке включить соединителем SIEM-приложение, проверьте параметры блокатора всплывающее окна в браузере. Это может быть блокировка открываемого окна при вскрывии возможности.




>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Статьи по теме
- [Включение интеграции SIEM в Microsoft Defender для конечной точки](enable-siem-integration.md)
- [Настройте ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек](configure-arcsight.md)
- [Притягивать обнаружения к средствам SIEM](configure-siem.md)
- [Microsoft Defender для полей обнаружения конечных точек](api-portal-mapping.md)
- [Pull Microsoft Defender для обнаружения конечных точек с помощью API REST](pull-alerts-using-rest-api.md)
