<template>
  <div class="main-wrapper">
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary fixed-top" id="sideNav">
      <a class="navbar-brand js-scroll-trigger" href="#page-top">
        <span class="d-block d-lg-none">Sergey Untilov</span>
        <span class="d-none d-lg-block">
          <img class="img-fluid img-profile rounded-circle mx-auto mb-2" src="@/assets/profile.png" alt="">
        </span>
      </a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#about">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#experience">Experience</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#education">Education</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#skills">Skills</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </nav>

    <div class="container-fluid p-0">

      <section class="resume-section p-3 p-lg-5 d-flex d-column" id="about">
        <div class="my-auto">
          <h1 class="mb-0">{{name}}
            <span class="text-primary">{{surname}}</span>
          </h1>
          <div class="subheading mb-5">
            <!-- {{address}}<nbsp/>·<nbsp/>
            <a :href="`tel:${{phone}}`">{{phone}}</a><nbsp/>·<nbsp/>
            <a :href="`mailto:${{email}}`">{{email}}</a> -->
          </div>
          <!-- <h3 class="mb-0">{{aboutMe}}</h3> -->
          <p class="mb-5">{{aboutMe}}</p>

          <div class="subheading mb-4">
            <a href="#contact" class="mr-2">CONTACT ME</a>
            <span class="ml-3 text-primary">Download:</span>
            <a :href="cv.pdf.location" download class="ml-3">{{cv.pdf.title}}</a>
            <a :href="cv.doc.location" download class="ml-3">{{cv.doc.title}}</a>
          </div>

          <ul class="list-inline list-social-icons mb-0">
            <li class="list-inline-item">
              <a :href="facebook" target="_blank">
                <span class="fa-stack fa-lg">
                  <i class="fa fa-circle fa-stack-2x"></i>
                  <i class="fa fa-facebook fa-stack-1x fa-inverse"></i>
                </span>
              </a>
            </li>
            <li class="list-inline-item">
              <a :href="linkedin" target="_blank">
                <span class="fa-stack fa-lg">
                  <i class="fa fa-circle fa-stack-2x"></i>
                  <i class="fa fa-linkedin fa-stack-1x fa-inverse"></i>
                </span>
              </a>
            </li>
            <li class="list-inline-item">
              <a :href="github" target="_blank">
                <span class="fa-stack fa-lg">
                  <i class="fa fa-circle fa-stack-2x"></i>
                  <i class="fa fa-github fa-stack-1x fa-inverse"></i>
                </span>
              </a>
            </li>
            <li class="list-inline-item">
              <a v-bind:href="'mailto:' + email">
                <span class="fa-stack fa-lg">
                  <i class="fa fa-circle fa-stack-2x"></i>
                  <i class="fa fa-envelope fa-stack-1x fa-inverse"></i>
                </span>
              </a>
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="experience">
        <div class="my-auto">
          <h2 class="mb-5">Experience</h2>
          <ul id="experience_list" class="hide-bullets">
            <li v-for="item in experience" :key="item.startDate">
              <div class="resume-item d-flex flex-column flex-md-row mb-5">
                <div class="resume-content mr-auto">
                  <h3 class="mb-0">{{item.position}}</h3>
                  <div class="subheading mb-3">{{item.company}}</div>
                  <span class="text-primary">{{item.description}}</span>
                  <div>
                    <div v-if="item.responsibilities">Key responsibilities:</div>
                    <ul id="responsibilities" >
                      <li v-for="(resp, index) in item.responsibilities" :key="index">
                        <span class="text-primary">{{resp}}</span>
                      </li>
                    </ul>
                  </div>
                  Using: <span class="text-primary">{{item.tools}}</span>
                </div>
                <div class="resume-date text-md-right">
                  <span class="text-primary">{{item.startDate}} - {{item.endDate}}</span>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="education">
        <div class="my-auto">
          <h2 class="mb-5">Education</h2>

          <div class="resume-item d-flex flex-column flex-md-row mb-5">
            <div class="resume-content mr-auto">
              <h3 class="mb-0">{{education.degree}}</h3>
              <div class="subheading mb-3">{{education.university}}</div>
            </div>
            <div class="resume-date text-md-right">
              <span class="text-primary">{{education.startDate}} - {{education.endDate}}</span>
            </div>
          </div>

          <h4 class="subheading mb-3">TRAININGS:</h4>
          <br>

          <ul id="trainings_list" class="hide-bullets">
            <li v-for="item in trainings" :key="item.startDate">
              <div class="resume-item d-flex flex-column flex-md-row mb-5">
                <div class="resume-content mr-auto">
                  <h3 class="mb-0">{{item.subject}}</h3>
                  <div class="subheading mb-3">{{item.company}}</div>
                </div>
                <div class="resume-date text-md-right">
                  <span class="text-primary">{{item.startDate}} - {{item.endDate}}</span>
                </div>
              </div>
            </li>
          </ul>

        </div>
      </section>

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="skills">
        <div class="my-auto">
          <h2 class="mb-5">Skills</h2>

          <div class="subheading mb-3">Job related skills</div>
          <ul class="fa-ul mb-0 hide-bullets">
            <li v-for="(item, index) in skills" :key="index">
              <i class="fa-li fa fa-check"></i>
              <span class="text-primary">{{item}}</span>
            </li>
          </ul>

          <br>

          <div class="subheading mb-3">Programming Languages</div>
          <ul class="fa-ul mb-0 hide-bullets">
            <li v-for="(item, index) in programming_languages" :key="index">
              <i class="fa-li fa fa-check"></i>
              <h3 class="mb-0">{{item.title}}</h3>
              Level: <span class="text-primary">{{item.level}}</span>
              <p>Experience with: <span class="text-primary">{{item.experience}}</span></p>
            </li>
          </ul>

          <div class="subheading mb-3">Tools &amp; OS</div>
          <ul class="fa-ul mb-0 hide-bullets">
            <li v-for="(item, index) in programming_tools" :key="index">
              <i class="fa-li fa fa-check"></i>
              <span class="text-primary">{{item}}</span>
            </li>
          </ul>
        </div>
      </section>

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="contact">

        <div class="my-auto">
          <h2 class="mb-5">Contact me</h2>

          <div class="typeform-widget"
              data-url="https://sergeyuntilov.typeform.com/to/r9BRJ3"
              style="width: 100%; height: 500px;"></div>
              <!-- <script>
                (function() { var qs,js,q,s,d=document, gi=d.getElementById, ce=d.createElement, gt=d.getElementsByTagName, id="typef_orm", b="https://embed.typeform.com/"; if(!gi.call(d,id)) { js=ce.call(d,"script"); js.id=id; js.src=b+"embed.js"; q=gt.call(d,"script")[0]; q.parentNode.insertBefore(js,q) } })()
              </script> -->
              <div style="font-family: Sans-Serif;font-size: 12px;color: #999;opacity: 0.5; padding-top: 5px;">
                powered by
                <a href="https://admin.typeform.com/signup?utm_campaign=r9BRJ3&utm_source=typeform.com-12347014-Basic&utm_medium=typeform&utm_content=typeform-embedded-poweredbytypeform&utm_term=EN"
                style="color: #999"
                target="_blank">Typeform</a>
              </div>

        </div>

      </section>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Sergey Untilov',
      name: 'Sergey',
      surname: 'Untilov',
      address: 'Kyiv, Ukraine',
      email: 's.untilov@gmail.com',
      aboutMe: 'C/C++ programmer',
      cv: {
        pdf: {
          title: 'CV.PDF',
          location: require('@/assets/files/CV-Europass-Untilov-EN.pdf')
        },
        doc: {
          title: 'CV.DOC',
          location: require('@/assets/files/CV-Europass-Untilov-EN.doc')
        }
      },
      facebook: 'https://www.facebook.com/s.untilov',
      linkedin: 'https://www.linkedin.com/in/сергей-унтилов-a6b3b5a9',
      github: 'https://github.com/sergey-untilov',
      experience: [
        {
          position: 'Programmer, team-lead',
          company: 'Intellect-Service, Kyiv (Ukraine)',
          description: 'Developing solutions for IS-Pro ERP system',
          responsibilities: [
            'developing applications for calculating salary and HR management',
            'programming, team managing, code reviewing, making presentations',
            'applications maintenance for compliance with legislation',
            'developing solutions in distributed accounting system for State Fiscal Service of Ukraine',
            'developing multiprocessing procedure of batch calculating for large organizations'
          ],
          tools: 'C, C++, Visual Studio, Oracle DB, SQL Server',
          startDate: 'Dec 2008',
          endDate: 'Dec 2017'
        },
        {
          position: 'Programmer',
          company: 'Programms-BEST, Kyiv (Ukraine)',
          description: 'Developing applications for BEST-Pro accounting system',
          responsibilities: [
            'salary calculating software development',
            'HR accounting software development',
            'making presentations'
          ],
          tools: 'C, C++, Visual Studio, Oracle DB, SQL Server, PowerDesigner',
          startDate: 'Feb 2003',
          endDate: 'Nov 2008'
        },
        {
          position: 'Programmer',
          company: 'Self-employed',
          description: 'Freelance',
          tools: 'C, C++, Visual Studio, Oracle DB, SQL Server',
          startDate: 'Mar 2002',
          endDate: 'Feb 2003'
        },
        {
          position: 'Programmer',
          company: 'Intellect-Service, Kyiv (Ukraine)',
          description: 'Software development for ERP system',
          tools: 'Borland C, Watcom C, Pervasive DB',
          startDate: 'Mar 1996',
          endDate: 'Mar 2002'
        },
        {
          position: 'Programmer',
          company: 'UkrAgroExim PA, Kyiv (Ukraine)',
          description: 'Development of software for warehouse accounting',
          tools: 'Paradox RDMS',
          startDate: 'Oct 1993',
          endDate: 'Mar 1996'
        },
        {
          position: 'Programmer',
          company: 'Orion Research Institute, Kyiv (Ukraine)',
          description: 'Software development',
          responsibilities: [
            'application for salary calculating',
            'application for an accounting of payments for electricity'
          ],

          tools: 'Clipper',
          startDate: 'Sep 1989',
          endDate: 'Oct 1993'
        }
      ],
      education: {
        university: 'Kyiv National Economic University (Ukraine)',
        degree: 'Master of Economic Cybernetics',
        startDate: 'Sep 2002',
        endDate: 'Mar 2007'
      },
      trainings: [
        {
          subject: 'Python programming language',
          company: 'prometheus.org.ua, Kyiv (Ukraine)',
          startDate: 'Jan 2015',
          endDate: 'Mar 2015'
        },
        {
          subject: 'Java-Pro',
          company: 'Prog.kiev.ua, Kyiv (Ukraine)',
          startDate: 'Sep 2016',
          endDate: 'Jan 2017'
        },
        {
          subject: 'English (elementary - intermediate)',
          company: 'Green Forest, Kyiv (Ukraine)',
          startDate: 'Feb 2017',
          endDate: 'Jun 2018'
        }
      ],
      skills: [
        'Good experience in desktop applications development',
        'Good experience in complex relational databases schemes',
        'Good knowledge of multi-tenant software architecture',
        'Experience in creating mockups for mobile applications'
      ],
      programming_languages: [
        {
          title: 'C/C++',
          level: 'Excellent',
          experience: 'StayLib, MFC, Qt'
        },
        {
          title: 'SQL',
          level: 'Good',
          experience: 'Oracle DB, SQL Server, PostgreSQL'
        },
        {
          title: 'Java',
          level: 'Basic',
          experience: 'JavaSE, Spring Boot, Hibernate'
        },
        {
          title: 'Python',
          level: 'Basic',
          experience: 'ExifRead, DBFPy, Flask, JWT'
        },
        {
          title: 'JavaScript',
          level: 'Basic',
          experience: 'VueJS, Vuetify, JWT, PWA'
        }
      ],
      programming_tools: [
        'MS Visual Studio, VS Code, Intellij Idea',
        'MS Management Studio, Toad for Oracle, pgAdmin',
        'Jira, Redmine',
        'PowerDesigner for data modeling',
        'Inkscape for making UI mockups',
        'MS PowerPoint',
        'SVN, Git',
        'MS Windows, Linux'
      ]
    }
  },
  mounted () {
    const $ = this.jquery
    this.$nextTick(() => {
      // our custom jQuery code goes here
      $('a.js-scroll-trigger[href*="#"]:not([href="#"])').click(function () {
        if (location.pathname.replace(/^\//, '') === this.pathname.replace(/^\//, '') && location.hostname === this.hostname) {
          var target = $(this.hash)
          target = target.length ? target : $('[name=' + this.hash.slice(1) + ']')
          if (target.length) {
            $('html, body').animate({
              scrollTop: (target.offset().top)
            }, 1000, 'easeInOutExpo')
            return false
          }
        }
      })
      // Closes responsive menu when a scroll trigger link is clicked
      $('.js-scroll-trigger').click(function () {
        $('.navbar-collapse').collapse('hide')
      })
      // Activate scrollspy to add active class to navbar items on scroll
      $('body').scrollspy({
        target: '#sideNav'
      })
    })
  }
}
</script>

<style>
</style>
