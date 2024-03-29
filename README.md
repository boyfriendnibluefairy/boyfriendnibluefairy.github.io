<h1 align="center">Apps, Software, & Libraries</h1>

******

# Cat Radar
**Cat Radar** is a free app that utilizes Machine Learning to detect cats. Powered by Apple's CoreML, the app works without internet connection and does not collect user data.

<img width="907" alt="cat_radar" src="https://github.com/boyfriendnibluefairy/boyfriendnibluefairy.github.io/assets/30497886/def71c96-002d-4923-aa15-d2152b4b9327">

*[You may download the app in App Store](https://apps.apple.com/us/app/cat-radar/id6476641987)



******



# Westeros Map
**Westeros Map** is a free companion app for those who read George R.R. Martin books and for those who watch Game of Thrones or House of the Dragon. It has the combined power of UIKit and SwiftUI so that user can explore Westeros and Essos with awesome animation and dynamic search list.

<img width="905" alt="westeros_map" src="https://github.com/boyfriendnibluefairy/boyfriendnibluefairy.github.io/assets/30497886/7be7257a-b1b0-4602-aa70-a3272e1aebd2">

* [You may download the app in App Store](https://apps.apple.com/us/app/westeros-map/id6476431991)



******



# Papyrus Offline  
**Papyrus Offline** is a free paperless registration app that can be used in recording the attendance of participants in conferences, seminars, symposiums, talks, etc.

* [Link to Papyrus Offline Privacy Policy](https://github.com/boyfriendnibluefairy/boyfriendnibluefairy.github.io/blob/main/Papyrus_Offline_-_Privacy_Policy.md)

<img width="360" alt="Papyrus_Offline_screenshots" src="https://github.com/boyfriendnibluefairy/boyfriendnibluefairy.github.io/assets/30497886/10d21659-6867-4152-864e-082d4e5b054d">  

* [Step-by-step tutorial on how to use Papyrus Offline](https://www.youtube.com/watch?v=wF4g5tHLlkc)  

* [You may download the app in App Store](https://apps.apple.com/gr/app/papyrus-offline/id6473137300?platform=iphone)  
  
  
  
******
  
  
  
# openphoton  
**openphoton** is a free python package for optical wave propagation  

* [Step-by-step tutorial on how to use openphoton](https://youtu.be/bz9cDEuyxx0)  

![openphoton_features](https://github.com/boyfriendnibluefairy/boyfriendnibluefairy.github.io/assets/30497886/08b756a9-1407-4315-b0b1-3c714b3256c0)  

### FEATURES:  
 - Light propagation using Rayleigh-Sommerfeld Diffraction Integral
 - Includes Fresnel Approximation and Fraunhofer Approximation
 - Simulation of converging lens and diverging Lens
 - Simulation of amplitude-based test object using SLM

This README.md file is under construction. But the steps presented below is sufficient for you to simulate light propagation from a laser, passing through lens, and passing through your test object. More features will be added soon.  

## Examples of How To Use (Alpha Version)

Add openphoton to your operating system or python virtual environment

```python
pip install openphoton
```

Create a laser beam
```python
import openphoton as op

# side length (m)
# aperture radius (m)
u0 = op.devices.laser_beam(
    side_length=0.06,
    aperture_radius=0.026)
```

In order to forward propagate the wave field, you must choose between fresnel (near-field) approximation and
fraunhoffer (far-field) approximation. To determine which approximation is best for your system, you have to calculate
the Fresnel number F_N. If F_N = [1, +infinity], then use fresnel approximation. Otherwise, use fraunhoffer approximation.
```python
# uo = wave field to propagate
# L = source plane side length (m)
# wavelength = wavelength of light (m)
# z = propagation distance (m)
# u1 = resulting wave field after propagation
u1 = op.rayleigh_sommerfeld.fresnel_approx(
    u0, L, wavelength, z)
```

Apply converging lens or diverging lens on the laser beam
```python
import numpy as np

# u1 = wave field before the lens
# L = u1 side length (m)
# wavelength of light (m)
# f_length = lens focal length (m)
# u2 = wave field after the lens
u2 = np.multiply(u1, op.lenses.converging_lens(u1,L,wavelength,f_length))
```

Apply SLM or test object on the laser beam
```python
import numpy as np

# filename = image of test object file name
filename : str = "USAF_1951_1024p.png"

# SLM_amplitude() converts RGB image into numpy array
# pixel_size = number of pixels of image, ideally this must be the same with u1
test_object = op.devices.SLM_amplitude(filename, pixel_size)

# u1 = wave field before the test object
# L = u1 side length (m)
# wavelength of light (m)
# u2 = wave field after the test object
u2 = np.multiply(u1, test_object)
```

### References:
 - Shen, Fabin, and Anbo Wang. "Fast-Fourier-transform based numerical integration method for the Rayleigh-Sommerfeld diffraction formula." Applied optics 45, no. 6 (2006): 1102-1110.
 - Schmidt, Jason D. "Numerical simulation of optical wave propagation with examples in MATLAB." SPIE (2010).
 - Voelz, David G., and Michael C. Roggemann. "Digital simulation of scalar optical diffraction: revisiting chirp function sampling criteria and consequences." Applied optics 48, no. 32 (2009): 6132-6142.
  
  

******


  
