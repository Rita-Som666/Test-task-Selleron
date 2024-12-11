# 1. Отсутсвует возможность регистрации
## Критичность: блокирующая
## Описание:
Невозможно начать оформление заказа без зарегистрированного профиля. При этом на открытие формы регистрации выпадает ошибка 404

## Фактическией результат
После нажатия Зарегестрироваться в разделе Мой профиль, появляется ошибка 404

## Ожидаемый результат
После нажатия Зарегистрироваться в разделе Мой профиль, открывается форма регистрации

### Шаги воспроизведения:
1. Открыть и запустить бот @SelleronOfficialBot
2. Выбрать в каталоге товар и добавить в корзину
3. Открыть корзину и нажать Перейти к оформлению
4. После появившегося предупреждения об отсутвии регистрации, закрыть корзину и открыть Мой профиль
5. Нажать Зарегистрироваться

## Скриншот

![image](https://github.com/user-attachments/assets/f03e7c8e-533b-4324-8932-1fd34e122fc1)

# 2. Некорректные цены
## Критичность: критическая
## Описание
Цены товаров в каталоге слишком высокие, абсолютно не соответсвующие товарам (если только не подразумевается магазин вещей класса люкс). Создаётся впечатление, что в цене товаров из test_task 3 лишних нуля. Так же, 
если открыть товар Dali не из test_task, видно, что цена в маркетплейсе сильно отличается от цены на фото.

## Cкриншоты

<img width="383" alt="image" src="https://github.com/user-attachments/assets/eeb26daa-3075-490d-97b4-1983b35dc7f8">

![image](https://github.com/user-attachments/assets/4c12ef1a-849d-4991-bf3e-9f86a046fea0)

# 3. Предупреждающее сообщение не исчезает после устранения причины
## Критичность: высокая
## Фактический результат: 
Предупреждение о том, что невозможно поместить в один заказ товары с разных складов остаётся даже после того, как в корзине остаётся товар только с одного склада, и даже при переходе на следующую страницу.
## Ожидаемый результат: 
Предупреждение исчезает, как только все товары в корзине с одного склада

### Шаги воспроизведения:
1. Открыть и запустить бот @SelleronOfficialBot
2. Выбрать в каталоге товары с разных складов (например футболку и кошачий корм)
3. Перейти в корзину и нажать Перейти к офрмлению
4. Удалить часть товаров, чтобы были товары с одного склада и нажать Перейти к оформлению
## Скриншоты

![image](https://github.com/user-attachments/assets/f038ee32-ecdd-4e6f-9314-7fdd66711a56)

![image](https://github.com/user-attachments/assets/c13c6c28-0f1f-46a6-be3c-f2ae783400ee)


![image](https://github.com/user-attachments/assets/e64237a2-4a09-4673-8e61-595825580a2d)

# 4. Невозможно открыть страницу продавца
## Критичность: Критическая
## Фактический результат:
При переходе по ссылке на продавца на странице товара, выдаётся ошибка 404
## Ожидаемый результат: 
При переходе по ссылке на продавца на странице товара, открывается страница с товарами соответсующего продавца

### Шаги воспроизведения:
1. Открыть и запустить бот @SelleronOfficialBot
2. Выбрать в каталоге товар
3. Нажать на ссылку на продавца внизу карточки товара
4. Перейти по ссылке, появившейся впереписке с ботом

## Скриншот:

![image](https://github.com/user-attachments/assets/ce2d6172-0f48-4f17-8c3d-a29ab44b40ec)



# Тестирование API

# 1. Добавленные через запрос API товары не появляются в каталоге
## Критичность: Высокая
## Фактический результат:
При добавлении товаров через запрос API они не появляются в каталоге в боте

## Ожидаемый результат:
При добавлении товара через запрос API, он появляется в каталоге бота и становится доступен для покупки

### Шаги воспроизведения:
1. Через Postman сделать на адрес https://selleron.ru/api/v1/vendor/create-product/?auth_key=4e9edfc6-8425-453f-9646-c6691f177424 зарос POST c телом (пример):
   ```
   { 
        "category_id": 1,
        "subcategory_id": 1,
        "storage_id": 12,
        "departure_method": "by_point",
        "remaining_quantity": 0,
        "title": "Рис",
        "description": "",
        "price": 1.0,
        "size_l": 1.0,
        "size_w": 1.0,
        "size_h": 1.0,
        "size_pack_l": 1.0,
        "size_pack_w": 1.0,
        "size_pack_h": 1.0,
        "weight": 15.0
    }
   ```
2. Запустить бот @SelleronOfficialBot в телеграмм и открыть каталог
   





