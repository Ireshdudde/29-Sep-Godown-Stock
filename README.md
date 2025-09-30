<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Stock Details (29 Sep 2025)</title>
  <style>
    * { box-sizing: border-box; }

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #f5f7fa;
      color: #2c3e50;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    header {
      background: linear-gradient(90deg, #0f2027, #203a43, #2c5364);
      color: #ffffff;
      padding: 1.2rem;
      text-align: center;
      font-size: 1.6rem;
      font-weight: 600;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
      letter-spacing: 0.8px;
    }

    .container {
      display: flex;
      flex: 1;
    }

    .sidebar {
      background-color: #1e272e;
      color: #ffffff;
      width: 250px;
      padding: 1rem;
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .sidebar button {
      background: transparent;
      border: none;
      color: #dcdde1;
      padding: 0.8rem 1rem;
      width: 100%;
      text-align: left;
      font-size: 1rem;
      cursor: pointer;
      border-left: 4px solid transparent;
      border-radius: 4px;
      transition: all 0.3s ease;
    }

    .sidebar button:hover,
    .sidebar button.active {
      background: #0abde3;
      color: #ffffff;
      border-left: 4px solid #00cec9;
      font-weight: bold;
    }

    @media (max-width: 768px) {
      .container { flex-direction: column; }

      .sidebar {
        width: 100%;
        flex-direction: row;
        overflow-x: auto;
        padding: 0.5rem;
        gap: 0.5rem;
      }

      .sidebar button {
        flex: 1;
        min-width: max-content;
        text-align: center;
        border-left: none;
        border-bottom: 3px solid transparent;
      }

      .sidebar button:hover,
      .sidebar button.active {
        border-left: none;
        border-bottom: 3px solid #00cec9;
      }
    }

    .content {
      flex: 1;
      padding: 1rem;
      background: #f5f7fa;
      overflow-y: auto;
    }

    .location-title {
      font-size: 1.4rem;
      font-weight: bold;
      margin: 0 0 1rem;
      position: relative;
      padding-bottom: 0.5rem;
      text-transform: capitalize;
    }

    .location-title::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 4px;
      border-radius: 2px;
    }
    .location-title.tembhurni::after { background: #6c5ce7; }
    .location-title.shirpur_chopada::after { background: #e17055; }
    .location-title.savda::after { background: #00b894; }
    .location-title.narayangaon::after { background: #16a085; }
    .location-title.jamner::after { background: #0984e3; }
    .location-title.ramwadi::after { background: #d63031; }

    .section-title {
      font-size: 1.2rem;
      margin: 1rem 0 0.5rem;
      color: #34495e;
      border-bottom: 2px solid #dcdde1;
      padding-bottom: 0.3rem;
    }

    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
      margin-top: 0.8rem;
    }

    .card {
      background: #ffffff;
      border-left: 6px solid #3498db;
      border-radius: 6px;
      padding: 0.8rem;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
      transition: transform 0.2s ease;
    }

    .card:hover { transform: translateY(-3px); }

    .card h4 {
      margin: 0;
      font-size: 0.95rem;
      font-weight: 600;
      color: #2c3e50;
    }

    .card p {
      margin: 0.3rem 0 0;
      font-size: 1.1rem;
      font-weight: bold;
      color: #2f3542;
    }

    .card p.negative { color: #e74c3c; }
  </style>
</head>
<body>
  <header>Stock Details (29 Sep 2025)</header>
  <div class="container">
    <div class="sidebar">
      <button onclick="showStock('tembhurni')" id="btn-tembhurni">Tembhurni</button>
      <button onclick="showStock('shirpur_chopada')" id="btn-shirpur_chopada">Shirpur_chopada</button>
      <button onclick="showStock('savda')" id="btn-savda">Savda</button>
      <button onclick="showStock('narayangaon')" id="btn-narayangaon">Narayangaon</button>
      <button onclick="showStock('jamner')" id="btn-jamner" class="active">Jamner</button>
      <button onclick="showStock('ramwadi')" id="btn-ramwadi">Ramwadi</button>
    </div>
    <div class="content" id="stockContent"></div>
  </div>

  <script>
    const createCards = (items) => {
      return items.map(item => {
        const isNegative = item.qty.toString().includes('-');
        return `
          <div class="card">
            <h4>${item.name}</h4>
            <p class="${isNegative ? 'negative' : ''}">${item.qty}</p>
          </div>
        `;
      }).join('');
    };

    const stockData = {
      tembhurni: {
        balance: [
          { name: "Roshana Box (Nos)", qty: "0 nos" },
          { name: "King White Box", qty: "360 nos" },
          { name: "Haniya Box", qty: "0 nos" },
          { name: "Vaccum Bag 13kg", qty: "30 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "0 nos" },
          { name: "Sachets (Nos)", qty: "105000 nos" },
          { name: "fevicol (kg)", qty: "185 KG" },
          { name: "Germination Paper (kg)", qty: "3150 KG" },
          { name: "Bavistin", qty: "2 KG" },
          { name: "Truti (kg)", qty: "2100 KG" },
          { name: "Bleaching Powder (g)", qty: "0 KG" },
          { name: "Rubber (kg)", qty: "20 KG" },
          { name: "Roshana Sticker (Nos)", qty: "3 box" },
          { name: "Bandhan Sticker (Nos)", qty: "1200000 nos" }
        ]
      },
      shirpur_chopada: {
        balance: [
          { name: "Bandhan Box", qty: "980 nos" },
          { name: "Roshana Box (Nos)", qty: "7638 nos" },
          { name: "Vaccum Bag 13kg", qty: "745.152 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "80813 nos" },
          { name: "Sachets (Nos)", qty: "17534 nos" },
          { name: "fevicol (kg)", qty: "132 KG" },
          { name: "Germination Paper (kg)", qty: "370.14 KG" },
          { name: "Fungicide (kg)", qty: "6.5 KG" },
          { name: "Truti (kg)", qty: "711 KG" },
          { name: "Bleaching Powder (g)", qty: "0.6 G" },
          { name: "Rubber (kg)", qty: "19.7 KG" },
          { name: "Roshana Sticker (Nos)", qty: "750482" }
        ]
      },
      savda: {
        balance: [
          { name: "King Brown Box (Nos)", qty: "2300" },
          { name: "Bandhan Premium", qty: "1500" },
          { name: "Alaa white Box (Nos)", qty: "500" },
          { name: "Roshana Box (Nos)", qty: "0" },
          { name: "Laibaah Box (Nos)", qty: "350" },
          { name: "Haniya Box (Nos)", qty: "800" },
          { name: "Shabad Box(Nos)", qty: "280" },
          { name: "Vaccum Bag 13kg", qty: "1720" },
          { name: "PE Form 1.5 MM (Nos)", qty: "0" },
          { name: "Sachets (Nos)", qty: "0" },
          { name: "Fevicol (kg)", qty: "0" },
          { name: "Germination Paper (kg)", qty: "350" },
          { name: "Fungicide (kg)", qty: "4" },
          { name: "Truti (kg)", qty: "0" },
          { name: "Bleaching Powder (g)", qty: "0" },
          { name: "Rubber (kg)", qty: "0" },
          { name: "King Sticker (Nos)", qty: "56000" },
          { name: "Alaa Sticker (Nos)", qty: "4650000" },
          { name: "Roshana Sticker (Nos)", qty: "1210000" },
          { name: "Other Sticker", qty: "2520000" }
        ]
      },
      narayangaon: {
        outward: [
          { name: "Roshana Box (Nos)", qty: "716 nos" },
          { name: "Vaccum Bag 13kg", qty: "32.54545455 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "4296 nos" },
          { name: "Sachets (Nos)", qty: "716 nos" },
          { name: "fevicol (kg)", qty: "4 KG" },
          { name: "Germination Paper (kg)", qty: "14.32 KG" },
          { name: "Fungicide (kg)", qty: "1 KG" },
          { name: "Truti (kg)", qty: "4 KG" },
          { name: "Bleaching Powder (g)", qty: "0.1 KG" },
          { name: "Rubber (kg)", qty: "0.4 KG" },
          { name: "Roshana Sticker (Nos)", qty: "10024 nos" }
        ],
        balance: [
          { name: "Roshana Box (Nos)", qty: "2288 nos" },
          { name: "Vaccum Bag 13kg", qty: "841.72 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "104717 nos" },
          { name: "Sachets (Nos)", qty: "16561 nos" },
          { name: "fevicol (kg)", qty: "6 KG" },
          { name: "Germination Paper (kg)", qty: "182.48 KG" },
          { name: "Fungicide (kg)", qty: "37.5 KG" },
          { name: "Truti (kg)", qty: "46 KG" },
          { name: "Bleaching Powder (g)", qty: "9.5 KG" },
          { name: "Rubber (kg)", qty: "14.6 KG" },
          { name: "Roshana Sticker (Nos)", qty: "189826 nos" },
          { name: "King Sticker (Nos)", qty: "218788 nos" },
          { name: "King Brown Box", qty: "400 nos" }
        ]
      },
      jamner: {
        outward: [
          { name: "Roshana Box (Nos)", qty: "2736 nos" },
          { name: "Vaccum Bag 13kg", qty: "124.3636364 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "16416 nos" },
          { name: "Sachets (Nos)", qty: "2736 nos" },
          { name: "fevicol (kg)", qty: "15 KG" },
          { name: "Germination Paper (kg)", qty: "54.72 KG" },
          { name: "Fungicide (kg)", qty: "4 KG" },
          { name: "Truti (kg)", qty: "20 KG" },
          { name: "Bleaching Powder (g)", qty: "0.4 G" },
          { name: "Rubber (kg)", qty: "2 KG" },
          { name: "Roshana Sticker (Nos)", qty: "38304" }
        ],
        balance: [
          { name: "Roshana Box (Nos)", qty: "13906 nos" },
          { name: "Vaccum Bag 13kg", qty: "2176 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "174538 nos" },
          { name: "Sachets (Nos)", qty: "88072 nos" },
          { name: "fevicol (kg)", qty: "182.5 KG" },
          { name: "Germination Paper (kg)", qty: "1095.23 KG" },
          { name: "Fungicide (kg)", qty: "22.5 KG" },
          { name: "Truti (kg)", qty: "350.3 KG" },
          { name: "Bleaching Powder (g)", qty: "2.3 KG" },
          { name: "Rubber (kg)", qty: "71.35 KG" },
          { name: "Roshana Sticker (Nos)", qty: "660453 nos" }
        ]
      },
      ramwadi: {
        balance: [
          { name: "Roshana Box (Nos)", qty: "1989 nos" },
          { name: "Laibaah Box", qty: "0 nos" },
          { name: "Haniya Box", qty: "0 nos" },
          { name: "Vaccum Bag 13kg", qty: "90.40909091 KG" },
          { name: "Vaccum Bag 7kg", qty: "0 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "11934 nos" },
          { name: "Sachets (Nos)", qty: "1989 nos" },
          { name: "fevicol (kg)", qty: "12 KG" },
          { name: "Germination Paper (kg)", qty: "39.78 KG" },
          { name: "Fungicide (kg)", qty: "4.5 KG" },
          { name: "Truti (kg)", qty: "15 KG" },
          { name: "Bleaching Powder (g)", qty: "0.3 KG" },
          { name: "Rubber (kg)", qty: "1.5 KG" },
          { name: "Roshana Sticker", qty: "27846" }
        ],
        balance2: [
          { name: "Roshana Box (Nos)", qty: "3900 nos" },
          { name: "Laibaah Box", qty: "0 nos" },
          { name: "Haniya Box", qty: "0 nos" },
          { name: "Vaccum Bag 13kg", qty: "424.6 KG" },
          { name: "Vaccum Bag 7kg", qty: "210 KG" },
          { name: "PE Form 1.5 MM (Nos)", qty: "0 nos" },
          { name: "Sachets (Nos)", qty: "18800 nos" },
          { name: "fevicol (kg)", qty: "0 KG" },
          { name: "Germination Paper (kg)", qty: "236 KG" },
          { name: "Fungicide (kg)", qty: "12.5 KG" },
          { name: "Truti (kg)", qty: "25 KG" },
          { name: "Bleaching Powder (g)", qty: "39.5 KG" },
          { name: "Rubber (kg)", qty: "5.5 KG" },
          { name: "Roshana Sticker", qty: "1355200" },
          { name: "King Sticker", qty: "5 bundle" },
          { name: "Bandhan Sticker", qty: "16 bundle" }
        ]
      }
    };

    function showStock(location) {
      document.querySelectorAll(".sidebar button").forEach(btn => btn.classList.remove("active"));
      document.getElementById(`btn-${location}`).classList.add("active");

      const locData = stockData[location];
      let html = `<h2 class="location-title ${location}">${location.replace('_',' ')}</h2>`;

      if (locData.inward) {
        html += `<h3 class="section-title">Inward</h3>`;
        html += `<div class="card-grid">${createCards(locData.inward)}</div>`;
      }

      if (locData.outward) {
        html += `<h3 class="section-title">Outward</h3>`;
        html += `<div class="card-grid">${createCards(locData.outward)}</div>`;
      }

      if (locData.balance) {
        html += `<h3 class="section-title">Balance</h3>`;
        html += `<div class="card-grid">${createCards(locData.balance)}</div>`;
      }

      if (locData.balance2) {
        html += `<h3 class="section-title">Balance 2</h3>`;
        html += `<div class="card-grid">${createCards(locData.balance2)}</div>`;
      }

      document.getElementById("stockContent").innerHTML = html;
    }

    showStock("jamner");
  </script>
</body>
</html>
