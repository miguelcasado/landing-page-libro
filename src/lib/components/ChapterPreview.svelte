<script>
  const chapters = [
    {
      number: 1,
      title: "Chapter 1: Introduction",
      strapline: "Getting started with your move",
      excerpt:
        "Moving to a new home can be an exciting adventure, but it can also be overwhelming and stressful. In this chapter, we`ll cover the basics of moving, including how to plan your move, what to expect during the process, and tips for making the transition as smooth as possible.",
    },
    {
      number: 2,
      title: "Chapter 2: Visas & Residency",
      strapline: "Permits, visas and paperwork",
      excerpt:
        "This chapter explains the different visa and residency options for Spain, the documentation required, timelines, and practical advice to avoid common administrative pitfalls. Includes checklists for appointments and how to prepare your paperwork.",
    },
    {
      number: 3,
      title: "Chapter 3: Finding a Home",
      strapline: "Renting, buying and neighbourhoods",
      excerpt:
        "Learn how the Spanish housing market works: renting vs buying, how to read contracts, what fees to expect, and tips for choosing the right neighbourhood. Also covers working with agents, negotiating rent, and avoiding rental scams.",
    },
    {
      number: 4,
      title: "Chapter 4: Healthcare & Insurance",
      strapline: "Staying healthy abroad",
      excerpt:
        "An overview of the Spanish healthcare system, how to register for public healthcare, options for private insurance, and what to do in a medical emergency. Includes guidance on prescriptions, family coverage and useful local resources.",
    },
    {
      number: 5,
      title: "Chapter 5: Settling In & Local Life",
      strapline: "Language, culture and daily routines",
      excerpt:
        "Practical tips for integrating: learning basic Spanish, understanding cultural norms, handling utilities and banking, registering with local authorities, and building a social support network. Advice to make day-to-day life easier from day one.",
    },
  ];
 
  let selectedChapterNumber = $state(1);
 
  let selectedChapter = $derived(chapters.find((chapter) => chapter.number === selectedChapterNumber));

  function selectChapter(chapter) {
    selectedChapterNumber = chapter.number;
  }

  </script>

<section class="chapter-preview default-margin">
  <h2 class="mb-l">What you`re getting</h2>
  <div class="chapter-container">
    <ul>
      {#each chapters as chapter, index}
      <li>
        <button 
          class="chapter-title"
          class:selected-chapter-title={chapter.number === selectedChapterNumber}
          aria-controls={`chapter-info-${chapter.number}`}
          aria-expanded={selectedChapterNumber === chapter.number}
          onclick={() => selectChapter(chapter)}>
          <h3>{chapter.title}</h3>
        </button>
      </li>
      {/each}
      
    </ul>
    <div class="chapter-info">
      <h3 class="chapter-strapline italic mb-s">
        {selectedChapter.title}
      </h3>
      <p class="mb-m">
        {selectedChapter.excerpt}
      </p>
    </div>
  </div>
</section>

<style>
  .chapter-preview {
    padding: 80px;
    margin-left: 12vw;
    margin-right: 20vw;
    max-width: 1150px;
  }
  .chapter-container {
    display: flex;
    justify-content: space-between;
  }

  .chapter-container ul {
    width: 40%;
  }

  .chapter-info {
    width: 55%;
  }

  .chapter-title {
    border-bottom: 1px solid grey;
    width: 100%;
    display: block;
    padding: 12px;
    text-align: left;
  }

  .selected-chapter-title {
    background-color: black;
    border: none;
    color: white;
    box-shadow:
      0 4px 6px rgba(0, 0, 0, 0.1),
      0 1px 3px rgba(0, 0, 0, 0.08);
  }
</style>
