<template>
  <div id="app">
    <header class="header">
      <nav class="navbar">
        <div class="nav-brand">
          <img src="/img/博客图标.jpg" alt="Blog Icon" class="nav-brand-icon" />
          Alinsms
        </div>
        <ul class="nav-links">
          <li><a href="#introduction">About Me</a></li>
          <li><a href="#skills-hobbies">Skills & Hobbies</a></li>
          <li><a href="#life">My Life</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#blogs">Blogs</a></li>
          <li><a href="#github">GitHub</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <!-- Hero Section with Mountain Background -->
      <section class="hero hero-background">
        <div class="hero-background-image">
          <img :src="mountainPeak" alt="Mountain Peak - Hero Background" />
        </div>
        <div class="hero-overlay"></div>
        <div class="hero-content">
          <div class="hero-title-container">
            <h1 class="hero-main-title">Alinsms</h1>
            <p class="hero-subtitle">Computer Science Student | Java Full Stack Developer</p>
          </div>
          <div class="hero-buttons">
            <a :href="githubData.html_url" target="_blank" class="btn btn-primary" @click="followOnGitHub">
              <i class="fab fa-github"></i> Follow on GitHub
            </a>
            <a href="#" class="btn btn-secondary" @click="sendEmail">
              <i class="fas fa-envelope"></i> Send Email
            </a>
            <a href="#about" class="btn btn-outline">
              <i class="fas fa-arrow-down"></i> Explore More
            </a>
          </div>
        </div>
      </section>

      <!-- Introduction Section -->
      <section id="introduction" class="section">
        <div class="container">
          <div class="intro-content slide-left">
            <h2 class="section-title">About Me</h2>
            <div class="intro-text">
              <p class="about-text">
                I am an ordinary college student currently learning Java full-stack development.
                I'm passionate about coding and dedicated to building my skills in modern web technologies.
                I enjoy writing clean code, solving problems, and continuously expanding my knowledge
                in software development.
              </p>
              </div>
              <div class="about-avatar-container scale-up">
                <div class="about-avatar-wrapper" @mouseenter="hoverName = true" @mouseleave="hoverName = false">
                  <div class="about-avatar">
                    <img :src="githubData.avatar_url" alt="Alinsms" v-if="githubData.avatar_url" />
                    <div v-else class="avatar-placeholder">
                      <i class="fas fa-user"></i>
                    </div>
                    <div class="avatar-overlay">
                      <i class="fas fa-user"></i>
                    </div>
                  </div>
                  <div class="about-avatar-name" :class="{ 'avatar-name-hover': hoverName }">
                    <h3>Li Keru</h3>
                    <p>GitHub Profile</p>
                  </div>
                </div>
              </div>
          </div>
        </div>
      </section>

  
      <section id="skills-hobbies" class="section section-alt">
        <div class="container">
          <h2 class="section-title">Skills & Hobbies</h2>
          <div class="skills-hobbies-container">
            <!-- Skills Section -->
            <div class="skills-section slide-left">
              <h3 class="subsection-title">Technical Skills</h3>
              <div class="skills-mini-grid">
                <div class="skill-mini-item stagger-item float-animation" v-for="skill in technicalSkills" :key="skill.name">
                  <div class="skill-mini-icon">
                    <i :class="skill.icon"></i>
                  </div>
                  <span class="skill-name">{{ skill.name }}</span>
                </div>
              </div>
            </div>

            <!-- Hobbies Section -->
            <div class="hobbies-section slide-right">
              <h3 class="subsection-title">Personal Hobbies</h3>
              <div class="hobbies-grid">
                <div class="hobby-item stagger-item">
                  <i class="fas fa-mountain"></i>
                  <span>Mountain Climbing</span>
                </div>
                <div class="hobby-item stagger-item">
                  <i class="fas fa-dumbbell"></i>
                  <span>Fitness</span>
                </div>
                <div class="hobby-item stagger-item">
                  <i class="fas fa-hiking"></i>
                  <span>Trekking</span>
                </div>
                <div class="hobby-item stagger-item">
                  <i class="fas fa-grip-vertical"></i>
                  <span>Rock Climbing</span>
                </div>
                <div class="hobby-item stagger-item">
                  <i class="fas fa-camera"></i>
                  <span>Photography</span>
                </div>
                <div class="hobby-item stagger-item">
                  <i class="fas fa-book"></i>
                  <span>Reading</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Life Section with Mountain Photos -->
      <section id="life" class="section">
        <div class="container">
          <h2 class="section-title">My Life Adventures</h2>
          <div class="life-content">
            <div class="life-text slide-left">
              <h3>Conquering New Heights</h3>
              <p>Besides coding, I'm passionate about mountain climbing. Here are some photos from my successful summit of a 5000-meter snow mountain:</p>
              <div class="life-stats">
                <div class="life-stat scale-up">
                  <i class="fas fa-mountain"></i>
                  <span>5000m</span>
                  <small>Peak Altitude</small>
                </div>
                <div class="life-stat scale-up">
                  <i class="fas fa-clock"></i>
                  <span>6hrs</span>
                  <small>Climbing Time</small>
                </div>
                <div class="life-stat scale-up">
                  <i class="fas fa-temperature-low"></i>
                  <span>-10°C</span>
                  <small>Temperature</small>
                </div>
              </div>
            </div>
            <div class="life-gallery slide-right">
              <div class="gallery-main scale-up">
                <img src="/img/微信图片_20251114150701_12_142.jpg" alt="Mountain Summit - Main View" />
              </div>
              <div class="gallery-thumbnails">
                <img class="stagger-item" src="/img/mountain1.jpg" alt="Mountain Climb - Photo 1" />
                <img class="stagger-item" src="/img/微信图片_20251114150644_11_142.jpg" alt="Mountain Climb - Photo 2" />
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="projects" class="section section-alt">
        <div class="container">
          <h2 class="section-title">GitHub Projects</h2>
          <div class="github-projects">
            <div class="github-project scale-up stagger-item" v-for="project in projects" :key="project.id">
              <div class="project-header">
                <div class="project-title-row">
                  <div class="project-icon">
                    <i class="fas fa-book"></i>
                  </div>
                  <div class="project-info">
                    <h3>
                      <a :href="project.html_url" target="_blank" class="project-name-link">
                        {{ project.owner?.login || 'alinsms' }} / {{ project.name }}
                      </a>
                    </h3>
                    <p class="project-description">{{ project.description || 'No description available' }}</p>
                  </div>
                </div>
                <div class="project-meta">
                  <span class="project-language" v-if="project.language">
                    <span class="language-dot" :style="{ backgroundColor: getLanguageColor(project.language) }"></span>
                    {{ project.language }}
                  </span>
                  <span class="project-stars">
                    <i class="fas fa-star"></i> {{ project.stargazers_count || 0 }}
                  </span>
                  <span class="project-forks">
                    <i class="fas fa-code-branch"></i> {{ project.forks_count || 0 }}
                  </span>
                  <span class="project-updated">
                    Updated {{ getRelativeTime(project.updated_at) }}
                  </span>
                </div>
              </div>
              <div class="project-body">
                <div class="project-stats">
                  <div class="stat">
                    <span class="stat-number">{{ project.stargazers_count || 0 }}</span>
                    <span class="stat-label">Stars</span>
                  </div>
                  <div class="stat">
                    <span class="stat-number">{{ project.forks_count || 0 }}</span>
                    <span class="stat-label">Forks</span>
                  </div>
                  <div class="stat">
                    <span class="stat-number">{{ project.open_issues_count || 0 }}</span>
                    <span class="stat-label">Issues</span>
                  </div>
                  <div class="stat">
                    <span class="stat-number">{{ getLicenseName(project) }}</span>
                    <span class="stat-label">License</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="blogs" class="section section-alt">
        <div class="container">
          <h2 class="section-title">Recent Blogs</h2>
          <div class="blogs-grid">
            <div class="blog-card" v-for="blog in recentBlogs" :key="blog.id">
              <h3>{{ blog.title }}</h3>
              <p>{{ blog.description }}</p>
              <div class="blog-meta">
                <span class="blog-date">{{ formatDate(blog.created_at) }}</span>
                <span class="blog-category">{{ blog.category }}</span>
              </div>
              <a :href="blog.url" target="_blank" class="blog-link">
                Read More <i class="fas fa-arrow-right"></i>
              </a>
            </div>
          </div>
        </div>
      </section>

      <section id="github" class="section">
        <div class="container">
          <h2 class="section-title">GitHub Contributions</h2>
          <div class="github-contributions">
            <div class="contribution-header">
              <h3>{{ githubData.login || 'alinsms' }}'s Contribution Activity</h3>
              <a :href="contributionCalendarUrl" target="_blank" class="view-full-activity">
                <i class="fas fa-external-link-alt"></i>
                View Full Activity on GitHub
              </a>
            </div>
            <div class="contribution-graph-container">
              <img :src="contributionGraphUrl" alt="GitHub Contribution Graph" class="contribution-graph" />
              <div class="contribution-stats" v-if="githubData.public_repos || githubData.followers || githubData.following">
                <div class="stat-item">
                  <span class="stat-number">{{ githubData.public_repos || 0 }}</span>
                  <span class="stat-label">Repositories</span>
                </div>
                <div class="stat-item">
                  <span class="stat-number">{{ githubData.followers || 0 }}</span>
                  <span class="stat-label">Followers</span>
                </div>
                <div class="stat-item">
                  <span class="stat-number">{{ githubData.following || 0 }}</span>
                  <span class="stat-label">Following</span>
                </div>
              </div>
            </div>
          </div>
          <div class="github-activity">
            <h3>Recent Activity</h3>
            <div class="activity-item" v-for="activity in recentActivity" :key="activity.id">
              <div class="activity-icon">
                <i class="fas fa-code-branch"></i>
              </div>
              <div class="activity-content">
                <h4>{{ activity.repo.name }}</h4>
                <p>{{ getActivityDescription(activity) }}</p>
                <small>{{ formatDate(activity.created_at) }}</small>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="contact" class="section section-alt">
        <div class="container">
          <h2 class="section-title">Contact Me</h2>
          <div class="contact-content">
            <div class="contact-info">
              <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <span>jade_maccin@163.com</span>
              </div>
              <div class="contact-item">
                <i class="fab fa-github"></i>
                <span>github.com/alinsms</span>
              </div>
              <div class="contact-item">
                <i class="fab fa-linkedin"></i>
                <span>linkedin.com/in/alinsms</span>
              </div>
            </div>
            <div class="contact-form">
              <form @submit.prevent="submitForm">
                <input type="text" v-model="contactForm.name" placeholder="Your Name" required>
                <input type="email" v-model="contactForm.email" placeholder="Your Email" required>
                <textarea v-model="contactForm.message" placeholder="Your Message" rows="5" required></textarea>
                <button type="submit" class="btn btn-primary">Send Message</button>
              </form>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="footer">
      <div class="container">
        <p>&copy; 2024 Alinsms. All rights reserved.</p>
        <div class="social-links">
          <a :href="githubData.html_url" target="_blank" title="GitHub">
            <i class="fab fa-github"></i>
          </a>
          <a href="#" title="LinkedIn">
            <i class="fab fa-linkedin"></i>
          </a>
          <a href="#" title="Twitter">
            <i class="fab fa-twitter"></i>
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref, onMounted, computed } from 'vue'
import axios from 'axios'
import mountainPeak from '/img/孤峰.png'

