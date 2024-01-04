# aniweb-beta

Система реактивности
Геттеры, Сеттеры

Паттерн "Прокси" - перезагрузка доступа к механизму.

Использовать систему "Контроллеров" {Пример 1, Пример 2} (как в Angular) 

```JavaScript
<div ng-controller="InputController">
    <!-- "Hello World!" -->
    <input ng-bind="message"/>   
    <input ng-bind="message"/>
</div>

<script type="javascript">
  function InputController () {
      this.message = 'Hello World!';
  }
  angular.controller('InputController', InputController);
</script>
```

```JavaScript	
<script>
	var controllers = {
		InputController: {
			factory: function InputController(){
				this.message = "Hello World!";
			},
			instances: [
				{message: "Hello World"}
			]
		}
	};
</script>
```

Vue оборачивает в "Прокси"
Реакции на события действия при изменении DOM

```JavaScript
Object.keys(bindings).forEach(function (boundValue) {
    var bind = bindings[boundValue];
    
    // Прослушивание событий элементов и обновление свойства прокси
    bind.elements.forEach(function (element) {
      element.addEventListener('input', function (event) {
        proxy[bind.boundValue] = event.target.value; // Кроме того, это вызывает срабатывание сеттера прокси
      });
    })  
  });
```



Расположение папок

	-Controllers
	-Settings
		-Imports.js
	-Models
		-Endpoints.js
	-Routing
		-Rout.js
	-Storage
		-State
		-Save
	-Public
		-Main
			-Main.html
			-Main.css
		-Header
			-Header.html
			-Header.css
		-Footer
			-Footer.html
			-Footer.css


