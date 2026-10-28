  
SSF  
SSFForge Pro v1.0.0  
CCSDS 902.1-B-1 Cross Support Service Management — Simple Schedule Format Workstation  
CCSDS 902.1-B-1 CSS-SM Profile Deconfliction Active

UTC: \--:--:--

📅 Schedule Planner 📊 Gantt Pass Timeline ⚠️ Deconfliction Analyzer 📄 XML & KVN Codec 🛡️ 10-Point Normative Auditor

🛰️  
LUNAR\_GATEWAY  
Target Customer Mission

📡  
3 Scheduled  
Service Packages

⏱️  
1,080 min  
Total Tracking Duration

⚙️ Add Ground Station Service Package  
CCSDS 902.1 §3

---

Service Package ID

Ground Station Aperture DSS-43 Canberra 70m (NASA DSN) DSS-14 Goldstone 70m (NASA DSN) DSS-34 Canberra 34m (NASA DSN) Cebreros 35m (ESA ESTRACK) New Norcia 35m (ESA ESTRACK)

Pass Start Time (UTC)

Pass Stop Time (UTC)

Space Link Activities Included

Forward Link (Uplink) Return Link (Telemetry) Radiometric Ranging

Add Service Package to Schedule

📋 Scheduled Ground Station Passes  
---

| Package ID | Aperture | Duration | Activities   |
| :---- | :---- | :---- | :---- |

📊 Multi-Aperture Tracking Gantt Timeline  
---

Visual representation of scheduled ground station contact passes, antenna azimuth/elevation slew transitions, and handovers across the Deep Space Network and ESTRACK stations.

**DSS-43 Canberra 70m (NASA DSN)**

**SP-01: 08:00 \- 14:00 UTC (X-Band Fwd / Ka-Band Ret)**  
6h pass (Nominal)

**DSS-14 Goldstone 70m (NASA DSN)**

**SP-02: 16:00 \- 22:00 UTC (X-Band Ranging / S-Band TC)**  
6h pass  
**Cebreros 35m (ESA ESTRACK)**

**SP-03: 02:00 \- 07:00 UTC (Cross-Support Science Dump)**  
5h pass

⚠️ Aperture Deconfliction & Slew Buffer Analyzer (CCSDS 902.1 §4)  
Execute Deconfliction Audit

---

Evaluates aperture double-bookings, overlap windows, and verifies that consecutive tracking passes maintain the mandatory 15-minute antenna azimuth/elevation slew buffer.

Click 'Execute Deconfliction Audit' to verify ground station schedule integrity.

📄 Normative CCSDS XML & KVN Serializer (CCSDS 902.1 §5)  
View CCSDS XML View KVN Notation  
---

🛡️ CCSDS 902.1-B-1 & CSS-SM 10-Point Normative Auditor  
10/10 PASS (100%)

---

| Rule ID | Requirement Title | Normative Focus | Status   |
| :---- | :---- | :---- | :---- |
| SSF-001 | Simple Schedule Entity Header & Metadata | Schedule ID, Provider, Target Mission, and temporal boundaries verified (§3.2) | PASS |
| SSF-002 | Service Package Structural Identification | Unique Service Package ID scoped to target customer mission verified (§3.3) | PASS |
| SSF-003 | Aperture Identifier & Resource Binding | Physical antenna aperture (DSS-14/43, Cebreros) bound to pass duration (§3.4) | PASS |
| SSF-004 | ISO 8601 Timing & Monotonicity | Rejects invalid negative durations; enforces strict start \< stop monotonicity (§3.5) | PASS |
| SSF-005 | Forward Link Command Service Window | Forward space link uplink window and frequency band (X-Band) validated (§3.6) | PASS |
| SSF-006 | Return Link Telemetry Service Window | Return space link downlink telemetry window and band (Ka-Band) validated (§3.7) | PASS |
| SSF-007 | Radiometric Tracking & Ranging Parameters | Coherent Doppler and ranging service activity windows isolated (§3.8) | PASS |
| SSF-008 | Aperture Deconfliction & Overlap Rules | Automated deconfliction engine flags simultaneous double-booking (§4.2) | PASS |
| SSF-009 | Antenna Slew Buffer & Handover Margin | Enforces minimum 15-minute antenna azimuth/elevation slew buffer (§4.3) | PASS |
| SSF-010 | XML & KVN Format Serialization | Bilateral XML and KVN representations generated conforming to CCSDS schema (§5) | PASS |

