# ARIA v4.0 - Hualien Disaster Accessibility Assessment

## Project Overview

This project develops an integrated disaster accessibility assessment framework by combining road network analysis, rainfall simulation, and terrain risk data. 
The goal is to evaluate how extreme weather events (e.g., typhoons) affect transportation efficiency and emergency response capability.

---

## Data Sources

- **Road Network**: OpenStreetMap (via OSMnx)
- **Rainfall Data**: Week 6 Kriging interpolation results
- **Terrain Risk**: Week 4 terrain analysis
- **Avoidance Factors**: Week 3 disaster avoidance and river distance analysis

---

## AI Diagnostic Log

### 1. OSMnx Extraction Issue
**Problem**: Road network extraction occasionally timed out or returned incomplete data.  
**Solution**: Reduced the study area and saved the graph as GraphML to avoid repeated downloads.

### 2. Isochrone Polygon Issue
**Problem**: Isochrone polygons appeared overly large due to convex hull approximation.  
**Solution**: Used adaptive time thresholds and accepted convex hull as a simplified representation.

### 3. Raster Sampling Issue
**Problem**: Rainfall raster sampling returned nodata values at some locations.  
**Solution**: Ensured CRS consistency and applied default rainfall values when data was missing.

### 4. Network Disconnection Issue
**Problem**: Some nodes became disconnected, causing NetworkX NoPath errors.  
**Solution**: Identified disconnected components and treated them as isolated regions in disaster scenarios.

### 5. Missing Speed Attributes
**Problem**: Some road segments lacked speed information.  
**Solution**: Assigned default speeds based on road types.

---

## Key Findings

- **Most critical bottleneck**: [Fill based on your top centrality node]
- **Maximum accessibility loss**: [Fill based on your table results, e.g., 30–50% reduction]
- **Emergency response priority**: Focus on high-centrality nodes with high accessibility contraction

---

## Submission Checklist

- [v]ARIA_v4.ipynb (Complete workflow and analysis)
- [v] hualien_network.graphml (Processed road network)
- [v] README.md (This file with diagnostic log)
- [v] Accessibility table (DataFrame or CSV)

