<template>
  <div class="container">
    <div class="row">
      <div class="col-6 bg-light">
        <span class="fs-4">ENTRADA DE DADOS</span>
        <hr />
        <!-- <form @submit.prevent="enviar($event)"> -->
        <form @reset.prevent="resetar()">
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Nome:</label>
            <div class="col">
              <input type="text" class="form-control" v-model="form.nome" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">E-mail:</label>
            <div class="col">
              <input type="email" class="form-control" v-model="form.email" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Senha:</label>
            <div class="col">
              <input
                type="password"
                class="form-control"
                v-model="form.senha"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Idade:</label>
            <div class="col">
              <input type="number" class="form-control" v-model="form.idade" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Gênero:</label>
            <div class="col">
              <div class="form-check form-check-inline">
                <input
                  class="form-check-input"
                  type="radio"
                  value="Feminino"
                  v-model="form.genero"
                />
                <label class="form-check-label"> Feminino </label>
              </div>
              <div class="form-check form-check-inline">
                <input
                  class="form-check-input"
                  type="radio"
                  value="Masculino"
                  v-model="form.genero"
                />
                <label class="form-check-label"> Masculino </label>
              </div>
            </div>
          </div>

          <div class="mb-3 row">
            <label class="col-3 col-form-label">Licença:</label>
            <div class="col">
              <div class="form-check form-switch">
                <input
                  class="form-check-input"
                  type="checkbox"
                  v-model="form.licenca"
                  true-value="SIM"
                  false-value="NAO"
                />
                <label class="form-check-label">Li e aceito os termos</label>
              </div>
            </div>
          </div>

          <div class="mb-3 row">
            <label class="col-3 col-form-label">Interesses:</label>
            <div class="col">
              <div class="form-check">
                <input
                  class="form-check-input"
                  type="checkbox"
                  value="JavaScript"
                  v-model="form.interesse"
                />
                <label class="form-check-label"> JavaScript </label>
              </div>
              <div class="form-check">
                <input
                  class="form-check-input"
                  type="checkbox"
                  value="VueJs"
                  v-model="form.interesse"
                />
                <label class="form-check-label"> VueJS </label>
              </div>
              <div class="form-check">
                <input
                  class="form-check-input"
                  type="checkbox"
                  value="Angular"
                  v-model="form.interesse"
                />
                <label class="form-check-label"> Angular </label>
              </div>
              <div class="form-check">
                <input
                  class="form-check-input"
                  type="checkbox"
                  value="NodeJS"
                  v-model="form.interesse"
                />
                <label class="form-check-label"> NodeJS </label>
              </div>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Telefone:</label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.telefone"
                v-maska="['(##) ####-####', '(##) #####-####']"
              />
              <small class="text-muted">Formato: 11 97777-5555</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Cep:</label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.cep"
                v-maska="'#####-###'"
              />
              <small class="text-muted">Formato: 00000-000</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">CPF:</label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.cpf"
                v-maska="'###.###.###-##'"
              />
              <small class="text-muted">Formato: 000.000.000-00</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">CNPJ:</label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.cnpj"
                v-maska="'##.###.###/####-##'"
              />
              <small class="text-muted">Formato: 00.000.000/0000-00</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Cartão de Credito:</label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.cartaoDeCredito"
                v-maska="'#### #### #### ####'"
              />
              <small class="text-muted">Formato: 0000 0000 0000 0000</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Placa Veículo: </label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.placaVeiculo"
                v-maska="'AAA-####'"
              />
              <small class="text-muted">Formato: AAA-0000</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Placa Mercosul Veículo: </label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.placaVeiculoMercosul"
                v-maska="'AAA#A##'"
              />
              <small class="text-muted">Formato: AAA0A00</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">RG: </label>
            <div class="col">
              <input
                type="text"
                class="form-control"
                v-model="form.rg"
                v-maska="'#*-X'"
              />
              <small class="text-muted">Formato: Sem padrão</small>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Data:</label>
            <div class="col">
              <input type="date" class="form-control" v-model="form.data" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Data/hora local:</label>
            <div class="col">
              <input
                type="datetime-local"
                class="form-control"
                v-model="form.dataHoraLocal"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Mês:</label>
            <div class="col">
              <input type="month" class="form-control" v-model="form.mes" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Semana:</label>
            <div class="col">
              <input type="week" class="form-control" v-model="form.semana" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Hora:</label>
            <div class="col">
              <input type="time" class="form-control" v-model="form.hora" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Cor:</label>
            <div class="col">
              <input type="color" class="form-color" v-model="form.cor" />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Valor limite:</label>
            <div class="col">
              <input
                type="range"
                class="form-range"
                min="0"
                max="100"
                step="0.1"
                v-model="form.alcance"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Escondido:</label>
            <div class="col">
              <input
                type="hidden"
                class="form-control"
                v-model="form.escondido"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Upload:</label>
            <div class="col">
              <input
                type="file"
                class="form-control"
                multiple
                @change="selecionarArquivos($event)"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Descrição:</label>
            <div class="col">
              <textarea
                class="form-control"
                rows="3"
                v-model="form.descricao"
              ></textarea>
            </div>
          </div>
          <div class="mb-3 row">
            <label class="col-3 col-form-label">Cursos:</label>
            <div class="col">
              <select class="form-select" v-model="form.curso">
                <option value="" disabled>-- Selecione um curso</option>
                <option
                  v-for="curso in cursos"
                  :key="curso.id"
                  :value="curso.id"
                >
                  {{ curso.curso }}
                </option>
              </select>
            </div>
          </div>

          <div class="mb-3 row">
            <label class="col-3 col-form-label">Avaliação:</label>
            <div class="col">
              <!-- <InputEstrelas
                :numero-estrelas="5"
                @avaliar="form.avaliacao = $event"
              /> -->
              <InputEstrelas
                :numero-estrelas="5"
                v-model:avaliar="form.avaliacao"
              />
            </div>
          </div>

          <hr />
          <div class="mb-3 row">
            <div class="col d-flex justify-content-between">
              <button class="btn btn-secondary" type="reset">Limpar</button>
              <button
                class="btn btn-success"
                type="button"
                @click="enviar($event)"
              >
                Enviar (btn)
              </button>
              <button class="btn btn-success" type="submit">
                Enviar (submit)
              </button>
            </div>
          </div>
        </form>
      </div>

      <div
        class="col-6 text-white bg-secondary"
        :style="`background-color: ${form.cor} !important`"
      >
        <span class="fs-4">ESTADO DO OBJETO</span>
        <hr />
        <div class="mb-5 row">
          <span>{{ form }}</span>
        </div>

        <span class="fs-4">SAÍDA DE DADOS</span>
        <hr />
        <div class="mb-3 row">
          <span
            >Nome: <span class="border-bottom">{{ form.nome }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >E-mail: <span class="border-bottom">{{ form.email }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Senha: <span class="border-bottom">{{ form.senha }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Idade: <span class="border-bottom">{{ form.idade }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Gênero: <span class="border-bottom">{{ form.genero }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Licença:
            <span class="border-bottom">{{ form.licenca }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Interesses:
            <span class="border-bottom">{{ form.interesse }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Telefone:
            <span class="border-bottom">{{ form.telefone }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Cep: <span class="border-bottom">{{ form.cep }}</span>
          </span>
        </div>
        <div class="mb-3 row">
          <span
            >CPF: <span class="border-bottom">{{ form.cpf }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >CNPJ: <span class="border-bottom">{{ form.cnpj }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Cartão de credito:
            <span class="border-bottom">{{ form.cartaoDeCredito }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Placa Veículo:
            <span class="border-bottom">{{ form.placaVeiculo }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Placa Veículo Mercosul:
            <span class="border-bottom">{{
              form.placaVeiculoMercosul
            }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >RG: <span class="border-bottom">{{ form.rg }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Data:
            <span class="border-bottom"
              >{{ form.data }} |
              {{ $moment(form.data).format("DD/MM/YYYY") }}</span
            ></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Data/hora local:
            <span class="border-bottom">{{ form.dataHoraLocal }}</span></span
          >
          <ul>
            <li>
              Dia da semana:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).format("dddd")
              }}</span>
            </li>
            <hr />
            <li>
              Add dias:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).add(10, "days").format("LL")
              }}</span>
            </li>
            <li>
              Add Mês:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).add(1, "months").format("LL")
              }}</span>
            </li>
            <li>
              Add Anos:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).add(2, "years").format("LL")
              }}</span>
            </li>
            <hr />
            <li>
              Sub dias:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).subtract(10, "days").format("LL")
              }}</span>
            </li>
            <li>
              Sub Mês:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).subtract(1, "months").format("LL")
              }}</span>
            </li>
            <li>
              sub Anos:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).subtract(2, "years").format("LL")
              }}</span>
            </li>
            <hr />
            <li>
              Data extenso:
              <span class="border-bottom">{{
                $moment(form.dataHoraLocal).format("LLLL")
              }}</span>
            </li>
          </ul>
        </div>
        <div class="mb-3 row">
          <span
            >Mês: <span class="border-bottom">{{ form.mes }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Semana: <span class="border-bottom">{{ form.semana }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Hora: <span class="border-bottom">{{ form.hora }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Cor: <span class="border-bottom">{{ form.cor }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Valor limite:
            <span class="border-bottom">{{ form.alcance }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span
            >Escondido:
            <span class="border-bottom">{{ form.escondido }}</span></span
          >
        </div>
        <div class="mb-3 row">
          <span>Upload:</span>
          <ul>
            <li v-for="(arquivo, index) in form.arquivos" :key="index">
              Nome: <span class="border-bottom">{{ arquivo.name }}</span>
            </li>
          </ul>
        </div>
        <div class="mb-3 row">
          <span
            >Descrição:
            <span class="border-bottom">
              <pre>{{ form.descricao }}</pre>
            </span></span
          >
        </div>
        <div class="mb-3 row">
          <span>
            Curso: <span class="border-bottom">{{ form.curso }}</span>
          </span>
        </div>
        <div class="mb-3 row">
          <span>
            Avaliacao: <span class="border-bottom">{{ form.avaliacao }}</span>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import InputEstrelas from "./InputEstrelas.vue";

export default {
  name: "FormStuding",

  components: {
    InputEstrelas,
  },

  data() {
    return {
      cursos: [
        { id: 1, curso: "Banco de dados relacionais" },
        { id: 2, curso: "Desenvolvimento web com VueJS" },
        { id: 3, curso: "Desenvolvimento web com Angular" },
        { id: 4, curso: "Desenvolvimento web com ReactJs" },
      ],
      form: {},
      formEstadoInicial: {
        nome: "",
        email: "",
        senha: "",
        idade: "",
        licenca: "SIM",
        interesse: ["VueJs", "Angular"],
        genero: "Feminino",
        telefone: "",
        cep: "",
        cpf: "",
        cnpj: "",
        cartaoDeCredito: "",
        rg: "",
        placaVeiculo: "",
        placaVeiculoMercosul: "",
        data: "",
        dataHoraLocal: "",
        mes: "",
        semana: "",
        hora: "",
        cor: "#6C757D",
        alcance: 2,
        escondido: "Input Oculto",
        arquivos: {},
        descricao: "",
        curso: "",
        avaliacao: 0,
      },
    };
  },

  created() {
    this.resetar();
  },

  methods: {
    selecionarArquivos(event) {
      this.form.arquivos = event.target.files;
    },

    enviar(event) {
      console.log(event);
      console.log("📋: ", this.form);
      const copiaForm = { ...this.form };
      console.log("🔑: ", copiaForm);
    },

    resetar() {
      this.form = { ...this.formEstadoInicial };
    },
  },
};
</script>

<style>
</style>

// ferramentas utilizadas