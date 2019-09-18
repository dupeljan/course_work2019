# course_work2019
Курсовая работа, написанная в tex, [PDF версия](https://github.com/dupeljan/course_work2019/raw/master/main.pdf). Можно использовать в качастве шаблона для нормоконроля

# Зачем мне использовать tex вместо ворда?
1) Автоматическое !!форматирвование!! текста по шаблону
2) Автоматическая генерация содержания
3) Поддержание ссылочной целостности. Например номер изображения в текте не указывается. При создании картинки ей присваивается `\label{reference}`, и XeTex автоматически вставляет номер картинки в текст по команде `\ref{reference}`
4) Простота редактирования математических формул
5) Мощный функционал, обширное комьюнити
# Как привести свою курсовую работу к нормальному виду, используя этот шаблон?
1) Установить [XelaTex](http://www.texts.io/download/)
2) Установить [TexMaker](http://www.xm1math.net/texmaker/download.html)
3) Скачать и открыть TexMakerом файл [main.tex](https://github.com/dupeljan/course_work2019/blob/master/main.tex)
4) Вставить свой текст, таблицы и картинки в шаблон
5) Сгенерировать pdf используя сборщик XeLaTex (Выбрать в списке перед стрелочкой генерации не LaTex, а XeLaTex)
# Как ставить свой текст, таблицы и картинки в шаблон?
Тех файл состоит из преамбулы, в которой хранится форматирование текста и самого текста
```
\documentclass[...]{...}
Преамбула
\begin{document}
Текст
\end{document}
```
В преамбуле хранятся команды форматирования. Их трогать не надо, все настроенно в соответсвии с норомоконтролем КубГу(2019).

# Часто используемые команды:
Новый абзац (пустая строка между абзацами)
```
Текст абзаца.

Текст абзаца.
```
Создать содержание
```
\tableofcontents
```
Добавить в содержание главу без номера, например введение
```
\begin{center}
\bfseries Введение
\end{center}
\addcontentsline{toc}{chapter}{Введение}
```
Добавить в документ и в содержание главу и подглаву (Страницы между главами разделяются автоматически)
```
\chapter{Название главы}
\section{Название подглавы}
```
Вставить математическую формулу в текст
```
Текст $формула$ еще текст
```
Вставить формулу под тектстом
```
\begin{equation}
формула
\end{equation}
```
# Картинки
Код для создания картинки с подписью
```
\begin{figure}
  \includegraphics[width=\linewidth]{boat.jpg}% Картинка занимает всю ширину текста{путь к картинке}
   % caption - подпись
  \caption{A boat.}
   % label - ссылка на картинку
  \label{fig:boat1}
\end{figure}
```
Код для создания нескольких картинок с одной подписью
```
\begin{figure}[H]
  \centering % Форматирование по центру
  \begin{subfigure}[b]{0.4\linewidth} % Подкартинка, занимает 0.4 ширины текста
    \includegraphics[width=\linewidth]{\picPath/perfect.png}%{Путь до картинки}
    \caption{ Идеальная граница}
  \end{subfigure}
  \begin{subfigure}[b]{0.4\linewidth}
    \includegraphics[width=\linewidth]{\picPath/smooth.png}
    \caption{Размытая граница}
  \end{subfigure}
  \begin{subfigure}[b]{0.4\linewidth}
    \includegraphics[width=\linewidth]{\picPath/roof.png}
    \caption{Крышевидная граница}
  \end{subfigure}
  % caption - подпись
  \caption{границы объектов: изображение, функция яркости, первая и вторая производные}
  % label - ссылка на фигуру
  \label{fig:border}
\end{figure}
```
# Таблицы
Создать квадратную таблицу - матрицу ii
```
\begin{table}[H]
% Подпись таблицы
\caption{cравнение результатов сравнения изображений по гистограмме}
% Ссылка на таблицу
\label{reference}
\begin{tabularx}{\textwidth}{|X|X|X|} % Столько X, сколько столбцов
\hline
1 1 & 1 2 & 1 3 \\ \hline
2 1 & 2 2 & 2 3 \\ \hline
3 1 & 3 2 & 3 3 \\ \hline
\end{tabularx}
```
# Сослаться на таблицу или картинку в тексте
```
Figure \ref{fig:boat1} shows a boat.
```
# Список литературы
Создать список литературы
```
\begin{thebibliography}{0}
\bibitem{ссылка на книгу} Имя, навзвание ...
%...
\bibitem{ссылка на книгу} Имя, навзвание ...
\end{thebibliography}
```
Сослаться на книжку
```
Как было показано в \cite{ссылка на книгу} , ...
```
Если вдруг что-то пойдет не так - [обращайтесь ко мне]( https://vk.com/dupeljan).Пользуйтесь документациями, информации предостаточно. Частично использовал [эту книжку](http://www.stolyarov.info/books/pdf/latex3days.pdf).
