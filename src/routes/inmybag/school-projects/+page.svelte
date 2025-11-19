<script lang="ts">
    import { asset } from '$app/paths';

    const items = [
      {
        name: "TA Queue",
        dateTaken: "Fall 2025",
        language: "JS / HTML",
        repoUrl: "https://github.com/basiltiongson0/TA-Queue-Project"
      },
      {
        name: "Bomberman Game",
        dateTaken: "Fall 2024",
        language: "Processing",
        repoUrl: "https://github.com/juliafbowman/bomberman"
      },
      {
        name: "Hello Roomie",
        dateTaken: "Spring 2025",
        language: "Python / JS / HTML",
        repoUrl: "https://github.com/juliafbowman/Hello-Roomie"
      },
      {
        name: "Heatstroke Wristband",
        dateTaken: "Fall 2024",
        language: "JS / HTML",
        repoUrl: "https://github.com/juliafbowman/heatStrokeWristband"
      },
      {
        name: "Systrum",
        dateTaken: "Spring 2025",
        language: "Python / JS / HTML",
        repoUrl: "https://github.com/edmuri/Systrum"
      },
      {
        name: "One Gram (SparkHacks)",
        dateTaken: "Spring 2025",
        language: "Python / JS / HTML",
        repoUrl: "https://github.com/juliafbowman/SparkHacks2025"
      },
    ];
  </script>
  
  <div class="file-container">
    <div class="file-header">
      <div class="header-cell">Course</div>
      <div class="header-cell">Date Taken</div>
      <div class="header-cell">Language</div>
      <div class="header-cell icon-header"></div>
    </div>
  
    <div class="file-list">
      {#each items as { name, dateTaken, language, repoUrl }, index}
        <div class="file-row {index % 2 === 0 ? 'even' : 'odd'}">
          <div class="file-cell">{name}</div>
          <div class="file-cell">{dateTaken}</div>
          <div class="file-cell">{language}</div>
            <!-- icon column -->
            <div class="file-cell icon-cell">
                {#if repoUrl}
                    <a
                    href={repoUrl}
                    class="icon-link"
                    target="_blank"
                    rel="noreferrer"
                    aria-label={`Open GitHub repository for ${name}`}
                    >
                    <img src={asset('/icons/github.png')} alt="" class="github-icon" />
                    </a>
                {/if}
                </div>
        </div>
      {/each}
    </div>
  </div>
  
  <style>
    .file-container {
      width: 100%;
      max-width: 800px;
      margin: -10px 0;
      padding: 10px 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        sans-serif;
      color: #222;
    }
  
    .file-header {
      display: flex;
      align-items: center;
      color: #6d6d6d;
      padding: 4px 8px;
      font-size: 0.72rem;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      font-weight: 500;
      border-bottom: 1px solid #e2e2e2;
    }
  
    .header-cell {
      flex: 1;
      padding: 0 8px;
      text-align: left;
    }
  
    /* narrow icon column in header */
    .icon-header {
      flex: 0 0 28px;
      max-width: 28px;
      padding: 0;
    }
  
    .file-list {
      display: flex;
      flex-direction: column;
    }
  
    .file-row {
      display: flex;
      align-items: center;
      padding: 6px 8px;
      transition: background-color 0.15s ease;
      font-size: 0.9rem;
      border-radius: 10px;
    }
  
    .file-row.even {
      background-color: #ffffff;
    }
    .file-row.odd {
      background-color: #fbfbfb;
    }
  
    .file-row:hover {
      background-color: #e9edf5;
    }
  
    .file-cell {
      flex: 1;
      padding: 2px 8px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
  
    /* icon column cell */
    .icon-cell {
      flex: 0 0 28px;
      max-width: 28px;
      padding-left: 0;
      padding-right: 4px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  
    .icon-link {
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }
  
    .icon-link:focus-visible {
      outline: 2px solid #4c7bd9;
      outline-offset: 2px;
      border-radius: 50%;
    }
  
    .github-icon {
      width: 16px;
      height: 16px;
      opacity: 0.55;
      filter: grayscale(100%);
      transition: opacity 0.15s ease, filter 0.15s ease;
    }

    /* when icon is hovered */
    .icon-link:hover .github-icon {
      opacity: 1;
      filter: grayscale(0%);
    }
        
    /* lighter dates and languages */
    .file-row .file-cell:nth-child(3),
    .file-row .file-cell:nth-child(4) {
      color: #777;
    }
  </style>
  