# -Flexbox
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.gallery-item {
  flex: 1 1 200px;
}
6. flex-grow, flex-shrink, flex-basis
flex-grow — насколько элемент может расти
flex-shrink — насколько может сжиматься
flex-basis — начальный базовый размер
7. gap — Отступы между элементами
.container {
  display: flex;
  gap: 20px;
}
Практический пример: Макет карточек
.cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: stretch;
  gap: 24px;
  padding: 32px;
  max-width: 1200px;
  margin: 0 auto;
}

.card {
  display: flex;
  flex-direction: column;
  flex: 1 1 280px;
  background: #ffffff;
  border-radius: 12px;
  padding: 24px;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
}

.card__text {
  flex-grow: 1;
  color: #555;
  margin-bottom: 16px;
}

.card__btn {
  align-self: flex-start;
  padding: 10px 20px;
  background: #4f46e5;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
