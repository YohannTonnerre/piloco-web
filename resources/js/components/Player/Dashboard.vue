<template>
	<div>
		<!-- <router-link :to="{ name: 'CreateRoom' }">Lancer une partie</router-link>
		<button @click.prevent="logout">Logout</button> -->
		<div class="dashboard">
			<div class="piloco-presentation">
				<img class="logo-size" src="/img/logo.png" alt="logo de piloco">
				<div class="presentation-texte">
					Un jeu fait uniquement pour vous amuser en soirée !
				</div>
			</div>
			<div class="game-create-start">
				<div class="h-50 position-relative">
					<div>
						<img src="/img/creation-partie.png" alt="Créer la partie">
						<div class="btn-partie btn-rejoindre-partie"> Créer la partie </div>
					</div>
				</div>
				<div class="h-50 position-relative">
					<div>
						<div class="btn-partie btn-creer-partie"> Rejoindre une partie </div>
						<img src="/img/rejoindre-partie.png" alt="Créer la partie">
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	methods: {
		logout() {
			axios.post('/api/logout').then(() => {
				this.$router.push({ name: 'Home' })
			})
		}
	},
}
</script>

<style lang="scss">

	@import "../../../sass/_variables.scss";

	.dashboard{
		height: 100vh;
		display: flex;
			
			.btn-partie{
				padding: 10px 30px;
				width: fit-content;
			}

			.btn-rejoindre-partie{
				background-color: $blue;
				color: $white;
				font-size: 40px;
				@include center-v-h;
			}

			.btn-creer-partie{
				background-color: $orange;
				color: $white;
				font-size: 40px;
				@include center-v-h;
			}
		.piloco-presentation{
			background-color: $blue;
			width: 40%;
			@include center-v-h;
			flex-direction: column;

			.logo-size{
				width: 80%;
				margin-left: auto;
				margin-right: auto;
			}

			.presentation-texte{
				text-align: center;
				margin-top: 40px;
				color: $white;
				font-size: 2rem;
				margin-left: 20px;
				margin-right: 20px;
			}
		}
		.game-create-start{
			background-color: $white;
			width: 60%;

			.position-relative{
				position: relative;
			}
		}
	}


</style>
