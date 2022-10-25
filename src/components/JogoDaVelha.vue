<template>
	<div>
		<div
			class="d-flex justify-content-center gap-2"
			id="vencedor"
			v-if="situacao"
		>
			<div class="alert alert-success text-center p-4 mt-3" role="alert">
				Quem ganhou foi | "{{ this.ganhador }}" |
			</div>
		</div>
		<div class="container-tabuleiro">
			<div class="tabuleiro">
				<input type="text" class="p1" v-model="p1" maxlength="1" />
				<input type="text" class="p2" v-model="p2" />
				<input type="text" class="p3" v-model="p3" />
				<br />

				<input type="text" class="p4" v-model="p4" />
				<input type="text" class="p5" v-model="p5" />
				<input type="text" class="p6" v-model="p6" />
				<br />
				<input type="text" class="p7" v-model="p7" />
				<input type="text" class="p8" v-model="p8" />
				<input type="text" class="p9" v-model="p9" />
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "JogoDaVelha",
	data() {
		return {
			p1: "",
			p2: "",
			p3: "",
			p4: "",
			p5: "",
			p6: "",
			p7: "",
			p8: "",
			p9: "",
			posicoes: {
				posicao1: "",
				posicao2: "",
				posicao3: "",
				posicao4: "",
				posicao5: "",
				posicao6: "",
				posicao7: "",
				posicao8: "",
				posicao9: "",
			},
			ganhador: "",
			situacao: false,
		};
	},
	methods: {
		alerta() {
			alert("Teclada digitada errada");
		},
		zerarTabuleiro() {},
	},
	watch: {
		p1(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p1 = novoValor;
				this.posicoes.posicao1 = this.p1;
			} else {
				this.p1 = "";
			}
		},
		p2(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p2 = novoValor;
				this.posicoes.posicao2 = this.p2;
			} else {
				this.p2 = "";
			}
		},
		p3(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p3 = novoValor;
				this.posicoes.posicao3 = this.p3;
			} else {
				this.p3 = "";
			}
		},
		p4(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p4 = novoValor;
				this.posicoes.posicao4 = this.p4;
			} else {
				this.p4 = "";
			}
		},
		p5(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p5 = novoValor;
				this.posicoes.posicao5 = this.p5;
			} else {
				this.p5 = "";
			}
		},
		p6(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p6 = novoValor;
				this.posicoes.posicao6 = this.p6;
			} else {
				this.p6 = "";
			}
		},
		p7(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p7 = novoValor;
				this.posicoes.posicao7 = this.p7;
			} else {
				this.p7 = "";
			}
		},
		p8(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p8 = novoValor;
				this.posicoes.posicao8 = this.p8;
			} else {
				this.p8 = "";
			}
		},
		p9(novoValor) {
			if (novoValor === "x" || novoValor === "o") {
				this.p9 = novoValor;
				this.posicoes.posicao9 = this.p9;
			} else {
				this.p9 = "";
			}
		},

		ganhador(novoValor) {
			if (novoValor.length === 1) {
				this.situacao = true;
				setTimeout(() => {
					this.situacao = false;
					this.p1 = "";
					this.p2 = "";
					this.p3 = "";
					this.p4 = "";
					this.p5 = "";
					this.p6 = "";
					this.p7 = "";
					this.p8 = "";
					this.p9 = "";
					this.posicoes.posicao1 = "";
					this.posicoes.posicao2 = "";
					this.posicoes.posicao3 = "";
					this.posicoes.posicao4 = "";
					this.posicoes.posicao5 = "";
					this.posicoes.posicao6 = "";
					this.posicoes.posicao7 = "";
					this.posicoes.posicao8 = "";
					this.posicoes.posicao9 = "";
					location.reload();
				}, 3000);
			}
		},
	},
	updated() {
		if (this.posicoes) {
			if (
				(this.posicoes.posicao1.length === 1) &
				(this.posicoes.posicao1 === this.posicoes.posicao2) &
				(this.posicoes.posicao1 === this.posicoes.posicao3)
			) {
				this.ganhador = this.p1.toUpperCase();
				const pp1 = document.querySelector(".p1");
				const pp2 = document.querySelector(".p2");
				const pp3 = document.querySelector(".p3");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			} else if (
				(this.posicoes.posicao1.length === 1) &
				(this.posicoes.posicao1 === this.posicoes.posicao5) &
				(this.posicoes.posicao1 === this.posicoes.posicao9)
			) {
				this.ganhador = this.p1.toUpperCase();
				const pp1 = document.querySelector(".p1");
				const pp2 = document.querySelector(".p5");
				const pp3 = document.querySelector(".p9");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			} else if (
				(this.posicoes.posicao1.length === 1) &
				(this.posicoes.posicao1 === this.posicoes.posicao4) &
				(this.posicoes.posicao1 === this.posicoes.posicao7)
			) {
				this.ganhador = this.p1.toUpperCase();
				const pp1 = document.querySelector(".p1");
				const pp2 = document.querySelector(".p4");
				const pp3 = document.querySelector(".p7");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			}

			if (
				(this.posicoes.posicao2.length === 1) &
				(this.posicoes.posicao2 === this.posicoes.posicao5) &
				(this.posicoes.posicao2 === this.posicoes.posicao8)
			) {
				this.ganhador = this.p2.toUpperCase();
				const pp1 = document.querySelector(".p2");
				const pp2 = document.querySelector(".p5");
				const pp3 = document.querySelector(".p8");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			}

			if (
				(this.posicoes.posicao3.length === 1) &
				(this.posicoes.posicao3 === this.posicoes.posicao6) &
				(this.posicoes.posicao3 === this.posicoes.posicao9)
			) {
				this.ganhador = this.p3.toUpperCase();
				const pp1 = document.querySelector(".p3");
				const pp2 = document.querySelector(".p6");
				const pp3 = document.querySelector(".p9");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			} else if (
				(this.posicoes.posicao3.length === 1) &
				(this.posicoes.posicao3 === this.posicoes.posicao5) &
				(this.posicoes.posicao3 === this.posicoes.posicao7)
			) {
				this.ganhador = this.p3.toUpperCase();
				const pp1 = document.querySelector(".p3");
				const pp2 = document.querySelector(".p5");
				const pp3 = document.querySelector(".p7");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			}

			if (
				(this.posicoes.posicao4.length === 1) &
				(this.posicoes.posicao4 === this.posicoes.posicao5) &
				(this.posicoes.posicao4 === this.posicoes.posicao6)
			) {
				this.ganhador = this.p4.toUpperCase();
				const pp1 = document.querySelector(".p4");
				const pp2 = document.querySelector(".p5");
				const pp3 = document.querySelector(".p6");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			}

			if (
				(this.posicoes.posicao7.length === 1) &
				(this.posicoes.posicao7 === this.posicoes.posicao8) &
				(this.posicoes.posicao7 === this.posicoes.posicao9)
			) {
				this.ganhador = this.p7.toUpperCase();
				const pp1 = document.querySelector(".p7");
				const pp2 = document.querySelector(".p8");
				const pp3 = document.querySelector(".p9");
				pp1.classList.add("cor");
				pp2.classList.add("cor");
				pp3.classList.add("cor");
			}
			if (
				(this.posicoes.posicao1.length === 1) &
				(this.posicoes.posicao2.length === 1) &
				(this.posicoes.posicao3.length === 1) &
				(this.posicoes.posicao4.length === 1) &
				(this.posicoes.posicao5.length === 1) &
				(this.posicoes.posicao6.length === 1) &
				(this.posicoes.posicao8.length === 1) &
				(this.posicoes.posicao9.length === 1) &
				(this.ganhador === "")
			) {
				setTimeout(() => {
					alert("Empate");
					location.reload();
				}, 300);
			}
		}
	},
};
</script>
<style scoped>
.cor {
	background-color: green;
}
.zerar {
	padding: 5px 10px;
	background-color: red;
	color: white;
	border: 1px solid red;
}
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
.container-tabuleiro {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 200px;
}
.p1,
.p2,
.p3,
.p4,
.p5,
.p6,
.p7,
.p8,
.p9 {
	padding: 20px;
}
input {
	border: none;
	text-align: center;
	font-size: 2rem;
}

.p1 {
	border-right: 4px solid black;
	border-bottom: 4px solid black;
	outline: none;
}
.p2 {
	border-right: 4px solid black;
	border-bottom: 4px solid black;
	outline: none;
}
.p3 {
	border-bottom: 4px solid black;
	outline: none;
}
.p4 {
	border-right: 4px solid black;
	border-bottom: 4px solid black;
	outline: none;
}
.p5 {
	border-right: 4px solid black;
	border-bottom: 4px solid black;
	outline: none;
}
.p6 {
	border-bottom: 4px solid black;
	outline: none;
}
.p7 {
	border-right: 4px solid black;
	outline: none;
}
.p8 {
	border-right: 4px solid black;

	outline: none;
}
.p9 {
	outline: none;
}
</style>
