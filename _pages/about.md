---
layout: about
title: Home
permalink: /
subtitle: 
profile:
  align: right
  image: prof_pic.jpg
  image_circular: false
  more_info: 
    
selected_papers: false
social: false
announcements:
  enabled: false
  scrollable: false
  limit: 5
latest_posts:
  enabled: false
  scrollable: false
  limit: 3
---

<div style="font-family: 'Times New Roman', 'SimSun', serif;">
  <p style="font-size: 18px; line-height: 1.8; text-indent: 2em; text-align: justify; margin-bottom: 1.5em;">
    主要研究方向为智慧农业技术与装备，针对果园进行全程智能化生产研究，研发的猕猴桃采摘机器人、授粉机器人、果园智能测产 App 等被央视 CCTV17《我爱发明》、《超级新农人》、陕西卫视等栏目专题报道。在Computers and Electronics in Agriculture、Precision Agriculture、Biosystems Engineering、Journal of the ASABE、Journal of FieldRobotics、Journal of FoodEngineering、International Journal of Agricultural and Biological Engineering (IJABE)、农业工程学报、农业机械学报、Information Processing in Agriculture、Artificial Intelligence in Agriculture等权威期刊上发表SCI论文 40 篇（ESI高被引论文 8 篇），连续入选World top 2 % scientists（全球前 2% 科学家榜单）、爱思唯尔"中国高被引学者"榜单、中国知网高被引学者Top 1%，获中国发明专利 12 项、国际发明专利 2 项、实用新型专利 43 项、外观设计专利 1 项、软件著作权 20 余项。
  </p>
</div>

<!-- ========== 完全自定义的4:3比例轮播组件 ========== -->
<div class="container my-5">
  <div class="row justify-content-center">
    <div class="col-lg-10 col-12">
      
      {% assign carousel_items = site.data.carousel %}
      {% assign total_items = carousel_items | size %}
      
      {% if total_items > 0 %}
      <div id="customCarousel" class="custom-carousel">
        <!-- 轮播轨道 -->
        <div class="carousel-track">
          {% for item in carousel_items %}
          <div class="carousel-slide {% if forloop.first %}active{% endif %}" data-index="{{ forloop.index0 }}">
            <div class="image-container-4-3">
              <!-- 已移除 onerror 外部占位图链接 -->
              <img src="/assets/img/carousel/{{ item.image }}" 
                   alt="{{ item.alt }}">
            </div>
          </div>
          {% endfor %}
        </div>
        
        <!-- 左右导航按钮 -->
        <button class="carousel-btn prev-btn" aria-label="上一张图片">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M15 18l-6-6 6-6"/>
          </svg>
        </button>
        <button class="carousel-btn next-btn" aria-label="下一张图片">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M9 18l6-6-6-6"/>
          </svg>
        </button>
        
        <!-- 指示器 -->
        <div class="carousel-indicators">
          {% for item in carousel_items %}
          <button class="indicator {% if forloop.first %}active{% endif %}" 
                  data-index="{{ forloop.index0 }}"
                  aria-label="跳转到图片 {{ forloop.index }}">
          </button>
          {% endfor %}
        </div>
        
        <!-- 当前图片计数器 -->
        <div class="carousel-counter">
          <span id="currentSlide">1</span> / <span id="totalSlides">{{ total_items }}</span>
        </div>
      </div>
      {% else %}
      <!-- 无图片时的占位符 -->
      <div class="text-center py-5 border rounded bg-light">
        <div class="image-container-4-3">
          <div class="d-flex flex-column align-items-center justify-content-center h-100">
            <i class="fas fa-image fa-3x text-muted mb-3"></i>
            <p class="text-muted mb-0">暂无展示图片</p>
          </div>
        </div>
      </div>
      {% endif %}
      
    </div>
  </div>
</div>

<!-- 自定义轮播样式 -->
<style>
/* 轮播容器 */
.custom-carousel {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
  background: #f8f9fa;
}

/* 轮播轨道 */
.carousel-track {
  display: flex;
  transition: transform 0.5s ease-in-out;
  height: 100%;
}

/* 轮播幻灯片 */
.carousel-slide {
  min-width: 100%;
  opacity: 0;
  transition: opacity 0.5s ease;
  position: relative;
}

.carousel-slide.active {
  opacity: 1;
}

/* 4:3比例图片容器 */
.image-container-4-3 {
  position: relative;
  width: 100%;
  padding-bottom: 75%; /* 4:3比例 (3/4 = 0.75) */
  height: 0;
  background: #f8f9fa;
}

.image-container-4-3 img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: contain;
  display: block;
}

/* 导航按钮 */
.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 48px;
  height: 48px;
  border: none;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10;
  opacity: 0.7;
  transition: all 0.3s ease;
}

