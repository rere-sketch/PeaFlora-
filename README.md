# PeaFlora-
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>PeaFlora - Jamu Telang & Millecrepes Telang</title>
  <style>
    /* Reset dan style dasar */
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background: #f9f9f9;
      color: #333;
    }
    header {
      background: #4a90e2;
      color: white;
      padding: 1.5rem 2rem;
      text-align: center;
      font-size: 2rem;
      font-weight: 700;
      letter-spacing: 2px;
    }
    nav {
      background: #357ABD;
      display: flex;
      justify-content: center;
      gap: 1rem;
      padding: 0.75rem 0;
    }
    nav button {
      background: transparent;
      border: 2px solid white;
      color: white;
      padding: 0.5rem 1rem;
      font-weight: 600;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s, color 0.3s;
    }
    nav button:hover {
      background: white;
      color: #357ABD;
    }
    main {
      max-width: 900px;
      margin: 2rem auto;
      padding: 0 1rem;
    }
    section {
      margin-bottom: 3rem;
      background: white;
      border-radius: 10px;
      box-shadow: 0 0 10px rgb(0 0 0 / 0.1);
      padding: 1.5rem;
    }
    section h2 {
      color: #4a90e2;
      margin-bottom: 1rem;
      font-weight: 700;
      border-bottom: 2px solid #4a90e2;
      padding-bottom: 0.5rem;
    }
    .product {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
      align-items: center;
    }
    .product img {
      max-width: 250px;
      border-radius: 10px;
      box-shadow: 0 0 8px rgb(0 0 0 / 0.15);
      cursor: pointer;
      transition: transform 0.3s;
    }
    .product img:hover {
      transform: scale(1.05);
    }
    .product-description {
      flex: 1;
      min-width: 250px;
    }
    .editable {
      border-bottom: 1px dashed transparent;
      cursor: pointer;
      transition: border-color 0.3s;
    }
    .editable:hover {
      border-color: #4a90e2;
    }
    /* Modal edit */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0; top: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
      justify-content: center;
      align-items: center;
      padding: 1rem;
    }
    .modal.active {
      display: flex;
    }
    .modal-content {
      background: white;
      border-radius: 10px;
      max-width: 500px;
      width: 100%;
      padding: 1.5rem;
      box-shadow: 0 0 15px rgb(0 0 0 / 0.3);
      position: relative;
    }
    .modal-content h3 {
      margin-top: 0;
      color: #4a90e2;
    }
    .modal-content label {
      display: block;
      margin: 1rem 0 0.5rem;
      font-weight: 600;
    }
    .modal-content input[type="text"],
    .modal-content textarea {
      width: 100%;
      padding: 0.5rem;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-radius: 5px;
      resize: vertical;
    }
    .modal-content input[type="file"] {
      margin-top: 0.5rem;
    }
    .modal-buttons {
      margin-top: 1.5rem;
      text-align: right;
    }
    .modal-buttons button {
      background: #4a90e2;
      border: none;
      color: white;
      padding: 0.5rem 1rem;
      font-weight: 600;
      border-radius: 5px;
      cursor: pointer;
      margin-left: 0.5rem;
      transition: background 0.3s;
    }
    .modal-buttons button:hover {
      background: #357ABD;
    }
    .close-btn {
      position: absolute;
      top: 0.5rem;
      right: 0.75rem;
      font-size: 1.5rem;
      color: #999;
      cursor: pointer;
      font-weight: 700;
    }
    .close-btn:hover {
      color: #4a90e2;
    }
    footer {
      text-align: center;
      padding: 1rem 0;
      background: #4a90e2;
      color: white;
      font-size: 0.9rem;
      margin-top: 3rem;
    }
    @media (max-width: 600px) {
      .product {
        flex-direction: column;
        align-items: flex-start;
      }
      .product img {
        max-width: 100%;
      }
    }
  </style>
