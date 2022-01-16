
<blockquote>
<p dir="auto">Цель работы: Поиск и устранение XSS уязвимостей.</p>
</blockquote>
<h2 dir="auto"><a id="user-content-задание-1" class="anchor" aria-hidden="true" href="#задание-1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Задание 1</h2>
<ol dir="auto">
<li>
<p dir="auto">Список книг и авторов
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146250673-84ec30dd-8ec2-413f-821d-c114268b0464.png"><img src="https://user-images.githubusercontent.com/82168526/146250673-84ec30dd-8ec2-413f-821d-c114268b0464.png" alt="image" style="max-width: 100%;"></a></p>
</li>
<li>
<p dir="auto">Обнаружим уязвимости:</p>
</li>
</ol>
<p dir="auto">2.1. Reflected XSS</p>
<p dir="auto">При вводе кода в фильтр выполнится скрипт:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146250711-0c550137-9a09-4b69-a7e0-4dc1c3a68323.png"><img src="https://user-images.githubusercontent.com/82168526/146250711-0c550137-9a09-4b69-a7e0-4dc1c3a68323.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">2.2. Persisted (Stored) XSS</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146250754-e7447154-f5ac-410f-916b-4a4d174e01df.png"><img src="https://user-images.githubusercontent.com/82168526/146250754-e7447154-f5ac-410f-916b-4a4d174e01df.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">Браузер интерпретирует введенный html, следовательно, внедряем JS:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146250785-30cfe791-18a0-4d1d-b9ea-c2e297e01174.png"><img src="https://user-images.githubusercontent.com/82168526/146250785-30cfe791-18a0-4d1d-b9ea-c2e297e01174.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146250796-1f897a5f-c2f6-4ecd-ad97-8b3b50e98130.png"><img src="https://user-images.githubusercontent.com/82168526/146250796-1f897a5f-c2f6-4ecd-ad97-8b3b50e98130.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">2.3. Cookie Injection</p>
<p dir="auto">Текст над фильтром отображает значение текущей cookie:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251002-0dde544b-1d89-4acf-8ca8-a57014278f7b.png"><img src="https://user-images.githubusercontent.com/82168526/146251002-0dde544b-1d89-4acf-8ca8-a57014278f7b.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">И интерпретирует код:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251027-795240be-f356-4b11-b07f-1cbe28babb4f.png"><img src="https://user-images.githubusercontent.com/82168526/146251027-795240be-f356-4b11-b07f-1cbe28babb4f.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">2.4. Session hijacking</p>
<p dir="auto">Мы можем захватит сессию, похитив cookie:</p>
<p dir="auto">Reflected XSS:
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251051-6a530b65-0913-4511-8ecd-d5a3634de3df.png"><img src="https://user-images.githubusercontent.com/82168526/146251051-6a530b65-0913-4511-8ecd-d5a3634de3df.png" alt="image" style="max-width: 100%;"></a>
Persisted (Stored) XSS:
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251085-64388aeb-7fb1-452b-a1d7-f6c72549a920.png"><img src="https://user-images.githubusercontent.com/82168526/146251085-64388aeb-7fb1-452b-a1d7-f6c72549a920.png" alt="image" style="max-width: 100%;"></a>
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251100-6fc95f45-3cb2-43cd-b387-fd6ef4bd5964.png"><img src="https://user-images.githubusercontent.com/82168526/146251100-6fc95f45-3cb2-43cd-b387-fd6ef4bd5964.png" alt="image" style="max-width: 100%;"></a>
Cookie Injection:
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251120-e5db4aae-c5e3-416c-bb1d-145555386ca1.png"><img src="https://user-images.githubusercontent.com/82168526/146251120-e5db4aae-c5e3-416c-bb1d-145555386ca1.png" alt="image" style="max-width: 100%;"></a></p>
<ol start="3" dir="auto">
<li>Исправим уязвимости</li>
</ol>
<p dir="auto">3.1. Session hijacking
Для устранения уязвимости установим атрибут httpOnly:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251180-524c668e-f388-4c38-865c-8f6a925e8044.png"><img src="https://user-images.githubusercontent.com/82168526/146251180-524c668e-f388-4c38-865c-8f6a925e8044.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">Заметим, что внедренный код все еще выполняется, но у него нет доступа к cookie:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251196-8ff6ed7b-f559-496f-be3d-336ab6193a5b.png"><img src="https://user-images.githubusercontent.com/82168526/146251196-8ff6ed7b-f559-496f-be3d-336ab6193a5b.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">3.2. Persisted (Stored) XSS:
Включим экранирование в шаблонизаторе pug:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251220-969f1cba-d812-47e6-8845-ad5e6ba996fb.png"><img src="https://user-images.githubusercontent.com/82168526/146251220-969f1cba-d812-47e6-8845-ad5e6ba996fb.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">Теперь внедренный код не интерпретируется:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251281-a19bf1b3-c403-43fa-811d-43552f92f81d.png"><img src="https://user-images.githubusercontent.com/82168526/146251281-a19bf1b3-c403-43fa-811d-43552f92f81d.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">3.3. Reflected XSS &amp; Cookie Injection
Добавим HTTP-заголовок Content-Security-Policy, в котором укажем безопасный источник загрузки скриптов:</p>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251344-e52b63d6-5feb-4e5c-a8d6-4076ce7d6c2b.png"><img src="https://user-images.githubusercontent.com/82168526/146251344-e52b63d6-5feb-4e5c-a8d6-4076ce7d6c2b.png" alt="image" style="max-width: 100%;"></a></p>
<p dir="auto">Данные уязвимости больше нельзя эксплуатировать:</p>
<p dir="auto">Reflected XSS
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251362-78927821-0d98-4bde-a2b3-bfcc195db730.png"><img src="https://user-images.githubusercontent.com/82168526/146251362-78927821-0d98-4bde-a2b3-bfcc195db730.png" alt="image" style="max-width: 100%;"></a>
Cookie Injection
<a target="_blank" rel="noopener noreferrer" href="https://user-images.githubusercontent.com/82168526/146251374-7d91a958-f406-4d81-948d-7b8ef20f153b.png"><img src="https://user-images.githubusercontent.com/82168526/146251374-7d91a958-f406-4d81-948d-7b8ef20f153b.png" alt="image" style="max-width: 100%;"></a></p>
</article>
  </div>

    </div>

  </readme-toc>

  

  <details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog">
    <summary data-hotkey="l" aria-label="Jump to line"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast linejump" aria-label="Jump to line">
      <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="js-jump-to-line-form Box-body d-flex" action="" accept-charset="UTF-8" method="get">
        <input class="form-control flex-auto mr-3 linejump-input js-jump-to-line-field" type="text" placeholder="Jump to line&hellip;" aria-label="Jump to line" autofocus>
        <button data-close-dialog="" type="submit" data-view-component="true" class="btn">  Go
</button>
</form>    </details-dialog>
  </details>
  
  <div class="Popover-message Popover-message--large Popover-message--top-left TagsearchPopover mt-1 mb-4 mx-auto Box color-shadow-large">
    <div class="TagsearchPopover-content js-tagsearch-popover-content overflow-auto" style="will-change:transform;">
    </div>
