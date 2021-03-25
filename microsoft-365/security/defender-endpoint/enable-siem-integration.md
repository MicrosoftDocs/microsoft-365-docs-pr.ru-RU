---
title: Включение интеграции SIEM в Microsoft Defender для конечной точки
description: Включение интеграции SIEM для получения обнаружения в решении по безопасности и управлению событиями (SIEM).
keywords: включить соединителем siem, siem, соединителем, сведениями о безопасности и событиями
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076245"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>Включение интеграции SIEM в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)


>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

Включение интеграции сведений о безопасности и управления событиями (SIEM), чтобы вы могли вытащить обнаружения из Центра безопасности Защитника Майкрософт. Вытяните обнаружения с помощью решения SIEM или непосредственно подключившись к API REST обнаружения.

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.
>- API оповещений Microsoft Defender для конечных точек — это последний API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения. Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)

## <a name="prerequisites"></a>Предварительные условия

- У пользователя, который активирует параметр, должны быть разрешения на создание приложения в Azure Active Directory (AAD). Это кто-то со следующими ролями: 

  - Администратор безопасности и глобальный администратор
  - Администратор облачного приложения
  - Администратор приложения
  - Владелец основного владельца службы

- Во время начальной активации отображается всплывающее экран для входа учетных данных. Убедитесь, что вы разрешаете всплывающие окантовки для этого сайта.

## <a name="enabling-siem-integration"></a>Включение интеграции SIEM 
1. В области навигации выберите **ПАРАМЕТРЫ**  >  **SIEM**.

    ![Изображение интеграции SIEM из меню Параметры1](images/enable_siem.png)

    >[!TIP]
    >Если вы столкнулись с ошибкой при попытке включить соединителем SIEM-приложение, проверьте параметры блокатора всплывающее окна в браузере. Это может быть блокировка открываемого окна при вскрывии возможности. 

2. Выберите **Включить интеграцию SIEM.** Это активирует раздел сведений о доступе к соединителем **SIEM** с предварительно заселяемыми значениями, и приложение создается под клиентом Azure Active Directory (Azure AD).

    > [!WARNING]
    >Секрет клиента отображается только один раз. Убедитесь, что вы храните его копию в безопасном месте.<br>
     

    ![Изображение интеграции SIEM из меню Параметры2](images/siem_details.png)

3. Выберите тип SIEM, который используется в организации.

   > [!NOTE]
   > Если вы выберете HP ArcSight, вам потребуется сохранить эти два файла конфигурации:<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   Если вы хотите напрямую подключиться к API REST обнаружения с помощью программного доступа, выберите **общий API.**

4. Скопируйте отдельные значения или выберите **сохранить сведения,** чтобы загрузить файл, содержащий все значения.

5. Выберите **маркеры Generate,** чтобы получить доступ и обновить маркер.
  
   > [!NOTE]
   > Необходимо создавать новый маркер обновления каждые 90 дней. 

6. Следуйте инструкциям по созданию регистрации приложений Azure AD для [Microsoft Defender для конечной](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) точки и назначьте ему правильные разрешения на чтение оповещений.

Теперь можно приступить к настройке решения SIEM или подключению к API REST обнаружения с помощью программного доступа. Вы должны использовать маркеры при настройке решения SIEM, чтобы разрешить ему получать обнаружения из Центра безопасности Защитника Майкрософт.

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>Интеграция Microsoft Defender для конечной точки с IBM QRadar 
Вы можете настроить IBM QRadar для сбора обнаружения в Microsoft Defender для конечной точки. Дополнительные сведения см. в [центре знаний IBM.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

## <a name="see-also"></a>См. также
- [Настройте HP ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек](configure-arcsight.md)
- [Microsoft Defender для полей обнаружения конечных точек](api-portal-mapping.md)
- [Pull Microsoft Defender для обнаружения конечных точек с помощью API REST](pull-alerts-using-rest-api.md)
- [Устранение неполадок в интеграции инструментов SIEM](troubleshoot-siem.md)