</head>
<body>
  <header>
    PeaFlora
  </header>
  <nav>
    <button id="editTextBtn">Edit Tulisan</button>
    <button id="editImageBtn">Edit Gambar</button>
  </nav>
  <main>
    <section id="section-minuman">
      <h2 class="editable" data-type="text" data-id="judul-minuman">Minuman Bunga Telang</h2>
      <div class="product">
        <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=400&q=80" alt="Minuman Bunga Telang" class="editable" data-type="image" data-id="img-minuman" />
        <div class="product-description">
          <p class="editable" data-type="text" data-id="desc-minuman">
            Nikmati kesegaran alami dari minuman bunga telang yang kaya warna dan manfaat kesehatan. Cocok untuk menemani hari Anda dengan sentuhan modern dan elegan.
          </p>
        </div>
      </div>
    </section>
    <section id="section-dessert">
      <h2 class="editable" data-type="text" data-id="judul-dessert">Dessert Millecrepes Bunga Telang</h2>
      <div class="product">
        <img src="https://images.unsplash.com/photo-1562440499-1a0a7a3a7a3a?auto=format&fit=crop&w=400&q=80" alt="Dessert Millecrepes Bunga Telang" class="editable" data-type="image" data-id="img-dessert" />
        <div class="product-description">
          <p class="editable" data-type="text" data-id="desc-dessert">
            Lezat dan cantik, dessert millecrepes dengan lapisan bunga telang yang lembut dan elegan, sempurna untuk momen spesial Anda.
          </p>
        </div>
      </div>
    </section>
  </main>

  <!-- Modal Edit Tulisan -->
  <div class="modal" id="modal-text">
    <div class="modal-content">
      <span class="close-btn" id="closeTextModal">&times;</span>
      <h3>Edit Tulisan</h3>
      <label for="textEditInput">Ubah teks:</label>
      <textarea id="textEditInput" rows="5"></textarea>
      <div class="modal-buttons">
        <button id="saveTextBtn">Simpan</button>
        <button id="cancelTextBtn">Batal</button>
      </div>
    </div>
  </div>

  <!-- Modal Edit Gambar -->
  <div class="modal" id="modal-image">
    <div class="modal-content">
      <span class="close-btn" id="closeImageModal">&times;</span>
      <h3>Edit Gambar</h3>
      <label for="imageEditInput">Pilih gambar baru (jpg/png):</label>
      <input type="file" id="imageEditInput" accept="image/png, image/jpeg" />
      <div class="modal-buttons">
        <button id="saveImageBtn">Simpan</button>
        <button id="cancelImageBtn">Batal</button>
      </div>
    </div>
  </div>

  <footer>
    &copy; 2024 PeaFlora. Semua hak cipta dilindungi.
  </footer>

  <script>
    // Variabel global untuk menyimpan elemen yang diedit
    let currentEditElement = null;

    // Tombol dan modal
    const editTextBtn = document.getElementById('editTextBtn');
    const editImageBtn = document.getElementById('editImageBtn');

    const modalText = document.getElementById('modal-text');
    const modalImage = document.getElementById('modal-image');

    const closeTextModal = document.getElementById('closeTextModal');
    const closeImageModal = document.getElementById('closeImageModal');

    const saveTextBtn = document.getElementById('saveTextBtn');
    const cancelTextBtn = document.getElementById('cancelTextBtn');

    const saveImageBtn = document.getElementById('saveImageBtn');
    const cancelImageBtn = document.getElementById('cancelImageBtn');

    const textEditInput = document.getElementById('textEditInput');
    const imageEditInput = document.getElementById('imageEditInput');

    // Fungsi untuk menonaktifkan semua highlight editable
    function clearHighlight() {
      document.querySelectorAll('.editable').forEach(el => {
        el.style.outline = 'none';
      });
    }

    // Fungsi untuk aktifkan mode edit tulisan
    function enableTextEditMode() {
      clearHighlight();
      currentEditElement = null;
      alert('Klik pada teks yang ingin Anda edit.');
      document.querySelectorAll('.editable[data-type="text"]').forEach(el => {
        el.style.outline = '2px dashed #4a90e2';
        el.style.cursor = 'pointer';
        el.onclick = () => {
          currentEditElement = el;
          textEditInput.value = el.textContent.trim();
          modalText.classList.add('active');
        };
      });
      // Disable image clicks
      document.querySelectorAll('.editable[data-type="image"]').forEach(el => {
        el.onclick = null;
        el.style.outline = 'none';
        el.style.cursor = 'default';
      });
    }

    // Fungsi untuk aktifkan mode edit gambar
    function enableImageEditMode() {
      clearHighlight();
      currentEditElement = null;
      alert('Klik pada gambar yang ingin Anda ganti.');
      document.querySelectorAll('.editable[data-type="image"]').forEach(el => {
        el.style.outline = '2px dashed #4a90e2';
        el.style.cursor = 'pointer';
        el.onclick = () => {
          currentEditElement = el;
          imageEditInput.value = '';
          modalImage.classList.add('active');
        };
      });
      // Disable text clicks
      document.querySelectorAll('.editable[data-type="text"]').forEach(el => {
        el.onclick = null;
        el.style.outline = 'none';
        el.style.cursor = 'default';
      });
    }

    // Tutup modal dan reset highlight
    function closeModal() {
      modalText.classList.remove('active');
      modalImage.classList.remove('active');
      clearHighlight();
      currentEditElement = null;
      // Reset onclick semua editable
      document.querySelectorAll('.editable').forEach(el => {
        el.onclick = null;
        el.style.outline = 'none';
        el.style.cursor = 'default';
      });
    }

    // Event tombol edit
    editTextBtn.addEventListener('click', enableTextEditMode);
    editImageBtn.addEventListener('click', enableImageEditMode);

    // Event tombol close modal
    closeTextModal.addEventListener('click', closeModal);
    closeImageModal.addEventListener('click', closeModal);

    // Event tombol batal modal
    cancelTextBtn.addEventListener('click', closeModal);
    cancelImageBtn.addEventListener('click', closeModal);

    // Simpan perubahan teks
    saveTextBtn.addEventListener('click', () => {
      if (currentEditElement) {
        const newText = textEditInput.value.trim();
        if (newText.length === 0) {
          alert('Teks tidak boleh kosong.');
          return;
        }
        currentEditElement.textContent = newText;
        closeModal();
      }
    });

    // Simpan perubahan gambar
    saveImageBtn.addEventListener('click', () => {
      if (currentEditElement) {
        const file = imageEditInput.files[0];
        if (!file) {
          alert('Silakan pilih file gambar terlebih dahulu.');
          return;
        }
        if (!file.type.startsWith('image/')) {
          alert('File harus berupa gambar (jpg/png).');
          return;
        }
        const reader = new FileReader();
        reader.onload = function(e) {
          currentEditElement.src = e.target.result;
          closeModal();
        };
        reader.readAsDataURL(file);
      }
    });

    // Optional: klik di luar modal untuk tutup
    window.addEventListener('click', (e) => {
      if (e.target === modalText || e.target === modalImage) {
        closeModal();
      }
    });
  </script>
</body>
</html>

