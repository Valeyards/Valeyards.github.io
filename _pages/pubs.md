<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <style>
    .spotlight-btn {
      position: relative;
      display: inline-block;
      padding: 0.75em 1.5em;
      background-color: #1e3a5f;
      color: rgba(255, 255, 255, 0.6);
      text-decoration: none !important;
      border-radius: 4px;
      font-weight: 500;
      overflow: hidden;
      --mouse-x: 50%;
      --mouse-y: 50%;
    }
    
    .spotlight-btn:hover {
      text-decoration: none !important;
    }
    
    .spotlight-btn::before {
      content: '';
      position: absolute;
      width: 0;
      height: 0;
      left: var(--mouse-x);
      top: var(--mouse-y);
      border-radius: 50%;
      background: radial-gradient(circle, rgba(255, 255, 255, 0.4) 0%, rgba(255, 255, 255, 0.1) 40%, transparent 70%);
      transform: translate(-50%, -50%);
      transition: width 0.4s ease, height 0.4s ease, opacity 0.3s ease;
      pointer-events: none;
      opacity: 0;
    }
    
    .spotlight-btn:hover::before {
      width: 150px;
      height: 150px;
      opacity: 1;
    }
    
    .spotlight-btn i {
      position: relative;
      z-index: 1;
      margin-right: 0.5em;
      transition: color 0.2s ease;
      color: rgba(255, 255, 255, 0.6);
    }
    
    .spotlight-btn i.highlight {
      color: #66b3ff;
    }
    
    .spotlight-btn span {
      position: relative;
      z-index: 1;
    }
    
    .spotlight-btn .word {
      position: relative;
      display: inline-block;
      transition: color 0.2s ease;
    }
    
    .spotlight-btn .word.highlight {
    }
  </style>
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const btn = document.querySelector('.spotlight-btn');
      if (!btn) return;
      
      btn.addEventListener('mousemove', function(e) {
        const rect = this.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        this.style.setProperty('--mouse-x', x + 'px');
        this.style.setProperty('--mouse-y', y + 'px');
      });
      
      function getRandomRainbowColor() {
        const hue = Math.floor(Math.random() * 360);
        return `hsl(${hue}, 100%, 70%)`;
      }
      
      const icon = btn.querySelector('i');
      const span = btn.querySelector('span');
      
      function clearHighlights() {
        if (icon) {
          icon.classList.remove('highlight');
          icon.style.color = '';
        }
        if (span) {
          span.querySelectorAll('.word').forEach(w => {
            w.classList.remove('highlight');
            w.style.color = '';
          });
        }
      }
      
      if (icon) {
        icon.addEventListener('mouseenter', function() {
          clearHighlights();
          this.classList.add('highlight');
        });
      }
      
      if (span) {
        const text = span.textContent;
        const words = text.split(/\s+/);
        span.innerHTML = words.map(word => `<span class="word">${word}</span>`).join(' ');
        
        const wordElements = span.querySelectorAll('.word');
        
        wordElements.forEach(wordEl => {
          wordEl.addEventListener('mouseenter', function() {
            clearHighlights();
            this.classList.add('highlight');
            this.style.color = getRandomRainbowColor();
          });
        });
        
        span.addEventListener('mouseleave', function() {
          clearHighlights();
        });
      }
      
      btn.addEventListener('mouseleave', function(e) {
        clearHighlights();
      });
    });
  </script>
</head>


<div class='paper-box'>
<div class='paper-box-image'><div><div class="badge">Signal Transduction and Targeted Therapy </div>
<a href="https://www.nature.com/articles/s41392-025-02374-w">
<img src='images/pub/progpath.jpg' alt="sym" width="100%" title="" href="https://www.nature.com/articles/s41392-025-02374-w">
</a>  
</div></div>
<div class='paper-box-text' markdown="1">
## **<font color=SteelBlue >Pancancer outcome prediction via a unified weakly supervised deep learning model</font>**
<a href="https://doi.org/10.1038/s41392-025-02374-w"><img src="https://img.shields.io/badge/DOI-10.1038%2Fs41392--025--02374--w-blue" alt="DOI"></a>
<a href="https://github.com/Valeyards/ProgPath"><img src="https://img.shields.io/github/stars/Valeyards/ProgPath?style=social&label=Code+★" alt="code"></a>

---

**W. Yuan**†, Y. J. Chen†, B. Y. Zhu, S. Yang, J. Y. Zhang, N. Mao, J. X. Xiang, Y. C. Li, Y. F. Ji, X. D. Luo, K. N. Zhang, X. H. Xing, S. Kang, D. Y. Xiao, F. Wang, J. K. Wu, H. Y. Zhang, H. P. Tang, H. Maurya, G. Corredor, C. Barrera. Y. F. Zhou, K. Pandav, J. H. Zhao, P. Jain, L. Delasos, J. Z. Huang, K. L. Yang, T. N. Teknos, J. Lewis Jr., S. Koyfman, N. A. Pennell, K. H. Yu, X. Han, J. Zhang#, X. Y. Wang#, A. Madabhushi
</div>
</div>



