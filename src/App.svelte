
<style>
	:global(body){
		background-color: black;
		background-color: rgb(0, 0, 0);
    margin: 0px;
    height: 100vh;
    display: grid;
    place-items: center;
	}
	
	.card-group, .card,.container {
		aspect-ratio: 5 / 7;
	}
	
.card-group, .big-card,.container {
	width: 30vmin;
	}
	.container{
		position: absolute;
	}
	.card {
		background-color: rgba(255, 255, 255, 0.05);
		position: absolute;
		transition: transform 800ms cubic-bezier(.05,.43,.25,.95);
		background-position: center;
		background-size: cover;
	}
	.big-card {
		width: 30vmin;
		border-radius: 1vmin;
	}
.little-card {
    width: 12vmin;
    border-radius: 2vmin;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}
.card-group {
    position: absolute;
    transition: transform 400ms ease;
}
.big-card:nth-child(2) {
	transform: translateX(-10%) rotate(-1deg);
	background-image: url("https://picsum.photos/200/301");
}
.big-card:nth-child(4) {
	transform: rotate(2deg);
	background-image: url("https://picsum.photos/200/302");
}
.big-card:nth-child(6) {
	transform: translateX(-10%) rotate(-3deg);
	background-image: url("https://picsum.photos/200/303");
}
.big-card:nth-child(8) {
	
	transform:translate(10%,3%) rotate(5deg);
	background-image: url("https://picsum.photos/200/304");
}
.card-group:hover .big-card:nth-child(2) {
	transform: translate(-75%,16%) rotate(-24deg) ;
}
.card-group:hover .big-card:nth-child(4) {
	transform: translate(-25%,8%) rotate(-8deg) ;
}
.card-group:hover .big-card:nth-child(6) {
	transform: translate(25%,8%) rotate(8deg) ;
}
.card-group:hover .big-card:nth-child(8) {
	transform: translate(75%,16%) rotate(24deg) ;
}
.card-group:hover > .little-card:nth-child(1) {
	transform: translate(270%, -180%) rotate(-15deg) ;
	background-image: url("https://picsum.photos/200/300");
}
.card-group:hover > .little-card:nth-child(3) {
	transform: translate(180%, 180%) rotate(15deg) ;
	background-image: url("https://picsum.photos/201/300");

}
.card-group:hover > .little-card:nth-child(5) {
	transform: translate(-200%, -190%) rotate(15deg) ;
	background-image: url("https://picsum.photos/202/300");
}
.card-group:hover > .little-card:nth-child(7) {
	transform: translate(-270%, 180%) rotate(-15deg) ;
	background-image: url("https://picsum.photos/203/300");
}
.player{
	margin-top: 8vmin;
	display: flex;
	justify-content: space-around;
}
.card-group[data-status="unknown"] {
	transform: scale(0);
}
.card-group[data-status="after"] {
	transform: translateX(50%) scale(0.5);
}
</style>
<div class="overlay">
	<div class="container">
	  <div class="card-group" data-index="0" data-status="active">
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
	  </div>
	  <div class="card-group" data-index="1" data-status="unknown">
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
	  </div>
	  <div class="card-group" data-index="2" data-status="unknown">
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
		<div class="little-card card">
  
		</div>
		<div class="big-card card">
  
		</div>
	  </div>
	</div>
	  <div class="player">
		<button id="play" on:click={()=>onbuttonclick()}>
			<i class="fa-solid fa-heart"></i>
		</button>
		<button id="hide">
			<i class="fa-solid fa-x"></i>
		</button>
	  </div>
	</div>
	<script>
  import { group_outros } from "svelte/internal";

		let active=null;
		const groups=document.querySelectorAll(".card-group");
		function onbuttonclick(){
			active=0;
			const nextIndex=active+1<=groups.length-1?active+1:0;
			const currentGroup=document.querySelector(`[data-index="${active}"]`),
			nextGroup=document.querySelector(`[data-index="${nextIndex}"]`);
			currentGroup.dataset.status="after";
			nextGroup.dataset.status="active";	
			active=nextIndex;
			
			
		}

	</script>