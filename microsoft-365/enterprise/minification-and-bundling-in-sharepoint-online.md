---
title: Минификация и объединение в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Узнайте, как использовать методы минирования и комплектации с помощью веб-элементов для уменьшения запросов http и времени загрузки страниц в SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692995"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Минификация и объединение в SharePoint Online

В этой статье описывается использование методов минирования и комплектации с веб-сайтами для уменьшения количества запросов HTTP и сокращения времени загрузки страниц в SharePoint Online.
  
При настройке веб-сайта можно добавить на сервер большое количество дополнительных файлов для поддержки настройки. Добавление дополнительных JavaScript, CSS и изображений увеличивает количество запросов HTTP на сервер, что, в свою очередь, увеличивает время отображения веб-страницы. Если у вас есть несколько файлов одного типа, вы можете объединить эти файлы, чтобы сделать загрузку этих файлов быстрее.
  
Для файлов JavaScript и CSS можно также использовать подход под названием minification, в котором можно уменьшить общий размер файлов, удалив белое пространство и другие не нужные символы.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minification and bundling JavaScript and CSS files with Web Essentials

Сторонние программы, такие как Web Essentials, можно использовать для комплекта CSS и JavaScript-файлов.
  
> [!IMPORTANT]
> Web Essentials — это сторонний проект с открытым исходным кодом, основанный на сообществе. Программное обеспечение является расширением Visual Studio 2012 и Visual Studio 2013 и не поддерживается Корпорацией Майкрософт. Чтобы скачать web Essentials, посетите веб-сайт по [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) ссылке . 
  
Web Essentials предлагает две формы комплектов:
  
- .bundle: для файлов CSS и JavaScript
    
- .sprite: для изображений (доступны только в Visual Studio 2013)
    
Можно использовать Web Essentials, если у вас есть существующая функция с некоторыми элементами брендинга, которые ссылались на пользовательские основные страницы, такие как:
  
![Снимок экрана: элемент фирменной символики на настраиваемой эталонной странице](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Создание пакета TE000127218 и CSS в Web Essentials**
  
1. В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.
    
2. Щелкните правой кнопкой мыши выбранные файлы, а затем выберите файл пакетов **Web Essentials** \> **Create JavaScript из** контекстного меню. Пример. 
    
    ![Снимок экрана: параметры меню Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Просмотр результатов комплектовки файлов JavaScript и CSS

При создании пакета JavaScript и CSS Web Essentials создает XML-файл, называемый файлом рецептов, который идентифицирует файлы JavaScript и CSS, а также некоторые другие сведения о конфигурации: 
  
![Снимок экрана: файл инструкций JavaScript и CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Кроме того, если в рецепте комплектов установлен true флага minify, файлы уменьшаются в размерах, а также в комплекте. Это означает, что были созданы новые, заминированная версия файлов JavaScript, на которые можно ссылаться на своей странице.
  
![Снимок экрана: флаг минификации со значением true](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
При загрузке страницы с веб-сайта можно использовать средства разработчика из вашего веб-браузера, такие как Internet Explorer 11, чтобы увидеть количество отправленных на сервер запросов и время загрузки каждого файла.
  
Следующая цифра — это результат загрузки файлов JavaScript и CSS перед минификацией.
  
![Снимок экрана: скачивание 80 элементов](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
После объединяет CSS и JavaScript файлы, количество запросов сократилось до 74, и каждый файл занимает немного больше времени, чем исходные файлы, чтобы скачать по отдельности:
  
![Снимок экрана: скачивание 74 элементов](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
После комплектовки файл пакета JavaScript значительно сокращается с 815 КБ до 365 КБ:
  
![Снимок экрана: сокращение размера скачиваемых элементов](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Комплектирование изображений путем создания спрайта изображения

Подобно тому, как вы объединяете файлы JavaScript и CSS, вы можете объединить множество небольших значков и других общих изображений в большой лист спрайта, а затем использовать CSS для раскрытия отдельных изображений. Вместо загрузки каждого отдельного изображения веб-браузер пользователя загружает лист спрайта один раз, а затем засеивает его на локальном компьютере. Это повышает производительность загрузки страниц, сокращая количество скачиваемых и круглых поездок на веб-сервер.
  
 **Создание спрайта изображения в Веб-основных**
  
1. В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.
    
2. Щелкните правой кнопкой мыши выбранные файлы, а затем выберите **веб-материалы** \> **Создать спрайт** изображения из контекстного меню. Пример. 
    
    ![Снимок экрана: как создать спрайт изображения](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Выберите расположение, чтобы сохранить спрайт-файл. Файл .sprite — это XML-файл, который описывает параметры и файлы в спрайте. На следующих рисунках покажите пример PNG-файла спрайта и соответствующего XML-файла спрайта.
    
    ![Снимок экрана: файл спрайта](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Снимок экрана: XML-файл спрайта](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