<div class='paper-box'>
<div class='paper-box-image'><div><div class="badge">Journal of Clinical Oncology </div>
<a href="https://pubmed.ncbi.nlm.nih.gov/40168636/">
<img src='images/pub/jco.PNG' alt="sym" width="100%" title="" href="https://pubmed.ncbi.nlm.nih.gov/40168636/">
</a>  
</div></div>
<div class='paper-box-text' markdown="1">
## **<font color=SteelBlue >Foundation Model for Predicting Prognosis and Adjuvant Therapy Benefit From Digital Pathology in GI Cancers</font>**
<a href="https://ascopubs.org/doi/10.1200/JCO-24-01501"><img src="https://img.shields.io/badge/DOI-10.1200%2FJCO--24--01501-blue" alt="DOI"></a>

---

X. Y. Wang†, Y. M. Jiang†, S. Yang, F. Wang, X. M. Zhang, W. Yang, Y. J. Chen, X. Y. Wu, J. X. Xiang, Y. C. Li, X. F. Jiang, **W. Yuan**, J. Zhang, K. H. Yu, R. L. Ward, N. Hawkins, J. Jonnagaddala, G. X. Li, R. J. Li#
</div>
</div>

<div class='paper-box'>
<div class='paper-box-image'><div><div class="badge">Nature </div>
<a href="https://www.nature.com/articles/s41586-024-07894-z">
<img src='images/pub/chief.png' alt="sym" width="100%" title="" href="https://www.nature.com/articles/s41586-024-07894-z">
</a>  
</div></div>
<div class='paper-box-text' markdown="1">
## **<font color=SteelBlue >A Pathology Foundation Model for Cancer Diagnosis and Prognosis Prediction</font>**
<a href="https://doi.org/10.1038/s41586-024-07894-z"><img src="https://img.shields.io/badge/DOI-10.1038%2Fs41586--024--07894--z-blue" alt="DOI"></a>
<a href="https://github.com/hms-dbmi/CHIEF"><img src="https://img.shields.io/github/stars/hms-dbmi/CHIEF?style=social&label=Code+★" alt="code"></a>

---

X. Y. Wang†, J. H. Zhao†, E. Marostica, **W. Yuan**, J. T. Jin, J. Y. Zhang, R. J. Li, H. P. Tang, K. R. Wang, Y. Li, F. Wang, Y. L. Peng, J. Y. Zhu, Jing Zhang, C. R. Jackson, Jun Zhang, D. Dillon, N. U. Lin, L. Sholl, T. Denize, D. Meredith, K. L. Ligon, S. Signoretti, S. Ogino, J. A. Golden, M. P. Nasrallah, X. Han, S. Yang#, K. H. Yu#

</div>
</div>

<div class='paper-box'>
<div class='paper-box-image'><div><div class="badge">IEEE Transactions on Medical Imaging </div>
<a href="https://ieeexplore.ieee.org/abstract/document/10571965">
<img src='images/pub/hicervix.png' alt="sym" width="100%" title="" href="https://ieeexplore.ieee.org/abstract/document/10571965">
</a>  
</div></div>
<div class='paper-box-text' markdown="1">
## **<font color=SteelBlue >HiCervix: An Extensive Hierarchical Dataset and Benchmark for Cervical Cytology Classification</font>**
<a href="https://doi.org/10.1109/TMI.2024.3419697"><img src="https://img.shields.io/badge/DOI-10.1109%2FTMI.2024.3419697-blue" alt="DOI"></a>
<a href="https://github.com/Scu-sen/HiCervix"><img src="https://img.shields.io/github/stars/Scu-sen/HiCervix?style=social&label=Code+★" alt="code"></a>

---

 D. Cai†, J. Chen†, J. H. Zhao†, Y. Xue, S. Yang, **W. Yuan**, M. Feng, H. Y. Weng, S. G. Liu,
 Y. L. Peng, J. Y. Zhu, K. R. Wang, C. Jackson, H. P. Tang#, J. Z. Huang, X. Y. Wang#

</div>
</div>

<div class='paper-box'>
<div class='paper-box-image'><div><div class="badge">Computers in Biology and Medicine </div>
<a href="https://doi.org/10.1016/j.compbiomed.2024.108673">
<img src='images/pub/macg.png' alt="sym" width="100%" title="" href="https://doi.org/10.1016/j.compbiomed.2024.108673">
</a>  
</div></div>
<div class='paper-box-text' markdown="1">
## **<font color=SteelBlue >MACG-Net: Multi-axis Cross Gating Network for Deformable Medical Image Registration</font>**
<a href="https://doi.org/10.1016/j.compbiomed.2024.108673">  <img src="https://img.shields.io/badge/DOI-10.1016%2Fj.compbiomed.2024.108673-blue" alt="DOI"></a>

---

**W. Yuan**, J. Cheng, Y. H. Gong, L. He#, J. Zhang

</div>
</div>


<div style="text-align: center; margin: 2em 0;">
  <a href="https://scholar.google.com/citations?user=iJTVJf8AAAAJ" class="spotlight-btn">
    <i class="fas fa-graduation-cap"></i><span>View All Publications on Google Scholar</span>
  </a>
</div>
