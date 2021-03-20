---
title: Microsoft OneDrive
description: Как Microsoft Managed Desktop настраивает OneDrive для зарегистрированных устройств
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904844"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop использует [OneDrive для](/onedrive/plan-onedrive-enterprise) бизнеса в качестве облачной службы хранения для всех устройств Microsoft Managed Desktop, чтобы обеспечить максимальное состояние устройств без состояния. Пользователь сможет найти свои файлы независимо от того, на какое устройство они впишутся. Например, если вы замените устройство Microsoft Managed Desktop на новое, файлы будут автоматически синхронизироваться с новым устройством.

Мы автоматически настраиваем эти параметры по умолчанию на управляемых устройствах Майкрософт:

- OneDrive безмолвно настроена с учетной записью пользователя и автоматически вписалась (без взаимодействия с пользователем) в учетную запись пользователя, которая была использована для входов в Windows. Дополнительные сведения см. в [немого настраивать учетные записи](/onedrive/use-silent-account-configuration) пользователей - OneDrive

- Функция Files-On-Demand включена, чтобы пользователи могли получать доступ к файлам из облачного хранилища в OneDrive без необходимости использования дискового пространства. Дополнительные сведения см. в [материалах Save disk space with OneDrive Files On-Demand for Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- Функция "Перемещение известных папок" включена безмолвно для архива данных пользователей в облаке, что дает им доступ к своим файлам с любого устройства. Дополнительные сведения см. в [документе Back up your Documents, Pictures и Desktop folders with OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Пользователи не могут отключить функцию "Перемещение известных папок" или изменить расположение известных папок для обеспечения согласованного работы на устройствах Microsoft Managed Desktop.

## <a name="user-experience"></a>Взаимодействие с пользователем

Когда пользователи microsoft Managed Desktop получают новое устройство, они проходят первый запуск, вводя учетные данные Azure при настройке устройства. После завершения этого процесса они могут получить доступ к рабочему столу и получить доступ к OneDrive.

1. Система сообщает пользователям, что OneDrive был настроен и что они были автоматически подписаны в OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Чтение уведомлений, в настоящее время синхронизируемая OneDrive, и вы можете редактировать файлы в OneDrive. щелкните здесь, чтобы просмотреть файлы":::

2. Система сообщает пользователям, что для них настроено перемещение известных папок OneDrive.

:::image type="content" source="media/onedrive-folders.png" alt-text="Уведомление, прочитав ИТ-отдел, поддержало важные папки. В настоящее время папки имеются в хранилище OneDrive и доступны на других устройствах.":::

3. Чтобы предотвратить повторение значков на рабочем столе при сбросе или переостановке устройств, система автоматически удаляет значки Microsoft Edge и Microsoft Teams из синхронизации OneDrive, как показано в этом представлении в Обозревателе файлов.

:::image type="content" source="media/onedrive-teams.png" alt-text="Обозреватель файлов показывает списки Teams и Edge с очищенными флажками и чтение текста наведении, исключаемом из синхронизации.":::


## <a name="onedrive-sync-restrictions"></a>Ограничения синхронизации OneDrive

Если требуется ограничить синхронизацию OneDrive, рекомендуется управлять доступом с помощью политики условного доступа Azure Active Directory. Дополнительные сведения см. в приложении ["Включить поддержку условного доступа" в приложении синхронизации OneDrive.](/onedrive/enable-conditional-access)

Если вы не можете использовать политику условного доступа Azure AD в организации, ИТ-администратор должен следовать следующим шагам:

1. Если вы еще не знаете этого, найдите свой ID клиента, как описано в Найти свой ID клиента [Microsoft 365](/onedrive/find-your-office-365-tenant-id).
2. Ворегистрируйтесь в центр администрирования OneDrive и выберите **синхронизацию** в левой области. Выберите **разрешить синхронизацию только** на ПК, присоединившись к определенным доменам, и добавьте его в список доменов. Дополнительные сведения см. в дополнительных сведениях о том, как разрешить синхронизацию только на [компьютерах, присоединившись к определенным доменам.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Это руководство применяется только к арендаторам в Microsoft Managed Desktop. В этой статье используются другие параметры, которые не обсуждаются.