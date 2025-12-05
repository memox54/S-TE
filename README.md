<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <title>Dijital Kaizen Platformu</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      background: #0f172a;
      color: #e5e7eb;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 20px;
    }

    .app {
      width: 100%;
      max-width: 960px;
    }

    header {
      margin-bottom: 20px;
    }

    .title {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .subtitle {
      font-size: 0.95rem;
      color: #9ca3af;
    }

    main {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .card {
      background: #020617;
      border-radius: 14px;
      padding: 18px 18px 20px;
      border: 1px solid #1f2937;
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.3);
    }

    .hidden {
      display: none;
    }

    .card-header {
      margin-bottom: 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
    }

    .card-title {
      font-size: 1.05rem;
      font-weight: 600;
    }

    .badge {
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      padding: 3px 8px;
      border-radius: 999px;
      background: #1d4ed8;
      color: #e5e7eb;
      white-space: nowrap;
    }

    label {
      font-size: 0.85rem;
      display: block;
      margin-bottom: 4px;
      color: #9ca3af;
    }

    select,
    input[type="text"],
    textarea {
      width: 100%;
      border-radius: 10px;
      border: 1px solid #374151;
      background: #020617;
      color: #e5e7eb;
      padding: 8px 10px;
      font-size: 0.9rem;
      margin-bottom: 10px;
      outline: none;
      transition: border 0.15s ease, box-shadow 0.15s ease;
    }

    select:focus,
    input[type="text"]:focus,
    textarea:focus {
      border-color: #3b82f6;
      box-shadow: 0 0 0 1px #3b82f6;
    }

    textarea {
      min-height: 80px;
      resize: vertical;
    }

    .row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .row > div {
      flex: 1;
      min-width: 180px;
    }

    .field-description {
      font-size: 0.75rem;
      color: #6b7280;
      margin-top: -6px;
      margin-bottom: 8px;
    }

    .btn {
      border: none;
      border-radius: 999px;
      padding: 8px 16px;
      font-size: 0.9rem;
      cursor: pointer;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      margin-top: 6px;
      background: #2563eb;
      color: white;
      transition: background 0.15s ease, transform 0.08s ease;
    }

    .btn.secondary {
      background: transparent;
      border: 1px solid #4b5563;
      color: #e5e7eb;
    }

    .btn:active {
      transform: scale(0.97);
    }

    .btn:hover {
      background: #1d4ed8;
    }

    .btn.secondary:hover {
      background: #111827;
    }

    .chips {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 4px;
    }

    .chip {
      padding: 4px 10px;
      border-radius: 999px;
      border: 1px solid #4b5563;
      font-size: 0.75rem;
      color: #d1d5db;
    }

    .info-text {
      font-size: 0.8rem;
      color: #9ca3af;
      margin-top: 6px;
    }

    .report-section {
      margin-top: 12px;
      padding-top: 10px;
      border-top: 1px dashed #1f2937;
    }

    .report-section h3 {
      font-size: 0.92rem;
      margin-bottom: 4px;
      color: #d1d5db;
    }

    .report-section p,
    .report-section ul {
      font-size: 0.82rem;
      color: #9ca3af;
      line-height: 1.5;
    }

    .report-section ul {
      padding-left: 18px;
      margin-top: 4px;
    }

    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 8px;
    }

    .pill {
      font-size: 0.72rem;
      padding: 3px 8px;
      border-radius: 999px;
      border: 1px solid #374151;
      color: #9ca3af;
    }

    .report-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 6px;
      font-size: 0.78rem;
      color: #6b7280;
    }

    .report-meta span {
      display: inline-flex;
      align-items: center;
      gap: 4px;
    }

    .small-pill {
      border-radius: 999px;
      border: 1px solid #1f2937;
      padding: 2px 6px;
      font-size: 0.7rem;
      color: #9ca3af;
    }

    @media (max-width: 640px) {
      .title {
        font-size: 1.4rem;
      }
      .card {
        padding: 14px 12px 16px;
      }
    }
  </style>
