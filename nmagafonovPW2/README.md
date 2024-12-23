# Ответы на вопросы из дз

## 1. What issues prevent us from using storyboards in real projects?
**Answer:** Например, мы не сможем проинициализировать `ViewController` в конструкторе, так как вызовется `required init` и приложение упадет. `Storyboard` ограничен в повторном использовании UI компонентов, также имеет проблемы с управлением зависимостями и т.д.

## 2. What does the code on lines 25 and 29 do?
**Answer:**  
- **Line 25**: `title.translatesAutoresizingMaskIntoConstraints = false` указывает, что мы хотим сами задавать все ограничения для компонента, отказываясь от того, чтобы создавались автоматические дополнительные ограничения.
- **Line 29**: `view.addSubview(title)` добавляет `title` как дочерний элемент к `view`. Теперь `title` стал частью иерархии и подчиняется свойствам и ограничениям `view`, становится видимым и отображается в `view`.

## 3. What is a safe area layout guide?
**Answer:** `Safe area` — это область на экране, которая не должна быть перекрыта элементами интерфейса. При размещении элементов в пределах `safe area` можно быть уверенным, что они не окажутся под вырезом экрана, динамиками, панелью навигации и т.д. Через `view.safeAreaLayoutGuide` мы получаем доступ к `safe area` и можем позиционировать объекты от него.

## 4. What is weak self on line 23 and why is it important?
**Answer:** Слабая ссылка на `self` нужна в данном случае для того, чтобы избежать цикла ссылок и предотвратить утечку памяти. Замыкание не будет удерживать `self` в памяти, и если контроллер будет освобожден, `self` станет `nil` внутри замыкания.

## 5. What does clipsToBounds mean?
**Answer:** Гарантирует, что содержимое `view` не будет выходить за его закругленные углы.

## 6. What is the valueChanged type? What is Void and what is Double?
**Answer:** Это замыкание типа `((Double) -> Void)?`, то есть функция, которая принимает один параметр типа `Double` и ничего не возвращает. Можно использовать для того, чтобы передать значение слайдера в любое место, где это замыкание будет вызвано.
