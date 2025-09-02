# website-uji-coba
import React, { useState } from "react";
import { motion } from "framer-motion";
import { Star } from "lucide-react";

export default function KenzoPortfolio() {
  const [activeSkill, setActiveSkill] = useState(null);
  const [activeProject, setActiveProject] = useState(null);
  const [activeCert, setActiveCert] = useState(null);

  const Rating = ({ stars }) => (
    <div className="flex gap-1 mt-1">
      {[...Array(5)].map((_, i) => (
        <Star
          key={i}
          size={14}
          className={
            i < stars ? "text-yellow-400 fill-yellow-400" : "text-slate-600"
          }
        />
      ))}
    </div>
  );

  return (
    <div className="min-h-screen w-full bg-gradient-to-b from-slate-900 via-slate-800 to-black text-slate-100 antialiased px-3">
      <header className="px-3 py-4">
        <h1 className="text-lg font-bold leading-tight">Kenzo — Ethical Hacker</h1>
        <p className="text-xs text-slate-400">Security Researcher & Pentester</p>
      </header>

      <main className="pb-12 space-y-6 max-w-md mx-auto">
        {/* HERO */}
        <section className="bg-white/5 rounded-lg p-4 shadow">
          <h2 className="text-base font-bold mb-2">
            Hai, saya Kenzo —{" "}
            <span className="text-indigo-400">Ethical Hacker</span>
          </h2>
          <p className="text-xs text-slate-300 mb-2">
            Saya membantu organisasi menemukan dan menutup celah keamanan dengan
            pendekatan etis.
          </p>
          <div className="text-xs text-slate-400">
            <div>
              <strong>Email:</strong> pykcyber@gmail.com
            </div>
            <div>
              <strong>WA:</strong>{" "}
              <a className="underline" href="https://wa.me/6283143490913">
                +62 831-4349-0913
              </a>
            </div>
          </div>
        </section>

        {/* SKILLS */}
        <section id="skills">
          <h3 className="text-base font-bold mb-3">Skills</h3>
          <div className="grid grid-cols-1 gap-2">
            {[
              { name: "Web App Pentesting", rate: 5 },
              { name: "API Security", rate: 4 },
              { name: "Network Hardening", rate: 4 },
              { name: "Reverse Engineering", rate: 3 },
              { name: "OSINT & Threat Intel", rate: 5 },
            ].map((skill, i) => (
              <motion.div
                whileTap={{ scale: 0.97 }}
                key={i}
                onClick={() => setActiveSkill(skill.name)}
                className={`p-2 rounded bg-white/5 border ${
                  activeSkill === skill.name
                    ? "border-indigo-500"
                    : "border-slate-700"
                }`}
              >
                <div className="flex justify-between items-center">
                  <span className="text-xs">{skill.name}</span>
                  <Rating stars={skill.rate} />
                </div>
              </motion.div>
            ))}
          </div>
        </section>

        {/* PROJECTS */}
        <section id="projects">
          <h3 className="text-base font-bold mb-3">Projects</h3>
          <div className="grid grid-cols-1 gap-2">
            {[
              { title: "Enterprise Audit", rate: 5 },
              { title: "Cloud Infra Review", rate: 4 },
              { title: "Bug Bounty Findings", rate: 5 },
              { title: "API Security Hardening", rate: 4 },
            ].map((proj, i) => (
              <motion.div
                whileTap={{ scale: 0.97 }}
                key={i}
                onClick={() => setActiveProject(proj.title)}
                className={`p-2 rounded bg-white/5 border ${
                  activeProject === proj.title
                    ? "border-emerald-500"
                    : "border-slate-700"
                }`}
              >
                <div className="flex justify-between items-center">
                  <span className="text-xs font-medium">{proj.title}</span>
                  <Rating stars={proj.rate} />
                </div>
              </motion.div>
            ))}
          </div>
        </section>

        {/* CERTIFICATES */}
        <section id="certificates">
          <h3 className="text-base font-bold mb-3">Certificates</h3>
          <div className="grid grid-cols-1 gap-2">
            {[
              { title: "Certified Ethical Hacker (CEH)", rate: 5, link: "#" },
              { title: "OSCP — Offensive Security", rate: 5, link: "#" },
              { title: "CompTIA Security+", rate: 4, link: "#" },
              { title: "eJPT — Junior Penetration Tester", rate: 4, link: "#" },
              { title: "TryHackMe Badge", rate: 5, link: "#" },
            ].map((cert, i) => (
              <motion.div
                whileTap={{ scale: 0.97 }}
                key={i}
                onClick={() => setActiveCert(cert.title)}
                className={`p-2 rounded bg-white/5 border ${
                  activeCert === cert.title
                    ? "border-cyan-500"
                    : "border-slate-700"
                }`}
              >
                <div className="flex justify-between items-center">
                  <div>
                    <span className="text-xs font-medium">{cert.title}</span>
                    <p className="text-[10px] text-slate-400">
                      Sertifikat ini saya berikan kepada: <b>Kenzo</b>
                    </p>
                  </div>
                  <Rating stars={cert.rate} />
                </div>
                <a
                  href={cert.link}
                  target="_blank"
                  rel="noreferrer"
                  className="text-[10px] underline text-cyan-400"
                >
                  View Credential
                </a>
              </motion.div>
            ))}
          </div>
        </section>

        {/* CONTACT */}
        <section id="contact" className="bg-white/5 rounded-lg p-4 shadow">
          <h3 className="text-base font-bold mb-2">Contact</h3>
          <a
            href="mailto:pykcyber@gmail.com"
            className="block text-xs underline"
          >
            pykcyber@gmail.com
          </a>
          <a
            href="https://wa.me/6283143490913"
            target="_blank"
            rel="noreferrer"
            className="block text-xs underline mt-1"
          >
            +62 831-4349-0913
          </a>
        </section>

        {/* FOOTER */}
        <footer className="text-center text-[10px] text-slate-500">
          <div>
            Website ini dibuat oleh <strong>Kenzo</strong>
          </div>
          <div>© {new Date().getFullYear()} Kenzo. Semua hak cipta dilindungi.</div>
        </footer>
      </main>
    </div>
  );
}
