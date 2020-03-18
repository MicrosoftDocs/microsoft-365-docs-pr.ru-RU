---
title: Использование бесплатной подписки на Azure Active Directory в Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Сведения о том, как получать доступ к Azure Active Directory в составе платной подписки организации на Office 365.
ms.openlocfilehash: fb1e2586c0b21c72084d7120b8735fccccd1a004
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710498"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a>Использование бесплатной подписки на Azure Active Directory в Office 365

Если у вашей организации есть платная подписка на Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility + Security E3 или другие службы Майкрософт, у вас есть бесплатная подписка на Microsoft Azure Active Directory. Вы и другие администраторы можете использовать Azure AD для создания учетных записей групп и пользователей, а также для управления ими. Для работы с Azure AD нужно просто войти на портал Azure, используя учетную запись Office 365.

## <a name="before-you-begin"></a>Перед началом работы

Используйте частный сеанс просмотра (не обычный сеанс) для доступа к порталу Azure (на шаге 1 ниже), поскольку это предотвращает передачу учетных данных, с которыми вы вошли в систему, в Azure. Чтобы открыть сеанс приватного просмотра:

- В Microsoft Edge (устаревшая версия), Internet Explorer или Mozilla FireFox нажмите клавиши `CTRL+SHIFT+P`.

- В Microsoft Edge (новая версия) или Google Chrome нажмите клавиши `CTRL+SHIFT+N`.

## <a name="access-azure-active-directory"></a>Доступ к Azure Active Directory

1. Войдите на сайт [portal.azure.com](https://portal.azure.com), используя рабочую или учебную учетную запись Office 365.

2. На панели навигации портала Azure выберите **Azure Active Directory**.

    ![На панели навигации портала Azure, расположенной слева, выберите пункт "Azure Active Directory".](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    Отобразится центр администрирования **Azure Active Directory**.

## <a name="more-information"></a>Дополнительные сведения

- Бесплатная подписка на Azure Active Directory не включает отчет о действиях входа. Чтобы записывать действия входа (это может быть полезно в случае нарушения безопасности данных), потребуется подписка на Azure Active Directory Premium. Дополнительные сведения см. в статье [Как долго в Azure AD хранятся данные?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)

- Вы также можете открыть Центр администрирования **Azure Active Directory** из Центра администрирования Microsoft 365. В левой области навигации Центра администрирования Microsoft 365 выберите **Центры администрирования** \> **Azure Active Directory**.

- Сведения об управлении пользователями и группами, а также о выполнении других задач по управлению каталогом см. в статье [Управление каталогом Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).
