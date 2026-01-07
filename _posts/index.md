---
layout: default
title: My Library
---

# 📚 私のライブラリ

{% for post in site.posts %}
<div style="border:1px solid #ddd; padding:20px; margin-bottom:20px; border-radius:8px; background-color: #fff;">
  
  <div style="display:flex; justify-content: space-between; align-items: center; border-bottom:1px solid #eee; padding-bottom:10px; margin-bottom:10px;">
    <h2 style="margin:0; font-size:1.5em;">{{ post.title }}</h2>
    <span style="color:orange; font-weight:bold; font-size:1.2em;">★ {{ post.rating }}</span>
  </div>

  <span style="background:#eee; padding:4px 8px; border-radius:4px; font-size:0.8em; color:#555;">{{ post.category }}</span>

  <div style="margin: 15px 0; font-size: 0.9em; color: #444; line-height: 1.6;">
    <div>👤 <strong>作者/監督:</strong> {{ post.author }}</div>
    <div>🏢 <strong>出版社/配給:</strong> {{ post.publisher }}</div>
    <div style="margin-top:5px; color:#666;">
      📅 公開: {{ post.release_date }}　|　✅ 読了: {{ post.date | date: "%Y-%m-%d" }}
    </div>
  </div>

  <div style="margin-top:15px;">
    {{ post.content }}
  </div>

</div>
{% endfor %}
