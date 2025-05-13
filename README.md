import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Sun, Moon, Mail, Github, Linkedin } from "lucide-react";
import { motion } from "framer-motion";

export default function Home() {
  const [dark, setDark] = useState(false);

  return (
    <main className={`${dark ? "dark bg-gray-900 text-white" : "bg-white text-black"} min-h-screen px-6 py-8 transition-all`}> 
      <header className="flex justify-between items-center mb-10">
        <h1 className="text-3xl font-bold tracking-tight">Dr. Jane Doe</h1>
        <Button variant="outline" onClick={() => setDark(!dark)}>
          {dark ? <Sun /> : <Moon />}
        </Button>
      </header>

      <section className="grid md:grid-cols-2 gap-8 items-center mb-16">
        <motion.img
          src="/profile.jpg"
          alt="Profile"
          className="rounded-2xl shadow-xl w-full max-w-xs mx-auto"
          initial={{ opacity: 0, x: -50 }}
          animate={{ opacity: 1, x: 0 }}
          transition={{ duration: 0.8 }}
        />
        <div>
          <h2 className="text-4xl font-bold mb-4">Hi, I'm Dr. Jane Doe</h2>
          <p className="text-lg leading-relaxed">
            A passionate Computer Scientist, AI Researcher, and Software Architect focused on building scalable, intelligent systems that create real-world impact.
          </p>
          <div className="flex gap-4 mt-4">
            <a href="mailto:jane.doe@example.com"><Mail /></a>
            <a href="https://github.com/janedoe"><Github /></a>
            <a href="https://linkedin.com/in/janedoe"><Linkedin /></a>
          </div>
        </div>
      </section>

      <section className="mb-16">
        <h3 className="text-2xl font-semibold mb-4">Core Skills</h3>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
          {["JavaScript", "React", "Next.js", "Python", "Django", "Node.js", "SQL", "NoSQL", "Git", "Docker", "Kubernetes", "Tailwind CSS", "Machine Learning", "Deep Learning", "Data Visualization"].map((skill) => (
            <Card key={skill}><CardContent className="p-4 text-center font-medium">{skill}</CardContent></Card>
          ))}
        </div>
      </section>

      <section className="mb-16">
        <h3 className="text-2xl font-semibold mb-4">Featured Projects</h3>
        <div className="grid md:grid-cols-2 gap-6">
          <Card>
            <CardContent className="p-4">
              <h4 className="font-bold text-lg">AI Research Toolkit</h4>
              <p className="text-sm text-muted-foreground mb-2">A Python-based toolkit for prototyping AI models with fast visualization and benchmarking.</p>
              <a className="text-blue-500" href="https://github.com/janedoe/ai-toolkit">View Code</a>
            </CardContent>
          </Card>
          <Card>
            <CardContent className="p-4">
              <h4 className="font-bold text-lg">Smart Portfolio App</h4>
              <p className="text-sm text-muted-foreground mb-2">A Next.js app to track and visualize investment portfolios in real-time.</p>
              <a className="text-blue-500" href="https://janedoe.app">Live Site</a>
            </CardContent>
          </Card>
        </div>
      </section>

      <section className="mb-16">
        <h3 className="text-2xl font-semibold mb-4">Experience</h3>
        <ul className="space-y-4">
          <li>
            <strong>Lead AI Engineer</strong> at DeepMind (2022–Present)
            <p className="text-sm">Designing robust ML models for healthcare diagnostics and NLP systems with scalable APIs.</p>
          </li>
          <li>
            <strong>Software Engineer</strong> at Google (2019–2022)
            <p className="text-sm">Built cloud-native solutions and optimized backend services for global-scale infrastructure.</p>
          </li>
        </ul>
      </section>

      <section className="mb-16">
        <h3 className="text-2xl font-semibold mb-4">Education</h3>
        <ul className="space-y-2">
          <li><strong>Ph.D. in Artificial Intelligence</strong>, MIT, 2021</li>
          <li><strong>M.Tech in Computer Science</strong>, Stanford University, 2017</li>
          <li><strong>B.Tech in CSE</strong>, IIT Bombay, 2015</li>
        </ul>
      </section>

      <section className="mb-16">
        <h3 className="text-2xl font-semibold mb-4">Certifications & Awards</h3>
        <ul className="list-disc pl-6 space-y-1 text-sm">
          <li>Google AI Fellowship, 2020</li>
          <li>Certified Kubernetes Administrator (CKA)</li>
          <li>MIT Technology Review Innovator Under 35, 2022</li>
        </ul>
      </section>

      <section>
        <h3 className="text-2xl font-semibold mb-4">Contact</h3>
        <form className="grid gap-4 max-w-xl">
          <input className="border rounded p-2" type="text" placeholder="Your Name" required />
          <input className="border rounded p-2" type="email" placeholder="Your Email" required />
          <textarea className="border rounded p-2" rows={4} placeholder="Your Message"></textarea>
          <Button type="submit">Send Message</Button>
        </form>
      </section>

      <footer className="mt-20 text-center text-sm text-muted-foreground">
        © {new Date().getFullYear()} Dr. Jane Doe. All rights reserved.
      </footer>
    </main>
  );
}
