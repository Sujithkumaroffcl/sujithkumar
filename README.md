import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Play, Mail, Instagram, Youtube } from "lucide-react";

export default function Portfolio() {
  const projects = [
   {
      title: "Shortfilm Editor",
      desc: "Dynamic cuts, transitions, and color grading for a Shortfilm Named - Red Moon.",
      video: "https://drive.google.com/file/d/1cMzLT-ve_tBSnn8-3MBtEVSlYnvrZAS-/view?usp=drive_link",
    },
    {
      title: "Fan Made Trailer",
      desc: "Cinematic trailer edit with dramatic pacing and sound design for a Movie Named DABBE.",
      video: "https://drive.google.com/file/d/1NgFnFL82U0ld3nj-2KX1lh_GmPHmUmBK/view?usp=drive_link",
    },
    {
      title: "Ad Commercial Edit",
      desc: "Fast-paced editing for a product launch commercial.",
      video: "https://www.youtube.com/embed/sample3",
    },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 to-black text-white px-6 py-10">
      {/* Header */}
      <motion.div
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        className="text-center mb-12"
      >
        <h1 className="text-4xl font-bold mb-2">🎬 My Video Editing Portfolio</h1>
        <p className="text-gray-400">Crafting stories through cuts, transitions, and sound</p>
      </motion.div>

      {/* Projects */}
      <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        {projects.map((proj, i) => (
          <motion.div
            key={i}
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ delay: i * 0.2 }}
          >
            <Card className="bg-gray-800 border-none shadow-lg rounded-2xl overflow-hidden">
              <iframe
                src={proj.video}
                title={proj.title}
                className="w-full h-48"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowFullScreen
              ></iframe>
              <CardContent className="p-4">
                <h2 className="text-xl font-semibold mb-2">{proj.title}</h2>
                <p className="text-gray-400 text-sm mb-4">{proj.desc}</p>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>

      {/* Contact Section */}
      <motion.div
        initial={{ opacity: 0 }}
        whileInView={{ opacity: 1 }}
        className="text-center mt-16"
      >
        <h2 className="text-2xl font-semibold mb-4">📩 Get in Touch</h2>
        <div className="flex justify-center gap-4">
          <Button variant="outline" className="flex items-center gap-2">
            <Mail className="w-4 h-4" /> Email
          </Button>
          <Button variant="outline" className="flex items-center gap-2">
            <Instagram className="w-4 h-4" /> Instagram
          </Button>
          <Button variant="outline" className="flex items-center gap-2">
            <Youtube className="w-4 h-4" /> YouTube
          </Button>
        </div>
      </motion.div>
    </div>
  );
}
