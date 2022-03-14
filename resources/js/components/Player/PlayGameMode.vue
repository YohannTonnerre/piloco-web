<template>
	<div class="container-game-mode">
		<h1> MODE DE JEU : </h1>
		<p> Désigne l'intensité dalcool que vous allez ingurgez ! </p>

			<div class="game-mode">
				<div @click="selectGame('selectGame1')" ref="selectGame1" class="button-game-mode"> 
						<img class="logo-mode" src="/img/facile-mode.png" alt="Mode Facile">
					<div class="txt-game-mode"> Facile </div>
				</div>
				<div @click="selectGame('selectGame2')" ref="selectGame2" class="button-game-mode"> 
						<img class="logo-mode" src="/img/medium-mode.png" alt="Mode Medium">
					<div class="txt-game-mode"> Medium </div>
				</div>
			</div>
			<div class="game-mode">
				<div @click="selectGame('selectGame3')" ref="selectGame3" class="button-game-mode"> 
						<img class="logo-mode" src="/img/difficile-mode.png" alt="Mode Diffile">
					<div class="txt-game-mode"> Difficile </div>
				</div>
				<div @click="selectGame('selectGame4')" ref="selectGame4" class="button-game-mode"> 
						<img class="logo-mode" src="/img/alcooliques-mode.png" alt="Mode Alcoolique">
					<div class="txt-game-mode"> Alcoolique </div>
				</div>
			</div>

		<button class="lancer-partie"> Lancer la partie </button>
	</div>

	<table class="table">
		<tr>
			<th>Name</th>
			<th></th>
		</tr>

		<tr v-for="mode in modes" :key="mode">
			<td>{{ mode.name }}</td>
			<td>
				<button @click="submit(mode.id)" class="btn btn-warning">
					Jouer
				</button>
			</td>
		</tr>
	</table>
</template>

<style lang="scss">
	@import "../../../sass/_variables.scss";

	.lancer-partie{
		background-color: $orange;
		margin-top: 40px;
		border: 0px;
		color: $white;
		padding: 5px 40px;
		border-radius: 5px;
		transition: 0.2s;
	}

	.lancer-partie:hover{
		background-color: $orange;
		margin-top: 40px;
		border: 0px;
		color: $white;
		padding: 5px 40px;
		border-radius: 5px;
		font-size: 1.1rem;
		transition: 0.2s;
	}

	.txt-game-mode{
		background-color: $white;
		color: $black;
		margin-top: 20px;
		width: 100%;
		text-align: center;
	}

	.container-game-mode{
		height: 100vh;
		background-color: $blue;
		color: $white;
		@include center-v-h;
		flex-direction: column;
		align-items: center;
	}

	.game-mode{
		display: flex;
		justify-content: inherit;
		width: 80%;
		height: 80%;
		max-height: 200px;
	}

	.button-game-mode{
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin: 10px;
		max-width: 150px;
		width: 100%;
		background-color: $orange;
		transition: 0.2s;
		cursor: pointer;
	}

	.button-game-mode:hover{
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin: 10px;
		max-width: 150px;
		width: 100%;
		background-color: $orange;
		transform: scale(1.1);
		transition: 0.2s;
		cursor: pointer;
	}

	.logo-mode{
		width: 50%;
	}
	.selectGame{
		border: 4px solid $black;
		transform: scale(1.1);
	}
</style>

<script>
import { authenticatedFetch } from "../../utils"

export default {
	data() {
		return {
			modes: [],
			data: {
				room: null,
				playerId: parseInt(localStorage.token.substr(0, localStorage.token.indexOf('|')))
			}
		}
	},

	methods: {
		allModes: function () {
			authenticatedFetch("get", "/api/mode/all").then((res) => {
				this.modes = res.data
			})
		},

		submit: function (e) {

			authenticatedFetch("POST", "/api/create-game", this.data)
				.then((res) => {
					console.log(res)
					this.$router.push({
						name: 'PlayGamePicolo', params: {
							difficultyId: e,
							room: this.data.room,
							gameId: res.data
						}
					})
				})
				.catch(error => {
					console.error(error)
				})
		},
		selectGame(selectGame) {

			this.$refs['selectGame1'].classList.remove('selectGame')
			this.$refs['selectGame2'].classList.remove('selectGame')
			this.$refs['selectGame3'].classList.remove('selectGame')
			this.$refs['selectGame4'].classList.remove('selectGame')
			this.$refs[selectGame].classList.add('selectGame')  
		}
	},

	created() {
		this.allModes()
		this.data.room = Math.floor((1 + Math.random()) * 0x10000)
			.toString(16)
			.substring(1)
	},
};
</script>
