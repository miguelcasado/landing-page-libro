<script>
  import { FaqItem, Button } from '$components';
  import twitterIcon from '$assets/icons/twitter.webp';

  const faqs = [
    {
      question: "What format is the ebook delivered in?",
      answer: "The ebook is delivered in PDF format, which is compatible with most devices including computers, tablets, and smartphones. You can read it using any PDF reader of your choice."
    },
    {
      question: "Can I get a refund if I'm not satisfied?",
      answer: "Yes, we offer a 30-day money-back guarantee. If you're not satisfied with your purchase, simply contact our support team within 30 days of your purchase date for a full refund."
    },
    {
      question: "Are there any additional resources included with the ebook?",
      answer: "Yes, the ebook includes access to exclusive online resources such as downloadable checklists, templates, and bonus content to enhance your learning experience."
    },
    {
      question: "Is there a physical copy of the ebook available?",
      answer: "Currently, we only offer the ebook in digital PDF format. However, you can print it out if you prefer a physical copy."
    }
  ];

  let questionCurrentlyExpanded = $state(1); 

  function onclick(index) {
    if (questionCurrentlyExpanded === index) {
      questionCurrentlyExpanded = -1;
    }else{
      questionCurrentlyExpanded = index;
    }
  }
</script>

<section class="faq-section">
  <h2 class="mb-l">Frequently Asked Questions</h2>
  <div class="faq-container">
    {#each faqs as faq, index}
      <FaqItem {faq} isExpanded={index === questionCurrentlyExpanded} onclick={() => onclick(index)} />
    {/each}
  </div>
  <div class="additional-info">
    <Button class="mt-s">BUY NOW</Button>
    <p class="mt-m">Any other questions?</p>
    <a href="https://x.com">
      <p>Reach out on Twitter</p> 
      <img src={twitterIcon} alt="Twitter Icon" class="twitter-icon" />
    </a>
  </div>
</section>

<style>
  .additional-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: grey;
  }

  .twitter-icon {
    width: 16px;
    height: 16px;
  }

  .additional-info a {
    text-decoration: underline;
  }
</style>
