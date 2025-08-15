import { useEffect, useState } from "react";

const GitHubProfile = () => {
  const [text, setText] = useState("");
  const fullText = "Full Stack Developer 🚀\nOpen Source Enthusiast 🌟\nBuilding Amazing Things ✨";
  const [currentIndex, setCurrentIndex] = useState(0);

  useEffect(() => {
    if (currentIndex < fullText.length) {
      const timeout = setTimeout(() => {
        setText(fullText.slice(0, currentIndex + 1));
        setCurrentIndex(currentIndex + 1);
      }, 100);
      return () => clearTimeout(timeout);
    }
  }, [currentIndex, fullText]);

  const techCategories = [
    {
      title: "💻 Languages",
      techs: [
        { name: "JavaScript", color: "text-yellow-400" },
        { name: "Python", color: "text-blue-400" },
        { name: "TypeScript", color: "text-blue-300" },
        { name: "Java", color: "text-orange-400" },
        { name: "C++", color: "text-blue-500" }
      ]
    },
    {
      title: "🎨 Frontend",
      techs: [
        { name: "React", color: "text-cyan-400" },
        { name: "Next.js", color: "text-foreground" },
        { name: "Vue.js", color: "text-green-400" },
        { name: "Tailwind CSS", color: "text-cyan-300" },
        { name: "HTML5", color: "text-orange-500" },
        { name: "CSS3", color: "text-blue-500" }
      ]
    },
    {
      title: "🔧 Backend & Database",
      techs: [
        { name: "Node.js", color: "text-green-500" },
        { name: "Express.js", color: "text-foreground" },
        { name: "Django", color: "text-green-600" },
        { name: "MongoDB", color: "text-green-400" },
        { name: "PostgreSQL", color: "text-blue-400" },
        { name: "Redis", color: "text-red-500" }
      ]
    },
    {
      title: "☁️ Cloud & DevOps",
      techs: [
        { name: "AWS", color: "text-orange-400" },
        { name: "Google Cloud", color: "text-blue-400" },
        { name: "Docker", color: "text-blue-500" },
        { name: "Kubernetes", color: "text-blue-600" },
        { name: "GitHub Actions", color: "text-foreground" }
      ]
    }
  ];

  const stats = [
    { label: "Total Commits", value: "2,847", icon: "📝" },
    { label: "Repositories", value: "47", icon: "📚" },
    { label: "Stars Earned", value: "239", icon: "⭐" },
    { label: "Followers", value: "156", icon: "👥" }
  ];

  const languages = [
    { name: "JavaScript", percentage: 35, color: "bg-yellow-400" },
    { name: "TypeScript", percentage: 28, color: "bg-blue-400" },
    { name: "Python", percentage: 20, color: "bg-green-400" },
    { name: "Java", percentage: 12, color: "bg-orange-400" },
    { name: "CSS", percentage: 5, color: "bg-purple-400" }
  ];

  const projects = [
    {
      title: "AI-Powered Task Manager",
      description: "A smart task management app with AI-driven prioritization and natural language processing for task creation.",
      tech: ["React", "Node.js", "OpenAI", "MongoDB"],
      github: "https://github.com",
      demo: "https://example.com",
      featured: true
    },
    {
      title: "Real-time Chat Platform",
      description: "Scalable chat application with real-time messaging, file sharing, and video calls using WebRTC.",
      tech: ["Next.js", "Socket.io", "PostgreSQL", "Redis"],
      github: "https://github.com",
      demo: "https://example.com",
      featured: true
    },
    {
      title: "E-commerce Analytics Dashboard",
      description: "Comprehensive analytics platform for e-commerce businesses with real-time data visualization.",
      tech: ["Vue.js", "Python", "FastAPI", "Docker"],
      github: "https://github.com",
      demo: "https://example.com",
      featured: false
    },
    {
      title: "Blockchain Voting System",
      description: "Secure and transparent voting system built on blockchain technology for elections and governance.",
      tech: ["Solidity", "Web3.js", "React", "IPFS"],
      github: "https://github.com",
      demo: "https://example.com",
      featured: false
    }
  ];

  const socialLinks = [
    {
      name: "LinkedIn",
      icon: "💼",
      url: "https://linkedin.com/in/your-profile",
      color: "hover:text-blue-400 hover:shadow-[0_0_20px_hsl(221_83%_53%/0.3)]"
    },
    {
      name: "GitHub", 
      icon: "🐙",
      url: "https://github.com/112Hunter112",
      color: "hover:text-foreground hover:shadow-glow"
    },
    {
      name: "Twitter",
      icon: "🐦",
      url: "https://twitter.com/your-handle",
      color: "hover:text-sky-400 hover:shadow-[0_0_20px_hsl(203_89%_53%/0.3)]"
    },
    {
      name: "Instagram",
      icon: "📷",
      url: "https://instagram.com/your-handle", 
      color: "hover:text-pink-400 hover:shadow-[0_0_20px_hsl(329_100%_71%/0.3)]"
    },
    {
      name: "Gmail",
      icon: "✉️",
      url: "mailto:parth.aditya01@gmail.com",
      color: "hover:text-red-400 hover:shadow-[0_0_20px_hsl(4_90%_58%/0.3)]"
    },
    {
      name: "Portfolio",
      icon: "🌐",
      url: "https://your-portfolio.com",
      color: "hover:text-orange-400 hover:shadow-[0_0_20px_hsl(24_100%_50%/0.3)]"
    }
  ];

  const achievements = [
    "🏆 GitHub Arctic Code Vault Contributor",
    "⭐ 200+ Stars across repositories", 
    "🚀 10+ Open Source Contributions",
    "💡 Featured Developer of the Month",
    "🎯 Successfully completed 30+ projects"
  ];

  return (
    <main className="min-h-screen">
      {/* Hero Section */}
      <section className="min-h-screen flex items-center justify-center px-4 relative overflow-hidden">
        {/* Animated background elements */}
        <div className="absolute inset-0 overflow-hidden">
          <div className="absolute -top-40 -right-40 w-80 h-80 bg-primary/20 rounded-full blur-3xl animate-pulse"></div>
          <div className="absolute -bottom-40 -left-40 w-80 h-80 bg-neon-pink/20 rounded-full blur-3xl animate-pulse" style={{ animationDelay: '2s' }}></div>
          <div className="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-neon-purple/10 rounded-full blur-3xl animate-pulse" style={{ animationDelay: '4s' }}></div>
        </div>

        <div className="text-center z-10">
          {/* Animated wave header */}
          <div className="mb-12 float-animation">
            <h1 className="text-6xl md:text-8xl font-bold mb-4 neon-text">
              Hey There! <span className="inline-block animate-bounce">👋</span>
            </h1>
          </div>

          {/* Typing animation */}
          <div className="mb-8">
            <p className="text-xl md:text-2xl text-muted-foreground mb-4">I'm Hunter</p>
            <div className="h-32 flex items-center justify-center">
              <pre className="text-xl md:text-3xl font-mono gradient-text whitespace-pre-wrap text-center">
                {text}
                <span className="animate-pulse">|</span>
              </pre>
            </div>
          </div>

          {/* CTA buttons */}
          <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
            <button className="glass-card px-8 py-4 neon-border hover:shadow-neon transition-all duration-300 group">
              <span className="text-primary font-semibold group-hover:text-foreground transition-colors">
                View My Work 🚀
              </span>
            </button>
            <button className="glass-card px-8 py-4 border-neon-pink/30 hover:shadow-[0_0_20px_hsl(var(--neon-pink)/0.3)] transition-all duration-300 group">
              <span className="text-neon-pink font-semibold group-hover:text-foreground transition-colors">
                Let's Connect 🤝
              </span>
            </button>
          </div>

          {/* Scroll indicator */}
          <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
            <div className="w-6 h-10 border-2 border-primary/50 rounded-full flex justify-center">
              <div className="w-1 h-3 bg-primary rounded-full mt-2 animate-pulse"></div>
            </div>
          </div>
        </div>
      </section>

      {/* Tech Stack Section */}
      <section className="py-20 px-4">
        <div className="max-w-6xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-6xl font-bold mb-4 gradient-text">
              🛠️ Tech Arsenal
            </h2>
            <p className="text-xl text-muted-foreground">Technologies I love working with</p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {techCategories.map((category, index) => (
              <div
                key={category.title}
                className="glass-card p-8 hover:shadow-neon transition-all duration-500 group"
                style={{ animationDelay: `${index * 0.2}s` }}
              >
                <h3 className="text-2xl font-bold mb-6 neon-text group-hover:text-primary transition-colors">
                  {category.title}
                </h3>
                <div className="flex flex-wrap gap-3">
                  {category.techs.map((tech, techIndex) => (
                    <span
                      key={tech.name}
                      className={`glass-card px-4 py-2 text-sm font-medium ${tech.color} hover:scale-110 transition-all duration-300 cursor-pointer hover:shadow-glow`}
                      style={{ animationDelay: `${(index * 0.2) + (techIndex * 0.1)}s` }}
                    >
                      {tech.name}
                    </span>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* GitHub Stats Section */}
      <section className="py-20 px-4">
        <div className="max-w-6xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-6xl font-bold mb-4 gradient-text">
              📊 GitHub Analytics
            </h2>
            <p className="text-xl text-muted-foreground">My coding journey in numbers</p>
          </div>

          {/* Stats Grid */}
          <div className="grid grid-cols-2 md:grid-cols-4 gap-6 mb-12">
            {stats.map((stat, index) => (
              <div
                key={stat.label}
                className="glass-card p-6 text-center hover:shadow-neon transition-all duration-500 group"
                style={{ animationDelay: `${index * 0.1}s` }}
              >
                <div className="text-4xl mb-2">{stat.icon}</div>
                <div className="text-3xl font-bold gradient-text mb-2 group-hover:scale-110 transition-transform">
                  {stat.value}
                </div>
                <div className="text-sm text-muted-foreground">{stat.label}</div>
              </div>
            ))}
          </div>

          {/* Language Stats */}
          <div className="glass-card p-8">
            <h3 className="text-2xl font-bold mb-8 text-center neon-text">
              🔥 Most Used Languages
            </h3>
            <div className="space-y-6">
              {languages.map((lang, index) => (
                <div key={lang.name} className="group">
                  <div className="flex justify-between items-center mb-2">
                    <span className="font-medium">{lang.name}</span>
                    <span className="text-sm text-muted-foreground">{lang.percentage}%</span>
                  </div>
                  <div className="w-full bg-muted/30 rounded-full h-3 overflow-hidden">
                    <div
                      className={`h-full ${lang.color} rounded-full transition-all duration-1000 ease-out group-hover:shadow-glow`}
                      style={{ 
                        width: `${lang.percentage}%`,
                        animationDelay: `${index * 0.2}s`
                      }}
                    ></div>
                  </div>
                </div>
              ))}
            </div>
          </div>

          {/* Contribution Graph Placeholder */}
          <div className="mt-12 glass-card p-8">
            <h3 className="text-2xl font-bold mb-8 text-center neon-text">
              📈 Contribution Activity
            </h3>
            <div className="grid grid-cols-12 gap-1">
              {Array.from({ length: 365 }, (_, i) => (
                <div
                  key={i}
                  className={`w-3 h-3 rounded-sm transition-all duration-300 hover:scale-150 cursor-pointer ${
                    Math.random() > 0.7 
                      ? 'bg-primary' 
                      : Math.random() > 0.5 
                      ? 'bg-primary/60' 
                      : Math.random() > 0.3 
                      ? 'bg-primary/30' 
                      : 'bg-muted/30'
                  }`}
                  style={{ animationDelay: `${i * 2}ms` }}
                ></div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Project Showcase Section */}
      <section className="py-20 px-4">
        <div className="max-w-6xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-6xl font-bold mb-4 gradient-text">
              🌟 Featured Projects
            </h2>
            <p className="text-xl text-muted-foreground">Some of my favorite builds</p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {projects.map((project, index) => (
              <div
                key={project.title}
                className={`glass-card p-8 hover:shadow-neon transition-all duration-500 group ${
                  project.featured ? 'md:col-span-2' : ''
                }`}
                style={{ animationDelay: `${index * 0.2}s` }}
              >
                <div className="flex items-start justify-between mb-4">
                  <h3 className="text-2xl font-bold neon-text group-hover:text-primary transition-colors">
                    {project.title}
                  </h3>
                  {project.featured && (
                    <span className="glass-card px-3 py-1 text-sm text-neon-pink border border-neon-pink/30">
                      Featured
                    </span>
                  )}
                </div>

                <p className="text-muted-foreground mb-6 leading-relaxed">
                  {project.description}
                </p>

                <div className="flex flex-wrap gap-2 mb-6">
                  {project.tech.map((tech) => (
                    <span
                      key={tech}
                      className="glass-card px-3 py-1 text-sm border border-primary/30 text-primary hover:shadow-glow transition-all duration-300"
                    >
                      {tech}
                    </span>
                  ))}
                </div>

                <div className="flex gap-4">
                  <a
                    href={project.github}
                    className="glass-card px-6 py-3 neon-border hover:shadow-neon transition-all duration-300 group/btn"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    <span className="text-primary font-medium group-hover/btn:text-foreground transition-colors">
                      GitHub 📂
                    </span>
                  </a>
                  <a
                    href={project.demo}
                    className="glass-card px-6 py-3 border-neon-pink/30 hover:shadow-[0_0_20px_hsl(var(--neon-pink)/0.3)] transition-all duration-300 group/btn"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    <span className="text-neon-pink font-medium group-hover/btn:text-foreground transition-colors">
                      Live Demo 🚀
                    </span>
                  </a>
                </div>
              </div>
            ))}
          </div>

          <div className="text-center mt-12">
            <button className="glass-card px-8 py-4 neon-border hover:shadow-neon transition-all duration-300 group">
              <span className="text-primary font-semibold group-hover:text-foreground transition-colors">
                View All Projects 👀
              </span>
            </button>
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section className="py-20 px-4">
        <div className="max-w-6xl mx-auto">
          {/* Achievements Section */}
          <div className="mb-20">
            <div className="text-center mb-16">
              <h2 className="text-4xl md:text-6xl font-bold mb-4 gradient-text">
                🏆 Achievements
              </h2>
              <p className="text-xl text-muted-foreground">Milestones in my journey</p>
            </div>

            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
              {achievements.map((achievement, index) => (
                <div
                  key={index}
                  className="glass-card p-6 hover:shadow-neon transition-all duration-500 group"
                  style={{ animationDelay: `${index * 0.1}s` }}
                >
                  <p className="text-center group-hover:scale-105 transition-transform duration-300">
                    {achievement}
                  </p>
                </div>
              ))}
            </div>
          </div>

          {/* Contact Section */}
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-6xl font-bold mb-4 gradient-text">
              🤝 Let's Connect!
            </h2>
            <p className="text-xl text-muted-foreground mb-8">
              Always excited to collaborate on amazing projects
            </p>
          </div>

          <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-6 mb-16">
            {socialLinks.map((link, index) => (
              <a
                key={link.name}
                href={link.url}
                target="_blank"
                rel="noopener noreferrer"
                className={`glass-card p-6 text-center transition-all duration-500 group ${link.color}`}
                style={{ animationDelay: `${index * 0.1}s` }}
              >
                <div className="text-4xl mb-3 group-hover:scale-125 transition-transform duration-300">
                  {link.icon}
                </div>
                <div className="text-sm font-medium">{link.name}</div>
              </a>
            ))}
          </div>

          {/* Call to Action */}
          <div className="glass-card p-12 text-center">
            <h3 className="text-3xl font-bold mb-6 neon-text">
              Ready to build something amazing together?
            </h3>
            <p className="text-lg text-muted-foreground mb-8 max-w-2xl mx-auto">
              I'm always open to discussing new opportunities, innovative projects, or just having a chat about technology and development.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center">
              <a
                href="mailto:parth.aditya01@gmail.com"
                className="glass-card px-8 py-4 neon-border hover:shadow-neon transition-all duration-300 group"
              >
                <span className="text-primary font-semibold group-hover:text-foreground transition-colors">
                  Send me an email 📧
                </span>
              </a>
              <a
                href="https://calendly.com/your-link"
                className="glass-card px-8 py-4 border-neon-pink/30 hover:shadow-[0_0_20px_hsl(var(--neon-pink)/0.3)] transition-all duration-300 group"
              >
                <span className="text-neon-pink font-semibold group-hover:text-foreground transition-colors">
                  Schedule a call 📅
                </span>
              </a>
            </div>
          </div>

          {/* Profile Views Counter */}
          <div className="text-center mt-12">
            <div className="glass-card inline-block px-6 py-3">
              <span className="text-sm text-muted-foreground">Profile Views: </span>
              <span className="font-bold gradient-text text-lg">12,847</span>
              <span className="text-sm text-muted-foreground ml-2">• Followers: </span>
              <span className="font-bold gradient-text text-lg">156</span>
            </div>
          </div>

          {/* Footer */}
          <div className="text-center mt-16 pt-8 border-t border-white/10">
            <p className="text-muted-foreground mb-4">
              💫 Thanks for visiting! Have a great day! 🌟
            </p>
            <div className="text-6xl">
              <span className="inline-block hover:scale-125 transition-transform duration-300 cursor-pointer">
                🚀
              </span>
            </div>
          </div>
        </div>
      </section>
    </main>
  );
};

export default GitHubProfile;
