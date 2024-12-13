import React, { useState } from 'react';
import { motion } from 'framer-motion';
import { 
  Code, 
  Brain, 
  Rocket, 
  Database, 
  GitBranch, 
  Star, 
  Activity, 
  Globe, 
  Award 
} from 'lucide-react';

const AnimatedProfileReadme = () => {
  const [activeSection, setActiveSection] = useState(null);

  const sectionVariants = {
    hidden: { opacity: 0, y: 20 },
    visible: { 
      opacity: 1, 
      y: 0,
      transition: { 
        duration: 0.5,
        ease: "easeInOut"
      }
    },
    hover: {
      scale: 1.05,
      transition: { duration: 0.3 }
    }
  };

  const techIcons = [
    { name: 'Python', color: '#3776AB', icon: Code },
    { name: 'TensorFlow', color: '#FF6F00', icon: Brain },
    { name: 'React', color: '#61DAFB', icon: GitBranch },
    { name: 'MongoDB', color: '#47A248', icon: Database }
  ];

  const projects = [
    {
      name: 'Brain Tumor Detection',
      description: 'Deep learning model for tumor detection',
      icon: Brain
    },
    {
      name: 'File Management System',
      description: 'Python GUI with MongoDB integration',
      icon: Rocket
    },
    {
      name: 'Scheduling Algorithms',
      description: 'Performance analysis of scheduling methods',
      icon: Activity
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-100 to-purple-200 p-8 font-sans">
      <motion.div 
        initial="hidden"
        animate="visible"
        className="max-w-4xl mx-auto bg-white shadow-2xl rounded-3xl overflow-hidden"
      >
        <motion.header 
          variants={sectionVariants}
          whileHover="hover"
          className="bg-gradient-to-r from-blue-500 to-purple-600 text-white p-8 text-center"
        >
          <motion.h1 
            initial={{ scale: 0.8 }}
            animate={{ scale: 1 }}
            className="text-4xl font-bold tracking-wide"
          >
            Mohamed Khacha 🚀
          </motion.h1>
          <p className="mt-2 text-xl opacity-80">
            Engineering Innovator in Data Science, Big Data & AI
          </p>
        </motion.header>

        <div className="p-8 space-y-8">
          <motion.section 
            variants={sectionVariants}
            whileHover="hover"
            onClick={() => setActiveSection('about')}
            className="bg-gray-50 p-6 rounded-2xl cursor-pointer"
          >
            <h2 className="flex items-center text-2xl font-semibold text-blue-600 mb-4">
              <Star className="mr-3 text-yellow-500" /> About Me
            </h2>
            <p className="text-gray-700">
              Passionate engineering student blending curiosity and innovation to craft impactful technological solutions.
            </p>
          </motion.section>

          <motion.section 
            variants={sectionVariants}
            whileHover="hover"
            className="bg-gray-50 p-6 rounded-2xl"
          >
            <h2 className="flex items-center text-2xl font-semibold text-green-600 mb-4">
              <Code className="mr-3 text-green-400" /> Tech Toolbox
            </h2>
            <div className="flex flex-wrap gap-4">
              {techIcons.map((tech, index) => (
                <motion.div 
                  key={index}
                  initial={{ opacity: 0, scale: 0.8 }}
                  animate={{ opacity: 1, scale: 1 }}
                  whileHover={{ scale: 1.1 }}
                  className="flex items-center bg-white shadow-md p-3 rounded-xl"
                >
                  <tech.icon color={tech.color} className="mr-2" />
                  <span style={{ color: tech.color }}>{tech.name}</span>
                </motion.div>
              ))}
            </div>
          </motion.section>

          <motion.section 
            variants={sectionVariants}
            whileHover="hover"
            className="bg-gray-50 p-6 rounded-2xl"
          >
            <h2 className="flex items-center text-2xl font-semibold text-purple-600 mb-4">
              <Globe className="mr-3 text-purple-400" /> Featured Projects
            </h2>
            <div className="space-y-4">
              {projects.map((project, index) => (
                <motion.div 
                  key={index}
                  initial={{ opacity: 0, x: -20 }}
                  animate={{ opacity: 1, x: 0 }}
                  className="flex items-center bg-white p-4 rounded-xl shadow-md"
                >
                  <project.icon className="mr-4 text-blue-500" />
                  <div>
                    <h3 className="font-bold text-lg">{project.name}</h3>
                    <p className="text-gray-600">{project.description}</p>
                  </div>
                </motion.div>
              ))}
            </div>
          </motion.section>

          <motion.section 
            variants={sectionVariants}
            whileHover="hover"
            className="bg-gray-50 p-6 rounded-2xl"
          >
            <h2 className="flex items-center text-2xl font-semibold text-red-600 mb-4">
              <Award className="mr-3 text-red-400" /> Future Goals
            </h2>
            <ul className="list-disc list-inside text-gray-700 space-y-2">
              <li>Build a scalable distributed file system</li>
              <li>Contribute to open-source AI research</li>
              <li>Secure an impactful internship in AI or Big Data</li>
            </ul>
          </motion.section>
        </div>

        <motion.footer 
          variants={sectionVariants}
          className="bg-blue-900 text-white p-6 text-center"
        >
          <p className="italic">"Life isn't about finding yourself. It's about creating yourself." – Unknown</p>
          <div className="mt-4 flex justify-center space-x-4">
            <a href="mailto:mohamedkhacha99@gmail.com" className="hover:text-blue-300">📧 Email</a>
            <a href="https://www.linkedin.com/in/mohamed-khacha-940a9025a/" className="hover:text-blue-300">🔗 LinkedIn</a>
          </div>
        </motion.footer>
      </motion.div>
    </div>
  );
};

export default AnimatedProfileReadme;
