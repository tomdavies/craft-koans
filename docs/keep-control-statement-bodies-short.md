# Keep control statement bodies short 

Long loop / conditional bodies are hard to read. It can be difficult to see where statement ends.

We can make the intent of our code clearer by abstracting the contents of the body to a partial or macro.

Avoid:

```twig
{# news/index.twig #}
{% for article in paginatedArticles %}
  <section class="flex md:flex-col space-y-4 space-x-4">
    <figure class="w-full md:w-1/2 lg:w-1/3">
      <img 
          src="{{ article.image.url }}" 
          class="w-full block"
          style="apsect-ratio: {{ article.image.width /article.image.height }}"
          alt="{{ article.image.alt }}">
      <figcaption class="text-sm">
        {{ article.image.caption }}
      </figcaption>
    </figure>
    <div class="w-full md:grow">
      <h2>{{ article.title }}</h2>
      {{ article.description }}
      <a href="{{ url(entry.url)}}" class="btn">Read more</a>
    </div>
  </section>
{% endfor %}
```

Instead

```twig
{# news/index.twig #}
{% for article in paginatedArticles %}
  {{ component('card/blog', { 
    data: { article: article },
  }) }}
{% endfor %}

{# _components/card/blog.twig #}
<section class="flex md:flex-col space-y-4 space-x-4">
  <figure class="w-full md:w-1/2 lg:w-1/3">
    <img 
        src="{{ article.image.url }}" 
        class="w-full block"
        style="apsect-ratio: {{ article.image.width /article.image.height }}"
        alt="{{ article.image.alt }}">
    <figcaption class="text-sm">
      {{ article.image.caption }}
    </figcaption>
  </figure>
  <div class="w-full md:grow">
    <h2>{{ article.title }}</h2>
    {{ article.description }}
    <a href="{{ url(entry.url)}}" class="btn">Read more</a>
  </div>
</section>
```