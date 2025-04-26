# site-imoveis-luxo
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Carousel, CarouselContent, CarouselItem } from "@/components/ui/carousel";
import { LineChart, Line, XAxis, YAxis, Tooltip, ResponsiveContainer } from "recharts";
import { motion } from "framer-motion";

const data = [
  { name: 'Topo', valor: 40 },
  { name: 'Meio', valor: 35 },
  { name: 'Fundo', valor: 25 }
];

export default function ApresentacaoImoveisLuxo() {
  return (
    <div className="p-4 md:p-10 space-y-10">
      <motion.h1 initial={{ opacity: 0 }} animate={{ opacity: 1 }} className="text-3xl font-bold text-center">
        Estratégia de Anúncios - Imóveis de Luxo
      </motion.h1>

      <section className="grid md:grid-cols-3 gap-6">
        <Card>
          <CardContent className="p-4">
            <h2 className="text-xl font-semibold mb-2">🎨 Artes de Alta Performance</h2>
            <ul className="list-disc list-inside text-sm">
              <li>Carrosséis com ambientes variados</li>
              <li>Vídeos imersivos (tours virtuais)</li>
              <li>Imagens com textos sobrepostos</li>
            </ul>
          </CardContent>
        </Card>
        <Card>
          <CardContent className="p-4">
            <h2 className="text-xl font-semibold mb-2">✍️ Copys de Impacto</h2>
            <p className="text-sm italic">"Descubra o ápice do luxo na Barra da Tijuca..."</p>
            <p className="text-sm italic">"Viva onde o luxo encontra o estilo de vida..."</p>
            <p className="text-sm italic">"Exclusividade e sofisticação em cada detalhe..."</p>
          </CardContent>
        </Card>
        <Card>
          <CardContent className="p-4">
            <h2 className="text-xl font-semibold mb-2">🔍 Concorrência</h2>
            <ul className="list-disc list-inside text-sm">
              <li>Invexo Imóveis</li>
              <li>Muller Imóveis RJ</li>
              <li>UpperHaus Imóveis</li>
            </ul>
          </CardContent>
        </Card>
      </section>

      <section>
        <h2 className="text-2xl font-bold mb-4">📊 Distribuição de Orçamento por Funil</h2>
        <ResponsiveContainer width="100%" height={300}>
          <LineChart data={data}>
            <XAxis dataKey="name" />
            <YAxis />
            <Tooltip />
            <Line type="monotone" dataKey="valor" stroke="#8884d8" strokeWidth={3} />
          </LineChart>
        </ResponsiveContainer>
      </section>

      <section>
        <h2 className="text-2xl font-bold mb-4">🧠 Criativos e Segmentações</h2>
        <div className="grid md:grid-cols-2 gap-4">
          <Card>
            <CardContent className="p-4">
              <h3 className="text-lg font-semibold">Headlines e CTAs</h3>
              <ul className="text-sm list-disc list-inside">
                <li>"Viva o Luxo na Barra da Tijuca"</li>
                <li>"Descubra Seu Novo Lar"</li>
                <li>"Agende Sua Visita Agora"</li>
              </ul>
            </CardContent>
          </Card>
          <Card>
            <CardContent className="p-4">
              <h3 className="text-lg font-semibold">Públicos e Segmentações</h3>
              <ul className="text-sm list-disc list-inside">
                <li>Bairros nobres do RJ</li>
                <li>Interesse em luxo, viagens, design</li>
                <li>Clientes antigos, visitantes do site</li>
              </ul>
            </CardContent>
          </Card>
        </div>
      </section>

      <section className="text-center pt-10">
        <Button className="text-lg px-8 py-4">Solicitar Apresentação Completa em PDF</Button>
      </section>
    </div>
  );
}
