## Data Processing and Product Lifecycle

### Overview

From a systems engineering perspective, the data processing chain is a critical subsystem that must be fully specified, designed, verified, and maintained. Understanding it deeply — both technically and from an SE lifecycle perspective — is a significant differentiator.

### The EUMETSAT Data Processing Hierarchy

EUMETSAT's data products are organised in processing levels that mirror international standards:

- **Level 0**: Raw, unprocessed instrument data as received from the satellite, in its native format with full resolution. Telemetry packets are assembled but no geophysical calibration has been applied. Level 0 data is typically archived for reprocessing.

- **Level 1b**: Calibrated, geolocated instrument measurements expressed in physical units (e.g., radiances in W/m²/sr/cm⁻¹ for IASI, brightness temperatures for AMSU). Calibration algorithms are applied to convert raw digital counts to physical quantities. Geolocation assigns geographical coordinates to each measurement. Level 1b is the primary output of the Instrument Data Processing Facility and is the starting point for most downstream users.

- **Level 1c**: For imaging instruments, Level 1c adds further processing for geometric correction, image navigation and registration (INR), and sometimes remapping to standard projections. The accuracy of Level 1c geolocation is critical for meteorological applications.

- **Level 2**: Geophysical parameters derived from Level 1b data by applying physical retrieval algorithms. Examples include: sea surface temperature (SST), atmospheric temperature and humidity profiles, total column ozone, cloud properties (cloud top height, optical thickness, phase), atmospheric motion vectors (AMVs), and precipitation estimates.

- **Level 3**: Gridded, composited, or averaged products derived from Level 2 data. These are typically created over regular time periods (daily, monthly) and on regular spatial grids. Important for climate monitoring applications.

### Calibration and Validation (Cal/Val)

Calibration and validation is the process of ensuring that instrument measurements and derived products are accurate and consistent over time. It bridges the gap between raw measurements and scientifically and operationally useful products.

- **Radiometric Calibration**: Conversion of raw digital counts to physical radiances using characterisation data from pre-launch calibration campaigns (in a thermal vacuum chamber). On-board calibration targets (blackbodies, solar diffusers) are used to track and correct for instrument degradation in orbit.
- **Geometric Calibration / Image Navigation and Registration (INR)**: Ensuring that the spatial position of each measurement pixel is accurately known. For geostationary imagers (MSG SEVIRI, MTG FCI), INR uses natural landmarks (coastlines, mountains) in the image to correct for satellite attitude and instrument mispointing errors. Geometric accuracy to sub-pixel levels is required for many applications.
- **Product Validation**: Comparing derived Level 2 products against independent reference data — for example, comparing satellite-derived SST with in-situ buoy measurements, or comparing retrieved temperature profiles with radiosonde data. Validation campaigns involve coordinated measurement campaigns and statistical assessment of bias, standard deviation, and correlation.

From a systems engineering perspective, the Cal/Val process must be planned, specified, and operationalised as part of the ground segment design — it is not an afterthought. Requirements for validation accuracy targets must be defined and verified.

### Data Formats and Access Standards

Proficiency with the data formats used in EUMETSAT products is essential:

- **NetCDF-4 / HDF5**: The dominant format for EUMETSAT higher-level products. Understanding the CF (Climate and Forecast) conventions for metadata, coordinate systems, and attribute naming is essential.
- **BUFR (Binary Universal Form for the Representation of meteorological data)**: The WMO standard format for satellite sounding data, widely used for data exchange with National Meteorological Services.
- **GRIB2 (GRIdded Binary)**: Standard format for gridded meteorological forecast and analysis fields, used for EUMETSAT products delivered to NWP centres.
- **HDF5 native formats**: Used for some Level 0 and Level 1 products (e.g., Sentinel-3 products use a specific HDF5 profile).
- **EUMETSAT Data Store API**: A RESTful API providing programmatic access to EUMETSAT's data archive. Python clients exist (eumdac Python library) and should be mastered for data retrieval automation.

### Ground Processing System Engineering

From a SE perspective, the data processing system is a complex software-intensive system that must be fully engineered. Key SE considerations include:

- **Performance Requirements**: Timeliness (latency from observation to product delivery), throughput (data volumes, products per unit time), and availability (uptime requirements in a 24/7 operational service).
- **Reprocessing**: A recurring requirement at EUMETSAT is the reprocessing of historical data with improved algorithms to generate consistent long time series for climate applications. The system must be designed to support reprocessing efficiently — this has major implications for storage architecture, software modularity, and configuration management.
- **Algorithm Baseline Management**: The processing algorithms evolve over the mission lifetime as calibration improves and scientific understanding advances. A robust configuration management system is needed to track algorithm versions, input data versions, and output product versions.
- **Cloud-Native Data Processing**: EUMETSAT is actively transitioning its data processing toward cloud-native, containerised architectures using technologies such as Kubernetes, object storage (S3-compatible), and cloud-based processing pipelines.
