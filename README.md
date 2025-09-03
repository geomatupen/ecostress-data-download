# ECOSTRESS LST Data Download Workflow

## Overview
Scripts and notebook to:
- Search & download ECOSTRESS LST data (via earthaccess)
- Convert LST (Kelvin) → GeoTIFF (°C)

## Requirements
- Python 3.9+
- gdal (with HDF5 support)
- numpy, python-dateutil
- earthaccess

## Install
### Use Environment
conda env export --from-history > environment.yml
### or install separately
conda create -n ecostress python=3.11 -y
conda activate ecostress
conda install -c conda-forge gdal numpy python-dateutil -y
pip install earthaccess

## major functions
- search_granules → search & download
  - **Function:** 
  ```search_granules(
	lat, 
	lon, 
	start_date, 
	end_date, 
	search_radius_km=1.0, 
	product_short_name="ECO_L2G_LSTE", product_version="002", out_dir="./ecostress_downloads"
  )```
- h5_to_geotiff → convert to GeoTIFF (°C)
  - **Function:** 
  ```h5_to_geotiff(
	h5_path, 
	out_tif_c=None
  )```

## Output
- Downloads in ./ecostress_downloads/
- GeoTIFF output: lst_celsius.tif
