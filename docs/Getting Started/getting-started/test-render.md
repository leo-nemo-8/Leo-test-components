---
title: test render
deprecated: false
hidden: false
metadata:
  robots: index
---
<div style={{ display: "flex", flexWrap: "wrap", gap: "16px", marginBottom: "24px" }}>
  {/* Card 1 */}

  <div
    style={{
      width: "calc(33.333% - 10.66px)",
      flexGrow: 0,
      boxSizing: "border-box",
      padding: "16px",
      borderRadius: "12px",
      boxShadow: "0 4px 10px rgba(200,200,200,0.12)",
      transition: "box-shadow 0.3s ease, transform 0.2s ease"
    }}
    onMouseEnter={e => {
      e.currentTarget.style.boxShadow = "0 8px 20px rgba(200,200,200,0.18)";
      e.currentTarget.style.transform = "translateY(-4px)";
    }}
    onMouseLeave={e => {
      e.currentTarget.style.boxShadow = "0 4px 10px rgba(200,200,200,0.12)";
      e.currentTarget.style.transform = "translateY(0)";
    }}
  >
    <a href="https://docs.emil.de/docs/user-guide-manage-claims" style={{ textDecoration: "none", color: "inherit" }}>
      <strong>Manage Claims</strong><br /><br />

      <span style={{ fontSize: "0.9rem" }}>
        Handle claims processing, create and update positions and regulations.
      </span>
    </a>
  </div>
