---
title: Использование политик защиты от потери данных для облачных приложений, не в корпорации Майкрософт (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать политики DLP для облачных приложений, не в корпорации Майкрософт.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649660"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Использование политик защиты от потери данных для облачных приложений, не в корпорации Майкрософт (предварительная версия)

Политики защиты от потери данных (DLP) для облачных приложений, не в корпорации Майкрософт, являются частью набора функций защиты от потери данных Microsoft 365; с помощью этих функций вы можете обнаруживть и защищать конфиденциальные элементы в службах Microsoft 365. Дополнительные сведения обо всех предложениях защиты от потери данных (Майкрософт) см. в обзоре защиты [от потери данных.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)

Политики DLP можно использовать для облачных приложений, не в корпорации Майкрософт, для отслеживания и обнаружения использования конфиденциальных элементов и их совместного использования через облачные приложения, не относящуюся к Майкрософт. Использование этих политик обеспечивает видимость и контроль, необходимые для их правильного использования и защиты, а также помогает предотвратить рискованные действия, которые могут привести к их компрометации.

## <a name="before-you-begin"></a>Прежде чем начать

### <a name="skusubscriptions-licensing"></a>Лицензирование SKU/подписки

Прежде чем приступить к использованию политик DLP в облачных приложениях, не в корпорации Майкрософт, подтвердите свою подписку [на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые надстройки. Чтобы получить доступ к этой функции и использовать ее, необходимо иметь одну из этих подписок или надстройки:

- Microsoft 365 E5
- Соответствие требованиям Microsoft 365 E5
- Безопасность Microsoft 365 E5

### <a name="prepare-your-cloud-app-security-environment"></a>Подготовка среды Cloud App Security

Политики DLP для облачных приложений, не в корпорации Майкрософт, используют возможности cloud App Security DLP. Чтобы использовать его, необходимо подготовить среду Cloud App Security. Инструкции см. в [настройках мгновенного видимости, защиты](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)и действий по управлению приложениями.

### <a name="connect-a-non-microsoft-cloud-app"></a>Подключение к облачному приложению от корпорации Майкрософт

Чтобы использовать политику DLP для определенного облачного приложения от корпорации Майкрософт, приложение должно быть подключено к Cloud App Security. Дополнительные сведения см. в указанных ниже статьях.

- [Connect Box](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Подключение Dropbox](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Подключение G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Подключение Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Подключение Cisco Webex](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

После подключения облачных приложений к Cloud App Security вы можете создать для них политики защиты от lp в Microsoft 365.

>[!NOTE]
>Кроме того, можно использовать Microsoft Cloud App Security для создания политик защиты от lp в облачных приложениях Майкрософт. Однако рекомендуется использовать Microsoft 365 для создания политик DLP в облачных приложениях Майкрософт и управления ими.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Создание политики DLP в облачном приложении от корпорации Майкрософт

Когда вы выбираете расположение для политики DLP, включаем расположение **Microsoft Cloud App Security.**

- Чтобы выбрать конкретное приложение или экземпляр, выберите **"Выбрать экземпляр".**
- Если экземпляр не выбран, политика использует все подключенные приложения в клиенте Microsoft Cloud App Security.

   ![Расположения для применения политики](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US и Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Вы можете выбрать различные действия для всех поддерживаемых облачных приложений, не в корпорации Майкрософт. Для каждого приложения существуют различные возможные действия (зависит от API облачного приложения).

![Создание правила](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

При создании правила в политике DLP можно выбрать действие для облачных приложений, не в корпорации Майкрософт. Чтобы ограничить сторонние приложения, выберите **"Ограничить сторонние приложения".**

![Ограничение сторонних приложений](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Сведения о создании и настройке политик DLP см. в подстройки "Создание тестирования [и настройка политики DLP".](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)

## <a name="see-also"></a>См. также

- [Создание тестовой и настраиваемой политики DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Начало работы со стандартной политикой защиты от потери данных](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Создание политики защиты от потери данных на основе шаблона](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
