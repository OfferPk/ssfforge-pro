# CCSDS 902.1-B-1 & CSS-SM Simple Schedule Format (SSF) Specification

## Executive Summary

This document provides the technical architecture and specification for **SSFForge Pro**, an industrial workstation implementation of the **Consultative Committee for Space Data Systems (CCSDS) 902.1-B-1** Recommended Standard (*Cross Support Service Management—Simple Schedule Format Specification*, Blue Book, Issue 1, May 2018 / Corrigendum 1\) and **ISO Cross Support Service Management (CSS-SM)**.

The Simple Schedule Information Entity summarizes the space communication, telemetry downlink, telecommand uplink, and radiometric tracking activities that a Provider Cross Support Service System (CSSS—such as NASA Deep Space Network DSN, ESA ESTRACK, KSAT, or commercial ground station networks) plans to perform for a customer mission over a defined scheduling period (e.g. 7-day tactical window).

---

## 1\. Information Architecture & Structural Hierarchy

\+-------------------------------------------------------------------------+

\|                  Simple Schedule Information Entity                     \|

\|  \+--------------------------------------------------------------------+  \|

\|  \| Header & Schedule Management Metadata:                             \|  \|

\|  \|   \- Schedule ID (Globally unique identifier)                       \|  \|

\|  \|   \- Provider CSSS (e.g. NASA\_DSN, ESA\_ESTRACK, KSAT\_POLAR)         \|  \|

\|  \|   \- Customer Mission Identifier (e.g. LUNAR\_GATEWAY, ARTEMIS\_II)   \|  \|

\|  \|   \- Generation Timestamp (UTC, ISO 8601\)                           \|  \|

\|  \|   \- Schedule Validity Period (Start UTC \-\> Stop UTC)               \|  \|

\|  \|   \- Specification Version (1.0)                                    \|  \|

\|  \+--------------------------------------------------------------------+  \|

\+-------------------------------------------------------------------------+

                                    \|

\+-----------------------------------+-------------------------------------+

\|                  Service Packages (Ground Tracking Passes)              \|

\|  \+--------------------------------------------------------------------+  \|

\|  \| For each scheduled pass:                                           \|  \|

\|  \|   \- Service Package ID (Unique within schedule)                    \|  \|

\|  \|   \- Physical Aperture Reference (e.g. DSS-14, DSS-43, Cebreros)    \|  \|

\|  \|   \- Tracking Pass Boundaries (Start Time UTC, Stop Time UTC)       \|  \|

\|  \|   \- Contact Duration (Minutes)                                     \|  \|

\|  \+--------------------------------------------------------------------+  \|

\+-------------------------------------------------------------------------+

                                    \|

\+-----------------------------------+-------------------------------------+

\|                  Space Link Services & Radiometric Activities           \|

\|  \+--------------------------------------------------------------------+  \|

\|  \| Embedded activities during the tracking pass:                      \|  \|

\|  \|   \- Forward Space Link (Command Uplink: X-Band, S-Band, Ka-Band)   \|  \|

\|  \|   \- Return Space Link (Telemetry Downlink: Ka-Band, X-Band)        \|  \|

\|  \|   \- Radiometric Tracking (Coherent Doppler, Two-Way Ranging)       \|  \|

\|  \|   \- Activity Window Boundaries (Start Time UTC \-\> Stop Time UTC)   \|  \|

\|  \+--------------------------------------------------------------------+  \|

\+-------------------------------------------------------------------------+

---

## 2\. Deconfliction & Antenna Slew Margins (§4)

### 2.1 Double-Booking Overlap Detection

No single physical antenna aperture (e.g. DSS-43 70m) may be scheduled to support two distinct missions simultaneously unless explicit Multiple Uplink/Downlink Carrier per Aperture (MSPA) capability is negotiated.

### 2.2 Minimum Antenna Slew and Configuration Buffer

A minimum buffer (nominally 15 minutes) is enforced between consecutive tracking passes on the same aperture:

- Allows mechanical antenna repositioning across azimuth/elevation limits.  
- Allows transmitter frequency synthesizer tuning, maser/LNA recalibration, and baseband modem configuration.

---

## 3\. Bilateral XML and KVN Formatting (§5)

CCSDS 902.1 defines both XML and Key-Value Notation (KVN) serializations:

- **XML Format**: Conforms to the SANA CSS-SM XML Schema (`urn:ccsds:schema:csssm:ssf`).  
- **KVN Format**: Clean ASCII representation matching legacy mission control parsers.