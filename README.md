Advanced Flood Risk Analysis System
A comprehensive flood risk assessment tool that combines geospatial analysis, machine learning, and interactive visualizations to evaluate flood risks across Indian metropolitan areas.
🌊 Features
Core Analysis Capabilities

Multi-Factor Risk Assessment: Combines elevation, slope, water proximity, drainage capacity, and land use patterns
Natural Language Processing: Extract locations and intents from plain English queries
Real-time Visualization: Interactive maps, heatmaps, and dashboards
Comprehensive Coverage: Pre-configured for Chennai, Mumbai, Bangalore, and Delhi
Risk Classification: Five-tier risk categorization (Very Low to Very High)

Advanced Visualizations

Elevation contour maps with area markers
Flood risk heatmaps with color-coded risk levels
Multi-factor risk breakdown analysis
Area-wise risk dashboards
Interactive Folium maps with detailed popups
Workflow progress tracking

Technical Features

Realistic topographical data generation
Advanced gradient analysis for slope calculation
Water body proximity modeling
Drainage capacity assessment
Land use risk evaluation
Export capabilities (JSON format)

🛠 Installation
Prerequisites

Python 3.8 or higher
pip package manager

Required Dependencies
bashpip install streamlit numpy pandas plotly folium streamlit-folium scipy rasterio
Complete Installation

Clone the repository

bashgit clone https://github.com/Tanvi0307/GEOSPATIAL.git
cd GEOSPATIAL

Install dependencies

bashpip install -r requirements.txt

Run the application

bashstreamlit run app.py
📋 Requirements File
Create a requirements.txt file with:
streamlit>=1.28.0
numpy>=1.24.0
pandas>=2.0.0
plotly>=5.15.0
folium>=0.14.0
streamlit-folium>=0.13.0
scipy>=1.11.0
rasterio>=1.3.0
🚀 Usage
Basic Usage

Start the application

bashstreamlit run app.py

Access the web interface

Open your browser to http://localhost:8501


Input your analysis query

Use natural language: "Analyze flood risk for Chennai areas near water bodies"
Or select a location from the dropdown


Configure analysis options

Choose which visualizations to generate
Select specific analysis components


Run the analysis

Click "Run Analysis" to start the comprehensive assessment



Natural Language Queries
The system understands various query formats:
"Analyze flood risk for Chennai"
"Show me Mumbai flooding patterns"
"Assess drainage issues in Bangalore"
"Evaluate water logging risk in Delhi"
"Emergency flood assessment for Tamil Nadu capital"
Supported Locations
Currently configured for:

Chennai (Tamil Nadu) - Coastal city with monsoon challenges
Mumbai (Maharashtra) - Coastal metropolis with extreme rainfall
Bangalore (Karnataka) - Inland city with lake systems
Delhi (NCR) - River-adjacent capital region

📊 Analysis Components
1. Elevation Analysis

Generates realistic topographical data
Considers coastal gradients and urban topology
Identifies low-lying vulnerable areas

2. Slope Assessment

Calculates surface gradients using advanced algorithms
Smooths data using Gaussian filters
Identifies steep and flat areas affecting water flow

3. Water Proximity Analysis

Maps distances to rivers, lakes, seas, and drainage channels
Considers multiple water body types and sizes
Factors in tidal influences for coastal areas

4. Drainage Capacity Evaluation

Assesses urban drainage infrastructure
Considers land use impacts on water absorption
Identifies areas with poor drainage systems

5. Land Use Risk Assessment

Evaluates commercial, residential, and industrial areas
Considers development density and surface permeability
Assesses infrastructure vulnerability

🗺 Location Data Structure
Each location includes:
python{
    'bounds': (min_lon, min_lat, max_lon, max_lat),
    'center': (center_lon, center_lat),
    'elevation_range': (min_elevation, max_elevation),
    'coastal': True/False,
    'areas': [
        {
            'name': 'Area Name',
            'coords': (longitude, latitude),
            'type': 'residential/commercial/industrial',
            'elevation': elevation_in_meters,
            'risk_factors': ['factor1', 'factor2']
        }
    ],
    'water_bodies': [
        {
            'name': 'Water Body Name',
            'type': 'river/lake/sea/canal',
            'coords': [(lon1, lat1), (lon2, lat2)],
            'width': width_in_meters
        }
    ]
}
📈 Risk Assessment Methodology
Risk Factors and Weights

Elevation (35%): Lower areas have higher flood risk
Slope (25%): Flatter areas retain water longer
Water Proximity (20%): Closer to water bodies increases risk
Drainage (15%): Poor drainage amplifies risk
Land Use (5%): Urban density affects vulnerability

Risk Categories

Very Low (0.0-0.2): Minimal flood risk
Low (0.2-0.4): Occasional minor flooding possible
Moderate (0.4-0.6): Moderate flooding during heavy rains
High (0.6-0.8): Regular flooding expected
Very High (0.8-1.0): Severe flood-prone areas

🔧 Customization
Adding New Locations

Extend the location manager

python# In EnhancedLocationManager class
self.location_data['new_city'] = {
    'country': 'India',
    'state': 'State Name',
    'bounds': (min_lon, min_lat, max_lon, max_lat),
    'center': (center_lon, center_lat),
    # ... other parameters
}

Update NLP patterns

python# In NLPQueryProcessor class
self.city_patterns['new_city'] = [
    r'\bnew_city\b',
    r'\bstate_name\s+capital\b'
]
Modifying Risk Weights
python# In AdvancedFloodRiskAnalyzer class
self.risk_factors = {
    'elevation_weight': 0.30,    # Adjust as needed
    'slope_weight': 0.25,
    'water_proximity_weight': 0.25,
    'drainage_weight': 0.15,
    'land_use_weight': 0.05
}
📤 Export Capabilities
The system generates downloadable reports in JSON format containing:

Analysis summary statistics
Risk assessment results
Area-specific data
Water body information
Workflow execution logs

🏗 Architecture
Class Structure

NLPQueryProcessor: Handles natural language understanding
WorkflowLogger: Tracks analysis progress and steps
EnhancedLocationManager: Manages geographic data
AdvancedFloodRiskAnalyzer: Core risk assessment engine
AdvancedDataVisualizer: Generates all visualizations
StreamlitApp: Main application interface

Data Flow

User input → NLP processing
Location data retrieval
Multi-factor risk analysis
Visualization generation
Interactive display
Export capabilities

⚠ Known Issues

Performance: Large grid calculations may be slow on older hardware
Memory: High-resolution analysis requires significant RAM
Data Accuracy: Uses simulated elevation data, not real DEM data
Limited Coverage: Currently supports only 4 Indian cities

🔮 Future Enhancements

Integration with real-time weather APIs
Satellite imagery overlay capabilities
Historical flood data integration
Machine learning risk prediction
Mobile-responsive interface
Real DEM data integration
Additional Indian cities
Multi-language support



