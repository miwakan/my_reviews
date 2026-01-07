---
layout: default
title: My Library
---

# 📚 私のライブラリ

{% for post in site.posts %}
<div style="border:1px solid #ddd; padding:20px; margin-bottom:20px; border-radius:8px; background-color: #fff;">
  
  <div style="display:flex; justify-content: space-between; align-items: center; border-bottom:1px solid #eee; padding-bottom:10px; margin-bottom:10px;">
    <h2 style="margin:0; font-size:1.5em;">
      {{ post.title }}
      {% if post.category == "Music" and post.music_type %}
        <span style="font-size:0.6em; color:#888; font-weight:normal;">({{ post.music_type }})</span>
      {% endif %}
    </h2>
    <span style="color:orange; font-weight:bold; font-size:1.2em;">★ {{ post.rating }}</span>
  </div>

  <span style="background:#eee; padding:4px 8px; border-radius:4px; font-size:0.8em; color:#555;">
    {{ post.category }}
  </span>

  <div style="margin: 15px 0; font-size: 0.9em; color: #444; line-height: 1.6;">
    
    {% if post.author %}
    <div>
      {% if post.category == "Movie" %}
        🎬 <strong>監督:</strong>
      {% elsif post.category == "Book" %}
        🖋 <strong>著者:</strong>
      {% elsif post.category == "Music" %}
        🎤 <strong>アーティスト:</strong>
      {% else %}
        👤 <strong>作者:</strong>
      {% endif %}
      {{ post.author }}
    </div>
    {% endif %}

    {% if post.publisher %}
    <div>
      {% if post.category == "Movie" %}
        🏢 <strong>配給:</strong>
      {% elsif post.category == "Book" %}
        🏢 <strong>出版社:</strong>
      {% elsif post.category == "Music" %}
        💿 <strong>レーベル:</strong>
      {% else %}
        🏢 <strong>発行:</strong>
      {% endif %}
      {{ post.publisher }}
    </div>
    {% endif %}

    <div style="margin-top:5px; color:#666;">
      {% if post.release_date %}
        📅 公開/発売: {{ post.release_date }}
      {% endif %}

      {% if post.release_date and post.date %}
        　|　
      {% endif %}

      {% if post.date %}
        ✅ 完了日: {{ post.date | date: "%Y-%m-%d" }}
      {% endif %}
    </div>

  </div>

  <div style="margin-top:15px;">
    {{ post.content }}
  </div>

</div>
{% endfor %}
