# Badge-Generator
export default function handler(req, res) {
  const name = req.query.name || "Participant";

  const svg = `
  <svg width="600" height="200" xmlns="http://www.w3.org/2000/svg">
    <rect width="600" height="200" fill="#111827"/>
    <text x="50%" y="80" font-size="36" fill="white" text-anchor="middle">
      Event Participant
    </text>
    <text x="50%" y="140" font-size="30" fill="#38bdf8" text-anchor="middle">
      ${name}
    </text>
  </svg>
  `;

  res.setHeader("Content-Type", "image/svg+xml");
  res.send(svg);
}
