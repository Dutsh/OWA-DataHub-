# OWA-DataHub-я делаю AI-чат-бот для DataHub. мвп не успеваю мы 9 часов сидели в этом зале на хакатоне потом решили с 0 и пошли домой делать.
<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>OWA-DataHub — Университетский Data Hub Казахстана</title>

  <!-- Google Fonts: современная читабельная типографика -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <meta name="description" content="OWA-DataHub — единый минималистичный сервис обмена данными между университетами Казахстана. Для аналитиков, администраторов и исследователей.">

  <style>
    /* =========================
       OWA-DataHub — Minimal CSS
       ========================= */

    :root{
      --bg: #ffffff;
      --text: #0b0b0b;
      --muted: #6b6b6b;
      --accent-red: #d62828;   /* основной акцент */
      --accent-yellow: #ffcc00; /* дополнительный акцент */
      --card-bg: #fafafa;
      --radius: 12px;
      --max-width: 1100px;
      --container-padding: 20px;
      --shadow: 0 6px 18px rgba(11,11,11,0.06);
      --focus: 3px solid rgba(214,40,40,0.12);
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }

    /* Reset & base */
    *{box-sizing: border-box}
    html,body{height:100%}
    body{
      margin:0;
      background:var(--bg);
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      font-size:16px;
    }

    a{color:inherit;text-decoration:none}
    img{max-width:100%;height:auto;display:block}

    /* Layout */
    .site{
      display:flex;
      flex-direction:column;
      min-height:100vh;
    }

    header{
      border-bottom: 1px solid rgba(11,11,11,0.06);
      background: linear-gradient(180deg, rgba(255,255,255,0.95), rgba(255,255,255,0.9));
      position:sticky;
      top:0;
      z-index:40;
      backdrop-filter: blur(4px);
    }

    .wrap{
      max-width:var(--max-width);
      margin:0 auto;
      padding:14px var(--container-padding);
    }

    /* Header content */
    .header-row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 12px;
    }

    /* Logo */
    .logo{
      display:flex;
      align-items:center;
      gap:12px;
    }
    .logo svg{width:48px;height:48px;flex:0 0 48px}
    .brand-title{
      display:flex;
      flex-direction:column;
      line-height:1;
    }
    .brand-title .name{
      font-weight:700;
      letter-spacing:0.2px;
      font-size:18px;
    }
    .brand-title .tagline{
      font-size:12px;
      color:var(--muted);
    }

    /* Nav / Actions */
    .nav-actions{
      display:flex;
      gap:10px;
      align-items:center;
    }
    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:10px 14px;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      border: none;
      transition:transform .12s ease, box-shadow .12s ease;
      text-decoration:none;
    }
    .btn:active{transform:translateY(1px)}
    .btn:focus{outline: none; box-shadow:var(--focus); border-radius:10px}

    .btn-ghost{
      background:transparent;
      color:var(--text);
      border:1px solid rgba(11,11,11,0.06);
      padding:8px 12px;
      font-weight:600;
    }

    .btn-primary{
      background:linear-gradient(90deg,var(--accent-red),#b71b1b);
      color:white;
      box-shadow: 0 6px 18px rgba(214,40,40,0.12);
      padding:10px 16px;
    }

    /* Hero */
    .hero{
      display:grid;
      grid-template-columns: 1fr 420px;
      gap:32px;
      align-items:center;
      padding:48px var(--container-padding);
    }
    .hero-left h1{
      margin:0 0 12px 0;
      font-size:34px;
      letter-spacing:-0.6px;
      line-height:1.05;
    }
    .hero-left p.lead{
      margin:0 0 20px 0;
      color:var(--muted);
      max-width:70ch;
    }

    .hero-cta { display:flex; gap:12px; align-items:center; }

    .card-visual{
      background:linear-gradient(180deg, #fff, var(--card-bg));
      border-radius:var(--radius);
      padding:18px;
      box-shadow:var(--shadow);
      display:flex;
      flex-direction:column;
      gap:12px;
      align-items:stretch;
    }

    .stats{
      display:flex;
      gap:12px;
      justify-content:space-between;
    }
    .stat{
      flex:1;
      background:white;
      border-radius:10px;
      padding:10px;
      text-align:center;
      border:1px solid rgba(11,11,11,0.03);
    }
    .stat b{display:block;font-size:18px}

    /* Features */
    .features{
      padding:36px var(--container-padding);
    }
    .features-grid{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:18px;
      margin-top:20px;
    }

    .feature-card{
      background:var(--card-bg);
      border-radius:12px;
      padding:18px;
      box-shadow:var(--shadow);
      border-left:6px solid transparent;
      transition:transform .12s ease, border-color .12s;
    }
    .feature-card:hover{
      transform:translateY(-6px);
      border-left-color:var(--accent-yellow);
    }
    .feature-card h3{margin:0 0 8px 0;font-size:16px}
    .feature-card p{margin:0;color:var(--muted);font-size:14px}

    /* Why section (3-4 cards) */
    .advantages{
      padding:36px var(--container-padding);
      background:linear-gradient(180deg, rgba(255,255,255,0.0), rgba(255,250,240,0.02));
    }
    .adv-grid{
      display:grid;
      gap:18px;
      grid-template-columns:repeat(4,1fr);
    }
    .adv-card{
      background:white;
      border-radius:12px;
      padding:16px;
      text-align:center;
      border:1px solid rgba(11,11,11,0.04);
      box-shadow:0 8px 24px rgba(11,11,11,0.04);
    }
    .adv-icon{
      width:56px;height:56px;border-radius:12px;
      display:inline-flex;align-items:center;justify-content:center;
      background:linear-gradient(180deg,var(--accent-red),#b71b1b);
      color:white;margin-bottom:12px;font-weight:700;
    }
    .adv-card h4{margin:6px 0 6px 0;font-size:15px}
    .adv-card p{margin:0;color:var(--muted);font-size:13px}

    /* Contact / Footer */
    footer{
      margin-top:auto;
      border-top:1px solid rgba(11,11,11,0.04);
      padding:26px var(--container-padding) 40px;
      background: #fff;
    }
    .footer-grid{
      display:flex;
      gap:24px;
      justify-content:space-between;
      align-items:flex-start;
      max-width:var(--max-width);
      margin:0 auto;
      padding:0 var(--container-padding);
      flex-wrap:wrap;
    }
    .contacts, .participants { min-width:220px; flex:1; }
    .participants ul{list-style:none;padding:0;margin:0;display:grid;gap:6px}
    .participants li{color:var(--muted);font-size:14px}

    .small{font-size:13px;color:var(--muted);}

    /* Responsive */
    @media (max-width:980px){
      .hero{grid-template-columns:1fr; padding:36px var(--container-padding)}
      .hero-visual { order: -1; } /* visual above on tablet */
      .features-grid{grid-template-columns:repeat(2,1fr)}
      .adv-grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:560px){
      .header-row{flex-direction:row;gap:8px}
      .brand-title .name{font-size:16px}
      .hero-left h1{font-size:26px}
      .features-grid{grid-template-columns:1fr}
      .adv-grid{grid-template-columns:1fr}
      .nav-actions{gap:6px}
      .logo svg{width:40px;height:40px}
    }

    /* Accessibility tweaks for color-only accents */
    .accent-dot{
      display:inline-block;width:10px;height:10px;border-radius:50%;
    }

    /* Utility */
    .muted{color:var(--muted)}
    .center{text-align:center}
    .mb-8{margin-bottom:8px}
    .mt-8{margin-top:8px}
  </style>
</head>
<body>
  <div class="site" id="top">
    <header role="banner">
      <div class="wrap header-row" aria-label="Заголовок сайта OWA-DataHub">
        <div class="logo" role="img" aria-label="Логотип OWA-DataHub">
          <!-- Минималистичный SVG логотип: OWA в маркере -->
          <svg viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <rect width="120" height="120" rx="18" fill="#0b0b0b"/>
            <g transform="translate(18,18)" fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="6">
              <path d="M6 72 L54 6 L102 72" stroke="#ffcc00" />
              <circle cx="30" cy="46" r="6" fill="#d62828" stroke="rgba(0,0,0,0)"/>
              <circle cx="78" cy="46" r="6" fill="#ffcc00" stroke="rgba(0,0,0,0)"/>
            </g>
          </svg>

          <div class="brand-title">
            <div class="name">OWA-DataHub</div>
            <div class="tagline">Единая платформа обмена данными университетов</div>
          </div>
        </div>

        <nav class="nav-actions" aria-label="Навигация">
          <a class="btn btn-ghost" href="#about">Подробнее</a>
          <a class="btn btn-primary" href="#contact">Подключиться</a>
        </nav>
      </div>
    </header>

    <main>
      <!-- HERO -->
      <section class="hero" id="about" aria-labelledby="hero-title">
        <div class="hero-left">
          <h1 id="hero-title">OWA-DataHub — данные, которыми доверяют университеты Казахстана</h1>
          <p class="lead">
            OWA-DataHub — минималистичный и безопасный сервис для централизованного обмена и агрегирования академических,
            административных и исследовательских данных между университетами. Ускоряет отчётность, облегчает исследования и поддерживает аналитические решения.
          </p>

          <div class="hero-cta">
            <a class="btn btn-primary" href="#contact">Подключиться</a>
            <a class="btn btn-ghost" href="#advantages">Преимущества</a>
          </div>

          <p class="small mt-8 muted">Подходит для: отделов аналитики, ИТ-служб, исследовательских групп и администрации университета.</p>
        </div>

        <aside class="card-visual hero-visual" aria-label="Краткое визуальное представление сервиса">
          <div style="display:flex;justify-content:space-between;align-items:center;">
            <div style="font-weight:700">Ключевые показатели</div>
            <div style="font-size:12px;color:var(--muted)">Обновляются в реальном времени</div>
          </div>

          <div class="stats" role="list" aria-label="Статистика">
            <div class="stat" role="listitem">
              <div class="muted">Университетов</div>
              <b>12+</b>
            </div>
            <div class="stat" role="listitem">
              <div class="muted">Наборов данных</div>
              <b>250+</b>
            </div>
            <div class="stat" role="listitem">
              <div class="muted">API-запросов / мес.</div>
              <b>120k+</b>
            </div>
          </div>

          <div style="display:flex;gap:8px;align-items:center;justify-content:space-between;margin-top:6px">
            <div class="small muted">Безопасность: шифрование TLS, RBAC</div>
            <div style="font-size:12px;color:var(--muted)">Версия: <b>v1.0</b></div>
          </div>
        </aside>
      </section>

      <!-- FEATURES -->
      <section class="features" aria-labelledby="features-title">
        <div class="wrap">
          <h2 id="features-title">Что делает OWA-DataHub</h2>
          <p class="muted mb-8">Коротко и по делу — только полезные инструменты и открытые интерфейсы.</p>

          <div class="features-grid" role="list">
            <article class="feature-card" role="listitem" aria-labelledby="f1">
              <h3 id="f1">Единый доступ к данным</h3>
              <p>Централизованное хранилище, стандартизованные схемы и унифицированные API для быстрого анализа.</p>
            </article>

            <article class="feature-card" role="listitem" aria-labelledby="f2">
              <h3 id="f2">Безопасность и контроль</h3>
              <p>Гибкие роли и права, аудит доступа и шифрование — данные под контролем вашей ИТ-службы.</p>
            </article>

            <article class="feature-card" role="listitem" aria-labelledby="f3">
              <h3 id="f3">Интеграция с аналитикой</h3>
              <p>Экспорт для популярных BI-инструментов, REST/GraphQL API и удобные CSV/Parquet выгрузки.</p>
            </article>

            <article class="feature-card" role="listitem" aria-labelledby="f4">
              <h3 id="f4">Поддержка и сопровождение</h3>
              <p>Лёгкий старт: шаблоны, документация и техподдержка — чтобы подключиться быстро и без лишних усилий.</p>
            </article>

            <article class="feature-card" role="listitem" aria-labelledby="f5">
              <h3 id="f5">Конфиденциальность</h3>
              <p>Соответствие внутренним политиками университета и защитa персональных данных.</p>
            </article>

            <article class="feature-card" role="listitem" aria-labelledby="f6">
              <h3 id="f6">Масштабируемость</h3>
              <p>Архитектура, рассчитанная на рост — от 1 до сотен универов и петабайт данных.</p>
            </article>
          </div>
        </div>
      </section>

      <!-- ADVANTAGES -->
      <section id="advantages" class="advantages" aria-labelledby="advantages-title">
        <div class="wrap">
          <h2 id="advantages-title">Преимущества</h2>
          <p class="muted">Три ключевых выгоды для университетов.</p>

          <div class="adv-grid" role="list" style="margin-top:18px">
            <div class="adv-card" role="listitem">
              <div class="adv-icon" aria-hidden="true">⚡</div>
              <h4>Быстрый доступ</h4>
              <p>Минимум времени на подготовку данных — максимум времени на аналитику.</p>
            </div>

            <div class="adv-card" role="listitem">
              <div class="adv-icon" style="background:linear-gradient(180deg,var(--accent-yellow),#e6b800)">🔒</div>
              <h4>Контроль и безопасность</h4>
              <p>Роли, аудит и шифрование — данные остаются внутри доверенной сети.</p>
            </div>

            <div class="adv-card" role="listitem">
              <div class="adv-icon" style="background:linear-gradient(180deg,var(--accent-red),#b71b1b)">📊</div>
              <h4>Готовность к BI</h4>
              <p>Стандартизованные форматы и API упрощают построение отчётности и дашбордов.</p>
            </div>

            <div class="adv-card" role="listitem">
              <div class="adv-icon" style="background:linear-gradient(180deg,#333, #111)">🤝</div>
              <h4>Коллаборация</h4>
              <p>Совместные проекты, репозитории данных и единые метрики для университетов.</p>
            </div>
          </div>

        </div>
      </section>

      <!-- CONTACT / CTA block -->
      <section id="contact" aria-labelledby="contact-title" style="padding:36px var(--container-padding);">
        <div class="wrap" style="display:grid;grid-template-columns:1fr 360px;gap:28px;align-items:start;">
          <div>
            <h2 id="contact-title">Связаться и подключиться</h2>
            <p class="muted">Оставьте контактные данные — мы подготовим пакет подключения и демонстрацию возможностей платформы.</p>

            <form id="contactForm" style="margin-top:16px;display:grid;gap:12px;" onsubmit="return sendForm(event)">
              <label class="small">
                <div class="mb-8">Организация / Университет</div>
                <input name="org" required placeholder="Например: КазНУ" style="width:100%;padding:10px;border-radius:8px;border:1px solid rgba(11,11,11,0.08)" />
              </label>

              <label class="small">
                <div class="mb-8">Контактный e-mail</div>
                <input name="email" type="email" required placeholder="contact@university.kz" style="width:100%;padding:10px;border-radius:8px;border:1px solid rgba(11,11,11,0.08)" />
              </label>

              <label class="small">
                <div class="mb-8">Кратко: цель подключения</div>
                <input name="purpose" placeholder="Отчётность / Исследования / Интеграция BI" style="width:100%;padding:10px;border-radius:8px;border:1px solid rgba(11,11,11,0.08)" />
              </label>

              <div style="display:flex;gap:8px;margin-top:6px">
                <button type="submit" class="btn btn-primary">Отправить заявку</button>
                <button type="button" class="btn btn-ghost" onclick="location.href='mailto:datateam@owa-datahub.kz'">Написать на почту</button>
              </div>

              <div id="formMessage" class="small muted mt-8" aria-live="polite"></div>
            </form>
          </div>

          <aside style="background:var(--card-bg);padding:16px;border-radius:12px;box-shadow:var(--shadow);">
            <h3 class="mb-8">Контакты</h3>
            <div class="small muted">
              <div><strong>OWA-DataHub</strong></div>
              <div>Эл. почта: <a href="mailto:datateam@owa-datahub.kz">datateam@owa-datahub.kz</a></div>
              <div>Телефон: <a href="tel:+77271234567">+7 (727) 123-45-67</a></div>
              <div class="mt-8">Офис: г. Алматы, Казахстан</div>
            </div>

            <hr style="margin:12px 0;border:none;border-top:1px solid rgba(11,11,11,0.04)">

            <div class="small muted">
              <strong>Университеты-участники (пример)</strong>
              <ul style="margin-top:8px">
                <li>Назарбаев Университет</li>
                <li>Ал-Фараби КазНУ</li>
                <li>Евразийский национальный университет им. Л. Н. Гумилёва</li>
                <li>Satbayev University</li>
                <li>Иные региональные вузы — подключение в процессе</li>
              </ul>
            </div>
          </aside>
        </div>
      </section>
    </main>

    <footer role="contentinfo">
      <div class="footer-grid">
        <div class="contacts">
          <div style="font-weight:700">OWA-DataHub</div>
          <div class="small muted mt-8">© <span id="year"></span> OWA-DataHub. Все права защищены.</div>
        </div>

        <div class="participants">
          <div style="font-weight:700">Университеты-участники</div>
          <ul aria-label="Список университетов-участников" style="margin-top:8px">
            <li>Назарбаев Университет</li>
            <li>Ал-Фараби КазНУ</li>
            <li>Евразийский национальный университет</li>
            <li>Satbayev University</li>
          </ul>
        </div>

        <div style="min-width:220px;">
          <div style="font-weight:700">Контакты</div>
          <div class="small muted mt-8">datateam@owa-datahub.kz<br>+7 (727) 123-45-67</div>
        </div>
      </div>
    </footer>
  </div>

  <script>
    // Простая логика формы: имитация отправки (клиентская демонстрация).
    function sendForm(e){
      e.preventDefault();
      const form = e.target;
      const msg = document.getElementById('formMessage');
      const submitBtn = form.querySelector('button[type="submit"]');

      submitBtn.disabled = true;
      submitBtn.textContent = 'Отправляем...';

      // Имитируем "отправку" — без сетевых вызовов, только демонстрация UX.
      setTimeout(() => {
        submitBtn.disabled = false;
        submitBtn.textContent = 'Отправить заявку';
        msg.textContent = 'Спасибо! Ваша заявка принята. Мы свяжемся в течение 2 рабочих дней.';
        form.reset();
      }, 900);
      return false;
    }

    // Smooth scroll for internal links
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', function(e){
        const href = this.getAttribute('href');
        if(href.length>1){
          const t = document.querySelector(href);
          if(t){
            e.preventDefault();
            t.scrollIntoView({behavior:'smooth',block:'start'});
            // update URL without jumping
            history.replaceState(null,'',href);
          }
        }
      });
    });

    // Footer year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