.carousel-btn:hover {
  opacity: 1;
  background: rgba(0, 0, 0, 0.8);
  transform: translateY(-50%) scale(1.1);
}

.carousel-btn:active {
  transform: translateY(-50%) scale(0.95);
}

.prev-btn {
  left: 16px;
}

.next-btn {
  right: 16px;
}

.carousel-btn svg {
  width: 20px;
  height: 20px;
}

/* 指示器 */
.carousel-indicators {
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  gap: 8px;
  z-index: 10;
  padding: 0 16px;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.7);
  background: rgba(255, 255, 255, 0.3);
  cursor: pointer;
  padding: 0;
  transition: all 0.3s ease;
}

.indicator.active {
  background: white;
  transform: scale(1.2);
  border-color: white;
}

.indicator:hover {
  background: rgba(255, 255, 255, 0.6);
  transform: scale(1.1);
}

/* 计数器 */
.carousel-counter {
  position: absolute;
  bottom: 20px;
  right: 20px;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 14px;
  z-index: 10;
}

/* 响应式调整 */
@media (max-width: 768px) {
  .carousel-btn {
    width: 40px;
    height: 40px;
  }
  
  .carousel-btn svg {
    width: 16px;
    height: 16px;
  }
  
  .prev-btn {
    left: 8px;
  }
  
  .next-btn {
    right: 8px;
  }
  
  .carousel-indicators {
    bottom: 15px;
  }
  
  .indicator {
    width: 10px;
    height: 10px;
  }
  
  .carousel-counter {
    bottom: 15px;
    right: 15px;
    font-size: 13px;
    padding: 3px 10px;
  }
}

@media (max-width: 576px) {
  .carousel-btn {
    width: 36px;
    height: 36px;
  }
  
  .carousel-btn svg {
    width: 14px;
    height: 14px;
  }
  
  .carousel-indicators {
    bottom: 12px;
    gap: 6px;
  }
  
  .indicator {
    width: 8px;
    height: 8px;
    border-width: 1.5px;
  }
}
</style>

