<script>
  let pagetitle = "How it Works";
  let steps = [
    {
      title:
        "Create fake tweets that are indistinguishable from the real ones.",
      content:
        "Whether you want to pull a prank or see what it feels like when you get a million views on your tweet, our fake tweet creator is here to help.",
      image: "/Burger.png",
      alignLeft: true,
    },
    {
      title:
        "Customize your tweet with any profile pic, handle, text and media",
      content:
        "Personalize your tweet with any profile picture, username, and content. Our intuitive generator lets you craft tweets as if they were posted from any account.",
      image: "/elonmusk.png",
      alignLeft: false,
    },
    {
      title: "Simulate Engagement",
      content:
        "Add elements like likes, retweets, quote tweets, bookmarks, and views to make your tweet look authentic.",
      image: "/engage.svg",
      alignLeft: true,
    },
  ];

  let enhancesteps = [
    {
      additional: [
        "Create high-engagement content in seconds",
        "Automate your posting schedule",
        "Interact with key accounts effortlessly",
        "Track and analyze your performance",
      ],
    },
  ];

  let faqItems = [
    {
      question: "Q1 : What is the Fake Tweet Generator used for?",
      answer:
        "The Fake Tweet Generator is a tool designed to simulate fake tweets. It allows you to create tweets as if they were posted on Twitter. It includes details like the user handle, tweet content, hashtags, and even engagement metrics like retweets and likes.",
    },
    {
      question: "Q2 : Do I need to sign in with my Twitter account?",
      answer:
        "No, you don't need to sign in with your Twitter account to use the Fake Tweet Generator. The tool operates independently of your Twitter account and simply creates visual representations of potential tweets.",
    },
    {
      question:
        "Q3 : How are engagement metrics simulated on fake Tweet Generator?",
      answer:
        "The Fake Tweet Generator allows you to manually set simulated engagement metrics for each tweet, such as retweets and likes. This feature helps visualize potential social engagement, although it does not predict actual engagement. It's a useful tool for crafting tweets and seeing how they would look in a live environment.",
    },
  ];
</script>

<div class="card-doc mx-auto max-w-screen-xl rounded-lg shadow-lg bg-white p-8">
  <h1 class="text-3xl font-bold mb-10 text-center">{pagetitle}</h1>
  <div class="documentation">
    {#each steps as { title, content, image, alignLeft }, i}
      <div
        class="step"
        class:left-align={alignLeft}
        class:right-align={!alignLeft}
      >
        {#if alignLeft}
          <div class="text-content">
            <h2 class="text-2xl font-semibold mb-4">{title}</h2>
            <h3 class="text-lg mb-6">{content}</h3>
          </div>
          <div class="image-container">
            <img src={image} alt="Step Image" />
          </div>
        {:else}
          <div class="image-container">
            <img src={image} alt="Step Image" />
          </div>
          <div class="text-content">
            <h2 class="text-2xl font-semibold mb-4">{title}</h2>
            <h3 class="text-lg mb-6">{content}</h3>
          </div>
        {/if}
      </div>
    {/each}

    <div class="dark-frame">
      <div class="enhance-twitter-section">
        <h3 class="text-2xl font-semibold my-4 text-white">
          Enhance Your Twitter Presence
        </h3>
        <p class="text-lg mb-4 text-white">
          Discover our AI-powered suite of tools designed to supercharge your
          Twitter growth.
        </p>
        <ul class="list-disc list-inside text-lg mb-6">
          {#each enhancesteps[0].additional as item}
            <li id="item" class="text-white">{item}</li>
          {/each}
        </ul>
      </div>
      <div class="image-container">
        <img
          src="/tweets.png"
          alt="AI Twitter Tool"
          class="rounded-lg shadow-md"
        />
      </div>
    </div>

    <div class="faq-section mt-8">
      <h3 class="text-2xl font-bold mb-6">Frequently Asked Questions</h3>
      {#each faqItems as { question, answer }}
        <div class="mb-6">
          <h4 class="text-xl font-medium mb-1">{question}</h4>
          <p class="text-sm mb-4">{answer}</p>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .card-doc {
    max-width: 1200px;
    margin: 0 auto;
    padding: 40px;
    background-color: white;
    border-radius: 10px;
  }
  .documentation {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .step {
    width: 100%;
    margin-bottom: 40px;
    display: flex;
    align-items: center;
  }
  .left-align .text-content {
    order: 1;
  }
  .left-align .image-container {
    order: 2;
    margin-left: 20px;
  }
  .right-align .text-content {
    order: 2;
    margin-left: 20px;
  }
  .right-align .image-container {
    order: 1;
  }
  .dark-frame {
    background-color: #1a202c;
    color: white;
    padding: 20px;
    border-radius: 10px;
    width: 100%;
    text-align: left;
    margin-bottom: 50px;
    display: flex;
    align-items: center;
  }
  .enhance-twitter-section {
    max-width: 50%;
    margin: 0 auto;
    margin-bottom: 20px;
    color: white;
  }
  .image-container {
    flex-shrink: 0;
    width: 50%;
    color: white;
  }
  .image-container img {
    max-width: 100%;
    height: auto;
  }
  .faq-section {
    max-width: 100%;
    margin: 0 auto;
    text-align: left;
  }
  h2,
  h4 {
    margin-top: 1em;
    color: #2d3748;
  }
  p,
  ul {
    list-style-type: disc;
    margin-left: 20px;
  }
</style>
