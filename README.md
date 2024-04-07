<h2>Описание</h2>
<p>Этот Helm-чарт предназначен для развертывания простого стека приложений, состоящего из фронтенд-приложения, бэкенд-API и базы данных PostgreSQL на кластере Kubernetes.</p>

<h2>Установка</h2>

<p>Чтобы установить этот Helm-чарт, выполните следующую команду:</p>

<pre><code>git clone https://github.com/reader2k24/K8S-HELM-LINK-SHORTENER.git</code></pre>

<h2>Настройка</h2>

<p>В таблице ниже приведены настраиваемые параметры Helm-чарта Short-Service и их значения по умолчанию.</p>

<table>
<thead>
<tr>
<th>Параметр</th>
<th>Описание</th>
<th>По умолчанию</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>app.name</code></td>
<td>Имя фронтенд-приложения</td>
<td><code>short-app</code></td>
</tr>
<tr>
<td><code>app.image</code></td>
<td>Образ Docker для фронтенд-приложения</td>
<td><code>antonlarichev/short-app</code></td>
</tr>
<tr>
<td><code>api.name</code></td>
<td>Имя бэкенд-приложения</td>
<td><code>short-api</code></td>
</tr>
<tr>
<td><code>api.image</code></td>
<td>Образ Docker для бэкенд-приложения</td>
<td><code>antonlarichev/short-api</code></td>
</tr>
<tr>
<td><code>postgres.name</code></td>
<td>Имя БД</td>
<td><code>postgres</code></td>
</tr>
<tr>
<td><code>postgres.image</code></td>
<td>Образ для БД</td>
<td><code>postgres:16.0</code></td>
</tr>
</tbody>
</table>

<h2>Секреты</h2>

<p>Этот Helm-чарт использует зашифрованные секреты, хранящиеся в <code>secrets.yml</code> для хранения конфиденциальной информации, такой как учетные данные для базы данных. Эти секреты расшифровываются во время развертывания.</p>

<h2>Ingress</h2>

<p>Ресурс Ingress, определенный в <code>templates/ingress.yml</code>, маршрутизирует трафик к фронтенд-приложению и бэкенд-API на основе указанных путей.</p>

<h2>Хранение данных</h2>

<p>Развертывание PostgreSQL использует PersistentVolumeClaim (<code>postgresql-pvc.yml</code>) для обеспечения сохранности данных.</p>

<h2>Тестирование</h2>

<p>Включен тестовый Pod (<code>api-test.yml</code>) для выполнения базовых тестов на развернутое бэкенд-API.</p>

<h2>Пример использования</h2>

<pre><code>helm install my-short-service ./short-service</code></pre>
