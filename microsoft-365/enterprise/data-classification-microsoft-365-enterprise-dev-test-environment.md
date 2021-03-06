---
title: Классификация данных для Microsoft 365 для тестовой среды предприятия
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по тестовой лаборатории для создания и использования меток хранения документов в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919192"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Классификация данных для Microsoft 365 для тестовой среды предприятия

*Это руководство по тестовой лаборатории можно использовать как для Microsoft 365, так и для Office 365 корпоративный среды тестирования.*

В этой статье описывается настройка классификации данных с помощью меток хранения в Microsoft 365 для корпоративной тестовой среды.

Классификация данных в тестовой среде включает три этапа:
- [Этап 1. Создание Microsoft 365 для корпоративной тестовой среды](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Создание меток хранения](#phase-2-create-retention-labels)
- [Этап 3. Применение меток хранения к документам](#phase-3-apply-retention-labels-to-documents)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание Microsoft 365 для корпоративной тестовой среды

Если вы просто хотите настроить метки хранения легким способом с минимальными требованиями, следуйте инструкциям в [легкой базовой конфигурации.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите настроить метки хранения в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Тестирование меток хранения не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS). Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет собой типичную организацию.

## <a name="phase-2-create-retention-labels"></a>Этап 2. Создание меток хранения

На этом этапе создайте метки хранения для различных уровней хранения для папок документов SharePoint Online:

1. Вопишитесь в [центр Microsoft 365 безопасности](https://security.microsoft.com/homepage) с учетной записью глобального администратора.
1. На **вкладке Home - Microsoft 365** безопасности браузера выберите метки **хранения**  >  **классификации.**
1. Нажмите **Создать метку**.
1. В области **Имя метки** **введите** внутреннюю публику в **Имя** метки, а затем выберите **Далее**.
1. В области **дескрипторов плана файлов** выберите **Далее**.
1. В области **параметров Метки** при необходимости установите **удержание** **в on** и выберите **Далее**.
1. В области **Обзор параметров** выберите **Создать метку**.
1. Повторите шаги 3–7 для дополнительных меток с этими именами:
  - частные
  - Конфиденциальный
  - Строго конфиденциально
1. В области **меток хранения** выберите **Метки Публикации**.
1. В **метке Выбор для публикации** выберите **метки для публикации.**
1. В области **Выберите метки** выберите **Добавить** и выбрать все четыре метки.
1. Выберите **Добавить,** а затем выберите **Готово**.
1. На **метке Выберите для публикации** области выберите **Далее**.
1. На области **Выбор расположения** выберите **Далее**.
1. На области **Имя политики** введите **организацию Пример** в **Name** и выберите **Далее**.
1. На области **Обзор параметров** выберите **Метки Публикации.**
 
Публикация меток хранения может занять несколько минут.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Этап 3. Применение меток хранения к документам

На этом этапе вы обнаружите поведение метки хранения по умолчанию для файлов в папке Документы сайта SharePoint Online и вручную измените метку хранения документа.

Сначала создайте веб-сайт SharePoint на конфиденциальном уровне:
  
1. С помощью частного экземпляра браузера вопишитесь в центр администрирования Microsoft 365 с [помощью](https://admin.microsoft.com) глобальной учетной записи администратора.
1. В списке плитки **выберите** SharePoint .
1. На **вкладке SharePoint** в браузере выберите **Создать сайт.**
1. На странице **Создать сайт** нажмите **Сайт группы**.
1. В поле **имя сайта Team** введите **SensitiveFiles**.
1. В поле **описание сайта Team** введите SharePoint для **конфиденциальных файлов.**
1. В **параметрах конфиденциальности** выберите **Private — доступ** к этому сайту могут получить только участники, а затем выберите **Далее**.
1. В Кто **вы хотите добавить?** области, выберите **Готово**.
    
Далее настройте папку Documents сайта команды SensitiveFiles для метки хранения Sensitive.
  
1. На **вкладке SensitiveFiles** браузера выберите **Документы**.
1. Выберите **значок Параметры,** а затем выберите **параметры Библиотеки.**
1. В **статье Разрешения и управление** выберите Нанесите метку на элементы в этом **списке или библиотеке.** Если этот параметр не появится, метки хранения еще не опубликованы. Попробуйте сделать этот шаг позже.
1. В **Параметры-Apply Label** выберите **Sensitive** в выпадаемом поле, а затем выберите **Сохранить**.

Затем создайте новый документ на сайте SensitiveFiles и измените метку хранения.
    
1. В папке документов выберите **документ New**  >  **Word**.
1. Введите текст в пустом документе. Подождите, пока текст будет сохранен.
1. В панели меню выберите **общие документы.**
1. Рядом с **именемDocument.docx** выберите вертикальный эллипсис, а затем выберите **Details**.
1. В правой области в разделе **Свойства** в разделе **Применить** метку хранения обратите внимание, что в документе автоматически применена метка хранения **Sensitive.**
1. Нажмите **Изменить все**.
1. В области **Document.docx** в статье **Применить** метку хранения выберите метку **Highly Confidential,** а затем выберите **Сохранить**.

## <a name="next-step"></a>Следующий этап

Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#information-protection) и возможностями защиты информации в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](/microsoft-365-enterprise/)