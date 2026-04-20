<!-- Bitfree Community Section -->
<div class="section community-section">
  <div class="section-header">
    <span class="section-label">推荐</span>
    <h2>bitfree开发者社区</h2>
  </div>
  <p class="section-desc">专注高级技术人才成长的专业平台</p>
  
  <div class="feature-tags">
    <span class="tag">专业课程</span>
    <span class="tag">社区交流</span>
    <span class="tag">实战项目</span>
    <span class="tag">职业发展</span>
  </div>
  
  <a href="http://bitfree.cn" target="_blank" class="btn btn-primary">
    访问社区 <i class="fas fa-arrow-right"></i>
  </a>
</div>

<!-- Personal Services Section -->
<div class="section services-section">
  <div class="section-header">
    <h2>一对一服务</h2>
    <span class="badge">限量预约</span>
  </div>
  
  <div class="service-list">
    <!-- Service Card 1 -->
    <div class="service-item" data-service="interview">
      <div class="service-main">
        <div class="service-icon">
          <i class="fas fa-comments"></i>
        </div>
        <div class="service-info">
          <h3>模拟面试 <span class="tag-hot">热门</span></h3>
          <p>真实面试环境模拟，针对性反馈与改进建议</p>
        </div>
        <button class="btn-expand" aria-label="查看详情">
          <i class="fas fa-chevron-down"></i>
        </button>
      </div>
      <div class="service-details">
        <div class="process-simple">
          <div class="step">B站私信预约</div>
          <i class="fas fa-arrow-right step-arrow"></i>
          <div class="step">确认时间</div>
          <i class="fas fa-arrow-right step-arrow"></i>
          <div class="step">面试+复盘</div>
        </div>
        <a href="https://message.bilibili.com/#/whisper/mid1525355" target="_blank" class="btn btn-secondary">
          立即预约
        </a>
      </div>
    </div>
    
    <!-- Service Card 2 -->
    <div class="service-item" data-service="career">
      <div class="service-main">
        <div class="service-icon">
          <i class="fas fa-route"></i>
        </div>
        <div class="service-info">
          <h3>职业咨询</h3>
          <p>深度分析职业现状，定制个人发展规划</p>
        </div>
        <button class="btn-expand" aria-label="查看详情">
          <i class="fas fa-chevron-down"></i>
        </button>
      </div>
      <div class="service-details">
        <div class="process-simple">
          <div class="step">B站私信预约</div>
          <i class="fas fa-arrow-right step-arrow"></i>
          <div class="step">确认时间</div>
          <i class="fas fa-arrow-right step-arrow"></i>
          <div class="step">定制方案</div>
        </div>
        <a href="https://message.bilibili.com/#/whisper/mid1525355" target="_blank" class="btn btn-secondary">
          立即预约
        </a>
      </div>
    </div>
  </div>
</div>

<!-- Contact Section -->
<div class="section contact-section" id="contact">
  <h2>联系方式</h2>
  <p class="contact-desc">扫码添加微信，或点击上方按钮预约服务</p>
  
  <div class="contact-grid">
    <div class="contact-item">
      <img src="img/weChat.jpg" alt="微信二维码" />
      <span>个人微信</span>
    </div>
    <div class="contact-item">
      <img src="img/PaymentCode.jpeg" alt="支付二维码" />
      <span>支付/赞赏</span>
    </div>
  </div>
</div>

<script>
// Service card expand/collapse
document.querySelectorAll('.service-item').forEach(item => {
  const main = item.querySelector('.service-main');
  const details = item.querySelector('.service-details');
  const expandBtn = item.querySelector('.btn-expand');
  
  main.addEventListener('click', (e) => {
    if (e.target.closest('.btn-expand') || e.target.closest('.service-main')) {
      const isExpanded = item.classList.contains('expanded');
      
      // Close all other items
      document.querySelectorAll('.service-item').forEach(other => {
        if (other !== item) {
          other.classList.remove('expanded');
          other.querySelector('.btn-expand i').style.transform = 'rotate(0deg)';
        }
      });
      
      // Toggle current item
      item.classList.toggle('expanded');
      expandBtn.querySelector('i').style.transform = isExpanded ? 'rotate(0deg)' : 'rotate(180deg)';
    }
  });
});

// Fade in animation on scroll
const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -50px 0px'
};

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, observerOptions);

document.querySelectorAll('.section, .service-item').forEach(el => {
  el.classList.add('fade-in');
  observer.observe(el);
});
</script>

<style>
/* ===== Base Styles ===== */
.section {
  margin-bottom: 48px;
  opacity: 1;
}

.section-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
}

.section-header h2 {
  font-size: 24px;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0;
  border: none;
  padding: 0;
  background: none;
  -webkit-text-fill-color: initial;
}

.section-label {
  font-size: 12px;
  font-weight: 500;
  color: #fff;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 4px 10px;
  border-radius: 12px;
}

