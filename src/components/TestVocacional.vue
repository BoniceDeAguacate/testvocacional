<template>
  <div class="test-vocacional">
    <h1>Test de Orientación Vocacional</h1>
    <p>Responde con "Sí" o "No" a cada pregunta según tu preferencia personal.</p>
    
    <div v-if="!showResults" class="questionnaire">
      <!-- Tabla 1C - Carreras Económicas/Comerciales -->
      <div class="section">
        <h2>Tabla 1 C</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.economica.interes" :key="'eco-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('economica', 'interes', index, true)"
                :class="{ active: answers.economica.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('economica', 'interes', index, false)"
                :class="{ active: answers.economica.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.economica.aptitud" :key="'eco-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('economica', 'aptitud', index, true)"
                :class="{ active: answers.economica.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('economica', 'aptitud', index, false)"
                :class="{ active: answers.economica.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 2H - Carreras Humanísticas -->
      <div class="section">
        <h2>Tabla 2 H</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.humanistica.interes" :key="'hum-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('humanistica', 'interes', index, true)"
                :class="{ active: answers.humanistica.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('humanistica', 'interes', index, false)"
                :class="{ active: answers.humanistica.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.humanistica.aptitud" :key="'hum-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('humanistica', 'aptitud', index, true)"
                :class="{ active: answers.humanistica.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('humanistica', 'aptitud', index, false)"
                :class="{ active: answers.humanistica.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 3A - Carreras Artísticas -->
      <div class="section">
        <h2>Tabla 3 A</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.artistica.interes" :key="'art-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('artistica', 'interes', index, true)"
                :class="{ active: answers.artistica.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('artistica', 'interes', index, false)"
                :class="{ active: answers.artistica.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.artistica.aptitud" :key="'art-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('artistica', 'aptitud', index, true)"
                :class="{ active: answers.artistica.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('artistica', 'aptitud', index, false)"
                :class="{ active: answers.artistica.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 4S - Carreras de Salud -->
      <div class="section">
        <h2>Tabla 4 S</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.salud.interes" :key="'sal-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('salud', 'interes', index, true)"
                :class="{ active: answers.salud.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('salud', 'interes', index, false)"
                :class="{ active: answers.salud.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.salud.aptitud" :key="'sal-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('salud', 'aptitud', index, true)"
                :class="{ active: answers.salud.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('salud', 'aptitud', index, false)"
                :class="{ active: answers.salud.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 5I - Carreras de Ingeniería -->
      <div class="section">
        <h2>Tabla 5 I</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.ingenieria.interes" :key="'ing-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('ingenieria', 'interes', index, true)"
                :class="{ active: answers.ingenieria.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('ingenieria', 'interes', index, false)"
                :class="{ active: answers.ingenieria.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.ingenieria.aptitud" :key="'ing-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('ingenieria', 'aptitud', index, true)"
                :class="{ active: answers.ingenieria.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('ingenieria', 'aptitud', index, false)"
                :class="{ active: answers.ingenieria.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 6D - Carreras de Defensa -->
      <div class="section">
        <h2>Tabla 6 D</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.defensa.interes" :key="'def-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('defensa', 'interes', index, true)"
                :class="{ active: answers.defensa.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('defensa', 'interes', index, false)"
                :class="{ active: answers.defensa.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.defensa.aptitud" :key="'def-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('defensa', 'aptitud', index, true)"
                :class="{ active: answers.defensa.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('defensa', 'aptitud', index, false)"
                :class="{ active: answers.defensa.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Tabla 7E - Carreras de Ciencias Exactas -->
      <div class="section">
        <h2>Tabla 7 E</h2>
        <div class="questions">
          <div v-for="(question, index) in questions.exactas.interes" :key="'exa-int-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('exactas', 'interes', index, true)"
                :class="{ active: answers.exactas.interes[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('exactas', 'interes', index, false)"
                :class="{ active: answers.exactas.interes[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
        
        <h3>Aptitud</h3>
        <div class="questions">
          <div v-for="(question, index) in questions.exactas.aptitud" :key="'exa-apt-' + index" class="question">
            <p>{{ question.text }}</p>
            <div class="answer-buttons">
              <button 
                @click="updateAnswer('exactas', 'aptitud', index, true)"
                :class="{ active: answers.exactas.aptitud[index] === true }"
                class="btn-yes"
              >
                Sí
              </button>
              <button 
                @click="updateAnswer('exactas', 'aptitud', index, false)"
                :class="{ active: answers.exactas.aptitud[index] === false }"
                class="btn-no"
              >
                No
              </button>
            </div>
          </div>
        </div>
      </div>

      <div class="submit-section">
        <div class="progress-info">
          <p>Progreso: {{ Object.keys(answers.economica.interes).length + Object.keys(answers.economica.aptitud).length + Object.keys(answers.humanistica.interes).length + Object.keys(answers.humanistica.aptitud).length + Object.keys(answers.artistica.interes).length + Object.keys(answers.artistica.aptitud).length + Object.keys(answers.salud.interes).length + Object.keys(answers.salud.aptitud).length + Object.keys(answers.ingenieria.interes).length + Object.keys(answers.ingenieria.aptitud).length + Object.keys(answers.defensa.interes).length + Object.keys(answers.defensa.aptitud).length + Object.keys(answers.exactas.interes).length + Object.keys(answers.exactas.aptitud).length }} / {{ questions.economica.interes.length + questions.economica.aptitud.length + questions.humanistica.interes.length + questions.humanistica.aptitud.length + questions.artistica.interes.length + questions.artistica.aptitud.length + questions.salud.interes.length + questions.salud.aptitud.length + questions.ingenieria.interes.length + questions.ingenieria.aptitud.length + questions.defensa.interes.length + questions.defensa.aptitud.length + questions.exactas.interes.length + questions.exactas.aptitud.length }} preguntas respondidas</p>
        </div>
        <button 
          @click="calculateResults" 
          :class="{ 'btn-disabled': !areAllQuestionsAnswered() }"
          class="btn-submit"
        >
          {{ areAllQuestionsAnswered() ? 'Ver Resultados' : 'Completa todas las preguntas' }}
        </button>
      </div>
    </div>

    <!-- Resultados -->
    <div v-if="showResults" class="results">
      <h2>Resultados del Test Vocacional</h2>
      <div class="results-grid">
        <div class="result-card">
          <h3>Administrativas, Contables y Económicas</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.economica.interes }}/{{ questions.economica.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.economica.aptitud }}/{{ questions.economica.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Humanísticas, Ciencias Jurídicas y Ciencias Sociales</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.humanistica.interes }}/{{ questions.humanistica.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.humanistica.aptitud }}/{{ questions.humanistica.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Artísticas</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.artistica.interes }}/{{ questions.artistica.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.artistica.aptitud }}/{{ questions.artistica.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Ciencias de la Salud</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.salud.interes }}/{{ questions.salud.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.salud.aptitud }}/{{ questions.salud.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Ingenierías, Carreras Técnicas y Computación</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.ingenieria.interes }}/{{ questions.ingenieria.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.ingenieria.aptitud }}/{{ questions.ingenieria.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Defensa y Seguridad</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.defensa.interes }}/{{ questions.defensa.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.defensa.aptitud }}/{{ questions.defensa.aptitud.length }}</span>
            </div>
          </div>
        </div>

        <div class="result-card">
          <h3>Ciencias Agrarias de la Naturaleza, Zoológicas y Biológicas</h3>
          <div class="score">
            <div class="score-item">
              <span class="label">Total Interés:</span>
              <span class="value">{{ results.exactas.interes }}/{{ questions.exactas.interes.length }}</span>
            </div>
            <div class="score-item">
              <span class="label">Total Aptitud:</span>
              <span class="value">{{ results.exactas.aptitud }}/{{ questions.exactas.aptitud.length }}</span>
            </div>
          </div>
        </div>
      </div>

      <div class="recommendation">
        <h3>Recomendación</h3>
        <p>{{ getRecommendation() }}</p>
      </div>

      <button @click="resetTest" class="btn-reset">Reiniciar Test</button>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'TestVocacional',
  setup() {
    const showResults = ref(false)

    const questions = reactive({
      economica: {
        interes: [
          { text: "¿Aceptarías trabajar escribiendo artículos en la sección económica de un periódico?" },
          { text: "¿Puedes establecer la diferencia conceptual entre macroeconomía y microeconomía?" },
          { text: "¿Si te convocara tu equipo preferido para planificar, organizar y dirigir un campo de deportes, aceptarías?" },
          { text: "¿Te gustaría realizar una investigación que contribuyera a hacer más justa la distribución de la riqueza?" },
          { text: "¿En un equipo de trabajo prefieres el rol de coordinador?" },
          { text: "¿Dirigirías el área de importación y exportación de una empresa?" },
          { text: "¿Te costearías tus estudios trabajando en una auditoría?" },
          { text: "¿Te resultaría gratificante ser asesor contable en una empresa reconocida?" },
          { text: "¿Sabes qué es el PRODUCTO INTERNO BRUTO?" }
        ],
        aptitud: [
          { text: "¿Te ofrecerías para organizar la despedida de soltero(a) de uno de tus amigos?" },
          { text: "¿Organizas tu dinero de manera que te alcance para todos tus gastos?" },
          { text: "¿Distribuyes tu horario adecuadamente para poder hacer todo lo planeado?" },
          { text: "¿Te resulta fácil coordinar un grupo de trabajo?" },
          { text: "¿Si una gran empresa solicita un profesional como gerente comercial, te sentirías a gusto desempeñando ese rol?" }
        ]
      },
      humanistica: {
        interes: [
          { text: "¿Te gustaría trabajar con niños?" },
          { text: "¿Elegirías una carrera cuyo instrumento de trabajo fuera la utilización de un idioma extranjero?" },
          { text: "¿Dedicarías parte de tu tiempo para ayudar a personas de zonas vulnerables?" },
          { text: "¿Te ofrecerías para explicar a tus compañeros un determinado tema que ellos no entendieran?" },
          { text: "¿Pasarías varias horas leyendo un libro de tu interés?" },
          { text: "¿Te interesan los temas relacionados al pasado y a la evolución del hombre?" },
          { text: "¿Participarías en una investigación sobre la violencia en el fútbol (las barras bravas)?" },
          { text: "¿Descubriste algún filósofo o escritor que haya expresado tus mismas ideas antes?" },
          { text: "¿La libertad y la justicia son valores importantes en tu vida?" },
          { text: "¿Lucharías por una causa justa hasta las últimas consecuencias?" }
        ],
        aptitud: [
          { text: "¿Consideras importante que desde la escuela primaria se fomente la actitud crítica y la participación activa?" },
          { text: "¿Preservar las raíces culturales de nuestro país te parece importante y necesario?" },
          { text: "¿En una discusión entre amigos te ofreces como mediador?" },
          { text: "¿Eres de los que defienden causas perdidas?" }
        ]
      },
      artistica: {
        interes: [
          { text: "¿Te gustaría dirigir un proyecto de urbanización en tu barrio?" },
          { text: "¿Te atrae armar rompecabezas?" },
          { text: "¿Eres el que pone un toque de alegría en las fiestas?" },
          { text: "¿Disfrutas trabajando con arcilla o plastilina?" },
          { text: "¿Fuera de los horarios escolares, dedicas algún día a la semana a practicar algún deporte o actividad física?" },
          { text: "¿Tolerarías empezar tantas veces como fuera necesario hasta obtener el logro deseado?" },
          { text: "¿Cuando estás en un grupo de trabajo, te agrada producir ideas originales y que sean tenidas en cuenta?" },
          { text: "¿Desearías que te regalaran algún instrumento musical para tu cumpleaños?" },
          { text: "¿Harías el afiche para una campaña de prevención del SIDA?" },
          { text: "¿Cuando eliges tu ropa o decoras un ambiente, tienes en cuenta la combinación de los colores, las telas o el estilo de los muebles?" }
        ],
        aptitud: [
          { text: "¿Crees que los detalles son tan importantes como el todo?" },
          { text: "¿Te gusta más el trabajo manual que el trabajo intelectual?" },
          { text: "¿Harías un nuevo diseño de una prenda pasada de moda ante una reunión imprevista?" },
          { text: "¿Dirigirías un grupo de teatro independiente?" }
        ]
      },
      salud: {
        interes: [
          { text: "¿Ante un llamado solidario, te ofrecerías para cuidar a un enfermo?" },
          { text: "¿Escuchas atentamente los problemas que tienen tus amigos?" },
          { text: "¿Convences fácilmente a otras personas sobre la validez de tus argumentos?" },
          { text: "¿Te sentirías a gusto trabajando en un ambiente hospitalario?" },
          { text: "¿Participarías en una campaña de prevención contra el virus AH1N1?" },
          { text: "¿Te gustaría hacer un curso de primeros auxilios?" },
          { text: "¿Acostumbras a leer revistas relacionadas con los últimos avances científicos y tecnológicos en el área de salud?" },
          { text: "¿Te gustaría investigar sobre alguna nueva vacuna?" },
          { text: "¿Te resulta interesante el estudio de las ciencias naturales?" },
          { text: "¿Ante una emergencia epidémica, participarías en una campaña brindando tu ayuda?" }
        ],
        aptitud: [
          { text: "¿Consideras que la salud pública debe ser prioritaria, gratuita y eficiente para todos?" },
          { text: "¿Estarías dispuesto a renunciar a un momento placentero para ofrecer tu servicio como profesional?" },
          { text: "¿Ayudas habitualmente a personas invidentes a cruzar la calle?" },
          { text: "¿A una posición negativa siempre planteas un pensamiento positivo?" }
        ]
      },
      ingenieria: {
        interes: [
          { text: "¿Te gustaría trabajar como profesional dirigiendo la construcción de una empresa hidroeléctrica?" },
          { text: "¿Cuando eras pequeño, te interesaba saber cómo estaban construidos tus juguetes?" },
          { text: "¿Cuando tienes que resolver un problema matemático, perseveras hasta encontrar la solución?" },
          { text: "¿Entablas una relación casi personal con tu computador?" },
          { text: "¿Te ofrecerías para colaborar como voluntario en la NASA?" },
          { text: "¿Harías un curso para aprender a fabricar los instrumentos y/o piezas de las máquinas o aparatos con que trabajas?" },
          { text: "¿Te incluirías en un proyecto nacional de desarrollo de la principal fuente de recursos de tu ciudad?" },
          { text: "¿Cuando se daña un electrodoméstico, rápidamente te ofreces para arreglarlo o repararlo?" },
          { text: "¿Te gustaría investigar científicamente sobre cultivos agrícolas?" },
          { text: "¿Enviarías tu hoja de vida a una empresa automotriz que solicita gente para su área de producción?" }
        ],
        aptitud: [
          { text: "¿Planificas detalladamente tus trabajos antes de empezar?" },
          { text: "¿Crees que tus ideas son importantes y haces todo lo posible para ponerlas en práctica?" },
          { text: "¿Trabajar con objetos te resulta más gratificante que trabajar con personas?" },
          { text: "¿Eres exigente y crítico con tu equipo de trabajo?" }
        ]
      },
      defensa: {
        interes: [
          { text: "¿Participarías en un grupo de defensa internacional dentro de alguna fuerza armada?" },
          { text: "¿Te dedicarías a ayudar a personas accidentadas o atacadas por asaltantes?" },
          { text: "¿Participarías como profesional en un espectáculo de acrobacia aérea?" },
          { text: "¿Te gustaría participar para mantener el orden ante grandes desórdenes o catástrofes?" },
          { text: "¿Aceptarías que las mujeres formaran parte de las fuerzas armadas bajo las mismas condiciones que los hombres?" },
          { text: "¿Te interesan las actividades de mucha acción y de reacción rápida en situaciones imprevistas y de peligro?" },
          { text: "¿Elegirías una profesión en la que tuvieras que estar algunos meses alejado de tu familia?" },
          { text: "¿Aceptarías colaborar con el cumplimiento de las normas en lugares públicos?" },
          { text: "¿Te gustaría realizar tareas auxiliares en un avión o aeronave, como izar velas, pintura y conservación de casco, arreglos de averías, conservación de motores?" },
          { text: "¿Estás de acuerdo con la formación de un cuerpo de soldados profesionales?" }
        ],
        aptitud: [
          { text: "¿Usar uniforme te hace sentir distinto, importante?" },
          { text: "¿Crees que el país debe poseer la más alta tecnología armamentista, a cualquier precio?" },
          { text: "¿Ante una situación de emergencia, actúas rápidamente?" },
          { text: "¿Arriesgarías tu vida para salvar la vida de otro que no conoces?" }
        ]
      },
      exactas: {
        interes: [
          { text: "¿Sabes responder qué significa ADN y ARN?" },
          { text: "¿Te atrae investigar sobre los misterios del universo, por ejemplo, los agujeros negros?" },
          { text: "¿Estás informado sobre nuevos descubrimientos que se están realizando sobre la Teoría del Big Bang?" },
          { text: "¿Te gustaría crear nuevas técnicas para descubrir las patologías de algunas enfermedades a través del microscopio?" },
          { text: "¿Te incluirías en un proyecto de investigación de los movimientos sísmicos y sus consecuencias?" },
          { text: "¿Te gustaría trabajar en un laboratorio mientras estudias?" },
          { text: "¿Te radicarías en una zona agrícola-ganadera para desarrollar tus actividades como profesional?" },
          { text: "¿Formarías parte de un equipo de trabajo orientado a la preservación de la flora y la fauna en extinción?" },
          { text: "¿Aceptarías hacer una práctica rentada en una industria de productos alimenticios, en el sector de control de calidad?" },
          { text: "¿Visitarías un observatorio astronómico para conocer en sección el funcionamiento de los aparatos?" }
        ],
        aptitud: [
          { text: "¿El trabajo individual te resulta más rápido y efectivo que el trabajo grupal?" },
          { text: "¿Te interesan más los misterios de la naturaleza que los secretos de la tecnología?" },
          { text: "¿Te inhibes al entrar a un lugar nuevo con gente desconocida?" },
          { text: "¿Tienes interés por saber cuáles son las causas que determinan ciertos fenómenos, aunque saberlo no incida en tu vida?" }
        ]
      }
    })

    const answers = reactive({
      economica: {
        interes: {},
        aptitud: {}
      },
      humanistica: {
        interes: {},
        aptitud: {}
      },
      artistica: {
        interes: {},
        aptitud: {}
      },
      salud: {
        interes: {},
        aptitud: {}
      },
      ingenieria: {
        interes: {},
        aptitud: {}
      },
      defensa: {
        interes: {},
        aptitud: {}
      },
      exactas: {
        interes: {},
        aptitud: {}
      }
    })

    const results = reactive({
      economica: {
        interes: 0,
        aptitud: 0
      },
      humanistica: {
        interes: 0,
        aptitud: 0
      },
      artistica: {
        interes: 0,
        aptitud: 0
      },
      salud: {
        interes: 0,
        aptitud: 0
      },
      ingenieria: {
        interes: 0,
        aptitud: 0
      },
      defensa: {
        interes: 0,
        aptitud: 0
      },
      exactas: {
        interes: 0,
        aptitud: 0
      }
    })

    function updateAnswer(area, type, questionIndex, value) {
      answers[area][type][questionIndex] = value
    }

    function areAllQuestionsAnswered() {
      const totalQuestions = 
        questions.economica.interes.length + questions.economica.aptitud.length +
        questions.humanistica.interes.length + questions.humanistica.aptitud.length +
        questions.artistica.interes.length + questions.artistica.aptitud.length +
        questions.salud.interes.length + questions.salud.aptitud.length +
        questions.ingenieria.interes.length + questions.ingenieria.aptitud.length +
        questions.defensa.interes.length + questions.defensa.aptitud.length +
        questions.exactas.interes.length + questions.exactas.aptitud.length

      const answeredQuestions = 
        Object.keys(answers.economica.interes).length + Object.keys(answers.economica.aptitud).length +
        Object.keys(answers.humanistica.interes).length + Object.keys(answers.humanistica.aptitud).length +
        Object.keys(answers.artistica.interes).length + Object.keys(answers.artistica.aptitud).length +
        Object.keys(answers.salud.interes).length + Object.keys(answers.salud.aptitud).length +
        Object.keys(answers.ingenieria.interes).length + Object.keys(answers.ingenieria.aptitud).length +
        Object.keys(answers.defensa.interes).length + Object.keys(answers.defensa.aptitud).length +
        Object.keys(answers.exactas.interes).length + Object.keys(answers.exactas.aptitud).length

      return answeredQuestions === totalQuestions
    }

    function calculateResults() {
      if (!areAllQuestionsAnswered()) {
        alert('Por favor, responde todas las preguntas antes de ver los resultados.')
        return
      }

      // Calcular resultados para área económica
      results.economica.interes = Object.values(answers.economica.interes).filter(answer => answer === true).length
      results.economica.aptitud = Object.values(answers.economica.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área humanística
      results.humanistica.interes = Object.values(answers.humanistica.interes).filter(answer => answer === true).length
      results.humanistica.aptitud = Object.values(answers.humanistica.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área artística
      results.artistica.interes = Object.values(answers.artistica.interes).filter(answer => answer === true).length
      results.artistica.aptitud = Object.values(answers.artistica.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área de salud
      results.salud.interes = Object.values(answers.salud.interes).filter(answer => answer === true).length
      results.salud.aptitud = Object.values(answers.salud.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área de ingeniería
      results.ingenieria.interes = Object.values(answers.ingenieria.interes).filter(answer => answer === true).length
      results.ingenieria.aptitud = Object.values(answers.ingenieria.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área de defensa
      results.defensa.interes = Object.values(answers.defensa.interes).filter(answer => answer === true).length
      results.defensa.aptitud = Object.values(answers.defensa.aptitud).filter(answer => answer === true).length
      
      // Calcular resultados para área de ciencias exactas
      results.exactas.interes = Object.values(answers.exactas.interes).filter(answer => answer === true).length
      results.exactas.aptitud = Object.values(answers.exactas.aptitud).filter(answer => answer === true).length
      
      showResults.value = true
    }

    function getRecommendation() {
      const areas = {
        economica: {
          total: results.economica.interes + results.economica.aptitud,
          name: "Administrativas, Contables y Económicas",
          careers: "Administración, Economía, Contabilidad, Marketing, Comercio Internacional"
        },
        humanistica: {
          total: results.humanistica.interes + results.humanistica.aptitud,
          name: "Humanísticas, Ciencias Jurídicas y Ciencias Sociales",
          careers: "Psicología, Sociología, Trabajo Social, Educación, Historia, Literatura, Filosofía, Derecho"
        },
        artistica: {
          total: results.artistica.interes + results.artistica.aptitud,
          name: "Artísticas",
          careers: "Diseño Gráfico, Arquitectura, Artes Plásticas, Música, Teatro, Diseño de Modas"
        },
        salud: {
          total: results.salud.interes + results.salud.aptitud,
          name: "Ciencias de la Salud",
          careers: "Medicina, Enfermería, Odontología, Kinesiología, Nutrición, Farmacia"
        },
        ingenieria: {
          total: results.ingenieria.interes + results.ingenieria.aptitud,
          name: "Ingenierías, Carreras Técnicas y Computación",
          careers: "Ingeniería Civil, Industrial, Informática, Mecánica, Electrónica, Química"
        },
        defensa: {
          total: results.defensa.interes + results.defensa.aptitud,
          name: "Defensa y Seguridad",
          careers: "Ciencias Militares, Seguridad Pública, Criminalística, Defensa Civil"
        },
        exactas: {
          total: results.exactas.interes + results.exactas.aptitud,
          name: "Ciencias Agrarias de la Naturaleza, Zoológicas y Biológicas",
          careers: "Matemáticas, Física, Química, Biología, Astronomía, Geología, Ingeniería Agrónoma"
        }
      }
      
      // Encontrar el área con mayor puntaje
      const maxArea = Object.keys(areas).reduce((a, b) => 
        areas[a].total > areas[b].total ? a : b
      )
      
      // Verificar si hay empates
      const maxScore = areas[maxArea].total
      const tiedAreas = Object.keys(areas).filter(area => areas[area].total === maxScore)
      
      if (tiedAreas.length > 1) {
        const areaNames = tiedAreas.map(area => areas[area].name).join(' y ')
        return `Tus resultados muestran un equilibrio entre las áreas de ${areaNames}. Podrías considerar carreras que combinen aspectos de estas áreas o explorar más a fondo cada una de ellas.`
      } else {
        return `Basado en tus respuestas, muestras mayor afinidad hacia las carreras del área ${areas[maxArea].name}. Podrías considerar carreras como: ${areas[maxArea].careers}, entre otras.`
      }
    }

    function resetTest() {
      // Limpiar respuestas
      Object.keys(answers.economica.interes).forEach(key => delete answers.economica.interes[key])
      Object.keys(answers.economica.aptitud).forEach(key => delete answers.economica.aptitud[key])
      Object.keys(answers.humanistica.interes).forEach(key => delete answers.humanistica.interes[key])
      Object.keys(answers.humanistica.aptitud).forEach(key => delete answers.humanistica.aptitud[key])
      Object.keys(answers.artistica.interes).forEach(key => delete answers.artistica.interes[key])
      Object.keys(answers.artistica.aptitud).forEach(key => delete answers.artistica.aptitud[key])
      Object.keys(answers.salud.interes).forEach(key => delete answers.salud.interes[key])
      Object.keys(answers.salud.aptitud).forEach(key => delete answers.salud.aptitud[key])
      Object.keys(answers.ingenieria.interes).forEach(key => delete answers.ingenieria.interes[key])
      Object.keys(answers.ingenieria.aptitud).forEach(key => delete answers.ingenieria.aptitud[key])
      Object.keys(answers.defensa.interes).forEach(key => delete answers.defensa.interes[key])
      Object.keys(answers.defensa.aptitud).forEach(key => delete answers.defensa.aptitud[key])
      Object.keys(answers.exactas.interes).forEach(key => delete answers.exactas.interes[key])
      Object.keys(answers.exactas.aptitud).forEach(key => delete answers.exactas.aptitud[key])
      
      // Limpiar resultados
      results.economica.interes = 0
      results.economica.aptitud = 0
      results.humanistica.interes = 0
      results.humanistica.aptitud = 0
      results.artistica.interes = 0
      results.artistica.aptitud = 0
      results.salud.interes = 0
      results.salud.aptitud = 0
      results.ingenieria.interes = 0
      results.ingenieria.aptitud = 0
      results.defensa.interes = 0
      results.defensa.aptitud = 0
      results.exactas.interes = 0
      results.exactas.aptitud = 0
      
      showResults.value = false
    }

    return {
      questions,
      answers,
      results,
      showResults,
      updateAnswer,
      areAllQuestionsAnswered,
      calculateResults,
      getRecommendation,
      resetTest
    }
  }
}
</script>

<style scoped>
.test-vocacional {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 10px;
}

.section {
  background: #f8f9fa;
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 30px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.section h2 {
  color: #34495e;
  border-bottom: 3px solid #3498db;
  padding-bottom: 10px;
  margin-bottom: 20px;
}

.section h3 {
  color: #2c3e50;
  margin-top: 30px;
  margin-bottom: 15px;
}

.question {
  background: white;
  border-radius: 8px;
  padding: 15px;
  margin-bottom: 15px;
  box-shadow: 0 1px 5px rgba(0,0,0,0.1);
}

.question p {
  margin: 0 0 10px 0;
  font-weight: 500;
  color: #2c3e50;
}

.answer-buttons {
  display: flex;
  gap: 10px;
}

.btn-yes, .btn-no {
  padding: 8px 20px;
  border: 2px solid;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: all 0.3s ease;
}

.btn-yes {
  background: white;
  color: #27ae60;
  border-color: #27ae60;
}

.btn-yes:hover, .btn-yes.active {
  background: #27ae60;
  color: white;
}

.btn-no {
  background: white;
  color: #e74c3c;
  border-color: #e74c3c;
}

.btn-no:hover, .btn-no.active {
  background: #e74c3c;
  color: white;
}

.submit-section {
  text-align: center;
  margin-top: 30px;
}

.progress-info {
  margin-bottom: 20px;
}

.progress-info p {
  font-size: 16px;
  font-weight: 600;
  color: #2c3e50;
  margin: 0;
}

.btn-submit, .btn-reset {
  background: linear-gradient(45deg, #3498db, #2980b9);
  color: white;
  border: none;
  padding: 15px 30px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 25px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.btn-submit:hover, .btn-reset:hover {
  transform: translateY(-2px);
}

.btn-disabled {
  background: linear-gradient(45deg, #95a5a6, #7f8c8d) !important;
  cursor: not-allowed !important;
  transform: none !important;
}

.btn-disabled:hover {
  transform: none !important;
}

.results {
  text-align: center;
}

.results-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
  margin: 20px 0;
}

.result-card {
  color: white;
  padding: 15px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  transition: transform 0.3s ease;
}

.result-card:hover {
  transform: translateY(-5px);
}

.result-card:nth-child(1) {
  background: linear-gradient(135deg, #2E86AB 0%, #A23B72 100%);
}

.result-card:nth-child(2) {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.result-card:nth-child(3) {
  background: linear-gradient(135deg, #ff6b6b 0%, #ee5a24 100%);
}

.result-card:nth-child(4) {
  background: linear-gradient(135deg, #00d2d3 0%, #54a0ff 100%);
}

.result-card:nth-child(5) {
  background: linear-gradient(135deg, #ff9ff3 0%, #f368e0 100%);
}

.result-card:nth-child(6) {
  background: linear-gradient(135deg, #feca57 0%, #ff9ff3 100%);
}

.result-card:nth-child(7) {
  background: linear-gradient(135deg, #48dbfb 0%, #0abde3 100%);
}

.result-card h3 {
  margin-top: 0;
  margin-bottom: 15px;
}

.score {
  text-align: left;
}

.score-item {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
  font-size: 16px;
}

.label {
  font-weight: 600;
}

.value {
  font-weight: bold;
  font-size: 18px;
}

.recommendation {
  background: #e8f5e8;
  border: 2px solid #27ae60;
  border-radius: 10px;
  padding: 20px;
  margin: 20px 0;
}

.recommendation h3 {
  color: #27ae60;
  margin-top: 0;
}

.recommendation p {
  color: #2c3e50;
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 768px) {
  .test-vocacional {
    padding: 10px;
  }
  
  .answer-buttons {
    flex-direction: column;
  }
  
  .btn-yes, .btn-no {
    width: 100%;
  }
}
</style>
