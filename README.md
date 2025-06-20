<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Data Kelengkapan Apel</title>
  <link rel="icon" type="image/x-icon" href="https://raw.githubusercontent.com/hanajelek/dataapel/refs/heads/main/ppic_logo.png">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@600;400&display=swap');
    :root {
      --color-bg: #ffffff;
      --color-text-primary: #111827;
      --color-text-secondary: #6b7280;
      --color-accent: #000000;
      --color-card-bg: #f9fafb;
      --border-radius: 0.75rem;
      --shadow-light: 0 4px 12px rgba(0,0,0,0.07);
      --transition: 0.3s ease;
      --font-headline: 'Inter', sans-serif;
      --font-body: 'Inter', sans-serif;
    }
    *, *::before, *::after {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: var(--font-body);
      background: var(--color-bg);
      color: var(--color-text-primary);
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      min-height: 100vh;
      line-height: 1.55;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* Container & Layout */
    .container {
      max-width: 1200px;
      margin-left: auto;
      margin-right: auto;
      padding-left: 2rem;
      padding-right: 2rem;
      padding-top: 4rem;
      padding-bottom: 5rem;
      display: flex;
      flex-direction: column;
      gap: 3.5rem;
    }

    /* Header */
    header {
      position: sticky;
      top: 0;
      background-color: var(--color-bg);
      border-bottom: 1px solid #e5e7eb;
      z-index: 100;
      padding: 1rem 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: var(--shadow-light);
    }
    header .logo {
      font-family: var(--font-headline);
      font-weight: 800;
      font-size: 1.75rem;
      color: var(--color-text-primary);
      user-select: none;
      letter-spacing: 0.06em;
      cursor: default;
      position: sticky;
      top: 10px; 
      left: 80px;
    }
    nav a {
      font-weight: 600;
      margin-left: 2rem;
      color: var(--color-text-secondary);
      font-size: 1rem;
      transition: color var(--transition);
      padding: 0.15rem 0;
      position: relative;
      user-select: none;
      cursor: pointer;
    }
    nav a::after {
      content: "";
      position: absolute;
      width: 0;
      height: 2px;
      bottom: -4px;
      left: 50%;
      background-color: var(--color-accent);
      transition: width 0.3s ease, left 0.3s ease;
      border-radius: 1px;
    }
    nav a:hover, nav a:focus-visible {
      color: var(--color-accent);
    }
    nav a:hover::after, nav a:focus-visible::after {
      width: 100%;
      left: 0;
    }

    /* Hero Section */
    .hero {
      max-width: 700px;
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
      user-select: text;
    }
    .hero h1 {
      font-family: var(--font-headline);
      font-weight: 700;
      font-size: 3.5rem;
      line-height: 1.05;
      color: var(--color-text-primary);
      margin: 0;
      word-break: break-word;
    }
    .hero p {
      font-size: 1.125rem;
      color: var(--color-text-secondary);
      margin: 0;
      max-width: 540px;
      line-height: 1.5;
    }
    .hero .cta-button {
      margin-top: 2.5rem;
      background-color: var(--color-accent);
      color: #fff;
      font-weight: 700;
      font-size: 1.125rem;
      padding: 0.85rem 2.5rem;
      border-radius: var(--border-radius);
      border: none;
      cursor: pointer;
      align-self: flex-start;
      transition: background-color var(--transition);
      user-select: none;
    }
    .hero .cta-button:hover,
    .hero .cta-button:focus-visible {
      background-color: #222222;
      outline-offset: 3px;
    }

    /* Controls Section */
    .controls-section, .datetime-section {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      align-items: center;
      user-select: text;
      max-width: 640px;
    }
    .controls-section label, .datetime-section label {
      font-weight: 600;
      font-size: 1.125rem;
      color: var(--color-text-primary);
      flex-shrink: 0;
    }
    select, input[type=date], input[type=time] {
      background: var(--color-card-bg);
      color: var(--color-text-primary);
      font-size: 1rem;
      font-weight: 600;
      border-radius: var(--border-radius);
      border: 1.5px solid #d1d5db;
      padding: 0.5rem 1.25rem;
      cursor: pointer;
      transition: border-color var(--transition);
      min-width: 150px;
    }
    select:focus, input[type=date]:focus, input[type=time]:focus {
      outline: none;
      border-color: var(--color-accent);
      box-shadow: 0 0 6px var(--color-accent);
    }
    button.add-group {
      background-color: var(--color-accent);
      color: white;
      border: none;
      font-weight: 700;
      font-size: 1rem;
      padding: 0.55rem 1.5rem;
      border-radius: var(--border-radius);
      cursor: pointer;
      user-select: none;
      transition: background-color var(--transition);
    }
    button.add-group:hover,
    button.add-group:focus-visible {
      background-color: #222222;
      outline-offset: 3px;
    }

    /* Groups List */
    .groups-list {
      display: grid;
      grid-template-columns: 1fr;
      gap: 2.25rem;
      margin-top: 1rem;
    }
    @media(min-width: 640px) {
      .groups-list {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    /* Group Card */
    .group-card {
      background: var(--color-card-bg);
      border-radius: var(--border-radius);
      padding: 2rem 2.5rem;
      box-shadow: var(--shadow-light);
      display: flex;
      flex-direction: column;
      gap: 1.75rem;
      user-select: none;
      transition: box-shadow 0.3s ease;
    }
    .group-card:hover,
    .group-card:focus-within {
      box-shadow: 0 8px 24px rgba(0,0,0,0.12);
    }
    .group-name {
      font-weight: 700;
      font-size: 1.5rem;
      color: var(--color-text-primary);
      user-select: text;
    }

    /* Input/Output Rows */
    .io-row {
      display: flex;
      gap: 2rem;
    }
    .io-row label {
      flex: 1;
      display: flex;
      flex-direction: column;
      font-weight: 600;
      font-size: 1rem;
      color: var(--color-text-secondary);
      user-select: text;
    }
    input[type=number] {
      margin-top: 0.35rem;
      padding: 0.5rem 0.65rem;
      border-radius: var(--border-radius);
      border: 1.5px solid #d1d5db;
      font-size: 1.125rem;
      font-weight: 600;
      color: var(--color-text-primary);
      transition: border-color var(--transition);
      -moz-appearance: textfield;
    }
    input[type=number]::-webkit-inner-spin-button,
    input[type=number]::-webkit-outer-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }
    input[type=number]:focus {
      outline: none;
      border-color: var(--color-accent);
      box-shadow: 0 0 8px var(--color-accent);
    }

    /* Output row */
    .output-row {
      display: flex;
      justify-content: space-between;
      gap: 1.5rem;
      font-weight: 700;
      color: var(--color-text-primary);
      user-select: text;
      font-size: 1.125rem;
    }
    .output-item {
      flex: 1;
      text-align: center;
    }

    /* Members Section */
    .members-section {
      border-top: 1px solid #d1d5db;
      padding-top: 1.25rem;
      user-select: none;
    }
    .members-header {
      font-weight: 700;
      font-size: 1.125rem;
      color: var(--color-text-primary);
      margin-bottom: 1.1rem;
      user-select: text;
    }
    .member-list {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    .member-row {
      display: flex;
      gap: 1.25rem;
      align-items: center;
    }
    .member-row input[type=text] {
      flex: 1;
      border-radius: var(--border-radius);
      border: 1.5px solid #d1d5db;
      padding: 0.45rem 0.6rem;
      font-size: 1rem;
      transition: border-color var(--transition);
      font-weight: 500;
      color: var(--color-text-primary);
    }
    .member-row input[type=text]:focus {
      outline: none;
      border-color: var(--color-accent);
      box-shadow: 0 0 8px var(--color-accent);
    }
    .member-row button.remove-member {
      background: transparent;
      border: none;
      color: #ef4444;
      font-weight: 700;
      font-size: 1.4rem;
      line-height: 1;
      cursor: pointer;
      user-select: none;
      transition: color var(--transition);
      padding: 0;
      width: 30px;
      height: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      transition: color 0.2s ease;
    }
    .member-row button.remove-member:hover,
    .member-row button.remove-member:focus {
      color: #b91c1c;
      outline-offset: 3px;
    }
    button.add-member {
      margin-top: 0.9rem;
      background-color: #2563eb;
      color: white;
      border: none;
      border-radius: var(--border-radius);
      padding: 0.55rem 1.35rem;
      font-weight: 700;
      font-size: 1rem;
      cursor: pointer;
      user-select: none;
      align-self: flex-start;
      transition: background-color var(--transition);
    }
    button.add-member:hover,
    button.add-member:focus-visible {
      background-color: #1e40af;
      outline-offset: 3px;
    }

    /* Footer Buttons */
    .footer-buttons {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 4rem;
      user-select: none;
    }
    .footer-buttons button,
    .footer-buttons label.import-label {
      border-radius: var(--border-radius);
      border: none;
      padding: 0.85rem 2.25rem;
      font-weight: 700;
      font-size: 1.125rem;
      cursor: pointer;
      transition: background-color var(--transition);
      user-select: none;
      text-align: center;
    }
    button.export-btn {
      background-color: var(--color-accent);
      color: white;
    }
    button.export-btn:hover,
    button.export-btn:focus-visible {
      background-color: #222222;
      outline-offset: 3px;
    }
    label.import-label {
      background-color: var(--color-accent);
      color: white;
      display: inline-block;
      cursor: pointer;
      user-select: none;
    }
    label.import-label:hover,
    label.import-label:focus-visible {
      background-color: #222222;
      outline-offset: 3px;
    }
    label.import-label input[type=file] {
      display: none;
    }

    /* Info Text */
    .info-text {
      font-size: 1rem;
      color: var(--color-text-secondary);
      user-select: text;
      text-align: center;
      max-width: 720px;
      margin-left: auto;
      margin-right: auto;
      line-height: 1.5;
    }

    /* Utility Class for Visually Hidden */
    .visually-hidden {
      position: absolute !important;
      width: 1px !important;
      height: 1px !important;
      padding: 0 !important;
      margin: -1px !important;
      overflow: hidden !important;
      clip: rect(0,0,0,0) !important;
      white-space: nowrap !important;
      border: 0 !important;
    }

    /* Date/Time output container */
    .datetime-output {
      max-width: 640px;
      margin-top: 0.5rem;
      font-weight: 600;
      font-size: 1.125rem;
      color: var(--color-text-primary);
      user-select: text;
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }
    .datetime-output span {
      background: var(--color-card-bg);
      border-radius: var(--border-radius);
      padding: 0.45rem 1rem;
      box-shadow: var(--shadow-light);
    }

  </style>
</head>
<body>
  <header>
    <div class="logo" aria-label="Logo Pendataan Anggota Kelompok">PENDATAAN APEL</div>
    <img src="https://raw.githubusercontent.com/hanajelek/dataapel/refs/heads/main/ppic_logo.png" alt="Logo PPI" style="width: 40px; height: auto; position: absolute; top: 15px; left: 20px;">
  
    <nav aria-label="Navigasi utama">
      <a href="#main-content" tabindex="0">Mulai</a>
      <a href="#footer" tabindex="0">Kontrol</a>
    </nav>
  </header>

  <main class="container" id="main-content" role="main" aria-label="Konten utama aplikasi pendataan anggota kelompok">
    <section class="hero" aria-labelledby="hero-title hero-desc">
      <h1 id="hero-title">Pendataan Kelengkapan Apel Politeknik Penerbangan Indonesia Curug</h1>
      <p id="hero-desc">Input jumlah anggota, yang tidak hadir, dan keterangan. Sinkronisasi data mudah ke Excel. Gunakan secara offline maupun online dengan UI modern dan nyaman.</p>
      <button class="cta-button" id="btn-add-first-group" aria-label="Tambahkan kelompok pertama">Tambah Course Baru</button>
    </section>

    <section class="datetime-section" aria-label="Input manual hari, tanggal, dan waktu">
      <label for="input-hari">Hari</label>
      <select id="input-hari" aria-describedby="desc-hari">
        <option value="">Pilih hari</option>
        <option value="Senin">Senin</option>
        <option value="Selasa">Selasa</option>
        <option value="Rabu">Rabu</option>
        <option value="Kamis">Kamis</option>
        <option value="Jumat">Jumat</option>
        <option value="Sabtu">Sabtu</option>
        <option value="Minggu">Minggu</option>
      </select>
      <label for="input-tanggal">Tanggal</label>
      <input type="date" id="input-tanggal" aria-describedby="desc-tanggal" />

      <label for="input-waktu">Waktu</label>
      <input type="time" id="input-waktu" aria-describedby="desc-waktu" />
    </section>

    <div class="datetime-output" aria-live="polite" aria-atomic="true" role="region" aria-label="Preview hari, tanggal, dan waktu yang dipilih">
      <span id="output-hari">Hari: -</span>
      <span id="output-tanggal">Tanggal: -</span>
      <span id="output-waktu">Waktu: -</span>
    </div>

    <section class="controls-section" aria-label="Kontrol klasifikasi kelompok">
      <label for="classification-select">Pilih Tingkat:</label>
      <select id="classification-select" aria-controls="groups-list" aria-describedby="desc-classification">
        <option value="1">Tingkat 1</option>
        <option value="2">Tingkat 2</option>
        <option value="3">Tingkat 3</option>
        <option value="4">Tingkat 4</option>
      </select>
      <button type="button" class="add-group" id="btn-add-group" aria-label="Tambahkan kelompok pada klasifikasi yang dipilih">+ Tambah Course</button>
      <div id="desc-classification" class="visually-hidden">Pilih klasifikasi untuk menampilkan dan menambahkan kelompok.</div>
    </section>

    <section id="groups-list" class="groups-list" aria-live="polite" aria-relevant="additions removals" tabindex="0" aria-label="Daftar kelompok"></section>

    <section class="footer-buttons" id="footer" aria-label="Kontrol ekspor dan impor data">
      <button class="export-btn" id="btn-export" aria-label="Ekspor data ke file Excel">Export ke Excel</button>
      <label for="import-file" class="import-label" aria-label="Import data dari file Excel">
        Import dari Excel
        <input type="file" id="import-file" accept=".xlsx" aria-describedby="desc-import" />
      </label>
      <span id="desc-import" class="visually-hidden">Pilih file Excel (.xlsx) untuk mengimpor data kelompok.</span>
    </section>

    <p class="info-text">* Jumlah: total anggota kelompok. Kurang: anggota yang tidak hadir. Hadir dihitung otomatis. Tambahkan anggota kelompok dengan <code>nama</code> dan <code>keterangan</code> (misal: <em>rafi, duty pendidikan</em>).</p>
  </main>

  <script src="https://cdn.jsdelivr.net/npm/xlsx@0.18.5/dist/xlsx.full.min.js" crossorigin="anonymous" defer></script>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const classificationSelect = document.getElementById('classification-select');
      const groupsList = document.getElementById('groups-list');
      const btnAddGroup = document.getElementById('btn-add-group');
      const btnAddFirstGroup = document.getElementById('btn-add-first-group');
      const btnExport = document.getElementById('btn-export');
      const importFileInput = document.getElementById('import-file');

      // New inputs for day, date, time
      const inputHari = document.getElementById('input-hari');
      const inputTanggal = document.getElementById('input-tanggal');
      const inputWaktu = document.getElementById('input-waktu');

      const outputHari = document.getElementById('output-hari');
      const outputTanggal = document.getElementById('output-tanggal');
      const outputWaktu = document.getElementById('output-waktu');

      // Struktur data kelompok
      let dataStore = {1: [], 2: [], 3: [], 4: []};

      const generateId = () => 'id-' + Math.random().toString(36).substr(2, 9);

      // Fungsi untuk render grup
      function renderGroups(classification) {
        groupsList.innerHTML = '';
        const groups = dataStore[classification] || [];
        if (groups.length === 0) {
          groupsList.innerHTML = `<p style="color:#6b7280; font-style: italic; user-select: text;">Belum ada kelompok dalam klasifikasi ini.</p>`;
          return;
        }
        groups.forEach(group => {
          const hadir = Math.max(0, group.jumlah - group.kurang);
          const groupCard = document.createElement('article');
          groupCard.className = 'group-card';
          groupCard.setAttribute('tabindex', '0');
          groupCard.setAttribute('aria-label', `Kelompok ${group.groupName}, jumlah anggota ${group.jumlah}, kurang hadir ${group.kurang}, hadir ${hadir}`);

          groupCard.innerHTML = `
            <div class="group-name">${group.groupName}</div>
            <div class="io-row" style="margin-bottom: 0.5rem;">
              <label for="jumlah-${group.id}">Jumlah
                <input type="number" min="0" id="jumlah-${group.id}" value="${group.jumlah}" aria-describedby="jumlah-desc-${group.id}" />
              </label>
              <label for="kurang-${group.id}">Kurang
                <input type="number" min="0" id="kurang-${group.id}" value="${group.kurang}" aria-describedby="kurang-desc-${group.id}" />
              </label>
            </div>
            <div class="output-row" aria-live="polite" aria-atomic="true">
              <div class="output-item" id="out-jumlah-${group.id}">Jumlah: ${group.jumlah}</div>
              <div class="output-item" id="out-kurang-${group.id}">Kurang: ${group.kurang}</div>
              <div class="output-item" id="out-hadir-${group.id}">Hadir: ${hadir}</div>
            </div>
            <section class="members-section" aria-label="Anggota kelompok">
              <div class="members-header">Anggota Kelompok (Nama, Keterangan)</div>
              <div class="member-list" id="members-list-${group.id}"></div>
              <button type="button" class="add-member" aria-label="Tambah anggota kelompok">+ Yang tidak hadir</button>
            </section>
          `;

          groupsList.appendChild(groupCard);

          // Input jumlah dan kurang event
          const inputJumlah = groupCard.querySelector(`#jumlah-${group.id}`);
          const inputKurang = groupCard.querySelector(`#kurang-${group.id}`);

          inputJumlah.addEventListener('input', e => {
            let val = parseInt(e.target.value);
            if (isNaN(val) || val < 0) val = 0;
            if (val < group.kurang) {
              group.kurang = val;
              inputKurang.value = val;
            }
            group.jumlah = val;
            updateOutputs(group);
          });

          inputKurang.addEventListener('input', e => {
            let val = parseInt(e.target.value);
            if (isNaN(val) || val < 0) val = 0;
            if (val > group.jumlah) {
              val = group.jumlah;
              e.target.value = val;
            }
            group.kurang = val;
            updateOutputs(group);
          });

          function updateOutputs(gr) {
            const hadirCount = Math.max(0, gr.jumlah - gr.kurang);
            document.getElementById(`out-jumlah-${gr.id}`).textContent = 'Jumlah: ' + gr.jumlah;
            document.getElementById(`out-kurang-${gr.id}`).textContent = 'Kurang: ' + gr.kurang;
            document.getElementById(`out-hadir-${gr.id}`).textContent = 'Hadir: ' + hadirCount;
          }

          // Manage Members list
          const membersList = groupCard.querySelector(`#members-list-${group.id}`);
          const btnAddMember = groupCard.querySelector('.add-member');

          function renderMembers() {
            membersList.innerHTML = '';
            if (!group.members || group.members.length === 0) {
              membersList.innerHTML = '<p style="color:#6b7280; font-style: italic; user-select: text;">Belum ada anggota.</p>';
              return;
            }
            group.members.forEach(member => {
              const memberRow = document.createElement('div');
              memberRow.className = 'member-row';
              memberRow.setAttribute('role', 'group');
              memberRow.setAttribute('aria-label', `Anggota: nama ${member.nama || 'kosong'}, keterangan ${member.keterangan || 'kosong'}`);

              memberRow.innerHTML = `
                <input type="text" class="member-nama" placeholder="Nama" aria-label="Nama anggota" value="${member.nama}" />
                <input type="text" class="member-keterangan" placeholder="Keterangan" aria-label="Keterangan anggota" value="${member.keterangan}" />
                <button type="button" class="remove-member" aria-label="Hapus anggota">&times;</button>
              `;

              membersList.appendChild(memberRow);

              const inputNama = memberRow.querySelector('.member-nama');
              const inputKet = memberRow.querySelector('.member-keterangan');
              const btnRemove = memberRow.querySelector('.remove-member');

              inputNama.addEventListener('input', e => {
                member.nama = e.target.value;
              });
              inputKet.addEventListener('input', e => {
                member.keterangan = e.target.value;
              });
              btnRemove.addEventListener('click', () => {
                group.members = group.members.filter(m => m.id !== member.id);
                renderMembers();
              });
            });
          }

          btnAddMember.addEventListener('click', () => {
            if (!group.members) group.members = [];
            group.members.push({
              id: generateId(),
              nama: '',
              keterangan: ''
            });
            renderMembers();
          });

          if (!group.members) group.members = [];
          renderMembers();
        });
      }

      // Add new group dialog
      function addNewGroup(classification) {
        const groupName = prompt('Masukkan nama kelompok baru untuk klasifikasi ' + classification + ':');
        if (groupName && groupName.trim().length > 0) {
          const cleanName = groupName.trim();
          const exists = dataStore[classification].some(g => g.groupName.toLowerCase() === cleanName.toLowerCase());
          if (exists) {
            alert('Nama kelompok sudah ada di klasifikasi ini. Silakan coba nama lain.');
            return;
          }
          dataStore[classification].push({
            id: generateId(),
            groupName: cleanName,
            jumlah: 0,
            kurang: 0,
            members: []
          });
          renderGroups(classification);
        }
      }

      // Export data to Excel (members excluded)
      function exportToExcel() {
        const wb = XLSX.utils.book_new();
        Object.keys(dataStore).forEach(classif => {
          const groups = dataStore[classif];
          const ws_data = [['Nama Kelompok', 'Jumlah', 'Kurang', 'Hadir']];
          groups.forEach(g => {
            ws_data.push([g.groupName, g.jumlah, g.kurang, Math.max(0, g.jumlah - g.kurang)]);
          });
          const ws = XLSX.utils.aoa_to_sheet(ws_data);
          XLSX.utils.book_append_sheet(wb, ws, 'Klasifikasi ' + classif);
        });
        XLSX.writeFile(wb, 'attendance-data.xlsx');
      }

      // Import Excel file (ignore members)
      function importFromExcel(file) {
        const reader = new FileReader();
        reader.onload = e => {
          const data = new Uint8Array(e.target.result);
          const wb = XLSX.read(data, {type: 'array'});
          dataStore = {1: [], 2: [], 3: [], 4: []};
          wb.SheetNames.forEach(sheetName => {
            const match = sheetName.match(/Klasifikasi\s*(\d)/i);
            if (match) {
              const classification = match[1];
              const ws = wb.Sheets[sheetName];
              const rows = XLSX.utils.sheet_to_json(ws, {header:1});
              for (let i = 1; i < rows.length; i++) {
                const row = rows[i];
                if (row && row.length >= 3) {
                  const groupName = row[0] ? row[0].toString() : '';
                  const jumlah = parseInt(row[1]) || 0;
                  const kurang = parseInt(row[2]) || 0;
                  if (groupName.trim().length > 0) {
                    dataStore[classification].push({
                      id: generateId(),
                      groupName: groupName.trim(),
                      jumlah: jumlah >= 0 ? jumlah : 0,
                      kurang: kurang >= 0 ? Math.min(kurang, jumlah) : 0,
                      members: []
                    });
                  }
                }
              }
            }
          });
          renderGroups(classificationSelect.value);
          alert('Data berhasil diimpor dari Excel.');
        };
        reader.readAsArrayBuffer(file);
      }

      // Event to handle day, date, time changes
      function updateDateTimePreview() {
        const hariVal = inputHari.value || '-';
        const tanggalVal = inputTanggal.value ? new Date(inputTanggal.value).toLocaleDateString('id-ID', {year:'numeric',month:'long',day:'numeric'}) : '-';
        const waktuVal = inputWaktu.value || '-';
        outputHari.textContent = 'Hari: ' + hariVal;
        outputTanggal.textContent = 'Tanggal: ' + tanggalVal;
        outputWaktu.textContent = 'Waktu: ' + waktuVal;
      }

      inputHari.addEventListener('change', updateDateTimePreview);
      inputTanggal.addEventListener('change', updateDateTimePreview);
      inputWaktu.addEventListener('change', updateDateTimePreview);

      classificationSelect.addEventListener('change', e => {
        renderGroups(e.target.value);
      });

      btnAddGroup.addEventListener('click', () => {
        addNewGroup(classificationSelect.value);
      });

      btnAddFirstGroup.addEventListener('click', () => {
        addNewGroup(classificationSelect.value);
      });

      btnExport.addEventListener('click', () => {
        exportToExcel();
      });

      importFileInput.addEventListener('change', e => {
        const file = e.target.files[0];
        if (file) {
          importFromExcel(file);
          importFileInput.value = null;
        }
      });

      renderGroups(classificationSelect.value);
      updateDateTimePreview();

      // Utility visually hidden style for ARIA
      const styleVH = document.createElement('style');
      styleVH.textContent = `.visually-hidden { position: absolute !important; width: 1px !important; height: 1px !important; padding: 0 !important; margin: -1px !important; overflow: hidden !important; clip: rect(0,0,0,0) !important; white-space: nowrap !important; border: 0 !important; }`;
      document.head.appendChild(styleVH);
    });
  </script>
</body>
</html>
