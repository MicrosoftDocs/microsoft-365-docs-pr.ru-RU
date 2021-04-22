---
title: Регистрация Microsoft Defender для конечной точки на устройствах macOS в Jamf Pro
description: Регистрация Microsoft Defender для конечной точки на устройствах macOS в Jamf Pro
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933101"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Регистрация Microsoft Defender для конечной точки на устройствах macOS в Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Регистрация устройств macOS

Существует несколько методов регистрации в JamF.

В этой статье вы сможете использовать два метода:

- [Метод 1. Приглашения на регистрацию](#enrollment-method-1-enrollment-invitations)
- [Метод 2. Предварительная регистрация](#enrollment-method-2-prestage-enrollments)

Полный список см. в [списке О регистрации на компьютере.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)


## <a name="enrollment-method-1-enrollment-invitations"></a>Метод регистрации 1. Приглашения на регистрацию

1. В панели мониторинга Jamf Pro перейдите к **приглашениям для регистрации.**

    ![Изображение параметров конфигурации1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Выберите **+ Новый**.

    ![Крупный план описания логотипа, созданного автоматически](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. В **указать получателей для** приглашения > **по** адресам электронной почты введите адрес электронной почты (es) получателей.

    ![Изображение параметров конфигурации2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Изображение параметров конфигурации3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Например: janedoe@contoso.com

    ![Изображение параметров конфигурации4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Настройка сообщения для приглашения.

    ![Изображение параметров конфигурации5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Изображение параметров конфигурации6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Изображение параметров конфигурации7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Изображение параметров конфигурации8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Метод регистрации 2. Предварительная регистрация

1. В панели мониторинга Jamf Pro перейдите к **предварительной регистрации.**

    ![Изображение параметров конфигурации9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Следуйте инструкциям в [записях предварительного выполнения](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)компьютера.

## <a name="enroll-macos-device"></a>Регистрация устройства macOS

1. Выберите **Продолжить** и установить сертификат ЦС из окна **"Параметры системы".**

    ![Изображение регистрации Jamf Pro1](images/jamfpro-ca-certificate.png)

2. После установки сертификата CA вернись в окно браузера и выберите **Продолжить** и установить профиль MDM. 

    ![Изображение регистрации Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. Выберите **Разрешить** скачивание из JAMF.

    ![Изображение регистрации Jamf Pro3](images/jamfpro-download.png)

4. Выберите **Продолжить** работу с установкой профиля MDM. 

    ![Изображение jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. Выберите **Продолжить** установку профиля MDM.

    ![Изображение jamf Pro enrollment5](images/jamfpro-mdm-unverified.png)

6. Выберите **Продолжить**  для завершения конфигурации. 

    ![Изображение jamf Pro enrollment6](images/jamfpro-mdm-profile.png)
