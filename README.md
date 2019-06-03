<h1><a id="Dynamic_AC__0"></a>Dynamic AC (β)</h1>
<p>API доступно по адресу: <a href="http://dynamicac.pythonanywhere.com/send">http://dynamicac.pythonanywhere.com/send</a></p>
<p>Запрос к API должен содержать в себе следующие данные:</p>
<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Поле</th>
<th>Описание</th>
<th>Тип данных</th>
<th>Вид передаваемых данных</th>
</tr>
</thead>
<tbody>
<tr>
<td>APIKey</td>
<td>Твой ключ API</td>
<td>str</td>
<td>API key</td>
</tr>
<tr>
<td>enc</td>
<td>Используется ли шифрование в запросе</td>
<td>str</td>
<td>yes/no</td>
</tr>
<tr>
<td>keys</td>
<td>Строка нажатых клавиш</td>
<td>str</td>
<td>ababab</td>
</tr>
<tr>
<td>time</td>
<td>Продолжительность игры</td>
<td>str</td>
<td>10m/1m/5h</td>
</tr>
<tr>
<td>dur</td>
<td>Продолжительность нажатия клавиши</td>
<td>float</td>
<td>0.1/0.5/1.5</td>
</tr>
</tbody>
</table>
<p>Пример реализации JSON запроса на Python:</p>
<pre><code class="language-python"><span class="hljs-function"><span class="hljs-keyword">def</span> <span class="hljs-title">snd</span><span class="hljs-params">()</span>:</span>
    values = {<span class="hljs-string">'APIKey'</span>:[ТВОЙ КЛЮЧ API],<span class="hljs-string">'enc'</span>:<span class="hljs-string">'yes'</span>,<span class="hljs-string">'keys'</span>:<span class="hljs-string">'adswdawdsadaw'</span>,<span class="hljs-string">'time'</span>:<span class="hljs-string">'10m'</span>,<span class="hljs-string">'dur'</span>:<span class="hljs-string">'0.1-0.2-0.1-0.2'</span>} <span class="hljs-comment"># json values</span>
    r = requests.post(<span class="hljs-string">'http://dynamicac.pythonanywhere.com/send/'</span>, json=values)
    <span class="hljs-keyword">return</span>(r.text)
</code></pre>
