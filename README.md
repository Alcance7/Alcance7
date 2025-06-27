"use client";

import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { useState } from "react";
import { Globe } from "lucide-react";
import Image from "next/image";

export default function Alcance7() {
  const [language, setLanguage] = useState("es");

  const messages = {
    es: {
      welcome: "Bienvenido a Alcance 7",
      phrase: "Llevando esperanza y luz a cada rincón.",
      verse: "Versículo del Día",
      podcast: "Escucha el Podcast",
      message: "Mensaje de Dios Diario",
      reviews: "Reseñas Bíblicas",
      about: "Sobre Alcance 7",
      connect: "Conéctate"
    },
    en: {
      welcome: "Welcome to Alcance 7",
      phrase: "Bringing hope and light to every corner.",
      verse: "Verse of the Day",
      podcast: "Listen to the Podcast",
      message: "Daily Message from God",
      reviews: "Bible Reviews",
      about: "About Alcance 7",
      connect: "Connect"
    }
  };

  const t = messages[language] || messages["es"];

  return (
    <div
      className="min-h-screen flex flex-col justify-center items-center p-6"
      style={{
        background: "linear-gradient(135deg, #fffbe6 0%, #ffe259 50%, #ffcc70 100%)"
      }}
    >
      <div className="flex justify-end w-full max-w-2xl mb-4">
        <Button onClick={() => setLanguage(language === "es" ? "en" : "es")}>
          <Globe className="mr-2" /> {language === "es" ? "English" : "Español"}
        </Button>
      </div>

      <div className="flex flex-col items-center mb-8 w-full">
        <div className="relative w-[180px] h-[180px] mb-2">
          <Image
            src="/Logo%20Asociados%20Minimalista%20Azul%20y%20Naranja%20(1).png"
            alt="Alcance 7 Logo"
            layout="fill"
            objectFit="contain"
            priority
          />
        </div>
        <h1 className="text-5xl md:text-6xl font-extrabold tracking-widest uppercase text-gray-800 drop-shadow-[0_5px_20px_rgba(255,235,59,0.6)] mb-3">
          Alcance
        </h1>
        <span className="text-lg md:text-xl font-medium text-yellow-700 drop-shadow-lg mb-3">
          {t.phrase}
        </span>
      </div>

      <Card className="mb-4 w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.verse}</h2>
          <p>"Jehová es mi pastor; nada me faltará." - Salmos 23:1</p>
        </CardContent>
      </Card>

      <Card className="mb-4 w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.podcast}</h2>
          <iframe
            src="https://open.spotify.com/embed/episode/1WFXKbl0x3Au1buNu5zttu?utm_source=generator"
            width="100%"
            height="152"
            allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
            loading="lazy"
          ></iframe>
        </CardContent>
      </Card>

      <Card className="mb-4 w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.message}</h2>
          <p>Hoy Dios quiere recordarte que Él está contigo en cada paso.</p>
        </CardContent>
      </Card>

      <Card className="mb-4 w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.reviews}</h2>
          <p>Reflexión: Éxodo 15 nos muestra que la alabanza precede a la victoria.</p>
        </CardContent>
      </Card>

      <Card className="mb-4 w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.about}</h2>
          <p>
            Alcance 7 es un espacio para compartir el mensaje de Cristo por medio del podcast, la Palabra diaria y reflexiones bíblicas.
          </p>
        </CardContent>
      </Card>

      <Card className="w-full max-w-2xl">
        <CardContent>
          <h2 className="text-2xl font-semibold mb-2">{t.connect}</h2>
          <p>¡Síguenos en Spotify y redes sociales para más contenido!</p>
          <div className="flex justify-center gap-6 mt-4">
            <a href="https://www.instagram.com/alcance_7/" target="_blank" rel="noopener noreferrer" className="text-blue-700 hover:underline">
              Instagram
            </a>
            <a href="https://www.youtube.com/@Alcancepodcast7" target="_blank" rel="noopener noreferrer" className="text-red-700 hover:underline">
              YouTube
            </a>
          </div>
        </CardContent>
      </Card>
    </div>
  );
}
