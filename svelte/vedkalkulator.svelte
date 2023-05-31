<script>
    let stromForbruk;
    let vedForbruk;
    const kwhTilSnorerForhold = 0.00628;
    function beregnVed() {
      if (stromForbruk && !isNaN(stromForbruk)) {
        vedForbruk = (stromForbruk * kwhTilSnorerForhold).toFixed(2);
      } else {
        vedForbruk = 0;
      }
    }
  </script>
<style>
        body {
            background-image: url('https://media.discordapp.net/attachments/1009811293953339403/1105929712599056429/forest.webp?width=889&height=664');
            background-size: cover;
            background-repeat: no-repeat;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        h1 {
            font-size: 3em;
            margin: 0;
        }
        nav {
            background-color: #ccc;
            padding: 10px;
            text-align: center;
        }
        nav ul {
            display: inline-block;
            list-style-type: none;
            margin: 0;
            padding: 0;
        }
        nav li {
            display: inline-block;
            margin: 0 10px;
        }
        nav a {
            color: #333;
            text-decoration: none;
            padding: 5px;
        }
        main {
            margin: 20px;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0,0,0,0.3);
            text-align: justify;
        }
        h2 {
            font-size: 2em;
            margin: 0 0 10px 0;
        }
        p {
            margin: 10px 0;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        .mabbes {
            align-items: center;
        }
        .gallery img {
            width: 200px;
            height: 200px;
            margin: 10px;
            border: 1px solid #ccc;
            box-shadow: 0 0 10px rgba(0,0,0,0.3);
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        .gallery img:hover {
            transform: scale(1.1);
        }
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.9);
        }
        .modal-content {
            margin: auto;
            display: block;
            width: 80%;
            max-width: 800px;
        }
        .modal-content img {
            width: 100%;
            height: auto;
        }
        .close {
            position: absolute;
            top: 15px;
            right: 25px;
            font-size: 30px;
            font-weight: bold;
            color: #fff;
            cursor: pointer;
        }
        .close:hover {
            color: #bbb;
        }
    .input-wrapper {
      display: flex;
      align-items: center;
      margin-bottom: 1rem;
    }
  
    .input-wrapper input {
      margin-left: 0.5rem;
    }
    /* Bredde */
::-webkit-scrollbar {
    width: 10px;
  }
  
  /* banen */
  ::-webkit-scrollbar-track {
    background: #f1f1f1; 
  }
   
  /* hendelen */
  ::-webkit-scrollbar-thumb {
    background: #888; 
  }
  
  /* hendel når du hovre over */
  ::-webkit-scrollbar-thumb:hover {
    background: #555; 
  }
  </style>
  <body>
    <header>
      <h1>Vedfirma</h1>
      <p>Din pålitelige kilde for kvalitetsved</p>
  </header>
  <nav>
    <ul>
        <li><a href="../index.html">Hjem</a></li>
        <li><a href="../html/omoss.html">Om oss</a></li>
        <li><a href="../html/produkt.html">Produkter</a></li>
        <li><a href="../html/kontakt.html">Kontakt</a></li>
        <li><a href="../svelte/vedkalkulator.svelte">Vedkalkulator</a></li>
    </ul>
</nav>
  <main>
  <div>
    <div class="input-wrapper">
      <label for="strom-forbruk">Strømforbruk for oppvarming (kWh):</label>
      <input
        id="strom-forbruk"
        type="number"
        min="0"
        bind:value="{stromForbruk}"
        on:input="{beregnVed}"
      />
    </div>
    <div>
      Tilsvarende ved som trengs (3.62 m^3): <strong>{vedForbruk || 0}</strong>
    </div>
    </div>
</main>
</body>