---
# 这里保留你原来的YAML配置（比如title/layout等），不要删！
title: "游戏介绍"
layout: single
permalink: /publications/game-intro/
---

<!-- 游戏介绍+角色展示+互动代码 -->
<div style="max-width: 1200px; margin: 20px auto; display: flex; gap: 40px; align-items: flex-start; flex-wrap: wrap;">
  <!-- 游戏封面/主视觉图 -->
  <div style="flex: 1; min-width: 350px;">
    <img src="https://你的游戏封面图链接.png" 
         alt="游戏封面" 
         style="width: 100%; border-radius: 12px; box-shadow: 0 5px 20px rgba(0,0,0,0.2);">
  </div>

  <!-- 右侧：游戏介绍+角色互动区 -->
  <div style="flex: 2; min-width: 400px;">
    <!-- 游戏标题+简介 -->
    <div style="background: white; padding: 30px; border-radius: 12px; box-shadow: 0 3px 15px rgba(0,0,0,0.1); margin-bottom: 25px;">
      <h1>游戏名称</h1>
      <p style="font-size: 16px; color: #555; line-height: 1.6;">
        游戏简介：这里写你的游戏核心玩法、世界观、特色等内容，比如“这是一款二次元冒险RPG，玩家将跟随主角探索奇幻世界，解开隐藏的秘密...”
      </p>
    </div>

    <!-- 角色展示+提问互动区 -->
    <div style="background: white; padding: 30px; border-radius: 12px; box-shadow: 0 3px 15px rgba(0,0,0,0.1);">
      <h2>核心角色</h2>
      <!-- 角色卡片 -->
      <div style="display: flex; gap: 20px; align-items: center; margin: 20px 0;">
        <!-- 角色立绘 -->
        <img src="https://你的角色立绘链接.png" 
             alt="核心角色" 
             style="width: 150px; border-radius: 10px; box-shadow: 0 3px 10px rgba(0,0,0,0.15);">
        <!-- 角色信息 -->
        <div>
          <h3>角色名称</h3>
          <p>定位：主角/辅助/输出</p>
          <p>背景：角色在游戏中的故事...</p>
        </div>
      </div>

      <!-- 提问气泡按钮 -->
      <button id="gameQuestionBtn" 
              style="background: #4a90e2; color: white; border: none; border-radius: 50px; padding: 12px 25px; cursor: pointer; font-size: 15px; box-shadow: 0 2px 10px rgba(74,144,226,0.3); margin-top: 10px;">
        对游戏/角色提问💬
      </button>

      <!-- 提问输入框（默认隐藏） -->
      <div id="gameQuestionBox" style="display: none; margin-top: 15px; padding: 20px; background: #f8f9fa; border-radius: 8px;">
        <input type="text" id="gameQuestionInput" placeholder="输入你的问题（比如‘游戏什么时候上线？’）..." style="width: 85%; padding: 12px; border: 1px solid #ddd; border-radius: 6px; font-size: 15px;">
        <button id="gameSubmitQuestion" style="padding: 12px 20px; background: #2ecc71; color: white; border: none; border-radius: 6px; cursor: pointer; margin-left: 10px;">发送</button>
      </div>

      <!-- 提问&回复区 -->
      <div style="margin-top: 20px; border-top: 1px solid #eee; padding-top: 20px;">
        <h4>大家的疑问</h4>
        <div id="gameCommentsList" style="margin-top: 15px;"></div>
      </div>
    </div>
  </div>
</div>

<!-- 游戏介绍页的互动JS -->
<script>
  // 显示/隐藏提问框
  document.getElementById('gameQuestionBtn').onclick = function() {
    const box = document.getElementById('gameQuestionBox');
    box.style.display = box.style.display === 'none' ? 'block' : 'none';
  };

  // 提交游戏相关提问
  document.getElementById('gameSubmitQuestion').onclick = function() {
    const question = document.getElementById('gameQuestionInput').value.trim();
    if (!question) { alert('请输入你的问题~'); return; }

    // 添加提问到列表
    const list = document.getElementById('gameCommentsList');
    const item = document.createElement('div');
    item.style = "margin: 15px 0; padding: 15px; border-left: 4px solid #4a90e2; background: #f8f9fa; border-radius: 0 8px 8px 0;";
    item.innerHTML = `
      <strong>玩家：</strong>${question}
      <button onclick="replyGameQuestion(this)" style="margin-left: 10px; background: #ff9800; color: white; border: none; border-radius: 4px; padding: 6px 12px; cursor: pointer; font-size: 13px;">回复</button>
      <div class="game-reply-area" style="display: none; margin-top: 10px; padding-left: 20px;"></div>
    `;
    list.appendChild(item);

    // 清空输入框
    document.getElementById('gameQuestionInput').value = '';
    document.getElementById('gameQuestionBox').style.display = 'none';
  };

  // 回复游戏提问
  function replyGameQuestion(btn) {
    const area = btn.nextElementSibling;
    area.style.display = 'block';
    area.innerHTML = `
      <input type="text" placeholder="输入你的回复..." style="width: 75%; padding: 10px; border: 1px solid #ddd; border-radius: 4px; font-size: 14px;">
      <button onclick="sendGameReply(this)" style="padding: 10px 18px; background: #2ecc71; color: white; border: none; border-radius: 4px; cursor: pointer; margin-left: 8px; font-size: 14px;">发送</button>
    `;
  }

  // 发送游戏回复
  function sendGameReply(btn) {
    const reply = btn.previousElementSibling.value.trim();
    if (!reply) { alert('请输入回复内容~'); return; }

    const text = document.createElement('div');
    text.style = "margin-top: 10px;";
    text.innerHTML = `<strong>开发者：</strong>${reply}`;
    btn.parentElement.replaceWith(text);
  }
</script>
