import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { LineChart, Line, XAxis, YAxis, Tooltip, ResponsiveContainer } from "recharts";
import { Sun, Moon } from "lucide-react";

const marketData = [
  { name: "Mon", price: 100 },
  { name: "Tue", price: 105 },
  { name: "Wed", price: 110 },
  { name: "Thu", price: 108 },
  { name: "Fri", price: 115 },
];

export default function TradeAIDashboard() {
  return (
    <div className="min-h-screen bg-gray-100 dark:bg-black p-4 grid gap-4 md:grid-cols-2 lg:grid-cols-3">
      <Card className="col-span-2">
        <CardContent>
          <h1 className="text-2xl font-bold mb-4">📈 Indian Market Overview</h1>
          <ResponsiveContainer width="100%" height={250}>
            <LineChart data={marketData}>
              <XAxis dataKey="name" stroke="#888" />
              <YAxis stroke="#888" />
              <Tooltip />
              <Line type="monotone" dataKey="price" stroke="#2563eb" strokeWidth={3} />
            </LineChart>
          </ResponsiveContainer>
        </CardContent>
      </Card>

      <Card>
        <CardContent>
          <h2 className="text-xl font-semibold mb-2">📰 Market News</h2>
          <ul className="text-sm space-y-2">
            <li>• Nifty hits all-time high amid strong earnings</li>
            <li>• Bitcoin crosses $70,000 again</li>
            <li>• Fed keeps interest rates unchanged</li>
          </ul>
        </CardContent>
      </Card>

      <Card>
        <CardContent>
          <h2 className="text-xl font-semibold mb-2">🧮 Calculator</h2>
          <Button className="w-full mb-2">💰 SIP Calculator</Button>
          <Button className="w-full mb-2">📊 P&L Calculator</Button>
          <Button className="w-full">💱 Currency Converter</Button>
        </CardContent>
      </Card>

      <Button className="fixed top-4 right-4 p-2 rounded-full shadow-md" variant="outline">
        <Sun className="dark:hidden" />
        <Moon className="hidden dark:inline" />
      </Button>
    </div>
  );
}
