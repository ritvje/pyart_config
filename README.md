# Py-ART config

This repository contains a modified version of the [Py-ART](https://github.com/ARM-DOE/pyart) configuration file.
To use the file, copy it in some path and export the path to the file in `PYART_CONFIG` environment variable.
To make sure that configuration is loaded, you might need to run:

```python
import os
import pyart
pyart.load_config(os.environ.get('PYART_CONFIG'))
```

## Modifications

The following modifications have been done compared to the original config file:

- In IRIS format, add `SNR8`/`SNR16` fields as `signal_to_noise_ratio` type field to be able to read SNR in RAW-files
- In IRIS format, add `PMI8`/"PMI16" fields as `polarimetric_meteo_index` type field to be able to read PMI in RAW-files
- Add metadata definition for `polarimetric_meteo_index` field
- Add metadata definition for melting layer designation (to be compliant with MeteoSwiss Py-ART `melting_layer_giangrande` function)
