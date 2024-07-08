<script>
	import html2canvas from "html2canvas";
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
  
	// input changes
	let dateTime = new Date().toISOString().slice(0, 16);
	let viewCount = 0;
	let retweetCount = 0;
	let quoteCount = 0;
	let likeCount = 0;
	let bookmarkCount = 0;
	let tweetTitle = "Tweet Generator";
	let tweetHandle = "@tweetgenerator";
	let tweetText = `
	  Hey there, Welcome to tweet generator ✨
  
  
	  - You can edit anything you want by clicking on them
	  - Move to the preview mode from the top bar
	  - Checkout the preview and download your image in one-click
	`;
  
	function handleDateClick() {
	  const inputElement = document.querySelector(".date-edit");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function handleViewClick() {
	  const inputElement = document.querySelector(".view-input");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function handleRetweetClick() {
	  const inputElement = document.querySelector(".retweet-input");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function handleQuoteClick() {
	  const inputElement = document.querySelector(".quotes-input");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function handleLikeClick() {
	  const inputElement = document.querySelector(".like-input");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function handleBookmarkClick() {
	  const inputElement = document.querySelector(".bookmark-input");
	  inputElement.hidden = !inputElement.hidden;
	  if (!inputElement.hidden) {
		inputElement.focus();
	  }
	}
  
	function updateDateTime(event) {
	  dateTime = event.target.value;
	}
  
	function updateViewCount(event) {
	  viewCount = event.target.value;
	}
  
	function updateRetweetCount(event) {
	  retweetCount = event.target.value;
	}
  
	function updateQuoteCount(event) {
	  quoteCount = event.target.value;
	}
  
	function updateLikeCount(event) {
	  likeCount = event.target.value;
	}
  
	function updateBookmarkCount(event) {
	  bookmarkCount = event.target.value;
	}
	function dark() {
	  //3c9aff
	  const card = document.querySelector(".tweet-generator");
	  const reset = document.querySelector(".reset-text");
	  const likeCount = document.querySelector(".like-count");
	  const retweetCount = document.querySelector(".retweet-count");
	  const bookmarkCount = document.querySelector(".bookmark-count");
	  const quotesCounts = document.querySelector(".quotes-count");
	  const viewsCounts = document.querySelector(".view-count");
	  const bg = document.querySelector(".Dark");
	  const bg1 = document.querySelector(".Light");
	  const bg2 = document.querySelector(".Dim");
	  card.style.backgroundColor = "#111419";
	  likeCount.style.color = "white";
	  retweetCount.style.color = "white";
	  bookmarkCount.style.color = "white";
	  viewsCounts.style.color = "white";
	  quotesCounts.style.color = "white";
	  card.style.color = "white";
	  reset.style.color = "white";
	  bg.style.backgroundColor = "#3c9aff";
	  bg.style.color = "white";
	  bg1.style.backgroundColor = "white";
	  bg1.style.color = "black";
	  bg2.style.backgroundColor = "white";
	  bg2.style.color = "black";
	}
	function light() {
	  const card = document.querySelector(".tweet-generator");
	  const reset = document.querySelector(".reset-text");
	  const likeCount = document.querySelector(".like-count");
	  const retweetCount = document.querySelector(".retweet-count");
	  const bookmarkCount = document.querySelector(".bookmark-count");
	  const quotesCounts = document.querySelector(".quotes-count");
	  const viewsCounts = document.querySelector(".view-count");
	  const bg = document.querySelector(".Light");
	  const bg1 = document.querySelector(".Dark");
	  const bg2 = document.querySelector(".Dim");
	  card.style.backgroundColor = "white";
	  likeCount.style.color = "black";
	  retweetCount.style.color = "black";
	  bookmarkCount.style.color = "black";
	  viewsCounts.style.color = "black";
	  quotesCounts.style.color = "black";
	  card.style.color = "black";
	  reset.style.color = "black";
	  bg.style.backgroundColor = "#3c9aff";
	  bg.style.color = "white";
	  bg1.style.backgroundColor = "white";
	  bg1.style.color = "black";
	  bg2.style.backgroundColor = "white";
	  bg2.style.color = "black";
	}
	function dim() {
	  const card = document.querySelector(".tweet-generator");
	  const reset = document.querySelector(".reset-text");
	  const likeCount = document.querySelector(".like-count");
	  const retweetCount = document.querySelector(".retweet-count");
	  const bookmarkCount = document.querySelector(".bookmark-count");
	  const quotesCounts = document.querySelector(".quotes-count");
	  const viewsCounts = document.querySelector(".view-count");
	  const bg = document.querySelector(".Dim");
	  const bg1 = document.querySelector(".Light");
	  const bg2 = document.querySelector(".Dark");
	  card.style.backgroundColor = "#232833";
	  likeCount.style.color = "white";
	  retweetCount.style.color = "white";
	  bookmarkCount.style.color = "white";
	  viewsCounts.style.color = "white";
	  quotesCounts.style.color = "white";
	  card.style.color = "white";
	  reset.style.color = "white";
	  bg.style.backgroundColor = "#3c9aff";
	  bg.style.color = "white";
	  bg1.style.backgroundColor = "white";
	  bg1.style.color = "black";
	  bg2.style.backgroundColor = "white";
	  bg2.style.color = "black";
	}
	function downloadDivAsImage() {
	  const divToDownload = document.querySelector(".tweet-generator");
	  html2canvas(divToDownload).then((canvas) => {
		const link = document.createElement("a");
		link.download = "tweet-generator.png";
		link.href = canvas.toDataURL("image/png");
		link.click();
	  });
	}
	// input changes//
  
	// image
	let imageUrl = "/avatr.jpg";
	let fileInput;
  
	function handleImageChange(event) {
	  const file = event.target.files[0];
	  if (file) {
		imageUrl = URL.createObjectURL(file);
	  }
	}
	// image
	// image
	let tweetImage = "";
	let imageInput;
  
	function handleImgChange(event) {
	  const file = event.target.files[0];
	  if (
		file &&
		(file.type === "image/png" ||
		  file.type === "image/jpeg" ||
		  file.type === "image/jpg")
	  ) {
		const reader = new FileReader();
		reader.onload = (e) => {
		  tweetImage = e.target.result;
		  adjustWrapperSize(e.target.result);
		};
		reader.readAsDataURL(file);
	  } else {
		alert("Please upload a valid PNG or JPEG image.");
	  }
	}
  
	function adjustWrapperSize(imageSrc) {
	  const img = new Image();
	  img.onload = () => {
		const avatarWrapper = document.querySelector(".file-input");
		let width = img.width;
		let height = img.height;
  
		if (width > 500) {
		  height = (height * 500) / width;
		  width = 500;
		}
		if (height > 1000) {
		  width = (width * 1000) / height;
		  height = 1000;
		}
  
		avatarWrapper.style.width = `${width}px`;
		avatarWrapper.style.height = `${height}px`;
	  };
	  img.src = imageSrc;
	}
  
	// image
	//tweet generator
	import { onMount } from "svelte";
	let isEditing = false;
	let inputValue = tweetTitle;
	let characterCount = tweetTitle.length;
  
	function handleTweetTitleClick() {
	  isEditing = true;
	  onMount(() => {
		inputElement.focus();
	  });
	}
  
	function updateTweetTitle(event) {
	  inputValue = event.target.value;
	  characterCount = inputValue.length;
	}
  
	function handleInputBlur() {
	  if (inputValue.trim() === "") {
		inputValue = tweetTitle;
	  }
	  tweetTitle = inputValue;
	  isEditing = false;
	}
  
	$: characterCount = inputValue.length > 50 ? 50 : inputValue.length;
	$: inputValue = inputValue.slice(0, 50);
	// tweet generator
	// tweet handle
	let inputHandle = tweetHandle;
	let isEditingHandle = false;
  
	let charCountHandle = tweetHandle.length;
	function handleTweetHandleClick() {
	  isEditingHandle = true;
	  onMount(() => {
		handleInputElement.focus();
	  });
	}
  
	function updateTweetHandle(event) {
	  inputHandle = event.target.value;
	  if (inputValue.length > 50) {
		inputValue = inputValue.slice(0, 50);
	  }
	  charCountHandle = inputHandle.length;
	}
  
	function handleHandleBlur() {
	  if (inputHandle.trim() === "") {
		inputHandle = tweetHandle;
	  }
	  tweetHandle = inputHandle;
	  isEditingHandle = false;
	}
  
	// tweet handle
	// editing text
	let inputText = tweetText;
	let isEditingText = false;
	let charCountText = tweetText.length;
	function handleTweetTextClick() {
	  isEditingText = true;
	  onMount(() => {
		textInputElement.focus();
	  });
	}
	function updateTweetText(event) {
	  inputText = event.target.value;
	  charCountText = inputText.length;
	}
	function handleTextBlur() {
	  if (inputText.trim() === "") {
		inputText = tweetText;
	  }
	  tweetText = inputText;
	  isEditingText = false;
	}
	$: charCountText = inputText.length > 280 ? 280 : inputText.length;
	$: inputText = inputText.slice(0, 280);
	// editing text
	// reset
  
	function resetValuesAndTheme() {
	  dateTime = new Date().toISOString().slice(0, 16);
	  viewCount = 0;
	  retweetCount = 0;
	  quoteCount = 0;
	  likeCount = 0;
	  bookmarkCount = 0;
	  tweetTitle = "Tweet Generator";
	  tweetHandle = "@tweetgenerator";
	  tweetText = `
		Hey there, Welcome to tweet generator ✨
  
		- You can edit anything you want by clicking on them
		- Move to the preview mode from the top bar
		- Checkout the preview and download your image in one-click
	  `;
	  tweetImage = "";
	  imageUrl = "/avatr.jpg";
	  fileInput.value = "";
	  imageInput.value = "";
	  inputHandle = tweetHandle;
	  inputText = tweetText;
	  charCountHandle = tweetHandle.length;
	  charCountText = tweetText.length;
	  light();
	}
	// reset
  </script>
  
  <head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
	  href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700&display=swap"
	  rel="stylesheet"
	/>
  </head>
  <div class="card rounded-lg">
	<div class="tweet-section">
	  <div class="container">
		<div class="side-container">
		  <div class="title">
			<svg
			  xmlns="http://www.w3.org/2000/svg"
			  enable-background="new 0 0 1668.56 1221.19"
			  viewBox="0 0 1668.56 1221.19"
			  class="twitter-logo"
			  ><circle
				cx="834.28"
				cy="610.6"
				r="481.33"
				stroke="#fff"
				stroke-miterlimit="10"
			  ></circle><path
				fill="#fff"
				d="M485.39,356.79l230.07,307.62L483.94,914.52h52.11l202.7-218.98l163.77,218.98h177.32
			  L836.82,589.6l215.5-232.81h-52.11L813.54,558.46L662.71,356.79H485.39z M562.02,395.17h81.46l359.72,480.97h-81.46L562.02,395.17
			  z"
				transform="translate(52.39 -25.059)"
			  ></path></svg
			>
			<span class="title-head">CraftLab Tweet Generator</span>
		  </div>
		  <div class="description">
			<h1 class="">Tweet Generator</h1>
			<p class="chakra-text-2">
			  Generate mock screenshots of tweets easily.
			</p>
			<p class="chakra-text">
			  Developed by Team-4 at CraftLab, our Tweet Generator creates
			  realistic tweet simulations. Perfect for pranking friends,
			  strategizing marketing campaigns, designing interfaces, and studying
			  social impacts. Simulate user handles, tweet content, hashtags, and
			  engagement metrics effortlessly. The ultimate tool for crafting
			  convincing mock tweets tailored to your needs.
			</p>
		  </div>
		</div>
	  </div>
  
	  <div class="right-container">
		<div class="header">
		  <div class="buttons flex justify-center">
			<div class="button-container flex">
			  <div class="edit-button">Edit</div>
			  <div class="preview-button">Preview</div>
			</div>
		  </div>
  
		  <div class="tweet-container">
			<div class="tweet-generator">
			  <div class="generator">
				<div class="gen-header">
				  <div class="twitter-header">
					<!--image avatar-->
					<div class="generator-avatar">
					  <input
						type="file"
						class="files"
						accept=".jpg, .jpeg, .png"
						on:change={handleImageChange}
						bind:this={fileInput}
					  />
					  <div class="avatar-wrapper">
						<img class="avatar" src={imageUrl} alt="" />
					  </div>
					</div>
					<!--image avatar-->
  
					<div class="gen-title">
					  <div class="editable">
						{#if isEditing}
						  <input
							class="tweet-generator-title"
							value={inputValue}
							on:blur={handleInputBlur}
							on:input={updateTweetTitle}
						  />
						  <p class="character-count">
							{characterCount}/50 characters written
						  </p>
						{:else}
						  <span
							class="editable_preview"
							on:click={handleTweetTitleClick}
						  >
							{tweetTitle}
						  </span>
						{/if}
						<button
						  type="button"
						  class="logo-button"
						  id="menu-button"
						  aria-expanded="false"
						  aria-haspopup="menu"
						  aria-controls="menu-list"
						>
						  <svg
							fill="#3c9aff"
							viewBox="0 0 22 22"
							focusable="false"
							class="chakra-icon"
							aria-hidden="true"
						  >
							<path
							  d="M20.396 11a3.487 3.487 0 00-2.008-3.062 3.474 3.474 0 00-.742-3.584 3.474 3.474 0 00-3.584-.742A3.468 3.468 0 0011 1.604a3.463 3.463 0 00-3.053 2.008 3.472 3.472 0 00-1.902-.14c-.635.13-1.22.436-1.69.882a3.461 3.461 0 00-.734 3.584A3.49 3.49 0 001.604 11a3.496 3.496 0 002.017 3.062 3.471 3.471 0 00.733 3.584 3.49 3.49 0 003.584.742A3.487 3.487 0 0011 20.396a3.476 3.476 0 003.062-2.007 3.335 3.335 0 004.326-4.327A3.487 3.487 0 0020.396 11zM9.662 14.85l-3.429-3.428 1.293-1.302 2.072 2.072 4.4-4.794 1.347 1.246z"
							></path>
						  </svg>
						</button>
					  </div>
					  <div class="tweet-editable">
						<div class="">
						  {#if isEditingHandle}
							<input
							  class="tweet-subheading"
							  bind:value={inputHandle}
							  on:blur={handleHandleBlur}
							  on:input={updateTweetHandle}
							  on:keyup={(event) =>
								event.key === "Enter" && handleHandleBlur()}
							/>
							<p class="character-count">
							  {charCountHandle}/15 characters. Should be only
							  numbers, letters, and _
							</p>
						  {:else}
							<span
							  class="tweet-editable_preview"
							  on:click={handleTweetHandleClick}
							>
							  {tweetHandle}
							</span>
						  {/if}
						</div>
					  </div>
					</div>
				  </div>
				  <div class="reset">
					<button
					  type="button"
					  class="reset-button"
					  on:click={resetValuesAndTheme}
					  ><span class="reset-button__icon"></span>
					  <p class="reset-text">Reset</p></button
					>
				  </div>
				</div>
				<div>
				  <div class="tweet-text">
					{#if isEditingText}
					  <textarea
						class="tweet-textarea"
						bind:value={inputText}
						on:blur={handleTextBlur}
						on:input={updateTweetText}
					  ></textarea>
					  <p class="character-count">
						{charCountText}/280 characters
					  </p>
					{:else}
					  <div on:click={handleTweetTextClick}>
						{#each inputText.split("\n") as line}
						  {#if line.trim() === ""}
							<br />
						  {:else}
							<p>{line}</p>
						  {/if}
						{/each}
					  </div>
					{/if}
				  </div>
				</div>
				<div>
				  <div class="file-input">
					<input
					  type="file"
					  class="files"
					  accept=".jpg, .jpeg, .png"
					  on:change={handleImgChange}
					  bind:this={imageInput}
					/>
					<div class="image-wrapper">
					  <img class="photo" src={tweetImage} alt="" />
					  
					  <p class="file-text">
						Drag and drop or click here to add image
					  </p>
					</div>
				  </div>
				</div>
				<div class="date-views">
				  <div class="date-editable">
					<div class="date-area edit-area">
					  <input
						type="datetime-local"
						class="date-edit edit-input"
						bind:value={dateTime}
						on:input={updateDateTime}
						hidden
					  />
					  <!-- svelte-ignore a11y-click-events-have-key-events -->
					  <div
						aria-label="Edit"
						type="button"
						class="date"
						on:click={handleDateClick}
					  >
						<p class="date-text">
						  {new Date(dateTime).toLocaleString("en-US", {
							hour: "numeric",
							minute: "numeric",
							hour12: true,
						  })} · {new Date(dateTime).toLocaleDateString("en-US", {
							month: "short",
							day: "numeric",
							year: "numeric",
						  })}
						</p>
					  </div>
					</div>
				  </div>
  
				  <div class="views-editable">
					<div class="view-area edit-area">
					  <input
						type="number"
						min="0"
						class="view-input edit-input"
						bind:value={viewCount}
						on:input={updateViewCount}
						hidden
					  />
					  <!-- svelte-ignore a11y-click-events-have-key-events -->
					  <div
						aria-label="Edit"
						type="button"
						class="view-div"
						on:click={handleViewClick}
					  >
						<p class="view-count">{viewCount}</p>
						<p class="view-text">Views</p>
					  </div>
					</div>
				  </div>
				</div>
  
				<div class="count-tab">
				  <div class="retweet-area edit-area">
					<input
					  type="number"
					  min="0"
					  class="retweet-input edit-input"
					  bind:value={retweetCount}
					  on:input={updateRetweetCount}
					  hidden
					/>
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<div
					  aria-label="Edit"
					  type="button"
					  class="retweet-div"
					  on:click={handleRetweetClick}
					>
					  <p class="retweet-count">{retweetCount}</p>
					  <p class="retweet-text">Retweets</p>
					</div>
				  </div>
  
				  <div class="quotes-area edit-area">
					<input
					  type="number"
					  min="0"
					  class="quotes-input edit-input"
					  bind:value={quoteCount}
					  on:input={updateQuoteCount}
					  hidden
					/>
					<div
					  aria-label="Edit"
					  type="button"
					  class="quotes-div"
					  on:click={handleQuoteClick}
					>
					  <p class="quotes-count">{quoteCount}</p>
					  <p class="quotes-text">Quotes</p>
					</div>
				  </div>
  
				  <div class="like-area edit-area">
					<input
					  type="number"
					  min="0"
					  class="like-input edit-input"
					  bind:value={likeCount}
					  on:input={updateLikeCount}
					  hidden
					/>
					<div
					  aria-label="Edit"
					  type="button"
					  class="like-div"
					  on:click={handleLikeClick}
					>
					  <p class="like-count">{likeCount}</p>
					  <p class="like-text">Likes</p>
					</div>
				  </div>
  
				  <div class="bookmark-area edit-area">
					<input
					  type="number"
					  min="0"
					  class="bookmark-input edit-input"
					  bind:value={bookmarkCount}
					  on:input={updateBookmarkCount}
					  hidden
					/>
					<div
					  aria-label="Edit"
					  type="button"
					  class="bookmark-div"
					  on:click={handleBookmarkClick}
					>
					  <p class="bookmark-count">{bookmarkCount}</p>
					  <p class="bookmark-text">Bookmarks</p>
					</div>
				  </div>
				</div>
  
				<div class="icon-container">
				  <div class="icon-area">
				   
				  </div>
				  <div class="icon-area">
					
				  </div>
				  <div class="icon-area">
					
				  </div>
				  <div class="icon-area">
				 
				  </div>
				  <div class="icon-area">
					
				  </div>
				</div>
				<!--generator-->
			  </div>
			  <!--tweet-generator-->
			</div>
			<!--tweet-container-->
		  </div>
		  <div class="theme-container">
			<div class="theme-group">
			  <p class="theme-label">Theme:</p>
			  <div class="theme-options" role="radiogroup">
				<div
				  value="Light"
				  name="theme"
				  class="edit-button theme-option Light"
				  data-checked=""
				  on:click={light}
				>
				  Light
				</div>
				<div
				  value="Dark"
				  name="theme"
				  class="theme-option Dark"
				  on:click={dark}
				>
				  Dark
				</div>
				<div
				  value="Dim"
				  name="theme"
				  class="theme-option Dim"
				  on:click={dim}
				>
				  Dim
				</div>
			  </div>
			</div>
			<div class="buttons-container">
			  <div class="button-copy">
				<svg
				  class="copyicon"
				  fill="currentColor"
				  viewBox="0 0 24 24"
				  width="16"
				  height="16"
				>
				  <path
					d="M16 1H4c-1.1 0-2 .9-2 2v14h2V3h12V1zm3 4H8c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h11c1.1 0 2-.9 2-2V7c0-1.1-.9-2-2-2zm0 16H8V7h11v14z"
				  ></path>
				</svg>
			  </div>
			  <div
				class="edit-button button download-button"
				on:click={downloadDivAsImage}
			  >
				<svg
				  class="chakra-icon"
				  fill="currentColor"
				  viewBox="0 0 14 14"
				  width="16"
				  height="16"
				>
				  <path
					d="M11.2857,6.05714 L10.08571,4.85714 L7.85714,7.14786 L7.85714,1 L6.14286,1 L6.14286,7.14786 L3.91429,4.85714 L2.71429,6.05714 L7,10.42857 L11.2857,6.05714 Z M1,11.2857 L1,13 L13,13 L13,11.2857 L1,11.2857 Z"
				  ></path>
				</svg>
				Download
			  </div>
			</div>
		  </div>
		  <!-- break -->
		</div>
		<!--right-container-->
	  </div>
	</div>
	<div class="card-doc bg-white">
	  <div class="card-doc-section">
		<h1 class="text-3xl font-bold mb-10 text-center">{pagetitle}</h1>
		<div class="documentation">
		  {#each steps as { title, content, image, alignLeft }, i}
			<div class="step {alignLeft ? 'left-align' : 'right-align'}">
			  {#if alignLeft}
				<div class="text-content">
				  <h2 class="text-2xl font-semibold mb-4">{title}</h2>
				  <h3 class="text-lg mb-6">{content}</h3>
				</div>
				<div class="image-container">
				  <img src={image} alt="Burger Illustration" />
				</div>
			  {:else}
				<div class="image-container">
				  <img src={image} alt="Elon musk illustration" />
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
				Discover our AI-powered suite of tools designed to supercharge
				your Twitter growth.
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
	</div>
  
	<!--container-->
  </div>
  
  <style>
	.image {
	  width: 100%;
	  min-height: 200px;
	}
	.tweet-textarea {
	  display: block;
	  margin-top: 10px;
	  border: none;
	  padding: 5px;
	  font-size: 16px;
	  width: 100%;
	  height: auto;
	  min-height: 200px;
	}
  
	.editable_preview,
	.tweet-editable_preview {
	  cursor: pointer;
	}
  
	.character-count {
	  font-size: 7px;
	  color: #777;
	}
  
	.tweet-text p {
	  margin: 5px 0;
	}
	.generator-avatar:hover .overlay-icon {
	  opacity: 1;
	}
	.avatar-wrapper {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  height: 100%;
	  text-align: center;
	}
	.character-count {
	  font-size: 10px;
	  color: #777;
	}
	.tweet-subheading {
	  width: 90%;
	}
	.tweet-generator-title {
	  display: block;
	  background-color: #edf2f7;
	  font-size: 16px;
	  font-weight: bold;
	}
	.edit-area {
	  display: flex;
	  align-items: center;
	}
  
	.edit-input {
	  margin-left: 10px;
	  width: 150px;
	}
  
	.view-input,
	.retweet-input,
	.quotes-input,
	.like-input,
	.bookmark-input {
	  margin-left: 10px;
	  width: 50px;
	}
  
	.tweet-genertor-title,
	.tweet-text-textarea {
	  margin-left: 10px;
	  width: 100%;
	}
  
	.tweet-text-textarea {
	  height: 100px;
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
	.theme-container,
	.container,
	.right-container {
	  display: flex;
	  justify-content: space-between;
	  align-items: center;
	  padding: 20px;
	  box-sizing: border-box;
	  font-family: "Open Sans", sans-serif;
	  background-color: #ffffff;
	}
  
	.container,
	.right-container {
	  flex-direction: column;
	  justify-content: space-between;
	  height: 100%;
	}
  
	.right-container {
	  background-color: #edf2f7;
	  box-shadow: -10px 0px 10px -10px rgba(0, 0, 0, 0.153);
	}
  
	.theme-container {
	  padding: 10px;
	  border-radius: 5px;
	  box-shadow: 5px 5px 10px rgba(126, 125, 125, 0.169);
	}
  
	.theme-group,
	.count-tab,
	.date-views,
	.icon-container,
	.buttons-container {
	  display: flex;
	  align-items: center;
	  justify-content: space-between;
	}
  
	.theme-label {
	  font-weight: bold;
	  font-size: 13px;
	  margin-right: 10px;
	}
  
	.theme-options {
	  display: flex;
	  gap: 10px;
	}
	.tweet-text {
	  cursor: pointer;
	}
	.theme-option,
	.edit-button,
	.preview-button,
	.reset-button,
	.logo-button,
	.button-copy {
	  cursor: pointer;
	  padding: 5px 10px;
	  border-radius: 5px;
	  font-size: 13px;
	  font-weight: bold;
	  display: flex;
	  align-items: center;
	}
  
	.theme-option,
	.button-copy {
	  border: 1px solid #e6e8eb;
	  box-shadow: 5px 5px 10px rgba(126, 125, 125, 0.169);
	}
	.editable_preview:hover,
	.tweet-editable_preview:hover,
	.reset-button:hover,
	.date-area:hover,
	.view-area:hover,
	.tweet-text-textarea:hover,
	.tweet-text:hover,
	.tweet-subheading:hover,
	.tweet-genertor-title:hover,
	.bookmark-area:hover,
	.quotes-area:hover,
	.like-area:hover,
	.retweet-area:hover {
	  background-color: #edf2f7;
	  border-radius: 7px;
	}
  
	.download-button,
	.button-copy,
	.download-button svg,
	.button-copy svg {
	  margin-right: 5px;
	}
	.button-copy {
	  background-color: #edf2f7;
	}
	.icon {
	  color: #888;
	}
  
	.count-tab,
	.date-views {
	  margin: 10px 0;
	  padding: 10px 0;
	  border-top: 1.5px solid #e7eaed;
	  border-bottom: 1.5px solid #e7eaed;
	}
  
	.date-area,
	.view-area,
	.bookmark-area,
	.quotes-area,
	.like-area,
	.retweet-area {
	  cursor: pointer;
	  padding-right: 5px;
	}
  
	.date-text,
	.view-text,
	.bookmark-text,
	.quotes-text,
	.like-text,
	.retweet-text {
	  font-size: 14px;
	  color: #777;
	  margin-right: 10px;
	}
  
	.view-count,
	.bookmark-count,
	.quotes-count,
	.like-count,
	.retweet-count {
	  font-weight: bold;
	  color: #222;
	}
  
	.date-text,
	.view-count,
	.view-text,
	.bookmark-text,
	.quotes-text,
	.like-text,
	.retweet-text,
	.bookmark-count,
	.quotes-count,
	.like-count,
	.retweet-count,
	.icon-area {
	  display: inline-block;
	}
  
	.file-icon {
	  color: #666;
	  height: 15px;
	}
  
	.file-input {
	  margin-top: 20px;
	  position: relative;
	  width: 100%;
	  height: 70px;
	  border: 2px dashed #cfd6dd;
	  border-radius: 5px;
	  overflow: hidden;
	  cursor: pointer;
	}
  
	.file-display {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  height: 100%;
	  text-align: center;
	}
  
	.file-text {
	  color: #555;
	  font-size: 12px;
	  margin-top: 5px;
	}
  
	.files {
	  position: absolute;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  opacity: 0;
	  cursor: pointer;
	}
  
	.tweet-text-wrapper,
	.tweet-text-textarea,
	.tweet-text,
	.tweet-subheading,
	.tweet-genertor-title {
	  width: 100%;
	  border: none;
	  outline: none !important;
	  resize: vertical;
	  line-height: 1.5;
	  font-family: inherit;
	  background-color: transparent;
	  overflow: hidden;
	  transition: border-color 0.3s ease;
	  padding: 10px;
	  margin-top: 10px;
	}
  
	.tweet-text-textarea {
	  min-height: 200px;
	  border-radius: 5px;
	}
  
	.tweet-text-textarea:focus,
	.tweet-subheading:focus,
	.tweet-genertor-title:focus {
	  border-color: #edf2f7;
	  outline-color: #edf2f7;
	  background-color: #edf2f7;
	  border-radius: 5px;
	}
  
	.tweet-text-textarea::placeholder,
	.tweet-subheading::placeholder,
	.tweet-genertor-title::placeholder {
	  color: black;
	}
  
	.tweet-subheading {
	  font-size: 13px;
	  color: #7b7b7b;
	}
  
	.tweet-genertor-title {
	  font-size: 16px;
	  font-weight: bold;
	  color: black;
	}
  
	.reset-text {
	  font-size: 15px;
	  font-weight: bold;
	  color: #444;
	}
  
	.reset-button {
	  padding: 10px;
	}
  
	.reset-button__icon svg {
	  color: #444;
	  height: 20px;
	  margin-right: 3px;
	}
  
	.logo-button {
	  background: none;
	  border: none;
	  padding: 5px;
	  cursor: pointer;
	  border: 2px dashed lightgrey;
	}
  
	.logo-button svg {
	  width: 20px;
	  height: 20px;
	}
  
	.logo-button:hover {
	  background-color: #efefef;
	}
  
	.twitter-header,
	.gen-header {
	  display: flex;
	  justify-content: space-between;
	  align-items: center;
	  gap: 10px;
	}
  
	.gen-title {
	  display: flex;
	  flex-direction: column;
	  padding-left: 8px;
	}
  
	.editable {
	  display: flex;
	  align-items: center;
	  gap: 8px;
	}
  
	.editable_preview {
	  font-size: 16px;
	  font-weight: bold;
	}
  
	.tweet-editable_preview {
	  font-size: 13px;
	  color: #7b7b7b;
	}
  
	.generator-avatar {
	  position: relative;
	  display: inline-block;
	}
  
	.tweet-container {
	  padding: 100px 5px;
	  width: auto;
	  max-width: auto;
	  height: auto;
	}
  
	img.avatar {
	  display: block;
	  border-radius: 40px;
	  height: 50px;
	  width: 50px;
	}
  
	.overlay-icon {
	  position: absolute;
	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	  opacity: 0;
	  height: 15px;
	  pointer-events: none;
	  z-index: 5;
	}
  
	.tweet-generator,
	.button-container {
	  background-color: #ffffff;
	  margin: 20px;
	  padding: 20px 5px;
	  box-shadow: 5px 5px 10px rgba(126, 125, 125, 0.169);
	  border-radius: 10px;
	}
  
	.generator {
	  margin: 20px;
	}
  
	.flex {
	  display: flex;
	  align-items: center;
	}
  
	.button-container {
	  width: auto;
	  padding: 10px 15px;
	  box-shadow: 5px 5px 10px rgba(126, 125, 125, 0.189);
	}
  
	.edit-button,
	.preview-button {
	  padding: 5px 20px;
	  font-size: 14px;
	  font-weight: 600;
	}
  
	.edit-button {
	  background-color: #3c9aff;
	  color: white;
	}
  
	.preview-button {
	  color: #3c9aff;
	}
  
	.description,
	.title {
	  text-align: left;
	}
  
	.title {
	  display: flex;
	  align-items: left;
	  justify-content: left;
	  padding-bottom: 150px;
	}
  
	.twitter-logo {
	  height: 30px;
	}
  
	span.title-head {
	  font-size: 20px;
	  font-weight: 800;
	}
  
	.description h1 {
	  font-size: 45px;
	  font-weight: bold;
	}
	.description p {
	  font-size: 18px;
	  line-height: 1.6;
	  margin-bottom: 20px;
	}
	p.chakra-text {
	  font-size: 14px;
	  line-height: 1.6;
	  margin-bottom: 20px;
	}
	.side-container {
	  padding: 10px;
	}
  
	/* Media queries */
	@media (min-width: 1020px) {
	  .tweet-section {
		display: grid;
		grid-template-columns: 1fr 1.5fr;
		gap: 0;
		height: auto;
		min-width: 100vh;
	  }
	  .card-doc {
		display: grid;
		gap: 0;
		height: auto;
		min-width: 100vh;
	  }
	}
  
	@media (max-width: 1020px) {
	  .tweet-section {
		max-width: 100vw;
	  }
  
	  .container,
	  .right-container {
		width: 100%;
		max-width: 100%;
		padding: 10px;
	  }
	  .card-doc {
		max-width: 100vw;
	  }
	}
  </style>
  