</head>
<body>
  <div class="app">
    <header>
      <div class="title">Dijital Kaizen Platformu</div>
      <div class="subtitle">
        Fabrikadaki sürekli iyileştirme (Kaizen) sürecini, basit bir web arayüzü ile dijitale taşı.
      </div>
    </header>

    <main>
      <!-- ADIM 1: Firma Seçimi -->
      <section class="card" id="step-1">
        <div class="card-header">
          <div class="card-title">1. Adım – Hangi firmada çalışıyorsun?</div>
          <div class="badge">Firma Seç</div>
        </div>

        <label for="company-select">Firma</label>
        <select id="company-select">
          <option value="">– Firma seçin –</option>
        </select>
        <div class="field-description">
          Listede olmayan bir firmaysa, ileride manuel ekleme özelliği ekleyebilirsin.
        </div>

        <button class="btn" id="go-step-2-btn">
          Devam et
          <span>→</span>
        </button>
      </section>

      <!-- ADIM 2: Sorun Girişi -->
      <section class="card hidden" id="step-2">
        <div class="card-header">
          <div class="card-title">
            2. Adım – Sorunu tanımla
          </div>
          <div class="badge" id="selected-company-badge">Firma</div>
        </div>

        <form id="problem-form">
          <div class="row">
            <div>
              <label for="category-select">Kategori</label>
              <select id="category-select" required>
                <option value="">– Kategori seçin –</option>
              </select>
              <div class="field-description">
                Sorunun en çok hangi alana dokunduğunu seç.
              </div>
            </div>
            <div>
              <label for="impact-select">Etkilenen Alan</label>
              <select id="impact-select" required>
                <option value="">– Seçin –</option>
                <option value="üretim_verimliliği">Üretim Verimliliği</option>
                <option value="kalite">Kalite</option>
                <option value="iş_guvenligi">İş Güvenliği</option>
                <option value="ergonomi">Ergonomi</option>
                <option value="maliyet">Maliyet</option>
                <option value="enerji">Enerji / İsraf</option>
              </select>
              <div class="field-description">
                Bu sorun çözülürse nerede iyileşme beklersin?
              </div>
            </div>
          </div>

          <label for="problem-title">Sorunun kısa başlığı</label>
          <input
            type="text"
            id="problem-title"
            placeholder="Örn: Pres hattında gereksiz bekleme"
            required
          />

          <label for="problem-description">Mevcut durum / detaylı anlatım</label>
          <textarea
            id="problem-description"
            placeholder="Sorunun nerede, ne zaman, kimler tarafından, nasıl yaşandığını somut örneklerle anlat..."
            required
          ></textarea>

          <div class="field-description">
            Ne kadar somut yazarsan, oluşturulan kaizen sunumu o kadar net olur.
          </div>

          <div class="row">
            <div>
              <label for="root-cause">Varsaydığın kök neden (opsiyonel)</label>
              <input
                type="text"
                id="root-cause"
                placeholder="Örn: Standart iş talimatı eksikliği, eğitim yetersizliği..."
              />
            </div>
            <div>
              <label for="attachment">Fotoğraf / doküman (şimdilik yalnızca seçim)</label>
              <input type="file" id="attachment" />
              <div class="field-description">
                Frontend tarafında şimdilik sadece isim tutuluyor, backend ile dosya yükleme eklenebilir.
              </div>
            </div>
          </div>

          <div class="chips">
            <span class="chip">PDCA döngüsüne göre raporlanacak</span>
            <span class="chip">Kaizen formatında çıktı</span>
            <span class="chip">Yöneticiye sunuma hazır</span>
          </div>

          <button type="submit" class="btn">
            Kaizen Sunumu Oluştur
            <span>🧠</span>
          </button>
          <button type="button" class="btn secondary" id="back-to-step-1">
            ← Firma Değiştir
          </button>
        </form>
      </section>

      <!-- ADIM 3: Kaizen Raporu -->
      <section class="card hidden" id="step-3">
        <div class="card-header">
          <div class="card-title">3. Adım – Otomatik Kaizen Sunumu</div>
          <div class="badge">Ön İzleme</div>
        </div>

        <div id="report-header"></div>

        <div class="report-section" id="report-current-state"></div>
        <div class="report-section" id="report-root-cause"></div>
        <div class="report-section" id="report-solutions"></div>
        <div class="report-section" id="report-pdca"></div>
        <div class="report-section" id="report-gain"></div>

        <div class="info-text" style="margin-top: 10px;">
          Bu yalnızca frontend tarafında çalışan bir demo. Backend + yapay zekâ ve “PDF indir” butonu ekleyerek
          gerçek bir projeye dönüştürebilirsin.
        </div>

        <div class="pill-row" id="report-tags"></div>

        <div class="report-meta" id="report-meta"></div>

        <button class="btn secondary" style="margin-top: 12px;" id="edit-problem-btn">
          ← Soruyu Düzenle
        </button>
      </section>
    </main>
  </div>

  <script>
    // -----------------------------
    // Sabit veri: Firmalar ve kategoriler
    // -----------------------------
    const COMPANIES = [
      "Sigma Elektrik",
      "Etien Elektrik",
      "Hilkar Elektrik",
      "Elkon Enerji",
      "Tem Kablo",
      "ATS Elektrik",
      "Federal Elektrik",
      "Erel Makina",
      "Vios Elektrik",
      "ATG Savunma Sanayi",
      "Sarpan Enerji",
      "Diğer"
    ];

    const CATEGORIES = [
      "Üretim (Verimlilik / Beklemeler)",
      "Kalite (Hata, Fire, Yeniden İş)",
      "İş Güvenliği (Risk, Kaza, Neredeyse kaza)",
      "Ergonomi (Zorlayıcı hareket, gereksiz yürüme)",
      "Malzeme Akışı / Lojistik",
      "Makine Arızası / Bakım",
      "5S / Düzen Uygunsuzlukları",
      "Enerji / İsraf (Su, elektrik, hava, malzeme)"
    ];

    // -----------------------------
    // DOM Referansları
    // -----------------------------
    const companySelect = document.getElementById("company-select");
    const goStep2Btn = document.getElementById("go-step-2-btn");
    const step1 = document.getElementById("step-1");
    const step2 = document.getElementById("step-2");
    const step3 = document.getElementById("step-3");
    const selectedCompanyBadge = document.getElementById("selected-company-badge");
    const categorySelect = document.getElementById("category-select");
    const problemForm = document.getElementById("problem-form");
    const backToStep1Btn = document.getElementById("back-to-step-1");
    const editProblemBtn = document.getElementById("edit-problem-btn");

    // Rapor alanları
    const reportHeaderEl = document.getElementById("report-header");
    const reportCurrentStateEl = document.getElementById("report-current-state");
    const reportRootCauseEl = document.getElementById("report-root-cause");
    const reportSolutionsEl = document.getElementById("report-solutions");
    const reportPdcaEl = document.getElementById("report-pdca");
    const reportGainEl = document.getElementById("report-gain");
    const reportTagsEl = document.getElementById("report-tags");
    const reportMetaEl = document.getElementById("report-meta");

    // Form alanları
    const problemTitleInput = document.getElementById("problem-title");
    const problemDescriptionInput = document.getElementById("problem-description");
    const rootCauseInput = document.getElementById("root-cause");
    const impactSelect = document.getElementById("impact-select");
    const attachmentInput = document.getElementById("attachment");

    // -----------------------------
    // Başlangıçta seçim alanlarını doldur
    // -----------------------------
    function initSelectOptions() {
      COMPANIES.forEach((company) => {
        const option = document.createElement("option");
        option.value = company;
        option.textContent = company;
        companySelect.appendChild(option);
      });

      CATEGORIES.forEach((cat) => {
        const option = document.createElement("option");
        option.value = cat;
        option.textContent = cat;
        categorySelect.appendChild(option);
      });
    }

    initSelectOptions();

    // -----------------------------
    // Adım geçişleri
    // -----------------------------
    goStep2Btn.addEventListener("click", () => {
      const selectedCompany = companySelect.value;
      if (!selectedCompany) {
        alert("Lütfen bir firma seçin.");
        return;
      }
      selectedCompanyBadge.textContent = selectedCompany;
      step1.classList.add("hidden");
      step2.classList.remove("hidden");
      step3.classList.add("hidden");
    });

    backToStep1Btn.addEventListener("click", () => {
      step1.classList.remove("hidden");
      step2.classList.add("hidden");
      step3.classList.add("hidden");
    });

    editProblemBtn.addEventListener("click", () => {
      step1.classList.add("hidden");
      step2.classList.remove("hidden");
      step3.classList.add("hidden");
    });

    // -----------------------------
    // Basit skor hesaplama (gösterim amaçlı)
    // -----------------------------
    function calculateImprovementScore(category, impact) {
      let base = 50;
      if (category.toLowerCase().includes("iş güvenliği")) base += 20;
      if (category.toLowerCase().includes("kalite")) base += 10;
      if (impact === "üretim_verimliliği") base += 10;
      if (impact === "iş_guvenligi") base += 15;
      if (impact === "ergonomi") base += 8;
      if (impact === "enerji") base += 6;
      if (impact === "maliyet") base += 8;

      if (base > 95) base = 95;
      if (base < 40) base = 40;

      return base;
    }

    // -----------------------------
    // Rapor oluşturma
    // -----------------------------
    function createKaizenReport(data) {
      const { company, category, title, description, rootCause, impact, attachmentName } = data;

      const score = calculateImprovementScore(category, impact);
      const today = new Date();
      const dateStr = today.toLocaleDateString("tr-TR", {
        day: "2-digit",
        month: "2-digit",
        year: "numeric"
      });

      // Başlık ve meta
      reportHeaderEl.innerHTML = `
        <div style="display:flex;justify-content:space-between;align-items:flex-start;gap:8px;">
          <div>
            <div style="font-size:1rem;font-weight:600;margin-bottom:2px;">
              Kaizen Önerisi – ${title || "Başlık belirtilmedi"}
            </div>
            <div style="font-size:0.82rem;color:#9ca3af;">
              Firma: <span class="small-pill">${company}</span>
              &nbsp;|&nbsp;
              Kategori: <span class="small-pill">${category}</span>
            </div>
          </div>
          <div style="text-align:right;">
            <div style="font-size:0.75rem;color:#6b7280;">Oluşturma Tarihi</div>
            <div style="font-size:0.85rem;">${dateStr}</div>
            <div style="margin-top:4px;font-size:0.75rem;color:#22c55e;">
              Tahmini İyileşme Potansiyeli: <strong>%${score}</strong>
            </div>
          </div>
        </div>
      `;

      // Mevcut durum
      reportCurrentStateEl.innerHTML = `
        <h3>1. Mevcut Durum ve Problem Tanımı</h3>
        <p>
          ${description}
        </p>
      `;

      // Kök neden
      const rootText =
        rootCause && rootCause.trim().length > 0
          ? rootCause
          : "İlk değerlendirmeye göre kök neden; standart iş tanımlarının net olmaması, çalışanların farklı yöntemler kullanması ve sürecin düzenli olarak takip edilmemesi olabilir.";

      reportRootCauseEl.innerHTML = `
        <h3>2. Kök Neden Analizi (Neden–Neden?)</h3>
        <p>
          Öneriyi yapan kişinin ön değerlendirmesine göre kök neden:
          <br/><br/>
          <strong>${rootText}</strong>
        </p>
        <p style="margin-top:6px;">
          Detaylı analiz için 5N1K ve Neden–Neden analizi ile ekip çalışması yapılmalıdır.
        </p>
      `;

      // Çözüm önerileri
      reportSolutionsEl.innerHTML = `
        <h3>3. Çözüm Önerileri</h3>
        <ul>
          <li><strong>Sıfır maliyet:</strong> Mevcut süreç için standart iş talimatı oluşturulması, herkesin aynı yöntemle çalışmasının sağlanması.</li>
          <li><strong>Düşük maliyet:</strong> Süreçteki gereksiz hareket ve beklemeleri azaltacak küçük düzenlemeler (yerleşim, etiketleme, görsel yönetim vb.).</li>
          <li><strong>Yatırım gerektiren:</strong> Gerekirse ekipman iyileştirmesi, otomasyon veya yardımcı aparat tasarlanması.</li>
        </ul>
      `;

      // PDCA
      reportPdcaEl.innerHTML = `
        <h3>4. Uygulama Planı (PDCA)</h3>
        <ul>
          <li><strong>Plan (Planla):</strong> Mevcut durum ölçümleri yapılır, hedef değer belirlenir, görev ve sorumlular tanımlanır.</li>
          <li><strong>Do (Uygula):</strong> Seçilen çözüm(ler) küçük ölçekte veya pilot alanda uygulanır.</li>
          <li><strong>Check (Kontrol Et):</strong> Öncesi-sonrası veriler karşılaştırılır; hedefe ne kadar yaklaşıldığı analiz edilir.</li>
          <li><strong>Act (Önlem Al / Standartlaştır):</strong> İyileştirme kalıcı hale getirilir, talimatlar güncellenir ve diğer alanlara yaygınlaştırma değerlendirilir.</li>
        </ul>
      `;

      // Beklenen kazanç
      const gainText = (() => {
        switch (impact) {
          case "üretim_verimliliği":
            return "Hattın çevrim süresinde azalma, birim zamanda üretilen adet sayısında artış ve gereksiz beklemelerde azalma beklenmektedir.";
          case "kalite":
            return "Hata oranlarında düşüş, yeniden iş miktarında azalma ve müşteri şikayetlerinde azalma beklenmektedir.";
          case "iş_guvenligi":
            return "Risk seviyesinde düşüş, iş kazası veya neredeyse kaza sayısında azalma ve çalışan güven algısında artış beklenmektedir.";
          case "ergonomi":
            return "Çalışan yorgunluğunda azalma, uzun vadede mesleki rahatsızlık riskinde düşüş ve iş motivasyonunda artış beklenmektedir.";
          case "enerji":
            return "Enerji tüketiminde düşüş, israf edilen kaynaklarda azalma ve sürdürülebilirlik göstergelerinde iyileşme beklenmektedir.";
          case "maliyet":
            return "Doğrudan üretim maliyetlerinde, fire ve yeniden iş maliyetlerinde azalma beklenmektedir.";
          default:
            return "Süreç genelinde verimlilik artışı, kalite iyileşmesi ve çalışan memnuniyetinde iyileşme beklenmektedir.";
        }
      })();

      reportGainEl.innerHTML = `
        <h3>5. Beklenen Kazanımlar</h3>
        <p>${gainText}</p>
      `;

      // Etiketler
      reportTagsEl.innerHTML = "";
      const tags = [
        "Kaizen",
        "Sürekli İyileştirme",
        category,
        impact.replace(/_/g, " "),
        "PDCA",
        "Saha Gözlemi"
      ];

      tags.forEach((tag) => {
        const span = document.createElement("span");
        span.className = "pill";
        span.textContent = tag;
        reportTagsEl.appendChild(span);
      });

      // Meta bilgi
      const metaItems = [];
      metaItems.push(`<span>📁 Firma: <strong>${company}</strong></span>`);
      if (attachmentName) {
        metaItems.push(`<span>📎 Ek: ${attachmentName}</span>`);
      }
      metaItems.push(`<span>🧮 Tahmini İyileşme Potansiyeli: %${score}</span>`);
      metaItems.push(`<span>🧷 Durum: Taslak Kaizen Raporu</span>`);

      reportMetaEl.innerHTML = metaItems.join("");
    }

    // -----------------------------
    // Form submit – Rapor oluştur
    // -----------------------------
    problemForm.addEventListener("submit", (event) => {
      event.preventDefault();

      const company = companySelect.value;
      const category = categorySelect.value;
      const title = problemTitleInput.value.trim();
      const description = problemDescriptionInput.value.trim();
      const rootCause = rootCauseInput.value.trim();
      const impact = impactSelect.value;
      const attachmentName = attachmentInput.files[0]?.name || "";

      if (!company || !category || !title || !description || !impact) {
        alert("Lütfen zorunlu alanları doldurun.");
        return;
      }

      const data = {
        company,
        category,
        title,
        description,
        rootCause,
        impact,
        attachmentName
      };

      createKaizenReport(data);

      // Adım değişimi
      step2.classList.add("hidden");
      step3.classList.remove("hidden");
      step1.classList.add("hidden");
    });
  </script>
</body>
</html>