.section-desc {
  color: var(--text-secondary);
  margin: 0 0 20px 0;
  font-size: 15px;
}

.badge {
  font-size: 12px;
  color: var(--accent-cyan);
  background: rgba(0, 245, 255, 0.1);
  padding: 4px 10px;
  border-radius: 12px;
  border: 1px solid rgba(0, 245, 255, 0.2);
}

/* ===== Community Section ===== */
.community-section {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.15) 100%);
  border-radius: 16px;
  padding: 32px;
  border: 1px solid rgba(139, 92, 246, 0.15);
}

.feature-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 24px;
}

.tag {
  font-size: 13px;
  color: var(--text-secondary);
  background: rgba(255, 255, 255, 0.05);
  padding: 6px 14px;
  border-radius: 20px;
  border: 1px solid rgba(255, 255, 255, 0.08);
}

/* ===== Services Section ===== */
.services-section .section-header {
  margin-bottom: 20px;
}

.service-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.service-item {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.06);
  border-radius: 14px;
  overflow: hidden;
  transition: all 0.3s ease;
  cursor: pointer;
}

.service-item:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(0, 245, 255, 0.15);
  transform: translateY(-2px);
}

.service-item.expanded {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(0, 245, 255, 0.2);
}

.service-main {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 20px 24px;
}

.service-icon {
  width: 44px;
  height: 44px;
  background: rgba(0, 245, 255, 0.1);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.service-icon i {
  font-size: 18px;
  color: var(--accent-cyan);
}

.service-info {
  flex: 1;
}

.service-info h3 {
  font-size: 17px;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0 0 6px 0;
  display: flex;
  align-items: center;
  gap: 8px;
  border: none;
  padding: 0;
}

.tag-hot {
  font-size: 11px;
  font-weight: 500;
  color: #fff;
  background: linear-gradient(135deg, #ec4899 0%, #8b5cf6 100%);
  padding: 2px 8px;
  border-radius: 10px;
}

.service-info p {
  font-size: 14px;
  color: var(--text-secondary);
  margin: 0;
}

.btn-expand {
  width: 32px;
  height: 32px;
  background: transparent;
  border: none;
  color: var(--text-muted);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  transition: all 0.2s ease;
}

.btn-expand:hover {
  background: rgba(255, 255, 255, 0.05);
  color: var(--text-primary);
}

.btn-expand i {
  transition: transform 0.3s ease;
}

.service-details {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease, padding 0.3s ease;
  padding: 0 24px;
}

.service-item.expanded .service-details {
  max-height: 200px;
  padding: 0 24px 24px 24px;
}

.process-simple {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin-bottom: 20px;
  flex-wrap: wrap;
}

.step {
  font-size: 13px;
  color: var(--text-secondary);
  background: rgba(255, 255, 255, 0.05);
  padding: 8px 16px;
  border-radius: 20px;
  white-space: nowrap;
}

.step-arrow {
  font-size: 12px;
  color: var(--text-muted);
}

/* ===== Contact Section ===== */
.contact-section h2 {
  font-size: 20px;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0 0 8px 0;
  border: none;
  padding: 0;
  background: none;
  -webkit-text-fill-color: initial;
}

.contact-desc {
  color: var(--text-secondary);
  font-size: 14px;
  margin: 0 0 20px 0;
}

.contact-grid {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
}

.contact-item {
  text-align: center;
}

.contact-item img {
  width: 140px;
  height: 140px;
  border-radius: 12px;
  object-fit: cover;
  margin-bottom: 10px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease;
}

.contact-item:hover img {
  transform: scale(1.02);
}

.contact-item span {
  display: block;
  font-size: 13px;
  color: var(--text-secondary);
}

/* ===== Buttons ===== */
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 24px;
  border-radius: 10px;
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.2s ease;
  cursor: pointer;
  border: none;
}

.btn-primary {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #fff;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 20px rgba(102, 126, 234, 0.4);
  text-decoration: none;
  filter: brightness(1.1);
}

.btn-secondary {
  background: rgba(0, 245, 255, 0.1);
  color: var(--accent-cyan);
  border: 1px solid rgba(0, 245, 255, 0.2);
  width: 100%;
  justify-content: center;
}

.btn-secondary:hover {
  background: rgba(0, 245, 255, 0.15);
  text-decoration: none;
}

/* ===== Animations ===== */
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ===== Responsive ===== */
@media (max-width: 600px) {
  .community-section {
    padding: 24px 20px;
  }
  
  .service-main {
    padding: 16px 20px;
  }
  
  .service-item.expanded .service-details {
    padding: 0 20px 20px 20px;
  }
  
  .process-simple {
    flex-direction: column;
    gap: 8px;
  }
  
  .step-arrow {
    transform: rotate(90deg);
  }
  
  .contact-grid {
    justify-content: center;
  }
  
  .contact-item img {
    width: 120px;
    height: 120px;
  }
}
</style>
