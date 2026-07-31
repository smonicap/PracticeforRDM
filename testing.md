<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Data Management Plan (DMP) Interactive Checklist</title>
  <style>
    :root {
      --primary: #2563eb;
      --bg: #f8fafc;
      --card-bg: #ffffff;
      --text: #1e293b;
      --text-muted: #64748b;
      --border: #e2e8f0;
      --accent: #dbeafe;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.5;
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }

    .header-container {
      margin-bottom: 30px;
      background: var(--card-bg);
      padding: 24px;
      border-radius: 12px;
      border: 1px solid var(--border);
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    }

    h1 {
      margin: 0 0 10px 0;
      font-size: 28px;
      color: #0f172a;
    }

    .progress-container {
      background: var(--border);
      height: 10px;
      border-radius: 5px;
      overflow: hidden;
      margin-top: 15px;
    }

    .progress-bar {
      background: var(--primary);
      height: 100%;
      width: 0%;
      transition: width 0.3s ease;
    }

    .counter-text {
      font-size: 14px;
      color: var(--text-muted);
      margin-top: 8px;
      display: block;
    }

    .section-card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px;
      margin-bottom: 24px;
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    }

    .section-title {
      font-size: 18px;
      font-weight: 700;
      margin-top: 0;
      margin-bottom: 6px;
      color: #0f172a;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .section-subtitle {
      font-size: 14px;
      color: var(--text-muted);
      margin-bottom: 16px;
      font-style: italic;
    }

    .checklist-group {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .checklist-item {
      display: flex;
      align-items: flex-start;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid transparent;
      cursor: pointer;
      transition: background 0.2s, border 0.2s;
    }

    .checklist-item:hover {
      background: var(--bg);
      border-color: var(--border);
    }

    .checklist-item input[type="checkbox"] {
      width: 18px;
      height: 18px;
      margin-top: 3px;
      margin-right: 12px;
      cursor: pointer;
      accent-color: var(--primary);
      flex-shrink: 0;
    }

    .checklist-text {
      font-size: 15px;
      transition: color 0.2s, text-decoration 0.2s;
    }

    /* Completed Item States */
    .checklist-item input[type="checkbox"]:checked + .checklist-text {
      text-decoration: line-through;
      color: var(--text-muted);
    }

    .footer {
      text-align: center;
      margin-top: 40px;
      font-size: 13px;
      color: var(--text-muted);
    }
  </style>
</head>
<body>

  <!-- Summary Dashboard Card -->
  <div class="header-container">
    <h1>DMP Compliance Checklist</h1>
    <p style="margin: 0; color: var(--text-muted);">Track your progress across all mandatory Data Management Plan sections.</p>
    <div class="progress-container">
      <div class="progress-bar" id="progressBar"></div>
    </div>
    <span class="counter-text" id="counterText">0 of 0 requirements completed (0%)</span>
  </div>

  <form id="dmpForm">

    <!-- 1. Responsibility -->
    <div class="section-card">
      <div class="section-title">Responsibility</div>
      <div class="section-subtitle">Ethical, legal, and commercial responsibilities</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Demonstrates clear consideration of institutional policies, platform terms of use, and third-party agreements.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides specific information on how sensitive data will be safeguarded (especially private participant data).</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Identifies if the research relates to Indigenous data and explicitly outlines a plan for Indigenous data sovereignty.</span>
        </label>
      </div>
    </div>

    <!-- 2. Data Collection -->
    <div class="section-card">
      <div class="section-title">Data Collection</div>
      <div class="section-subtitle">Sources and formats</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Thoroughly describes all data types collected or acquired, including a commitment to open, non-proprietary formats.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides a clear estimate of overall data size (in GB or TB) including all expected data types and file versioning data.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Explicitly indicates which data subsets are sensitive and/or directly involve Indigenous groups and traditional knowledge.</span>
        </label>
      </div>
    </div>

    <!-- 3. Documentation -->
    <div class="section-card">
      <div class="section-title">Documentation</div>
      <div class="section-subtitle">Understandable and reproducible</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Outlines a clear plan for metadata and documentation standards across the full lifecycle of the data cycle.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Explicitly names and structures tracking formats: codebooks, data dictionaries, READMEs, lab notes, code scripts, and file/folder naming systems.</span>
        </label>
      </div>
    </div>

    <!-- 4. Active Data Management -->
    <div class="section-card">
      <div class="section-title">Active Data Management</div>
      <div class="section-subtitle">Data storage, security, backups</div>
      <div class="checklist-group">
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Describes active working storage locations and operational processes, including specific software, program versions, and hosting platforms.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Details alternate backup locations, regular backup workflows, retention length, and the data access recovery process.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Identifies clear access permissions (including explicit roles or team member designations mapping to specific accessible data tiers).</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Describes physical and digital security measures alongside active protection protocols for sensitive data (including strict access restrictions).</span>
        </label>
      </div>
    </div>

    <!-- 5. Long-Term Data Management -->
    <div class="section-card">
      <div class="section-title">Long-Term Data Management</div>
      <div class="section-subtitle">Stewardship, Retention, Deposit, and Preservation</div>
      <div class="checklist-group">
        <!-- Base Stewardship/Confidentiality -->
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Provides explicit information on procedural mechanisms used to protect long-term participant confidentiality.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text">Outlines a long-term data stewardship and general access plan that remains fully compliant with institutional research ethics.</span>
        </label>
        
        <!-- Retention sub-points -->
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Retention:</strong> Describes exactly which data files will be kept vs. permanently deleted long-term, providing rationales for each.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Retention Timelines:</strong> Formulates concrete, time-bound retention milestones for all involved data types.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Quality & De-identification:</strong> Explains the process for quality assurance, data normalizing, and rigorous file de-identification.</span>
        </label>
        <label class="checklist-item">
          <input type="checkbox" class="dmp-cb">
          <span class="checklist-text"><strong>Non-Deposited Copies:</strong> Addresses storage locations, security setups, and file parameters for copies retained but not deposited in a public registry.</span>
        </label>

        <!-- Deposit sub-points -->
