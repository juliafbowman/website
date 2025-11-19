<script lang="ts">
    import { resolve } from '$app/paths';
    export let title: string = "get to know me";
    console.log("Finder.svelte received title:", title);
  
    let isClosed = false;
    let isCollapsed = false;
    let isZoomed = false;
  </script>
  
  <main>
    {#if !isClosed}
      <div
        class="finder-window"
        class:zoomed={isZoomed}
        class:collapsed={isCollapsed}
      >
        <!-- sidebar for finder -->
        <aside class="finder-sidebar">
          <div class="control-lights">
            <!-- Red: close window -->
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
  
            <!-- yellow: minimize (collapse sidebar / content) -->
            <button
              type="button"
              class="light yellow"
              aria-label="Minimize window"
              on:click={() => {
                isCollapsed = !isCollapsed;
              }}
            ></button>
  
            <!-- green: zoom  -->
            <button
              type="button"
              class="light green"
              aria-label="Zoom window"
              on:click={() => {
                isZoomed = !isZoomed;
              }}
            ></button>
          </div>
  
          <div class="sidebar-content">
            <div class="sidebar-section">
              <h4 class="sidebar-header">Experience</h4>
              <ul class="sidebar-list">
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/fitch')}>Fitch Ratings</a>
                </li>
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/intern')}>Internship</a>
                </li>
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/school-projects')}>Projects</a>
                </li>
              </ul>
            </div>
            <div class="sidebar-divider"></div>
            <div class="sidebar-section">
              <h4 class="sidebar-header">Academics</h4>
              <ul class="sidebar-list">
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/relevant-courses')}>Relevant Courses</a>
                </li>
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/university-orgs')}>University Orgs</a>
                </li>
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/mentor')}>Mentorship</a>
                </li>
              </ul>
            </div>
            <div class="sidebar-divider"></div>
            <div class="sidebar-section">
              <h4 class="sidebar-header">Personal</h4>
              <ul class="sidebar-list">
                <li class="sidebar-item">
                  <a href={resolve('/inmybag/bag')}>In My Bag</a>
                </li>
              </ul>
            </div>
          </div>
        </aside>
  
        <div class="finder-content">
          <div class="top-bar">
            <div class="title">
              {#if isCollapsed}
                {title} (minimized)
              {:else}
                {title}
              {/if}
            </div>
          </div>
          <div class="content-area">
            <div class="file-grid">
              <slot />
            </div>
          </div>
        </div>
      </div>
    {:else}
      <button class="reopen-button" on:click={() => (isClosed = false)}>
        reopen window
      </button>
    {/if}
  </main>
  
  <style>
    * {
      box-sizing: border-box;
    }
  
    main {
      display: flex;
      justify-content: center;
      padding: 2rem;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        sans-serif;
      color: #222;
    }
  
    /* prevent weird horizontal scrolling */
    main,
    .finder-window,
    .finder-content,
    .content-area {
      overflow-x: hidden !important;
    }
  
    /* finder window container */
    .finder-window {
      display: flex;
      flex-direction: row;
      width: 850px;
      height: 500px;
      border-radius: 16px;
      border: 1px solid #e2e2e6;
      background-color: #ffffff;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.121);
      margin: 0 auto;
      transition: transform 0.18s ease, box-shadow 0.18s ease, opacity 0.18s ease,
        height 0.18s ease;
    }
  
    .finder-window.zoomed {
      transform: scale(1.03);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.021);
    }
  
    /* when mini, hide inner content (sidebar / right pane) */
    .finder-window.collapsed {
      height: 43px;
    }
  
    .finder-window.collapsed .sidebar-content,
    .finder-window.collapsed .content-area {
      display: none;
    }
  
    /* sidebar */
    .finder-sidebar {
      flex: 0 0 200px;
      width: 200px;
      background-color: #f5f5f7;
      border-right: 1px solid #e0e0e4;
      padding: 1rem;
      position: relative;
    }
  
    .sidebar-content {
      margin-top: 30px;
    }
  
    .sidebar-section {
      margin-bottom: 0.6rem;
    }
  
    .sidebar-header {
      font-size: 0.72rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      font-weight: 600;
      color: #a0a0a5;
      margin: 0 0 0.15rem 0;
    }
  
    .sidebar-list {
      list-style: none;
      margin: 0;
      padding: 0;
    }
  
    .sidebar-item {
      padding: 0.25rem 0.35rem;
      font-size: 0.95rem;
      color: #333;
      cursor: pointer;
      border-radius: 6px;
      transition: background-color 0.15s ease, color 0.15s ease;
    }
  
    .sidebar-item a {
      text-decoration: none;
      color: inherit;
      display: block;
    }
  
    .sidebar-item:hover,
    .sidebar-item a:hover {
      background-color: #e2e5f0;
      color: #222;
    }
  
    .sidebar-divider {
      border-bottom: 1px solid #e0e0e4;
      margin: 0.65rem 0;
    }
  
    /* window control lights */
    .control-lights {
      display: flex;
      gap: 0.5rem;
      position: absolute;
      top: 16px;
      left: 16px;
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
      transition: transform 0.1s ease;
  
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
  
    /* right side content */
    .finder-content {
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      background-color: #ffffff;
    }
  
    /* top bar in the finder */
    .top-bar {
      display: flex;
      align-items: center;
      justify-content: flex-start;
      background-color: #f8f8fa;
      padding: 0.5rem 1.25rem;
      border-bottom: 1px solid #e3e3e7;
      height: 42px;
    }
  
    .title {
      font-size: 0.95rem;
      font-weight: 600;
      color: #555;
    }
  
    .content-area {
      flex-grow: 1;
      padding: 0;
      overflow-y: auto;
      background-color: #ffffff;
    }
  
    .file-grid {
      width: 100%;
      height: 100%;
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
  
    /* mobile */
    @media (max-width: 768px) {
      main {
        padding: 1.5rem 1rem;
        align-items: center;
      }
  
      .finder-window {
        flex-direction: column;
        width: 100%;
        max-width: 600px;
        height: auto;
        min-height: 400px;
      }
  
      .finder-window.collapsed {
        height: 70px;
        min-height: 70px;
      }
  
      .finder-sidebar {
        width: 100%;
        border-right: none;
        border-bottom: 1px solid #e0e0e4;
        padding-top: 2.5rem;
      }
  
      .control-lights {
        top: 14px;
        left: 16px;
      }
  
      .top-bar {
        justify-content: center;
        padding: 0.4rem 0.75rem;
      }
  
      .content-area {
        padding: 0;
      }
    }
  
    @media (max-width: 480px) {
      main {
        padding: 1rem 0.75rem;
      }
  
      .finder-window {
        max-width: 100%;
        min-height: 360px;
      }
  
      .sidebar-item {
        font-size: 0.9rem;
        padding: 0.25rem 0.25rem;
      }
  
      .title {
        font-size: 0.92rem;
      }
    }
  </style>
  