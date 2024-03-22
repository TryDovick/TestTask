
<template>
  <div class="content">
    <div class="content-container">
      <div class="content-container__title">
        <h1 class="title">
          Список задач (Web)
        </h1>
        
      </div>
      <div class="sidebar">  
        <div class="sidebar-container">
        
          <h1>СОРТИРОВКА</h1>
          <ul class="checkboxes1">
            <li><input checked class="sort-container__checkbox-new" name="radio" type="radio" ><p>Новые</p></li>
            <li><input class="sort-container__checkbox-old" name="radio" type="radio" ><p>Старые</p></li>
          </ul>
         
        </div>
        <div class="btn-add-task">
          <button type="button"><p>Добавить задачу</p></button>
        </div>
        <div class="priority-mark-container">
          <h1 class="priority-mark__title-Priority">Приоритет</h1>
          <ul class="checkboxes2">
            <li><input class="priority-container-mark__checkbox-low" name="checkbox" type="checkbox" ><p>Low</p></li>
            <li><input class="priority-container-mark__checkbox-normal" name="checkbox" type="checkbox"><p>Normal</p></li>
            <li><input class="priority-container-mark__checkbox-high" name="checkbox" type="checkbox" ><p>High</p></li>

            <h1 class="priority-mark__title-Mark">Отметка</h1>

            <li><input class="priority-container-mark__checkbox-Research" name="checkbox" type="checkbox" ><p>Research</p></li>
            <li><input class="priority-container-mark__checkbox-Disign" name="checkbox" type="checkbox"><p>Disign</p></li>
            <li><input class="priority-container-mark__checkbox-Development" name="checkbox" type="checkbox" ><p>Development</p></li>

          </ul>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script >
const addTaskButton = document.querySelector('.btn-add-task button');

addTaskButton.addEventListener('click', () => {
  // Создать карточку задачи
  const card = document.createElement('div');
  card.classList.add('card');

  // Создать заголовок карточки
  const cardTitle = document.createElement('h1');
  cardTitle.classList.add('card-title');
  cardTitle.textContent = 'Новая задача';

  // Создать список с информацией о задаче
  const cardInfoList = document.createElement('ul');

  // Создать элементы списка с информацией о дате создания, приоритете и отметках
  const cardInfoCreatedDate = document.createElement('li');
  cardInfoCreatedDate.textContent = 'Создано: только что';

  const cardInfoPriority = document.createElement('li');
  cardInfoPriority.textContent = 'Приоритет: normal';

  const cardInfoMarks = document.createElement('li');
  cardInfoMarks.textContent = 'Отметки: ';

  // Создать поле ввода для редактирования названия задачи
  const cardTitleInput = document.createElement('input');
  cardTitleInput.classList.add('card-title-input');
  cardTitleInput.type = 'text';
  cardTitleInput.value = cardTitle.textContent;

  // Создать кнопку для сохранения изменений
  const cardSaveButton = document.createElement('button');
  cardSaveButton.classList.add('card-save-button');
  cardSaveButton.textContent = 'Сохранить';

  // Добавить элементы в карточку задачи
  card.appendChild(cardTitle);
  card.appendChild(cardInfoList);
  cardInfoList.appendChild(cardInfoCreatedDate);
  cardInfoList.appendChild(cardInfoPriority);
  cardInfoList.appendChild(cardInfoMarks);
  card.appendChild(cardTitleInput);
  card.appendChild(cardSaveButton);

  // Добавить карточку задачи в контейнер карточек
  const cardContainer = document.querySelector('.card-container');
  cardContainer.appendChild(card);

  // Скрыть заголовок карточки и отобразить поле ввода для редактирования
  cardTitle.style.display = 'none';
  cardTitleInput.style.display = 'block';

  // Добавить обработчик события для кнопки сохранения изменений
  cardSaveButton.addEventListener('click', () => {
    // Обновить заголовок карточки новым значением из поля ввода
    cardTitle.textContent = cardTitleInput.value;

    // Скрыть поле ввода и отобразить заголовок карточки
    cardTitleInput.style.display = 'none';
    cardTitle.style.display = 'block';
  });
});
</script>

<style scoped>

</style>
