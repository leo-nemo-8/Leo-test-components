---
name: APIEndpoints
---
export const APIEndpoints = () => (
  <div>

    <style>{`

      .ae-badge {
        display: inline-flex;
        align-items: center;
        gap: 6px;
        background: #f2f0f9;
        border: 1px solid #dddddd;
        border-radius: 6px;
        padding: 4px 10px;
        font-size: 11px;
        font-weight: 600;
        color: #3d2c7d;
        letter-spacing: 0.06em;
        text-transform: uppercase;
        margin-bottom: 14px;
      }
      .ae-badge-dot {
        width: 6px; height: 6px;
        border-radius: 50%;
        background: #3d2c7d;
        display: inline-block;
      }
      .ae-headline {
        font-size: 22px;
        font-weight: 600;
        color: #0f172a;
        margin: 0 0 8px;
        line-height: 1.25;
        letter-spacing: -0.01em;
      }
      .ae-sub {
        font-size: 14px;
        color: #475569;
        line-height: 1.7;
        margin: 0 0 24px;
        max-width: 640px;
      }
      html[data-color-mode="dark"] .ae-sub {
        color: #94a3b8;
      }
      .ae-section-label {
        font-size: 11px;
        font-weight: 600;
        letter-spacing: 0.08em;
        text-transform: uppercase;
        color: #94a3b8;
        margin: 0 0 12px;
      }
      .ae-divider {
        border: none;
        border-top: 1px solid #e2e8f0;
        margin: 24px 0;
      }

      .ae-grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 12px;
        margin: 0 0 4px;
      }
      @media (max-width: 580px) {
        .ae-grid { grid-template-columns: 1fr; }
      }
      .ae-card {
        border: 1px solid #e2e8f0;
        border-radius: 12px;
        overflow: hidden;
      }
      html[data-color-mode="dark"] .ae-card {
        border-color: rgba(51, 65, 85, 0.5);
      }
      .ae-card-header {
        display: flex;
        align-items: center;
        gap: 10px;
        padding: 14px 16px;
        border-bottom: 1px solid #e2e8f0;
        background: #f8fafc;
      }
      html[data-color-mode="dark"] .ae-card-header {
        background: #1e293b;
        border-bottom-color: rgba(51, 65, 85, 0.5);
      }
      .ae-card-dot {
        width: 8px; height: 8px;
        border-radius: 50%;
        flex-shrink: 0;
      }
      .ae-card-title {
        font-size: 13px;
        font-weight: 600;
        color: #0f172a;
      }
      html[data-color-mode="dark"] .ae-card-title {
        color: #f1f5f9;
      }
      .ae-card-body {
        padding: 14px 16px;
        display: flex;
        flex-direction: column;
        gap: 10px;
        background: #ffffff;
      }
      html[data-color-mode="dark"] .ae-card-body {
        background: #0f172a;
      }
      .ae-card-desc {
        font-size: 12px;
        color: #64748b;
        line-height: 1.65;
        margin: 0;
        min-height: 54px;
      }
      html[data-color-mode="dark"] .ae-card-desc {
        color: #94a3b8;
      }
      .ae-endpoint {
        display: flex;
        align-items: center;
        gap: 0;
        background: #0f172a;
        border: 1px solid rgba(51,65,85,0.5);
        border-radius: 6px;
        overflow: hidden;
      }
      .ae-endpoint-method {
        font-family: 'DM Mono', monospace;
        font-size: 10px;
        font-weight: 600;
        letter-spacing: 0.06em;
        padding: 7px 10px;
        border-right: 1px solid rgba(51,65,85,0.5);
        white-space: nowrap;
      }
      .ae-endpoint-url {
        font-family: 'DM Mono', monospace;
        font-size: 11px;
        font-weight: 500;
        padding: 7px 12px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
      }
      .ae-caveat {
        display: flex;
        align-items: flex-start;
        gap: 8px;
        background: #fff8e6;
        border: 1px solid #ffb121;
        border-radius: 6px;
        padding: 8px 10px;
        font-size: 11px;
        color: #735400;
        line-height: 1.6;
      }
      html[data-color-mode="dark"] .ae-caveat {
        background: rgba(255, 177, 33, 0.1);
        border-color: rgba(255, 177, 33, 0.3);
        color: #ffb121;
      }
      .ae-success {
        display: flex;
        align-items: flex-start;
        gap: 8px;
        background: #f2fffa;
        border: 1px solid #007e4d;
        border-radius: 6px;
        padding: 8px 10px;
        font-size: 11px;
        color: #007e4d;
        line-height: 1.6;
      }
      html[data-color-mode="dark"] .ae-success {
        background: rgba(0, 126, 77, 0.1);
        border-color: rgba(0, 126, 77, 0.3);
        color: #4db88a;
      }
      `}</style>

    <div className="ae-grid">

      {/* Test Mode */}
      <div className="ae-card">
        <div className="ae-card-header">
          <span className="ae-card-dot" style={{ background: "#ffb121" }}></span>
          <span className="ae-card-title">Test mode</span>
        </div>
        <div className="ae-card-body">
          <p className="ae-card-desc">Use during development to validate requests without impacting production data or reporting.</p>

          <div className="ae-endpoint">
						<span className="ae-endpoint-method" style={{ color: "#ffb121", background: "rgba(255,177,33,0.12)" }}>POST</span>
            <span className="ae-endpoint-url" style={{ color: "#ffd277" }}>https://tracking.api.cj.com/graphqltest</span>
          </div>

          <div className="ae-caveat">
            <svg style={{ flexShrink: 0, marginTop: "1px" }} width="13" height="13" viewBox="0 0 16 16" fill="none">
              <circle cx="8" cy="8" r="7" stroke="#735400" strokeWidth="1.4"></circle>
              <path d="M8 5v4M8 10.5v.5" stroke="#735400" strokeWidth="1.5" strokeLinecap="round"></path>
            </svg>
            <span>Requests are validated the same as production but are not posted to reporting. Order lock and closure status is not checked — something may pass in Test Mode but fail in production.</span>
          </div>
        </div>
      </div>

      {/* Live Mode */}
      <div className="ae-card">
        <div className="ae-card-header">
          <span className="ae-card-dot" style={{ background: "#007e4d" }}></span>
          <span className="ae-card-title">Live mode</span>
        </div>
        <div className="ae-card-body">
          <p className="ae-card-desc">Use once data has been tested and validated. All valid requests are processed and posted to production reporting.</p>

          <div className="ae-endpoint">
            <span className="ae-endpoint-method" style={{ color: "#007e4d", background: "rgba(0,126,77,0.08)" }}>POST</span>
            <span className="ae-endpoint-url" style={{ color: "#52c99a" }}>https://tracking.api.cj.com/graphql</span>
          </div>

          <div className="ae-success">
            <svg style={{ flexShrink: 0, marginTop: "1px" }} width="13" height="13" viewBox="0 0 16 16" fill="none">
              <circle cx="8" cy="8" r="7" stroke="#007e4d" strokeWidth="1.4"></circle>
              <path d="M5 8l2 2 4-4" stroke="#007e4d" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round"></path>
            </svg>
            <span>All requests run through order processing in production. Valid requests are posted to production reporting and impact your affiliate program data.</span>
          </div>
        </div>
      </div>

    </div>

  </div>
);

<APIEndpoints />

<br />
