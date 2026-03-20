# Ansible Role: LightHouse

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-lighthouse--role-blue.svg)](https://galaxy.ansible.com/yourusername/lighthouse-role)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

Устанавливает и настраивает LightHouse — веб-интерфейс для управления и мониторинга ClickHouse от VKCOM.

## Требования

- Ansible 2.9 или выше
- Поддерживаемые ОС:
  - Ubuntu 20.04 (Focal), 22.04 (Jammy)
  - Debian 11 (Bullseye), 12 (Bookworm)
- Доступ в интернет для клонирования репозитория LightHouse
- Установленный и настроенный ClickHouse (на этом или удаленном сервере)
- Nginx (устанавливается автоматически)

## Переменные

### Основные переменные

| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| `lighthouse_version` | Версия/ветка LightHouse | `master` |
| `lighthouse_user` | Пользователь для файлов | `lighthouse` |
| `lighthouse_group` | Группа для файлов | `lighthouse` |
| `lighthouse_create_user` | Создавать ли пользователя | `true` |
| `lighthouse_create_group` | Создавать ли группу | `true` |
| `lighthouse_install_dir` | Директория установки | `/opt/lighthouse` |

### Настройки веб-сервера

| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| `lighthouse_port` | Порт для веб-интерфейса | `8080` |
| `lighthouse_server_name` | Server name для Nginx | `_` |
| `lighthouse_nginx_enable` | Настроить Nginx автоматически | `true` |
| `lighthouse_remove_default_nginx_site` | Удалить дефолтный сайт Nginx | `true` |
| `lighthouse_nginx_user` | Пользователь Nginx | `www-data` |

### Подключение к ClickHouse

| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| `lighthouse_clickhouse_host` | Хост ClickHouse | `localhost` |
| `lighthouse_clickhouse_port` | HTTP порт ClickHouse | `8123` |
| `lighthouse_clickhouse_user` | Пользователь ClickHouse | `default` |
| `lighthouse_clickhouse_password` | Пароль ClickHouse | `""` |

## Зависимости

Нет явных зависимостей от других Ansible ролей.

## Примеры использования

### Базовая установка на localhost

```yaml
- hosts: lighthouse
  roles:
    - role: ansible-lighthouse-role# DevOps_Netology_Homework_08-ansible-04_role-ansible-lighthouse-role
