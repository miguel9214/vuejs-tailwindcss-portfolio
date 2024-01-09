<script>
export default {
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:'¡Hola! Soy Miguel Ramos, un ingeniero de sistemas con una pasión por el desarrollo web. Como desarrollador junior, combino mi sólido trasfondo técnico con mi energía juvenil y compromiso. Me encanta desafiarme a mí mismo tanto en el mundo del código como en el gimnasio, donde canalizo mi disciplina y determinación. Mi creatividad y habilidad para generar buenas ideas son innegables. Me esfuerzo por contribuir con soluciones innovadoras y eficientes a los desafíos que se presentan en el desarrollo web. Mi enfoque es siempre aprender y crecer, aprovechando cada oportunidad para mejorar mis habilidades y contribuir al éxito del equipo.',
				},
				{
					id: 2,
					bio:
						'¡Estoy emocionado por la posibilidad de ser parte de proyectos apasionantes y seguir evolucionando como desarrollador web junior',
				},
			],
		};
	},
};
</script>

<template>
	<div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
		<!-- About profile image -->
		<div class="w-full sm:w-1/4 mb-7 sm:mb-0">
			<img
				src="@/assets/images/profile.jpeg"
				class="rounded-xl w-96"
				alt=""
			/>
		</div>

		<!-- About details -->
		<div class="w-full sm:w-3/4 text-left">
			<p
				v-for="bio in bios"
				:key="bio.id"
				class="font-general-regular mb-4 text-ternary-dark dark:text-ternary-light text-lg"
			>
				{{ bio.bio }}
			</p>
		</div>
	</div>
</template>
