<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Tabs from './shared/Tabs.svelte';
	import CreatePollForm from './components/CreatePollForm.svelte';
	import PollList from './components/PollList.svelte';


	//tabs
	let items =['Current Polls', 'Add New Poll'];
	let activeItem='Current Polls';

	const tabChanger = (e) => {
		activeItem = e.detail;
	}

	//polls


	const handleAdd =(e)=>{
		activeItem = 'Current Polls'
	};




</script>
<Header></Header>
<main>
	<Tabs {items}  {activeItem} on:tabChange={tabChanger}/>
	{#if activeItem === 'Current Polls'}
		<PollList/>
	{:else if activeItem === 'Add New Poll'}
		<CreatePollForm on:add ={handleAdd}/>
	{/if}
</main>
<Footer></Footer>

<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
	
</style>  