---
title: Вопросы базовой мобильности и безопасности, часто задаваемые (часто задаваемые вопросы)
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
description: Часто задамые вопросы о базовой мобильности и безопасности.
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023897"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Вопросы базовой мобильности и безопасности, часто задаваемые (часто задаваемые вопросы)

В этой статье часто задаются вопросы о базовой мобильности и безопасности, функции, которая помогает управлять и обеспечивать безопасность мобильных устройств в Microsoft 365. Если вы не можете найти ответ на ваш вопрос, дайте нам знать, оставив комментарий на странице, чтобы мы могли рассмотреть возможность добавления вашего вопроса в эту статью.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Как получить базовую мобильность и безопасность? Я не вижу его в центре администрирования Microsoft 365

1.  Активируйте базовую мобильность и безопасность, переехав на страницу [Безопасности Office 365 & соответствия](https://protection.office.com/) требованиям.

2.  Перейдите к управлению > потери данных.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Как начать работу с управлением устройствами в Basic Mobility and Security?

Существует четыре шага к началу работы с basic Mobility and Security: 

1. Активируйте базовую мобильность и безопасность, переехав в [службу безопасности Office 365 & соответствие](https://protection.office.com/)требованиям.

2. Перейдите к политике > управления устройствами > данных.
    
3. Создайте политики управления устройствами и применяйте их к группам пользователей, которые настроены в группах безопасности. Рекомендуется начать с развертывания политик в небольшой тестовой группе. Дополнительные сведения см. в [сайте Create device security policies in Basic Mobility and Security.](create-device-security-policies.md)

4. Пользователям, у которых к ним применена политика, предложено зарегистрироваться на своих устройствах при попытке получить доступ к данным Microsoft 365. Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md)

Дополнительные сведения см. в [материале Настройка базовой мобильности и безопасности.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Я пытаюсь настроить основные мобильности и безопасности, но кажется, застрял. Microsoft 365 Service Health уже некоторое время демонстрирует "подготовка". Что я могу сделать?

Может потребоваться некоторое время, чтобы получить службу готовой для вас. После завершения подготовки вы увидите страницу Basic Mobility and Security. Если вы прождали 24 часа и состояние еще находится в состоянии подготовка, обратитесь в службу поддержки, и мы поможем выяснить, в чем проблема.

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Что делать в случае сбой регистрации устройства?

Если у вас возникли проблемы с регистрацией устройства, сначала проверьте следующее:

- Убедитесь, что устройство еще не зарегистрировано с другим поставщиком управления мобильными устройствами, например Intune.

- Убедитесь, что устройство настроено на правильную дату и время.

- Переключение на другую WIFI или клеточную сеть на устройстве.

- Для устройств с Android или iOS удалить и переустановить приложение Портал компании Intune на устройстве.
    
Если регистрация по-прежнему не работает, см. в записи [Устранение неполадок с базовой мобильностью и безопасностью.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>В чем разница между Intune и Basic Mobility and Security?

Базовая мобильность и безопасность организована службой Intune. Это подмножество служб Intune, предоставляемых в качестве дополнительного преимущества для Microsoft 365, и встроенное облачное решение для управления устройствами в организации. Для сравнения двух служб, которые помогут вам решить, является ли использование Intune или Basic Mobility and Security для Microsoft 365 наиболее подходящим для вас, см. в справке Выберите между Basic Mobility Security и [Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Как работают политики для базовой мобильности и безопасности? Как настроить их? Отключить их?

После завершения начальной настройки базовой мобильности и безопасности вы создаете политики и применяйте их к группам пользователей в Центре & соответствия требованиям. Политики требуют, чтобы пользователи политик зарегистрировались на своих устройствах в Basic Mobility and Security, прежде чем устройство можно было использовать для доступа к данным Microsoft 365. Политики, которые вы настраивали, определяют параметры для мобильных устройств, например, как часто необходимо сбросить пароли или требуется ли шифрование данных. Дополнительные сведения см. в [веб-сайте Create device security policies in Basic Mobility and Security](create-device-security-policies.md)and Microsoft   [365 compliance center.](../../compliance/microsoft-365-compliance-center.md)

Пошаговая инструкция по созданию и развертыванию политик устройств см. в инструкции [Create device security policies in Basic Mobility and Security.](create-device-security-policies.md)

Если вы хотите исключить из политики определенную группу пользователей, вы можете добавить группу в группу исключения.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Могу ли я перейти Exchange ActiveSync управления устройствами на Basic Mobility and Security для Microsoft 365?

Если вы уже используете Exchange ActiveSync для управления мобильными устройствами, вы можете начать использовать Basic Mobility and Security, следуя шагам по настройкам Basic Mobility and Security. Дополнительные сведения см. в [дополнительных сведениях" Protect user and device access](../../compliance/protect-access-to-data-and-services.md) and Set up Basic Mobility and [Security.](set-up.md)

При применении политик, созданных в Basic Mobility and Security к группам пользователей, эти политики переопределяют политики Exchange ActiveSync почтовых ящиков мобильных устройств и правила доступа к устройствам, созданные ранее в центре администрирования Exchange для этих пользователей.

После регистрации устройства в Basic Mobility and Security любая политика Exchange ActiveSync почтового ящика мобильных устройств или правило доступа к устройству игнорируются.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Я установил базовую мобильность и безопасность, но теперь я хочу удалить его. Какие действия?

К сожалению, нельзя просто "отсутвить" базовую мобильность и безопасность после ее настройка. Но вы можете удалить его для групп пользователей, удалив группы безопасности пользователей из созданных политик устройства. Или вы можете отключить его для всех, удалив политики устройств, чтобы они не были на месте и не соблюдались. Дополнительные сведения см. в [дополнительных сведениях о том, как отключить базовую мобильность и безопасность.](turn-off.md)