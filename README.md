<h1>Guia Completo de Expressões Regulares (RegExp)</h1>

  <h2>O que é o RegExp?</h2>
  <p><strong>RegExp</strong> (abreviação de <em>Regular Expression</em>, ou <em>Expressão Regular</em>) é um <strong>objeto nativo do JavaScript</strong> usado para buscar, validar e manipular strings com base em padrões definidos.</p>

  <h2>Como usar RegExp?</h2>
  <p>Você pode usar RegExp de duas formas:</p>
  <ul>
    <li><strong>Sintaxe literal:</strong> <code>/[a-zA-Z]/</code></li>
    <li><strong>Construtor:</strong> <code>new RegExp("[a-zA-Z]")</code></li>
  </ul>

  <h2>Métodos do RegExp</h2>
  <table>
    <thead>
      <tr><th>Método</th><th>Descrição</th><th>Exemplo</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><code>.test()</code></td>
        <td>Verifica se a string bate com o padrão. Retorna <code>true</code> ou <code>false</code>.</td>
        <td><code>/\d+/.test("123") // true</code></td>
      </tr>
      <tr>
        <td><code>.exec()</code></td>
        <td>Executa uma busca e retorna um array com a correspondência ou <code>null</code>.</td>
        <td><code>/\d+/.exec("idade 27") // ["27"]</code></td>
      </tr>
    </tbody>
  </table>

  <h2>Métodos de <code>String</code> que funcionam com RegExp</h2>
  <table>
    <thead>
      <tr><th>Método</th><th>Descrição</th><th>Exemplo</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><code>.match()</code></td>
        <td>Retorna todas as correspondências com a expressão regular.</td>
        <td><code>"abc123".match(/\d+/g) // ["123"]</code></td>
      </tr>
      <tr>
        <td><code>.replace()</code></td>
        <td>Substitui partes da string com base na RegExp.</td>
        <td><code>"abc123".replace(/\d+/, "") // "abc"</code></td>
      </tr>
      <tr>
        <td><code>.search()</code></td>
        <td>Retorna o índice da primeira correspondência ou <code>-1</code>.</td>
        <td><code>"abc123".search(/\d+/) // 3</code></td>
      </tr>
      <tr>
        <td><code>.split()</code></td>
        <td>Divide a string com base em uma RegExp.</td>
        <td><code>"1,2,3".split(/,/) // ["1", "2", "3"]</code></td>
      </tr>
    </tbody>
  </table>

  <h2>Estrutura Básica</h2>
  <p><code>/expressao/modificadores</code></p>
  <ul>
    <li><strong>/ /</strong> delimitam a RegExp</li>
    <li>Dentro das barras: o <strong>padrão</strong></li>
    <li>Depois da barra: <strong>modificadores</strong> (como <code>g</code>, <code>i</code>)</li>
  </ul>

  <h2>Elementos Comuns</h2>
  <table>
    <thead>
      <tr><th>Elemento</th><th>Descrição</th><th>Exemplo</th></tr>
    </thead>
    <tbody>
      <tr><td>^</td><td>Início da string</td><td><code>/^a/</code></td></tr>
      <tr><td>$</td><td>Fim da string</td><td><code>/a$/</code></td></tr>
      <tr><td>.</td><td>Qualquer caractere (exceto nova linha)</td><td><code>/a.b/</code></td></tr>
      <tr><td>[]</td><td>Conjunto de caracteres</td><td><code>/[abc]/</code></td></tr>
      <tr><td>[^ ]</td><td>Negação (qualquer caractere que não esteja no conjunto)</td><td><code>/[^0-9]/</code></td></tr>
      <tr><td>\s</td><td>Espaço em branco</td><td><code>/\s/</code></td></tr>
      <tr><td>\S</td><td>Não-espaço</td><td><code>/\S/</code></td></tr>
      <tr><td>\d</td><td>Dígito (0-9)</td><td><code>/\d/</code></td></tr>
      <tr><td>\D</td><td>Não-dígito</td><td><code>/\D/</code></td></tr>
      <tr><td>\w</td><td>Letra, número ou sublinhado</td><td><code>/\w/</code></td></tr>
      <tr><td>\W</td><td>Qualquer coisa que não seja \w</td><td><code>/\W/</code></td></tr>
      <tr><td>+</td><td>1 ou mais</td><td><code>/a+/</code></td></tr>
      <tr><td>*</td><td>0 ou mais</td><td><code>/a*/</code></td></tr>
      <tr><td>?</td><td>0 ou 1</td><td><code>/a?/</code></td></tr>
      <tr><td>{n}</td><td>Exatamente n vezes</td><td><code>/a{3}/</code></td></tr>
      <tr><td>{n,}</td><td>No mínimo n vezes</td><td><code>/a{2,}/</code></td></tr>
      <tr><td>{n,m}</td><td>Entre n e m vezes</td><td><code>/a{2,4}/</code></td></tr>
      <tr><td>()</td><td>Agrupamento</td><td><code>/(ab)+/</code></td></tr>
      <tr><td>|</td><td>Ou</td><td><code>/a|b/</code></td></tr>
      <tr><td>\\</td><td>Escape</td><td><code>/\./</code> (ponto literal)</td></tr>
    </tbody>
  </table>

  <h2>Modificadores</h2>
  <table>
    <thead>
      <tr><th>Modificador</th><th>Significado</th></tr>
    </thead>
    <tbody>
      <tr><td>g</td><td>Global (procura todas as ocorrências)</td></tr>
      <tr><td>i</td><td>Ignora maiúsculas/minúsculas</td></tr>
      <tr><td>m</td><td>Multilinha</td></tr>
    </tbody>
  </table>

  <h2>Exemplos Completos</h2>
  <ul>
    <li><strong>Apenas letras e espaços:</strong> <code>/^[a-zA-Z\s]+$/</code></li>
    <li><strong>CPF:</strong> <code>/^\d{3}\.\d{3}\.\d{3}-\d{2}$/</code></li>
    <li><strong>Começa com abc e termina com 123:</strong> <code>/^abc.*123$/</code></li>
  </ul>

  <h2>Exemplo com JavaScript</h2>
  <pre><code>const nome = "Albéres";
const apenasLetras = /^[a-zA-Z\s]+$/;

console.log(apenasLetras.test(nome)); // true</code></pre>
