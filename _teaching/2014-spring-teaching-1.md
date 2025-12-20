---
layout: archive
title: "风景特色"
permalink: /teaching/
author_profile: true
---

<!-- 重置样式，避免和网站原有样式冲突 -->
<style>
  .game-screenshots {
    display: flex;
    flex-wrap: wrap;
    gap: 25px !important;
    justify-content: center !important;
    padding: 30px 0 !important;
    max-width: 100% !important;
    margin: 0 auto !important;
    box-sizing: border-box !important;
  }
  .game-screenshot-item {
    width: 40% !important;
    min-width: 280px !important;
    text-align: center !important;
    margin: 0 !important;
    padding: 0 !important;
  }
  .game-screenshot-img {
    width: 100% !important;
    height: auto !important;
    border-radius: 8px !important;
    box-shadow: 0 3px 10px rgba(0,0,0,0.3) !important;
    border: 2px solid #eee !important;
    display: block !important;
    margin: 0 auto !important;
  }
  .game-screenshot-text {
    margin-top: 10px !important;
    color: #333 !important;
    font-size: 14px !important;
    text-align: center !important;
  }
  .game-screenshot-desc {
    text-align: center !important;
    margin: 20px 0 !important;
    color: #555 !important;
    font-size: 16px !important;
  }
</style>

<!-- 游戏截图展示区 - 修复路径+样式冲突 -->
<div class="game-screenshots">
  <!-- 第一张截图：增加 base_path 兼容Jekyll路径 -->
  <div class="game-screenshot-item">
    <img src="{{ site.baseurl }}/assets/images/image1.png" 
         alt="游戏实机画面1" 
         class="game-screenshot-img">
    <p class="game-screenshot-text">游戏场景1</p>
  </div>

  <!-- 第二张截图 -->
  <div class="game-screenshot-item">
    <img src="{{ site.baseurl }}/assets/images/image2.png" 
         alt="游戏实机画面2" 
         class="game-screenshot-img">
    <p class="game-screenshot-text">游戏场景2</p>
  </div>

  <!-- 第三张截图 -->
  <div class="game-screenshot-item">
    <img src="{{ site.baseurl }}/assets/images/image3.png" 
         alt="游戏实机画面3" 
         class="game-screenshot-img">
    <p class="game-screenshot-text">游戏场景3</p>
  </div>

  <!-- 第四张截图 -->
  <div class="game-screenshot-item">
    <img src="{{ site.baseurl }}/assets/images/image4.png" 
         alt="游戏实机画面4" 
         class="game-screenshot-img">
    <p class="game-screenshot-text">游戏场景4</p>
  </div>
</div>

<!-- 整体说明 -->
<div class="game-screenshot-desc">
  游戏实机运行画面展示
</div>
