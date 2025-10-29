<script>
  import authorImage from '$assets/profile_pic.jpg';
</script>

<section class="author-section">
  <h2 class="mb-l">About the Author</h2>
  <div class="author-container">
    <div class="author-text">
      <p class="mb-m">
        Hi! I'm Miguel, a software developer with a passion for teaching and sharing knowledge. With over a decade of experience in the tech industry, I've worked on a variety of projects ranging from small startups to large-scale applications.
      </p>
      <p class="mb-m">
        I created this ebook to help aspiring developers navigate the complexities of modern web development. My goal is to provide clear, concise, and practical information that you can apply directly to your projects.
      </p>
      <p>
        When I'm not coding or writing, I enjoy hiking, photography, and exploring new technologies. Feel free to connect with me on social media or check out my blog for more insights and tutorials!
      </p>
    </div>
    <img src={authorImage} alt="Author's picture" />
  </div>
</section>

<style>
  .author-section {
    padding: 80px 0;
    margin-left: 12vw;
    margin-right: 20vw;
    max-width: 1150px;
  }
  .author-container {
    display: flex;
    justify-content: space-between;
  }

  .author-container img {
    width: 40%;
    border: 6px solid black;
    box-shadow: 0 4px 24px rgba(0, 0, 0, 0.5);
  }

  .author-text {
    width: 55%;
  }

  /* .author-text p:not(:last-of-type) {
    margin-bottom: 8px;
  } */
</style>
