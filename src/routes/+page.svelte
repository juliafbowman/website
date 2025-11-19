<!-- homepage -->
<script>
    import { asset } from '$app/paths';
  
    let isClosed = false;
    let isCollapsed = false;
    let isZoomed = false;
  </script>
  
  <main>
    <div class="page-container">
      <!-- left and right background flowers -->
      <div class="background">
        <div class="left-image">
          <img src={asset('/flowers/flower1.png')} alt="flower1 :3" />
        </div>
        <div class="left-image2">
          <img src={asset('/flowers/flower2.png')} alt="flower2" />
        </div>
        <div class="left-image3">
          <img src={asset('/flowers/flower3.png')} alt="flower3 :D" />
        </div>
        <div class="left-image4">
          <img src={asset('/flowers/flower18.png')} alt="flower4 :D" />
        </div>
  
        <div class="right-image">
          <img src={asset('/flowers/flower6.png')} alt="flower6 :O" />
        </div>
        <div class="right-image2">
          <img src={asset('/flowers/flower11.png')} alt="flower5 C:" />
        </div>
        <div class="right-image3">
          <img src={asset('/flowers/flower5.png')} alt="flower7 C:" />
        </div>
        <div class="right-image4">
          <img src={asset('/flowers/flower10.png')} alt="flower8 C:" />
        </div>
      </div>
  
      <!-- content -->
      <div class="content">
        {#if !isClosed}
          <div
            class="browser-container"
            class:zoomed={isZoomed}
            class:collapsed={isCollapsed}
          >
            <div class="top-bar">
              <div class="control-lights">
                <!-- red - close window -->
                <button
                  type="button"
                  class="light red"
                  aria-label="Close window"
                  on:click={() => {
                    isClosed = true;
                    isCollapsed = false;
                    isZoomed = false;
                  }}
                ></button>
  
                <!-- yellow - minimize (collapse content) -->
                <button
                  type="button"
                  class="light yellow"
                  aria-label="Minimize window"
                  on:click={() => {
                    isCollapsed = !isCollapsed;
                  }}
                ></button>
  
                <!-- green - zoom -->
                <button
                  type="button"
                  class="light green"
                  aria-label="Zoom window"
                  on:click={() => {
                    isZoomed = !isZoomed;
                  }}
                ></button>
              </div>
              <div class="title">
                {isCollapsed ? 'hello (minimized)' : 'hello'}
              </div>
            </div>
  
            <!-- content hides when collapsed -->
            {#if !isCollapsed}
              <div class="browser-box">
                <h1 class="welcome-title">Welcome</h1>
  
                <p class="intro-text">
                  I’m <strong>Julia Bowman</strong>, a Computer Science student at the
                  <strong>University of Illinois Chicago</strong>.
                </p>
  
                <p class="status-text">
                  Currently at
                  <span class="graduation" data-tooltip="Graduation Fall 2025"
                    >senior standing</span
                  >.
                </p>
  
                <hr class="divider" />
  
                <p class="explore-text">Feel free to take a look around : )</p>
              </div>
            {/if}
          </div>
        {:else}
          <button class="reopen-button" on:click={() => (isClosed = false)}>
            reopen window
          </button>
        {/if}
  
        <div class="title-container">
          <a
            href="https://www.linkedin.com/in/juliafbowman/"
            target="_blank"
            class="image-link linkedin"
          >
            <img
              src={asset('/icons/linkedin.png')}
              alt="linkedin logo here..."
              class="link-image linkedin"
            />
          </a>
          <a
            href="https://github.com/juliafbowman"
            target="_blank"
            class="image-link github"
          >
            <img
              src={asset('/icons/github.png')}
              alt="github logo here..."
              class="link-image github"
            />
          </a>
        </div>
      </div>
    </div>
  </main>
  
  <style>
    * {
      box-sizing: border-box;
    }
  
    main {
      font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", system-ui,
        sans-serif;
      padding: 2rem;
      min-height: 100vh;
    }
  
    .page-container {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 1rem;
      padding: 35px;
      width: 100%; /* keep full page width so card width is stable */
    }
  
    /* -------------------------
      background flowers
    -------------------------- */
    .background {
      position: absolute;
      inset: 0;
      pointer-events: none;
      z-index: -1;
    }
  
    .left-image {
      position: relative;
      margin-top: 100px;
      top: 30px;
    }
    .left-image img {
      width: 300px;
      transform: translateY(-10%);
    }
  
    .left-image2 {
      position: relative;
      margin-left: 30px;
      top: 30px;
    }
    .left-image2 img {
      width: 300px;
      transform: translateY(-20%);
    }
  
    .left-image3 {
      position: relative;
      margin-left: 230px;
      top: -370px;
    }
    .left-image3 img {
      width: 250px;
      transform: translateY(-50%);
    }
  
    .left-image4 {
      position: relative;
      margin-left: 260px;
      top: -445px;
    }
    .left-image4 img {
      width: 340px;
      transform: translateY(-10%);
    }
  
    .right-image img {
      width: 300px;
      transform: translateY(-50%);
    }
    .right-image {
      position: absolute;
      top: 55%;
      right: 20px;
      transform: translateY(-50%);
    }
  
    .right-image2 img {
      width: 250px;
    }
    .right-image2 {
      position: absolute;
      top: 70%;
      right: 80px;
      transform: translateY(-50%);
    }
  
    .right-image3 img {
      width: 200px;
    }
    .right-image3 {
      position: absolute;
      top: 52%;
      right: 270px;
      transform: translateY(-50%);
    }
  
    .right-image4 img {
      width: 300px;
    }
    .right-image4 {
      position: absolute;
      top: 10%;
      right: 270px;
      transform: translateY(-50%);
    }
  
    /* -------------------------
           content layout
    -------------------------- */
    .content {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1.5rem;
      width: 100%;
    }
  
    /* -------------------------
          socials
    -------------------------- */
    .title-container {
      display: flex;
      gap: 1.5rem;
    }
  
    .image-link {
      display: inline-block;
    }
  
    .link-image {
      opacity: 0.65;
      transition: transform 0.2s ease, opacity 0.2s ease;
    }
  
    .link-image:hover {
      opacity: 0.95;
      transform: translateY(-1px) scale(1.06);
    }
  
    .github {
      width: 36px;
    }
    .linkedin {
      width: 40px;
    }
  
    /* -------------------------
          browser window
    -------------------------- */
    .browser-container {
      display: flex;
      flex-direction: column;
      width: 100%;
      max-width: 520px; /* card width */
      border-radius: 18px;
      border: 1px solid #e3e3e8;
      overflow: hidden;
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(8px);
      box-shadow: 0 14px 30px rgba(0, 0, 0, 0.07);
      transition: transform 0.18s ease, box-shadow 0.18s ease, opacity 0.18s ease;
    }
  
    .browser-container.zoomed {
      transform: scale(1.03);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.11);
    }
  
    /* height collapses, width stays the same bc of maxwidth/width above */
    .browser-container.collapsed .browser-box {
      display: none;
    }
  
    .top-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0.55rem 1rem;
      background: linear-gradient(to bottom, #fafafa, #f2f2f5);
      border-bottom: 1px solid #dadade;
    }
  
    .control-lights {
      display: flex;
      gap: 0.45rem;
    }
  
    .control-lights .light {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background-color: #ddd;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
  
      /* reset button defaults */
      border: none;
      padding: 0;
      outline: none;
    }
  
    .control-lights .light:focus-visible {
      outline: 2px solid rgba(0, 0, 0, 0.55);
      outline-offset: 2px;
    }
  
    .control-lights .light:active {
      transform: scale(0.9);
    }
  
    .control-lights .light::before,
    .control-lights .light::after {
      content: "";
      position: absolute;
      opacity: 0;
      transition: opacity 120ms ease;
    }
  
    .control-lights:hover .light::before,
    .control-lights:hover .light::after {
      opacity: 0.75;
    }
  
    .control-lights .light.red {
      background-color: #ff605c;
    }
  
    .control-lights .light.red::before {
      content: "×";
      font-size: 10px;
      margin-top: -1px;
      color: rgba(0, 0, 0, 0.7);
    }
  
    .control-lights .light.yellow {
      background-color: #ffbd44;
    }
  
    .control-lights .light.yellow::before {
      content: "–";
      font-size: 12px;
      margin-top: -1px;
      color: rgba(0, 0, 0, 0.7);
    }
  
    .control-lights .light.green {
      background-color: #00ca4e;
    }
  
    /* top-left arrow (points ↙) */
    .control-lights .light.green::before {
      content: "";
      position: absolute;
      border-style: solid;
      border-width: 4px 4px 0 0;
      border-color: rgba(0, 0, 0, 0.7) transparent transparent transparent;
      transform: translate(-1px, -1px) rotate(0deg);
    }
  
    /* bottom-right arrow (points ↗) */
    .control-lights .light.green::after {
      content: "";
      position: absolute;
      border-style: solid;
      border-width: 0 0 4px 4px;
      border-color: transparent transparent rgba(0, 0, 0, 0.7) transparent;
      transform: translate(1px, 1px) rotate(0deg);
    }
  
    .title {
      font-size: 0.9rem;
      color: #555;
    }
  
    /* -------------------------
           inner window 
    -------------------------- */
    .browser-box {
      padding: 1.4rem 1.6rem;
      background: linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0.98),
        rgba(250, 250, 250, 0.92)
      );
    }
  
    .welcome-title {
      font-size: 1.7rem;
      font-weight: 600;
      color: #505050;
      margin: 0 0 0.6rem 0;
      letter-spacing: -0.01em;
    }
  
    .intro-text,
    .status-text,
    .explore-text {
      font-size: 1.1rem;
      color: #666;
      line-height: 1.5;
      margin: 0.4rem 0;
    }
  
    .intro-text strong {
      color: #4c4c4c;
    }
  
    .divider {
      margin: 1rem 0;
      border: none;
      border-top: 1px solid #e4e4e4;
    }
  
    /* Tooltip text */
    .graduation {
      color: #9696a4;
      position: relative;
      cursor: pointer;
    }
  
    .graduation::after {
      content: attr(data-tooltip);
      position: absolute;
      bottom: 128%;
      left: 50%;
      transform: translateX(-50%);
      background: white;
      padding: 0.25rem 0.5rem;
      border-radius: 6px;
      border: 1px solid #ddd;
      font-size: 0.75rem;
      box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
      opacity: 0;
      visibility: hidden;
      transition: 0.15s ease;
    }
  
    .graduation:hover::after {
      opacity: 1;
      visibility: visible;
    }
  
    .reopen-button {
      border-radius: 999px;
      border: 1px solid #dadade;
      padding: 0.4rem 0.9rem;
      background: rgba(255, 255, 255, 0.9);
      font-size: 0.85rem;
      color: #555;
      cursor: pointer;
      box-shadow: 0 8px 18px rgba(0, 0, 0, 0.06);
      backdrop-filter: blur(6px);
      transition: transform 0.15s ease, box-shadow 0.15s ease, opacity 0.15s ease;
      opacity: 0.95;
    }
  
    .reopen-button:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 24px rgba(0, 0, 0, 0.08);
      opacity: 1;
    }
  
    /* -------------------------
        mobile
    -------------------------- */
    @media (max-width: 768px) {
      .page-container {
        flex-direction: column;
        align-items: center;
      }
      .background {
        position: fixed;
        inset: 0;
        z-index: -1;
      }
      .left-image2,
      .left-image3,
      .left-image4,
      .right-image3,
      .right-image4 {
        display: none;
      }
      .browser-container {
        max-width: 100%;
      }
    }
  
    @media (max-width: 480px) {
      .welcome-title {
        font-size: 1.4rem;
      }
      .intro-text,
      .status-text {
        font-size: 1rem;
      }
    }
  </style>
  