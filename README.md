import express from "express";
import cors from "cors";

const app = express();
app.use(cors());
app.use(express.json());

app.post("/lyra/generate", (req, res) => {
  const { prompt } = req.body;
  res.json({ reply: `Lyra received: ${prompt}` });
});

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Lyra backend running on port ${PORT}`);
});
