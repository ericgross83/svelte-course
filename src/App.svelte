<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./shared/Tabs.svelte";
  import CreatePollForm from "./components/CreatePollForm.svelte";
  import PollList from "./components/PollList.svelte";

  //    tabs
  let items = ["Current Polls", "Add New Poll"];
  let activeItem = "Current Polls";

  const handleAdd = (e) => {
    const poll = e.detail;
    polls = [poll, ...polls];
    console.log(polls);
    activeItem = "Current Polls";
  };

  const handleUpVote = (e) => {
    const upvote = e.detail;
    let copiedPolls = [...polls];
    let upvotedPoll = polls.find((poll) => poll.id == upvote.id);

    if (upvote.answer === "a") {
      upvotedPoll.votesA++;
    }
    if (upvote.answer === "b") {
      upvotedPoll.votesB++;
    }
    polls = copiedPolls;
  };
</script>

<Header />
<main>
  <Tabs {items} {activeItem} on:tabSelected={(e) => (activeItem = e.detail)} />
  {#if activeItem === "Current Polls"}
    <PollList on:upvote={handleUpVote} />
  {:else if activeItem === "Add New Poll"}
    <CreatePollForm on:add={handleAdd} />
  {/if}
</main>

<Footer />

<style>
  main {
    max-width: 960px;
    margin: 40px auto;
  }
</style>
