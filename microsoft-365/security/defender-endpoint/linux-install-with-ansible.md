---
title: Развертывание Microsoft Defender для конечной точки на Linux с Ansible
ms.reviewer: ''
description: Описывает, как развернуть Microsoft Defender для конечной точки на Linux с помощью Ansible.
keywords: Microsoft, защитник, Microsoft Defender для Конечной точки, Linux, установка, развертывание, удаление, марионетка, аноскоп, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572733"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Развертывание Microsoft Defender для конечной точки на Linux с Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender for Endpoint? [Подпишитесь на бесплатную пробную версию.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этой статье описывается, как развернуть Defender for Endpoint на Linux с помощью Ansible. Успешное развертывание требует выполнения всех следующих задач:

- [Скачать бортовой пакет](#download-the-onboarding-package)
- [Создание файлов Ansible YAML](#create-ansible-yaml-files)
- [Развертывание](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Предпосылки и системные требования

Перед началом работы с основным [защитником конечной точки на странице Linux](microsoft-defender-endpoint-linux.md) можно получить описание предпосылок и системных требований к текущей версии программного обеспечения.

Кроме того, для развертывания Ansible необходимо ознакомиться с задачами управления Ansible, настроить Ansible и знать, как развертывать игровые игры и задачи. Ansible имеет много способов для выполнения той же задачи. Эти инструкции предполагают наличие поддерживаемых модулей Ansible, таких как *apt* *и unarchive* для развертывания пакета. Организация может использовать другой рабочий процесс. Для получения [подробной информации обратитесь к документации Ansible.](https://docs.ansible.com/)

- Ansible должен быть установлен по крайней мере на одном компьютере (Ansible называет это узел управления).
- SSH должен быть настроен для учетной записи администратора между узлом управления и всеми управляемыми узлами (устройства, на которых будет установлен Defender for Endpoint), и рекомендуется настроить его с помощью общедоступной проверки подлинности ключей.
- Следующее программное обеспечение должно быть установлено на всех управляемых узлах:
  - локон
  - питон-apt

- Все управляемые узлы должны быть перечислены в следующем формате в соответствующем `/etc/ansible/hosts` файле:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Пинг-тест:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Скачать бортовой пакет

Загрузите бортовой пакет из Центр безопасности в Microsoft Defender:

1. В Центр безопасности в Microsoft Defender, перейдите **на Параметры > управления устройствами > борту**.
2. В первом меню для высадки выберите **Linux Server в** качестве операционной системы. Во втором меню для высадки выберите **предпочтительный инструмент управления конфигурацией Linux** в качестве метода развертывания.
3. Выберите **Скачать бортовой пакет**. Сохраните файл в WindowsDefenderATPOnboardingPackage.zip.

    ![Центр безопасности в Microsoft Defender скриншот](images/atp-portal-onboarding-linux-2.png)

4. Из подсказки команды убедитесь, что у вас есть файл. Извлекайте содержимое архива:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Создание файлов Ansible YAML

Создайте подзапись или файлы ролевых игр, которые вносят свой вклад в воспроизведение или задачу.

- Создайте бортовое `onboarding_setup.yml` задание:

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Добавьте репозиторий Defender for Endpoint и `add_apt_repo.yml` ключ:

    Защитник для Конечной точки на Linux может быть развернут из одного из следующих каналов (обозначенных ниже *как «канал»):* *инсайдеры-быстрые,* *инсайдеры-медленные,* *или prod*. Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.

    Выбор канала определяет тип и частоту обновлений, которые предлагаются вашему устройству. Устройства в *инсайдеры-быстрые* являются первыми, чтобы получить обновления и новые функции, а затем *инсайдеры медленно* и, наконец, *prod*.

    Для того, чтобы просмотреть новые функции и обеспечить раннюю обратную связь, рекомендуется настроить некоторые устройства на предприятии, чтобы использовать либо *инсайдеров быстро* *или инсайдеров медленно*.

    > [!WARNING]
    > Переключение канала после первоначальной установки требует переустановки продукта. Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство, чтобы использовать новый канал, и следуйте шагам в этом документе, чтобы установить пакет из нового местоположения.

    Обратите внимание на дистрибутив и версию и определите ближайшую запись для него под `https://packages.microsoft.com/config/` .

    В следующих командах *замените «дистро»* *и «версию»* информацией, которую вы определили.

    > [!NOTE]
    > В случае Oracle Linux *замените «дистрибутив»* на «rhel».

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Создайте Ansible и удалите файлы YAML.

    - Для дистрибутивов на основе apt используйте следующий файл YAML:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - Для дистрибутивов на основе dnf используйте следующий файл YAML:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Развертывание

Теперь запустите файлы задач под `/etc/ansible/playbooks/` соответствующим каталогом.

- установка:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Когда продукт запускается в первый раз, он загружает последние определения противомамальных программ. В зависимости от подключения к Интернету это может занять до нескольких минут.

- Проверка/конфигурация:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Удаление:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Проблемы с установкой журнала

Дополнительные [сведения о том,](linux-resources.md#log-installation-issues) как найти автоматически генерируемый журнал, созданный установщиком при ошибке, можно найти в журнале log.

## <a name="operating-system-upgrades"></a>Модернизация операционной системы

При обновлении операционной системы до новой основной версии, вы должны сначала удалить Защитник для конечной точки на Linux, установить обновление, и, наконец, перенастроить Защитник для конечной точки на Linux на вашем устройстве.

## <a name="references"></a>Ссылки

- [Добавление или удаление репозиториев YUM](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Управление пакетами с менеджером пакета dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Добавление и удаление репозиториев APT](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Управление apt-пакетами](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>См. также
- [Исследование проблем работоспособности агента](health-status.md)
