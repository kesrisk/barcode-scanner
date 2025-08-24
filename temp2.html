<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Barcode Scanner with Modal</title>
  <script src="https://unpkg.com/quagga/dist/quagga.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background: #f4f6f8;
      text-align: center;
    }
    #camera {
      width: 100%;
      max-width: 400px;
      height: 56vw;
      max-height: 300px;
      margin: 0 auto 20px auto;
      border: 2px solid #ddd;
      border-radius: 8px;
      background: black;
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
      position: relative;
    }

    /* The Modal (background) */
    .modal {
      display: none; /* Hidden by default */
      position: fixed;
      z-index: 1000; /* Sit on top */
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto; /* Enable scroll if needed */
      background-color: rgba(0,0,0,0.5); /* Black with opacity */
    }

    /* Modal Content Box */
    .modal-content {
      background-color: #fff;
      margin: 10% auto;
      padding: 20px;
      border-radius: 8px;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.3);
      text-align: left;
      position: relative;
    }

    /* Close Button */
    .close {
      color: #aaa;
      position: absolute;
      top: 10px;
      right: 16px;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
    }

    .close:hover,
    .close:focus {
      color: black;
      text-decoration: none;
    }

    .modal-content b {
      display: inline-block;
      width: 100px;
    }

    button.retry-btn {
      margin-top: 20px;
      background-color: #007bff;
      color: white;
      padding: 10px 22px;
      font-size: 1em;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      width: 100%;
    }

    button.retry-btn:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>
  <h2>Barcode Scanner</h2>
  <div id="camera"></div>

  <!-- Modal -->
  <div id="modal" class="modal">
    <div class="modal-content">
      <span id="closeBtn" class="close">&times;</span>
      <div id="modalBody">
        <!-- Product info will go here -->
      </div>
      <button id="retryBtn" class="retry-btn">Scan Again</button>
    </div>
  </div>

  <script>
    const products = [
      { barcode: "123456", name: "Headphones", price: 100, gst: 18 },
      { barcode: "654321", name: "Speaker", price: 200, gst: 12 }
    ];

    const modal = document.getElementById("modal");
    const modalBody = document.getElementById("modalBody");
    const closeBtn = document.getElementById("closeBtn");
    const retryBtn = document.getElementById("retryBtn");

    function showModal(barcode) {
      const product = products.find(p => p.barcode === barcode);
      if (product) {
        const gstAmount = (product.price * product.gst) / 100;
        const total = product.price + gstAmount;

        modalBody.innerHTML = `
          <p><b>Product:</b> ${product.name}</p>
          <p><b>Price:</b> ₹${product.price.toFixed(2)}</p>
          <p><b>GST (${product.gst}%):</b> ₹${gstAmount.toFixed(2)}</p>
          <p><b>Total:</b> ₹${total.toFixed(2)}</p>
        `;
      } else {
        modalBody.innerHTML = `<p style="color:red;">Product not found for barcode: ${barcode}</p>`;
      }
      modal.style.display = "block";
    }

    function startScanner() {
      modal.style.display = "none";
      Quagga.init({
        inputStream: {
          type: "LiveStream",
          target: document.querySelector("#camera"),
          constraints: {
            width: { min: 320, ideal: 640, max: 1280 },
            height: { min: 240, ideal: 480, max: 720 },
            facingMode: "environment"
          },
        },
        decoder: {
          readers: ["code_128_reader", "ean_reader", "ean_8_reader", "upc_reader"]
        },
        locate: true
      }, err => {
        if (err) {
          console.error(err);
          alert("Error initializing camera or permission denied.");
          return;
        }
        Quagga.start();
      });

      Quagga.onDetected(onDetectedHandler);
    }

    function onDetectedHandler(result) {
      if (result && result.codeResult && result.codeResult.code) {
        Quagga.offDetected(onDetectedHandler);
        Quagga.stop();
        showModal(result.codeResult.code);
      }
    }

    closeBtn.onclick = () => {
      modal.style.display = "none";
    };

    retryBtn.onclick = () => {
      startScanner();
    };

    // Close modal if clicked outside the content
    window.onclick = (event) => {
      if (event.target === modal) {
        modal.style.display = "none
