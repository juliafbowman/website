<script>
    import { asset } from '$app/paths';
  </script>  

<main>
  <div class="page-container">
    <div class="background">
    <!-- first column left -->
    <div class="left-image1">
        <img src={asset('/backgrounds/snowheart.jpg')} alt="snowheart" class="centered-image" />
      <p class="caption">
        Winter (<i>nature</i>): <a href="https://en.wikipedia.org/wiki/Heart" target="_blank" class="highlight">heart</a> imprinted in the snow.
      </p>
    </div>
    <div class="left-image2">
      <img src={asset('/backgrounds/cathedral.jpg')} alt="cathedral" class="centered-image" />
      <p class="caption">
        Cologne Cathedral (<i>façade</i>): <a href="https://en.wikipedia.org/wiki/Gothic_architecture" target="_blank" class="highlight">gothic architecture</a> shown from the ground.
      </p>
    </div>
    <div class="left-image3">
      <img src={asset('/backgrounds/countryside.jpg')} alt="countryside" class="centered-image" />
      <p class="caption">
        Countryside (<i>landscape</i>): Rolling <a href="https://en.wikipedia.org/wiki/countryside" target="_blank" class="highlight">countryside</a> hills seen through a mist.
      </p>
    </div>
    <div class="left-image4">
      <img src={asset('/backgrounds/sunlight.jpg')} alt="sunlight" class="centered-image" />
      <p class="caption">
        Forest (<i>sunlight</i>): Soft <a href="https://en.wikipedia.org/wiki/sunlight" target="_blank" class="highlight">sunlight</a> seen filtering through branches.
      </p>
    </div>

    <!-- second column left -->
    <div class="left-image5">
      <img src={asset('/backgrounds/deer.jpg')} alt="deer" class="centered-image" />
      <p class="caption">
        Deer (<i>snowfall</i>): A lone <a href="https://en.wikipedia.org/wiki/Deer" target="_blank" class="highlight">deer</a> wanders a snowy forest.
      </p>
    </div>
    <div class="left-image6">
      <img src={asset('/backgrounds/dam.jpg')} alt="dam" class="centered-image" />
      <p class="caption">
        Ashikaga (<i>Tochigi</i>): A delicate design created on the <a href="https://en.wikipedia.org/wiki/Matsudagawa_Dam" target="_blank" class="highlight">Matsudagawa Dam</a> using high-pressure cleaners.
      </p>
    </div>
    <div class="left-image7">
      <img src={asset('/backgrounds/fog.png')} alt="fog" class="centered-image" />
      <p class="caption">
        Fog (<i>hazy</i>): Fog blankets a <a href="https://en.wikipedia.org/wiki/Mill_pond" target="_blank" class="highlight">millpond</a>.
      </p>
    </div>
    <div class="left-image8">
      <img src={asset('/backgrounds/shakespeare.jpg')} alt="shakespeares heriones" class="centered-image" />
      <p class="caption">
        Shakespeare's Heroines (<i>cover</i>): 1832 book authored by <a href="https://en.wikipedia.org/wiki/Anna_Brownell_Jameson" target="_blank" class="highlight">Anna Brownell Jameson</a>.
      </p>
    </div>

    <!-- first column right -->
    <div class="right-image1">
      <img src={asset('/backgrounds/roses.jpg')} alt="spring" class="centered-image" />
      <p class="caption">
        Spring (<i>renewal</i>): <a href="https://en.wikipedia.org/wiki/Flower" target="_blank" class="highlight">flowers</a> blooming brightly.
      </p>
    </div>
    <div class="right-image2">
      <img src={asset('/backgrounds/castle.jpg')} alt="castle" class="centered-image" />
      <p class="caption">
        Romania (<i>autumn</i>): <a href="https://en.wikipedia.org/wiki/Peleș_Castle" target="_blank" class="highlight">Peleş Castle</a> shown through the fog.
      </p>
    </div>
    <div class="right-image3">
      <img src={asset('/backgrounds/palacesnow.jpg')} alt="palace" class="centered-image" />
      <p class="caption">
        Palace (<i>Versailles</i>): First dusting of <a href="https://en.wikipedia.org/wiki/snow" target="_blank" class="highlight">snow</a> (Nov. 2024). 
      </p>
    </div>
    <div class="right-image4">
      <img src={asset('/backgrounds/winterwindow.jpg')} alt="winterwindow" class="centered-image" />
      <p class="caption">
        Window (<i>morning</i>): A frosty <a href="https://en.wikipedia.org/wiki/Ocean_wave" target="_blank" class="highlight">window</a> frames the woods.
      </p>
    </div>

    <!-- second column right -->
    <div class="right-image5">
      <img src={asset('/backgrounds/sketch.jpg')} alt="sketch" class="centered-image" />
      <p class="caption">
        Sphaera Mundi (<i>sketch</i>): <a href="https://en.wikipedia.org/wiki/Giuseppe_Biancani" target="_blank" class="highlight">Giuseppe Biancani</a> work depicts the stars, 1620.
      </p>
    </div>
    <div class="right-image6">
      <img src={asset('/backgrounds/hungariancastle.jpg')} alt="hungarian castle" class="centered-image" />
      <p class="caption">
        Budapest (<i>Hungary</i>): <a href="https://en.wikipedia.org/wiki/Vajdahunyad_Castle" target="_blank" class="highlight">Vajdahunyad Castle</a> stands tall in City Park.
      </p>
    </div>
    <div class="right-image7">
      <img src={asset('/backgrounds/swinside.jpg')} alt="swinside cirlce" class="centered-image" />
      <p class="caption">
        Stone Circle (<i>megalith</i>): <a href="https://en.wikipedia.org/wiki/Swinside" target="_blank" class="highlight">Swinside</a> located in North West England.
      </p>
    </div>
    <div class="right-image8">
      <img src={asset('/backgrounds/lakechicot.jpg')} alt="lake chicot" class="centered-image" />
      <p class="caption">
        Louisiana (<i>preservation</i>): The still, mossy water of <a href="https://en.wikipedia.org/wiki/Chicot_State_Park" target="_blank" class="highlight">Lake Chicot</a>.
      </p>
    </div>
  </div> <!-- background -->

    <!-- the centered info frame -->
    <div class="center-frame">
      <div class="frame-header">
        Contact Me
      </div>
      <div class="frame-content">
        <!-- my photo -->
        <img src={asset('/icons/me.jpg')} alt="just me" class="frame-image" />
        <p class="caption">
          Pictured on the steps of <a href="https://en.wikipedia.org/wiki/St_Paul%27s_Cathedral" target="_blank" class="highlight">St. Paul's Cathedral</a>, August 2024. 
        </p>
        <hr />
        <div class="frame-section">
          <h3>Email</h3>
          <p>
            <b>Primary:</b> 
            <a href="mailto:juliafbowman@me.com" class="highlight">juliafbowman@me.com</a>
          </p>        </div>
        <div class="frame-section">
          <h3>Location</h3>
          <p><b>Chicago,</b> IL</p>
          <p><b>UIC: </b> <i>Class of Fall 2025</i></p>
        </div>
        <div class="frame-section">
          <h3>Socials</h3>
          <p><b><a href="https://www.linkedin.com/in/juliafbowman/" target="_blank" class="highlight">LinkedIn</a></b>, 
             <b><a href="https://github.com/juliafbowman" target="_blank" class="highlight">Github</a></b></p>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
  /* general styles */
  main {
    font-family: Arial, sans-serif;
    position: relative;
    min-height: 100vh;
    background-color: #ffffff;
    z-index: 0;
  }

  .page-container {
    position: relative;
    width: 100%;
    height: 100%;
    z-index: 1; 
  }

  .background {
    position: relative;
    z-index: 1; /* background layer */
  }

  .left-image1,
  .left-image2,
  .left-image3,
  .left-image4, 
  .left-image5,
  .left-image6,
  .left-image7,
  .left-image8,
  .right-image1,
  .right-image2,
  .right-image3,
  .right-image4,
  .right-image5,
  .right-image6,
  .right-image7,
  .right-image8
   {
    position: absolute;
    background-color: #ffffff;
    padding: 10px;
    border: 1px solid #ccc;
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: fit-content;
  }

  /* beginning of first column left */

  /* snow heart */ 
  .left-image1 {
    top: -130px; 
    left: 10px; 
  }

  /* cathedral */ 
  .left-image2 {
    top: 95px; 
    left: 10px; 
  }

  /* countryside */ 
  .left-image3 {
    top: 385px; 
    left: 10px; 
  }

  /* sunlight */ 
  .left-image4 {
    top: 645px; 
    left: 10px; 
  }

  /* beginning of second column left */ 

  /* deer */ 
  .left-image5 {
    top: -130px; 
    left: 250px; 
  }

  /* dam */ 
  .left-image6 {
    top: 104px; 
    left: 250px; 
  }

  /* fog */ 
  .left-image7 {
    top: 345px; 
    left: 250px; 
  }

    /* book */ 
  .left-image8 {
    top: 590px; 
    left: 250px; 
  }

  /* beginning of first column right */ 

  /* pink roses */ 
  .right-image1 {
    top: -200px;
    right: 10px; 
  }

  /* romanian castle */ 
  .right-image2 {
    top: 395px; 
    right: 10px; 
  }

  /* palace snow */ 
  .right-image3 {
    top: 130px; 
    right: 10px; 
  }

  /* winter snow window */ 
  .right-image4 {
    top: 640px; 
    right: 10px; 
  }

  /* beginning of second column right */ 

  /* sketch */ 
  .right-image5 {
    top: -130px; /* starts at top - under header */ 
    right: 250px; 
  }

  /* hungarian castle */ 
  .right-image6 {
    top: 140px;  
    right: 250px; 
  }

  /* stone circle */ 
  .right-image7 {
    top: 390px;  
    right: 250px; 
  }

  /* lake chicot */ 
  .right-image8 {
    top: 665px;  
    right: 250px; 
  }

  .centered-image {
    width: auto;
    max-width: 200px;
    height: auto;
    display: block;
    margin: 0 auto;
  }

  .caption {
    margin-top: 10px;
    font-size: 1rem;
    color: #333;
    max-width: 200px;
    word-wrap: break-word;
    margin: 0 auto;
  }

  /* specific for the caption under my photo */
  .frame-content .caption {
    max-width: 350px; 
    margin: 0 auto;
    word-wrap: break-word;
    text-align: center;
  }

  .highlight {
    color: #0073e6;
    font-weight: bold;
    text-decoration: none;
  }

  .highlight:hover {
    text-decoration: underline;
    color: blue; 
  }

  /* centered info frame */
  .center-frame {
    background-color: #fbfbfb;
    border: 1px solid #ccc;
    padding: 5px;
    box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
    /* width: 50%; */
    max-width: 400px;
    text-align: center;
    overflow: hidden;
    position: absolute;
    top: 380px;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 10; 
  }

  /* header styles */
  .frame-header,
  .frame-section h3 {
    background-color: #e0e0e0;
    padding: 5px;
    font-size: 1.25rem;
    font-weight: bold;
    text-align: center;
    border-bottom: 1px solid #ccc;
    margin: 0;
  }

  .frame-content {
    padding: 5px; /* tiny smaller than top grey heading */
  }

  .frame-image {
    display: block;
    max-width: 100%;
    height: auto;
    margin: 0 auto 10px auto;
    border: 1px solid #ddd;
  }

  .frame-section {
    margin-top: 10px;
  }

  hr {
    border: none;
    border-top: 1px solid #ccc;
    margin: 15px 0;
  }

  /* mobile */
   @media (max-width: 900px) {
  main {
    padding: 1rem 0.75rem;
  }

  .page-container {
    height: auto;
  }

  .background {
    display: none !important;
  }

  .left-image1,
  .left-image2,
  .left-image3,
  .left-image4,
  .left-image5,
  .left-image6,
  .left-image7,
  .left-image8,
  .right-image1,
  .right-image2,
  .right-image3,
  .right-image4,
  .right-image5,
  .right-image6,
  .right-image7,
  .right-image8 {
    display: none !important;
  }

  .centered-image {
    max-width: 100%;
  }

  .caption {
    font-size: 0.9rem;
    max-width: 100%;
  }

  .center-frame {
    position: static;
    transform: none;
    width: 100%;
    max-width: 420px;
    margin: 2rem auto;
    z-index: 10;
  }

  .frame-content .caption {
    max-width: 100%;
  }
}

/* Extra small phones */
@media (max-width: 480px) {
  .caption {
    font-size: 0.85rem;
  }

  .center-frame {
    padding: 8px;
  }
}

</style>
