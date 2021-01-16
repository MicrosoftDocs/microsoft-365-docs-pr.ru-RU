---
title: Вопросы и ответы по базовой мобильности и безопасности
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Вопросы и ответы о базовой мобильности и безопасности.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876880"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Вопросы и ответы по базовой мобильности и безопасности

В этой статье содержатся часто задающие вопросы об Basic Mobility and Security, функции, которая помогает управлять мобильными устройствами в Microsoft 365 и обеспечивать их безопасность. Если вы не можете найти ответ на свой вопрос, дайте нам знать, оставив комментарий на странице, чтобы мы могли добавить ваш вопрос в эту статью.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Как получить базовую мобильность и безопасность? Я не вижу его в Центре администрирования Microsoft 365

1.  Активируйте базовые функции мобильности и безопасности, переехав на страницу соответствия & безопасности [Office 365.](https://protection.office.com/)

2.  Перейдите в > управления устройствами.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Как начать управление устройствами в Basic Mobility and Security?

Для начала работы с Базовой мобильностью и безопасностью необходимо четыре этапа: 

1. Активируйте базовые функции мобильности и безопасности, переехав в Службу безопасности [и соответствия & Office 365.](https://protection.office.com/)

2. Перейдите в > управление > устройств.
    
3. Создайте политики управления устройствами и применйте их к группам пользователей, которые настроены в группах безопасности. Рекомендуем сначала развернуть политики в небольшой тестовой группе. Дополнительные сведения см. в дополнительных сведениях о создании политик безопасности [устройств в Basic Mobility and Security.](create-device-security-policies.md)

4. Пользователям, к которым применена политика, будет предложено зарегистрировать свои устройства при попытке доступа к данным Microsoft 365. Дополнительные сведения см. в записи [мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md)

Дополнительные сведения [см. в подстройки "Настройка базовой мобильности и безопасности".](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Я хочу настроить Basic Mobility and Security, но кажется, что он завис. Microsoft 365 Service Health некоторое время показывает "подготовка". Что я могу сделать?

Чтобы служба была готова, может потребоваться некоторое время. После завершения подготовки вы увидите страницу Basic Mobility and Security. If you've waited 24 hours and the status is still provisioning, please contact Support and we'll help figure out what the issue is. For support options, see [Still need help?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Что делать в случае сбой регистрации устройства?

Если у вас возникли проблемы с регистрацией устройства, сначала проверьте следующее:

- Убедитесь, что устройство еще не зарегистрировать у другого поставщика управления мобильными устройствами, например Intune.

- Убедитесь, что на устройстве установлены правильные дата и время.

- Переключение на другую сеть WIFI или сотовая сеть на устройстве.

- Для устройств с Android или iOS можно удалить и переустановить приложение "Портал компании Intune" на устройстве.
    
Если регистрация по-прежнему не работает, см. ["Устранение неполадок с базовой мобильностью и безопасностью".](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>В чем разница между Intune и Базовой мобильностью и безопасностью?

Базовая мобильность и безопасность находится в службе Intune. Это подмножество служб Intune, предоставляемых в качестве дополнительного преимущества для Microsoft 365, и встроенное облачное решение для управления устройствами в организации. Сравнение этих двух служб поможет вам решить, подходит ли вам Использование Intune или Basic Mobility and Security для Microsoft 365, см. в подстроке "Выбор между Basic Mobility Security и [Intune".](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Как политики работают для базовой мобильности и безопасности? Как их настроить? Отключить их?

После завершения начальной настройки basic Mobility and Security вы создаете политики и применяйте их к группам пользователей в Центре безопасности & соответствия требованиям. Политики требуют, чтобы пользователи политик зарегистрировали свои устройства в Basic Mobility and Security, прежде чем устройство сможет использоваться для доступа к данным Microsoft 365. Настраиваемая политика определяет параметры мобильных устройств, например, количество сбросов паролей или обязательное шифрование данных. Дополнительные сведения см. в теме "Создание политик безопасности устройств [в Basic Mobility and Security"](create-device-security-policies.md)и Центре соответствия требованиям Microsoft   [365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

Пошаговая инструкция по созданию и развертыванию политик устройств см. в этой [теме.](create-device-security-policies.md)

Если вы хотите исключить определенную группу пользователей, на которые влияют политики, можно добавить группу в группу исключений.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Можно ли переключиться с Exchange ActiveSync управления устройствами на Базовую мобильность и безопасность для Microsoft 365?

Если вы уже используете политики Exchange ActiveSync для управления мобильными устройствами, вы можете начать использовать Basic Mobility and Security, вынастроив Базовые мобильные устройства и безопасность. Дополнительные сведения см. в подстройки "Защита доступа пользователей и [устройств"](https://go.microsoft.com/fwlink/?LinkId=615145) [и "Настройка базовой мобильности и безопасности".](set-up.md)

При применении политик, созданных в Basic Mobility and Security, к группам пользователей эти политики переопретют политики почтовых ящиков Exchange ActiveSync мобильных устройств и правила доступа к устройствам, которые вы ранее создали в Центре администрирования Exchange для этих пользователей.

После регистрации устройства в basic Mobility and Security все политики почтовых ящиков Exchange ActiveSync или правила доступа к устройствам, применяемые к устройству, игнорируются.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Я настроил Basic Mobility and Security, но теперь хочу удалить его. Какие действия необходимо предпринять?

К сожалению, вы не можете просто "отопреподавить" Базовые функции мобильности и безопасности после ее настройка. Но вы можете удалить его для групп пользователей, удалите группы безопасности пользователей из созданных вами политик устройств. Кроме того, вы можете отключить ее для всех, удалив политики устройств, чтобы они не были применены и не были применены. Дополнительные сведения см. в [подзаговоре "Отключение базовой мобильности и безопасности".](turn-off.md)