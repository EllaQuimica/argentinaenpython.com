# Modelos do Django

Hora de exibir dados! O Django já vem com algumas **tags de template** que são úteis pra isso.

## O que são tags de template?

Infelizmente, em HTML, não dá pra incluir código Python, porque os browsers não conseguem entender. Eles só entendem HTML. Nós sabemos que o HTML é bem estático, enquanto o Python é muito mais dinâmico.

**Tags de template Django** nos permite transformar objetos Python em código HTML, para que você possa construir sites dinâmicos mais rápido e mais fácil. Uhuu!

## Modelo de lista de post de exibição

No capitulo anterior, nós fornecemos ao nosso template uma lista de postagens e a variável <o>posts</o>. Agora vamos exibir em nosso HTML.

Pra mostrar uma variável dentro de um template do Django, nós usamos chaves duplas com o nome da variável dentro, assim:

    html
    {{ posts }}
    

Tente fazer isso no seu template `blog/templates/blog/post_list.html`. Substitua tudo desde o segundo `<div>` até o terceiro `</div>` com `{{ posts }}`. Salve o arquivo, e atualize a página para ver o resultado:

![Figura 13.1][1]

 [1]: images/step1.png

Você pode ver, tudo que temos é:

    [<Post: My second post>, <Post: My first post>]
    

Isto significa que o Django a entende como uma lista de objetos. Lembre-se de **introdução ao Python** como podemos exibir listas? Sim, com laços "for"! Em um template do Django você pode criá-los assim:

    html
    {% for post in posts %}
        {{ post }}
    {% endfor %}
    

Tente fazer isso no seu template.

![Figura 13.2][2]

 [2]: images/step2.png

Funciona! Mas nós queremos que eles sejam exibidos como os posts estáticos, como os que criamos anteriormente no capítulo de **Introdução a HTML**. Nós podemos misturar HTML com tags de template. O conteúdo da tag `body` ficará assim:

    html
    <div>
        <h1><a href="/">Django Girls Blog</a></h1>
    </div>
    
    {% for post in posts %}
        <div>
            <p>published: {{ post.published_date }}</p>
            <h1><a href="">{{ post.title }}</a></h1>
            <p>{{ post.text|linebreaks }}</p>
        </div>
    {% endfor %}
    

{% raw %}Tudo o que você colocar entre `{% for %}` e `{% endfor %}` será repetido para cada objeto na lista. Atualize a página:{% endraw %}

![Figura 13.3][3]

 [3]: images/step3.png

Você notou que dessa vez nós usamos uma notação um pouco diferente `{{ post.title }}` ou `{{ post.text }}`? Nós estamos acessando os dados em cada um dos campos que definimos no model do `Post`. Além disso, `|linebreaks` está passando o texto do post por um filtro, convertendo quebras de linha em parágrafos.

## Mais uma coisa

Seria bom ver se seu site ainda estará funcionando na internet, certo? Vamos tentar implantar a PythonAnywhere novamente. Aqui está um resumo dos passos...

*   Primeiro, envie seu código para o Github

    $ git status
    [...]
    $ git add -A .
    $ git status
    [...]
    $ git commit -m "Modifica templates para mostrar posts a partir do banco de dados."
    [...]
    $ git push
    

*   Em seguida, faça login em [PythonAnywhere][4] e vá para seu **Bash console** (ou comece um novo) e execute:

 [4]: https://www.pythonanywhere.com/consoles/

    $ cd my-first-blog
    $ git pull
    [...]
    

*   Finalmente, vá para a aba [Web app setup][5] e aperte **Reload** em seu aplicativo Web. Sua atualização deve ter aparecido!

 [5]: https://www.pythonanywhere.com/web_app_setup/

Parabéns! Agora vá em frente e tente adicionar um novo post em seu Django admin (Lembre-se de adicionar published_date!), em seguida, atualize a página para ver se o post aparece por lá.

Funciona como mágica? Estamos orgulhosos! Afaste-se do seu computador um pouco, você ganhou uma pausa. :)

![Figura 13.4][6]

 [6]: images/donut.png