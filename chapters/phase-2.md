## 3. Phase 2 — Space and Ground Segment Architecture

### 3.1 Overview

Phase 2 builds domain-specific knowledge of satellite systems architecture, with a focus on EUMETSAT's operational systems. Understanding what EUMETSAT operates — in full architectural detail — is essential for any SE role within the organisation.

### 3.2 The EUMETSAT End-to-End System

The EUMETSAT system can be understood as three interconnected domains: the space segment, the ground segment, and the user segment. Systems engineers must understand all three and the interfaces between them.

**The Space Segment**

EUMETSAT's satellite fleet currently consists of:

- **Meteosat Second Generation (MSG)**: Four geostationary satellites at approximately 0° longitude providing full-disc imagery every 15 minutes. Primary instruments: SEVIRI (Spinning Enhanced Visible and Infrared Imager) and GERB (Geostationary Earth Radiation Budget). These are mature, well-documented systems and excellent for study.

- **Meteosat Third Generation (MTG)**: The next generation of geostationary satellites. MTG-I (Imager) carries the Flexible Combined Imager (FCI) and Lightning Imager (LI). MTG-S (Sounder) carries the Infrared Sounder (IRS) and hosts the ESA Sentinel-4 UVN instrument for atmospheric composition monitoring. MTG represents the current state of the art and is the focus of most current ground segment SE activity at EUMETSAT.

- **Metop (EPS)**: Three polar-orbiting satellites in sun-synchronous orbit at 817 km altitude. Carry a suite of instruments including IASI (Infrared Atmospheric Sounding Interferometer), AVHRR, AMSU, and MHS. Metop-B and Metop-C are currently operational.

- **Metop Second Generation (EPS-SG)**: Under development, will replace Metop with improved instruments including IASI-NG, MWS, and RO instruments.

- **Sentinel-3 and Sentinel-6**: Copernicus missions operated by EUMETSAT on behalf of the EU, providing ocean colour, sea surface temperature, and altimetry data.

- **EPS-Sterna**: A new constellation of microsatellites carrying microwave sounders, currently in preparation.

**The Ground Segment**

The EUMETSAT ground segment is the set of ground-based infrastructure required to operate the satellites and process and deliver their data. Its major components are:

- **Mission Control Centre (MCC)**: Located at EUMETSAT headquarters in Darmstadt, the MCC is responsible for the safe operation of all satellites. It comprises two main control rooms — one for geostationary missions and one for low-Earth-orbit missions. From the MCC, teams communicate with satellites and acquire data through a network of ground stations. Operations run continuously, 24 hours a day, 365 days a year.

- **Telemetry, Tracking and Control (TT&C) Ground Stations**: These stations provide the uplink and downlink communication interface between the satellites and the MCC. They send telecommands to the satellite and receive housekeeping telemetry, and perform ranging for orbit determination. Primary and backup stations are distributed across Europe.

- **Mission Data Acquisition (MDA) Stations / Ground Station Facilities (GSTF)**: Separate from TT&C, these stations receive the high-rate payload data (instrument science data) from the satellites. For MTG, data is received in the Ka band from both MTG-I and MTG-S at sites including Lario (Italy) and Leuk (Switzerland).

- **Mission Operations Facility (MOF)**: The MOF provides all functions needed to plan and operate the missions. It includes the Mission Control Subsystem (MCS) for satellite monitoring and control, the Mission Planning Subsystem (MPS) for scheduling, and the Flight Dynamics Subsystem (FDS) for orbit determination and manoeuvre planning.

- **Instrument Data Processing Facilities (IDPF)**: These facilities process the raw instrument data into calibrated, geolocated Level 1b products. For MTG, there are separate IDPFs for the imager and sounder instruments.

- **Level 2 Processing Facility (L2PF)**: Transforms Level 1b data into geophysical products (Level 2) such as cloud properties, atmospheric motion vectors, and sea surface temperature.

- **Multi-Mission Elements (MME)**: EUMETSAT has developed a set of common operational facilities shared across all programmes, covering data centre services, EUMETCast dissemination, system monitoring, and IT infrastructure. This multi-mission approach reduces duplication and cost.

- **EUMETCast**: EUMETSAT's primary near-real-time data dissemination mechanism, based on Digital Video Broadcast-S2 (DVB-S2) technology. It uses commercial geostationary satellites to multicast data and products to users worldwide who have appropriate receiving equipment.

- **Satellite Application Facilities (SAFs)**: A network of eight thematic processing centres distributed across EUMETSAT member states, each specialising in a particular application domain: Nowcasting (NWC SAF), Numerical Weather Prediction (NWP SAF), Ocean and Sea Ice (OSI SAF), Land Surface Analysis (LSA SAF), Atmospheric Composition Monitoring (AC SAF), Climate Monitoring (CM SAF), Radio Occultation Monitoring (ROM SAF), and the HSAF for Hydrological and Snow products.

### 3.3 Interfaces and Interface Control

A critical SE skill is understanding and managing interfaces — the boundaries between systems or subsystems where data, power, physical connections, or functions are exchanged. At EUMETSAT, key interfaces include:

- **Space-to-Ground Interface**: The radio frequency link between satellite and ground station (TT&C on S-band, payload data on X-band or Ka-band). Defined in Interface Control Documents (ICDs).
- **Intra-Ground Segment Interfaces**: Data flows between ground segment elements (e.g., from data acquisition to processing to dissemination). These are documented in Interface Requirements Documents (IRDs).
- **External Interfaces**: Data exchanges with ESA (joint programmes), NOAA (IJPS cooperation), ECMWF (NWP products), and Copernicus services.

Study the EUMETSAT publicly available interface documentation for MTG and EPS-SG. These documents give real-world examples of how interface requirements are specified and managed.

### 3.4 Orbit and Spacecraft Fundamentals

While not required to be an orbital mechanics expert, systems engineers must understand:

- **Geostationary orbit (GEO)**: ~35,786 km altitude, satellite appears stationary relative to Earth, ideal for continuous regional imaging (Meteosat).
- **Sun-synchronous orbit (SSO)**: ~800 km altitude, polar orbit crossing the equator at a consistent local solar time, ideal for global coverage (Metop, Sentinels).
- **Spacecraft subsystems**: Power (solar panels, batteries), attitude control (star trackers, reaction wheels), propulsion (for orbit manoeuvres), on-board data handling (OBDH), communications (TT&C transponder).
- **Launch and Early Operations Phase (LEOP)**: The critical period immediately after launch when the satellite is deployed, activated, and tested before being handed to routine operations.

Recommended reading: ESA's "Essentials of Spacecraft Attitude Determination and Control" and the EUMETSAT satellite pages on eumetsat.int.
