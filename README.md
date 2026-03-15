export default function handler(req, res) {

  const name = req.query.name || "Student Attendee";
  const img = req.query.img || "https://i.pravatar.cc/120";

  const svg = `
  <svg width="700" height="240" xmlns="http://www.w3.org/2000/svg">

    <!-- Background -->
    <rect width="700" height="240" fill="black"/>

    <!-- Border -->
    <rect x="5" y="5" width="690" height="230" fill="none" stroke="white" stroke-width="2"/>

    <!-- Header -->
    <text x="50%" y="40"
      font-size="28"
      fill="#ff2b2b"
      text-anchor="middle"
      font-family="Arial"
      font-weight="bold">
      RH Panel Discussion
    </text>

    <!-- Profile Picture -->
    <image 
      href="${img}"
      x="300"
      y="70"
      width="100"
      height="100"
      clip-path="circle(50px at center)"
    />

    <!-- Main Banner -->
    <text x="50%" y="200"
      font-size="42"
      fill="#ff0000"
      text-anchor="middle"
      font-family="Arial"
      font-weight="bold">
      ${name}
    </text>

    <!-- Subtitle -->
    <text x="50%" y="225"
      font-size="18"
      fill="#ff8c00"
      text-anchor="middle"
      font-family="Arial">
      RH Ambassador
    </text>

  </svg>
  `;

  res.setHeader("Content-Type", "image/svg+xml");
  res.send(svg);
}
