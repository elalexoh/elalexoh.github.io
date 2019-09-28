<template>
  <div class="resume">
    <div class="base">
      <div class="profile">
        <div class="photo">
          <img width="50px" src="../assets/img/frederick2.png">
        </div>
        <div class="info">
          <h4 class="name">{{ person.introduction.name }}</h4>
          <small class="job">{{ person.introduction.title }}</small>
        </div>
      </div>
      <div class="about" style="text-align: justify; text-justify: inter-word;">
        <h3>{{ person.profile.label }}</h3>
        {{ person.profile.description}}
        <br>
      </div>
      <div class="contact">
        <h3>{{ person.contact.label }}</h3>
        <div class="call">
          <i class="fa fa-phone"></i>
          <span>{{ person.contact.telefono }}</span>
        </div>
        <div class="address">
          <i class="fa fa-map-marker"></i>
          <span>{{ person.contact.direccion }}</span>
        </div>
        <div class="email">
          <i class="fa fa-envelope"></i>
          <span>{{ person.contact.email }}</span>
        </div>
        <div v-bind:key="social_media" v-for="social_media in person.contact.social_medias">
          <div class="box">
            <a href="https://codepen.io/Deeply/" target="_blank">
              <i class="fa fa-codepen"></i>
              <span>{{ social_media.name }}</span>
            </a>
          </div>
        </div>
      </div>
      <div class="contact">
        <h3>{{ person.references.label }}</h3>
        <div v-bind:key="reference" v-for="reference in person.references.ref">
          <div class="call">
            <i class="fa fa-phone"></i>
            <span>{{ reference.telefono }}</span>
          </div>
          <div class="address">
            <i class="fa fa-user" aria-hidden="true"></i>
            <span>{{ reference.name }}</span>
          </div>
        </div>
      </div>
    </div>
    <div class="func">
      <div id="development">
        <div class="work">
          <h3>
            <i class="fa fa-briefcase"></i>{{ person.experiences.label }}
          </h3>
          <ul>
            <li v-bind:key="experience" v-for="experience in person.experiences.exp">
              <span>{{ experience.lugar }}</span>
              <small>{{ experience.fecha_ini }} - {{ experience.fecha_fin  }}</small>
            </li>
          </ul>
        </div>
        <div class="edu">
          <h3>
            <i class="fa fa-graduation-cap"></i>{{ person.education.label }}
          </h3>
          <ul>
            <li v-bind:key="education" v-for="education in person.education.titles">
              <span>{{ education.titulo }}</span>
              <small>{{ education.fecha_ini }} - {{ education.fecha_fin  }}</small>
            </li>
            <li v-bind:key="collage" v-for="collage in person.education.collage">
              <span>{{ collage.lugar }}</span>
            </li>
          </ul>
        </div>
        <div class="skills-prog">
          <h3>
            <i class="fa fa-code"></i>{{ person.skills.label_front }}
          </h3>
          <ul>
            <li v-bind:key="skill_f" v-for="skill_f in person.skills.front_end">
              <img class="image" width="50" :src="skill_f.icon">
              <!-- <span>{{ skill_f.name }}</span> -->
              <div class="skills-bar">
                <div class="bar" :style="`width:${skill_f.porcentaje}%`"></div>
              </div>
            </li>
          </ul>
          <div class="skills-prog-soft">
            <h3>
              <i class="fa fa-code"></i>{{ person.skills.label_back }}
            </h3>
            <ul>
              <li v-bind:key="skill_b" v-for="skill_b in person.skills.back_end">
                <img class="image" width="50" :src="skill_b.icon">
                <!-- <span>{{ skill_b.name }}</span> -->
                <div class="skills-bar">
                  <div class="bar" :style="`width:${skill_b.porcentaje}%`"></div>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div class>
          <h3>
            <i class="fa fa-bookmark"></i>Certificados
          </h3>
          <div class="interests-items">
            <div v-bind:key="certification" v-for="certification in person.certifications" class="certificacion-content">
              <div class="draw">
                <img :src="certification.icon">
              </div>
                <h6></h6>
              <div>{{ certification.name }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Resume',
  data () {
    return {
      msg: {
        label: 'label',
        text: 'hey'
      },
      person: {
        introduction: {
          name: 'Frederick A. Gonzalez',
          title: 'Desarrollador Web'
        },
        profile: {
          label: 'Perfil Profesional',
          description:
            'Soy un Ingeniero apasionado por el diseño y Desarrollo web, enfocado en crear software de calidad que solvente a través de las nuevas tecnologías las problemáticas del mundo actual.'
        },
        contact: {
          label: 'Contacto',
          telefono: '(+58) 424 178 5377',
          direccion: 'Los magallanes de Catia, Caracas - Venezuela',
          email: 'g7.alexander@gmail.com',
          social_medias: [
            {
              name: 'Codepen',
              url: 'https://codepen.io/Deeply/',
              icon: ''
            }
          ]
        },
        references: {
          label: 'Referencias personales',
          ref: [
            {
              name: 'Anthony E. Gadea',
              telefono: '(416) 200-9468'
            },
            {
              name: 'Riquenny Lugo',
              telefono: '(412) 703-7985'
            }
          ]
        },
        experiences: {
          label: 'Exp. Laboral',
          exp: [
            {
              lugar: 'Orugastudio',
              fecha_ini: 'Nov - 2018',
              fecha_fin: 'May - 2019'
            },
            {
              lugar: 'M.P.P.E.F. - ONCOP',
              fecha_ini: 'Jun - 2017',
              fecha_fin: 'Oct - 2018'
            },
            {
              lugar: 'IUTA',
              fecha_ini: 'Mar - 2017',
              fecha_fin: 'Jun - 2017'
            }
          ]
        },
        education: {
          label: 'Educación',
          titles: [
            {
              titulo: 'Ingeniero en sistemas',
              fecha_ini: 'Ene - 2014',
              fecha_fin: 'Jun - 2017'
            },
            {
              titulo: 'Técnico Superior Universitario',
              fecha_ini: 'Ene - 2012',
              fecha_fin: 'Jun - 2014'
            }
          ],
          collage: [
            {
              lugar: 'Colegio Universitario Francisco de Miranda (Cufm)'
            }
          ]
        },
        skills: {
          label_front: 'Hablidades Front-End',
          label_back: 'Hablidades Back-End',
          front_end: [
            {
              name: 'Css3/Html5',
              porcentaje: '95',
              icon: require('@/assets/img/html.svg')
            },
            {
              name: 'Sass',
              porcentaje: '90',
              icon: require('@/assets/img/sass.svg')
            },
            {
              name: 'Boostrap 4 Materialize',
              porcentaje: '85',
              icon: require('@/assets/img/bs4.png')
            },
            {
              name: 'Javascript',
              porcentaje: '60',
              icon: require('@/assets/img/javascript.svg')
            },
            {
              name: 'Vue',
              porcentaje: '50',
              icon: require('@/assets/img/vue.png')
            }
          ],
          back_end: [
            {
              name: 'Wordpress',
              porcentaje: '75',
              icon: require('@/assets/img/wordpres.png')
            },
            {
              name: 'Php',
              porcentaje: '80',
              icon: require('@/assets/img/php.png')
            },
            {
              name: 'Laravel 5*',
              porcentaje: '60',
              icon: require('@/assets/img/laravel5.png')
            },
            {
              name: 'Sql',
              porcentaje: '60',
              icon: require('@/assets/img/sql.png')
            }
          ]
        },
        certifications: [
          {
            name: 'Promagación',
            icon: require('@/assets/img/programming.png')
          },
          {
            name: 'Laravel',
            icon: require('@/assets/img/laravel.png')
          }
        ]
      }
    }
  }
}

/* eslint-disable */
</script>
<style lang="scss" scoped>
@import "../styles/resume/main.css";
  .skills-prog {
    .image {
      margin-right: 2rem;
    }
  }
</style>