<!-- 自定义轮播脚本 - 确保100%工作 -->
<script>
// 等待页面完全加载
document.addEventListener('DOMContentLoaded', function() {
  console.log('🚀 开始初始化自定义轮播...');
  
  // 获取轮播元素
  const carousel = document.getElementById('customCarousel');
  if (!carousel) {
    console.warn('⚠️ 未找到轮播元素，跳过初始化');
    return;
  }
  
  // 获取所有需要的元素
  const track = carousel.querySelector('.carousel-track');
  const slides = carousel.querySelectorAll('.carousel-slide');
  const prevBtn = carousel.querySelector('.prev-btn');
  const nextBtn = carousel.querySelector('.next-btn');
  const indicators = carousel.querySelectorAll('.indicator');
  const currentSlideSpan = document.getElementById('currentSlide');
  const totalSlidesSpan = document.getElementById('totalSlides');
  
  // 验证元素是否存在
  if (!track || slides.length === 0) {
    console.warn('⚠️ 轮播元素不完整，跳过初始化');
    return;
  }
  
  console.log(`✅ 找到 ${slides.length} 张图片`);
  
  // 初始化变量
  let currentIndex = 0;
  let isTransitioning = false;
  let autoPlayInterval = null;
  const transitionDuration = 500; // 与CSS中的transition时间匹配
  const autoPlayDelay = 3000; // 3秒自动切换
  
  // 更新轮播状态
  function updateCarousel() {
    if (isTransitioning) return;
    
    // 移动轨道
    track.style.transform = `translateX(-${currentIndex * 100}%)`;
    
    // 更新幻灯片active状态
    slides.forEach((slide, index) => {
      slide.classList.toggle('active', index === currentIndex);
    });
    
    // 更新指示器active状态
    indicators.forEach((indicator, index) => {
      indicator.classList.toggle('active', index === currentIndex);
    });
    
    // 更新计数器
    if (currentSlideSpan) {
      currentSlideSpan.textContent = currentIndex + 1;
    }
    
    // 更新总张数
    if (totalSlidesSpan && !totalSlidesSpan.textContent) {
      totalSlidesSpan.textContent = slides.length;
    }
    
    // 设置过渡状态，防止过快切换
    isTransitioning = true;
    setTimeout(() => {
      isTransitioning = false;
    }, transitionDuration);
    
    console.log(`🔍 显示图片 ${currentIndex + 1}/${slides.length}`);
  }
  
  // 下一张图片
  function nextSlide() {
    if (isTransitioning) return;
    
    if (currentIndex >= slides.length - 1) {
      currentIndex = 0;
    } else {
      currentIndex++;
    }
    
    updateCarousel();
    restartAutoPlay(); // 每次手动操作后重置自动播放
  }
  
  // 上一张图片
  function prevSlide() {
    if (isTransitioning) return;
    
    if (currentIndex <= 0) {
      currentIndex = slides.length - 1;
    } else {
      currentIndex--;
    }
    
    updateCarousel();
    restartAutoPlay(); // 每次手动操作后重置自动播放
  }
  
  // 跳转到指定索引的图片
  function goToSlide(index) {
    if (isTransitioning || index < 0 || index >= slides.length || index === currentIndex) {
      return;
    }
    
    currentIndex = index;
    updateCarousel();
    restartAutoPlay(); // 每次手动操作后重置自动播放
  }
  
  // 启动自动播放
  function startAutoPlay() {
    stopAutoPlay(); // 先停止现有的
    autoPlayInterval = setInterval(nextSlide, autoPlayDelay);
    console.log('▶️ 自动播放已启动');
  }
  
  // 停止自动播放
  function stopAutoPlay() {
    if (autoPlayInterval) {
      clearInterval(autoPlayInterval);
      autoPlayInterval = null;
      console.log('⏸️ 自动播放已停止');
    }
  }
  
  // 重新启动自动播放
  function restartAutoPlay() {
    stopAutoPlay();
    startAutoPlay();
  }
  
  // 绑定事件监听器
  function bindEvents() {
    console.log('🔗 绑定事件监听器...');
    
    // 左箭头按钮
    if (prevBtn) {
      prevBtn.addEventListener('click', function(e) {
        e.preventDefault();
        e.stopPropagation();
        console.log('🖱️ 点击上一张按钮');
        prevSlide();
      });
    }
    
    // 右箭头按钮
    if (nextBtn) {
      nextBtn.addEventListener('click', function(e) {
        e.preventDefault();
        e.stopPropagation();
        console.log('🖱️ 点击下一张按钮');
        nextSlide();
      });
    }
    
    // 指示器按钮
    indicators.forEach((indicator, index) => {
      indicator.addEventListener('click', function(e) {
        e.preventDefault();
        e.stopPropagation();
        console.log(`🖱️ 点击指示器 ${index + 1}`);
        goToSlide(index);
      });
    });
    
    // 键盘控制 - 这是确保工作的关键
    document.addEventListener('keydown', function(e) {
      // 检查是否在输入框中
      const activeElement = document.activeElement;
      const isInput = activeElement.tagName === 'INPUT' || 
                      activeElement.tagName === 'TEXTAREA' || 
                      activeElement.isContentEditable;
      
      if (isInput) return;
      
      switch(e.key) {
        case 'ArrowLeft':
          console.log('← 键盘左箭头键按下');
          prevSlide();
          e.preventDefault();
          break;
          
        case 'ArrowRight':
          console.log('→ 键盘右箭头键按下');
          nextSlide();
          e.preventDefault();
          break;
          
        case ' ':
          // 空格键暂停/播放
          if (autoPlayInterval) {
            stopAutoPlay();
          } else {
            startAutoPlay();
          }
          e.preventDefault();
          break;
      }
    });
    
    // 触摸滑动支持（移动端）
    let touchStartX = 0;
    let touchEndX = 0;
    const swipeThreshold = 50; // 滑动阈值
    
    carousel.addEventListener('touchstart', function(e) {
      touchStartX = e.touches[0].clientX;
      stopAutoPlay(); // 触摸时暂停自动播放
    }, { passive: true });
    
    carousel.addEventListener('touchend', function(e) {
      touchEndX = e.changedTouches[0].clientX;
      const diff = touchStartX - touchEndX;
      
      if (Math.abs(diff) > swipeThreshold) {
        if (diff > 0) {
          // 向左滑动，下一张
          nextSlide();
        } else {
          // 向右滑动，上一张
          prevSlide();
        }
      }
      
      // 触摸结束后重新启动自动播放
      setTimeout(() => {
        startAutoPlay();
      }, 1000);
    }, { passive: true });
    
    // 鼠标悬停暂停
    carousel.addEventListener('mouseenter', stopAutoPlay);
    carousel.addEventListener('mouseleave', startAutoPlay);
    
    console.log('✅ 事件监听器绑定完成');
  }
  
  // 初始化轮播
  function initCarousel() {
    console.log('🔧 初始化轮播...');
    
    // 确保初始状态正确
    if (slides.length > 0) {
      updateCarousel();
    }
    
    // 绑定所有事件
    bindEvents();
    
    // 启动自动播放
    startAutoPlay();
    
    console.log('✅ 轮播初始化完成');
  }
  
  // 执行初始化
  initCarousel();
  
  // 全局暴露函数以便调试（可选）
  window.carouselControls = {
    nextSlide,
    prevSlide,
    goToSlide,
    startAutoPlay,
    stopAutoPlay
  };
  
  console.log('🎉 自定义轮播组件已完全加载，键盘左右箭头键可用');
});
</script>