export default {
  name: 'App',
  setup() {
    const githubData = ref({})
    const projects = ref([])
    const recentActivity = ref([])
    const recentBlogs = ref([])
    const loading = ref(true)
    const contactForm = ref({
      name: '',
      email: '',
      message: ''
    })

    const hoverName = ref(false)

    const technicalSkills = ref([
      { name: 'Java', icon: 'fab fa-java' },
      { name: 'Spring', icon: 'fas fa-leaf' },
      { name: 'Spring Boot', icon: 'fas fa-bolt' },
      { name: 'Spring Cloud', icon: 'fas fa-cloud' },
      { name: 'Maven', icon: 'fas fa-box' },
      { name: 'MySQL', icon: 'fas fa-database' },
      { name: 'Redis', icon: 'fas fa-memory' },
      { name: 'Vue.js', icon: 'fab fa-vuejs' },
      { name: 'JavaScript', icon: 'fab fa-js' },
      { name: 'Git', icon: 'fab fa-git-alt' },
      { name: 'Docker', icon: 'fab fa-docker' },
      { name: 'Linux', icon: 'fab fa-linux' }
    ])

    const contributionGraphUrl = computed(() => {
      return githubData.value.login ?
        `https://ghchart.rshah.org/${githubData.value.login}?theme=dark` :
        ''
    })

    const contributionCalendarUrl = computed(() => {
      return githubData.value.login ?
        `https://github.com/${githubData.value.login}` :
        'https://github.com/alinsms'
    })

    const fetchGitHubData = async () => {
      try {
        const username = 'alinsms'

        // Fetch user data
        const userResponse = await axios.get(`https://api.github.com/users/${username}`)
        githubData.value = userResponse.data

        // Fetch repositories
        const reposResponse = await axios.get(`https://api.github.com/users/${username}/repos?sort=updated&per_page=6`)
        projects.value = reposResponse.data

        // Fetch recent activity
        const eventsResponse = await axios.get(`https://api.github.com/users/${username}/events?per_page=5`)
        recentActivity.value = eventsResponse.data

        // Fetch recent blogs (from repositories with README that look like blogs)
        const blogRepos = reposResponse.data.filter(repo =>
          repo.name.includes('blog') ||
          repo.description?.toLowerCase().includes('blog') ||
          repo.topics?.includes('blog')
        )

        recentBlogs.value = blogRepos.slice(0, 3).map(repo => ({
          id: repo.id,
          title: repo.name.replace(/-/g, ' ').replace(/_/g, ' ').replace(/\b\w/g, l => l.toUpperCase()),
          description: repo.description || 'A blog post about development and technology',
          created_at: repo.created_at,
          category: 'Technology',
          url: repo.html_url
        }))

        loading.value = false
      } catch (error) {
        console.error('Failed to fetch GitHub data:', error)
        loading.value = false
      }
    }

    const formatDate = (dateString) => {
      const date = new Date(dateString)
      return date.toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'long',
        day: 'numeric'
      })
    }

    const getProjectTags = (project) => {
      const tags = []
      if (project.language) tags.push(project.language)
      if (project.topics && project.topics.length > 0) {
        tags.push(...project.topics.slice(0, 2))
      }
      return tags.length > 0 ? tags : ['Project']
    }

    const getActivityDescription = (activity) => {
      const type = activity.type
      switch (type) {
        case 'PushEvent':
          return 'Pushed code to repository'
        case 'CreateEvent':
          return 'Created new repository'
        case 'IssuesEvent':
          return 'Opened an issue'
        case 'PullRequestEvent':
          return 'Created a pull request'
        default:
          return 'Repository activity'
      }
    }

    const followOnGitHub = (event) => {
      event.preventDefault()
      window.open(`${githubData.value.html_url}?tab=followers`, '_blank')
    }

    const sendEmail = (event) => {
      event.preventDefault()
      window.location.href = 'mailto:jade_maccin@163.com?subject=Hello from your portfolio&body=Hi Alinsms, I found your portfolio and wanted to connect!'
    }

    const submitForm = () => {
      alert('Thank you for your message! I will get back to you soon.')
      contactForm.value = { name: '', email: '', message: '' }
    }

    const getLanguageColor = (language) => {
      const colors = {
        'JavaScript': '#f1e05a',
        'Java': '#b07219',
        'Python': '#3572A5',
        'TypeScript': '#2b7489',
        'Vue': '#41b883',
        'HTML': '#e34c26',
        'CSS': '#563d7c',
        'Shell': '#89e051',
        'Ruby': '#701516',
        'Go': '#00ADD8',
        'PHP': '#4F5D95',
        'C++': '#f34b7d',
        'C#': '#239120',
        'Swift': '#ffac45',
        'Kotlin': '#F18E33',
        'Rust': '#dea584',
        'Dart': '#00B4AB'
      }
      return colors[language] || '#586069'
    }

    const getRelativeTime = (dateString) => {
      const date = new Date(dateString)
      const now = new Date()
      const diffInSeconds = Math.floor((now - date) / 1000)

      if (diffInSeconds < 60) return 'just now'
      if (diffInSeconds < 3600) return `${Math.floor(diffInSeconds / 60)} minutes ago`
      if (diffInSeconds < 86400) return `${Math.floor(diffInSeconds / 3600)} hours ago`
      if (diffInSeconds < 604800) return `${Math.floor(diffInSeconds / 86400)} days ago`
      if (diffInSeconds < 2592000) return `${Math.floor(diffInSeconds / 604800)} weeks ago`
      if (diffInSeconds < 31536000) return `${Math.floor(diffInSeconds / 2592000)} months ago`
      return `${Math.floor(diffInSeconds / 31536000)} years ago`
    }

    const getLicenseName = (project) => {
      return project.license?.name || 'No License'
    }

    onMounted(() => {
      fetchGitHubData()
      setupScrollAnimations()
    })

    const setupScrollAnimations = () => {
      // Apple-style intersection observer setup
      const observerOptions = {
        threshold: [0.05, 0.15, 0.85, 0.95],
        rootMargin: '0px 0px -5% 0px'
      }

      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          const target = entry.target
          const isIntersecting = entry.isIntersecting
          const intersectionRatio = entry.intersectionRatio

          if (isIntersecting && intersectionRatio > 0.15) {
            // Element is entering viewport - show animation
            if (!target.classList.contains('visible')) {
              target.classList.add('visible')

              // Trigger child animations
              if (target.classList.contains('section')) {
                const staggerItems = target.querySelectorAll('.stagger-item:not(.visible)')
                const slideLeftItems = target.querySelectorAll('.slide-left:not(.visible)')
                const slideRightItems = target.querySelectorAll('.slide-right:not(.visible)')
                const scaleItems = target.querySelectorAll('.scale-up:not(.visible)')

                // Animate stagger items
                staggerItems.forEach((item, index) => {
                  setTimeout(() => {
                    item.classList.add('visible')
                  }, index * 80)
                })

                // Animate slide items
                slideLeftItems.forEach((item, index) => {
                  setTimeout(() => {
                    item.classList.add('visible')
                  }, index * 100)
                })

                slideRightItems.forEach((item, index) => {
                  setTimeout(() => {
                    item.classList.add('visible')
                  }, index * 100)
                })

                // Animate scale items
                scaleItems.forEach((item, index) => {
                  setTimeout(() => {
                    item.classList.add('visible')
                  }, index * 120)
                })
              }
            }
          } else if (!isIntersecting && intersectionRatio < 0.05) {
            // Element is completely out of view - remove visible class for re-animation
            if (target.classList.contains('visible')) {
              target.classList.remove('visible')

              // Remove visible from children
              const children = target.querySelectorAll('.visible')
              children.forEach(child => {
                child.classList.remove('visible')
              })
            }
          }
        })
      }, observerOptions)

      // Observe all sections
      const sections = document.querySelectorAll('.section')
      sections.forEach(section => {
        observer.observe(section)
      })

      // Observe standalone animated elements
      const animatedElements = document.querySelectorAll('.stagger-item, .slide-left, .slide-right, .scale-up')
      animatedElements.forEach(element => {
        // Only observe if not inside a section
        if (!element.closest('.section')) {
          observer.observe(element)
        }
      })

      // Show hero immediately with Apple-style entrance
      setTimeout(() => {
        const hero = document.querySelector('.hero')
        if (hero) {
          hero.classList.add('visible')
        }
      }, 300)

      // Performance optimization: reduce motion for users who prefer it
      if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
        document.querySelectorAll('.section, .stagger-item, .slide-left, .slide-right, .scale-up').forEach(el => {
          el.classList.add('visible')
        })
      }
    }

    return {
      githubData,
      projects,
      recentActivity,
      recentBlogs,
      technicalSkills,
      loading,
      contactForm,
      hoverName,
      mountainPeak,
      contributionGraphUrl,
      contributionCalendarUrl,
      formatDate,
      getProjectTags,
      getActivityDescription,
      getLanguageColor,
      getRelativeTime,
      getLicenseName,
      followOnGitHub,
      sendEmail,
      submitForm
    }
  }
}
</script>