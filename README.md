Краткий отчёт по Лабораторной работе 1 (HTML + JS)
В ходе выполнения работы было разработано небольшое веб-приложение для управления списком студентов. Интерфейс создан с помощью HTML, а логика работы реализована на JavaScript. Приложение позволяет добавлять студентов, удалять их, выполнять поиск по имени и сортировать список по алфавиту.
HTML-структура
HTML-код содержит основные элементы интерфейса:
•	поле ввода имени студента;
•	кнопка «Добавить»;
•	поле для поиска;
•	кнопки «Найти» и «Сортировать»;
•	контейнер <ul> для отображения списка студентов.
Все элементы помещены в блок .card, который служит центральным визуальным контейнером.
Фрагмент HTML-кода
<div class="card">
    <h2>Список студентов</h2>

    <input type="text" id="nameInput" placeholder="Имя студента">
    <button onclick="addStudent()">Добавить</button>

    <input type="text" id="searchInput" placeholder="Поиск по имени">
    <button onclick="searchStudent()">Найти</button>

    <button onclick="sortStudents()">Сортировать по алфавиту</button>

    <ul id="studentList"></ul>
</div>
Основная часть JavaScript
JavaScript отвечает за добавление данных, их хранение и обновление интерфейса. Основная логика работы — добавление, поиск, сортировка и удаление студентов.
Фрагмент JS-кода

let students = [];

function addStudent() {
    const name = document.getElementById("nameInput").value.trim();
    if (!name) return;

    const student = { id: Date.now(), name };
    students.push(student);
    renderList();
}

function renderList() {
    const ul = document.getElementById("studentList");
    ul.innerHTML = "";
    students.forEach(s => {
        ul.innerHTML += `<li>${s.name} <span onclick="deleteStudent(${s.id})">Удалить</span></li>`;
    });
}
Результат
Полученное приложение позволяет быстро создавать список студентов, искать записи и сортировать их. HTML определяет структуру интерфейса, а JavaScript обеспечивает всю интерактивность.
Ссылка на Гит хаб
https://github.com/Loliklox0/Lab.13
