# Surya Saathi (सूर्य साथी)

SoStAT is a browser tool for following the Sun from any place in India. It has two pages:

1. **Shadow board** (`index.html`) – shows where the shadow of a vertical stick falls on the ground: its path through the day, its position at a chosen moment, and the analemma over the year.
2. **Sky map** (`skymap.html`) – shows the whole sky above you at the same moment, with the Sun placed among the stars and constellations.

Both pages are plain HTML files. There is nothing to install and no build step. All calculations run inside the browser.

**Live version:** `https://astrovariable.github.io/Solar-and-Stellar-Astronomy-Tool/`

---

## Contents

- [What each page does](#what-each-page-does)
- [Terms used in this tool](#terms-used-in-this-tool)
- [How to use it](#how-to-use-it)
- [Using it with a real stick and board](#using-it-with-a-real-stick-and-board)
- [Things to try](#things-to-try)
- [Sharing a link to a place and time](#sharing-a-link-to-a-place-and-time)
- [Running it on your computer](#running-it-on-your-computer)
- [Putting it on GitHub Pages](#putting-it-on-github-pages)
- [How the calculations work](#how-the-calculations-work)
- [Accuracy and limitations](#accuracy-and-limitations)
- [Files in this repository](#files-in-this-repository)
- [Credits](#credits)
- [Licence](#licence)

---

## What each page does

### Shadow board (`index.html`)

You give a place, a date, a time and the height of the stick. The page draws a round board, seen from above, with the stick at the centre.

- **Board layout:** north is at the top and east is on the right, the same as a normal map lying on the ground. The board has a radius of 60 cm, with rings every 10 cm.
- **Three views** (tabs above the board):
  - *Shadow through the day* – the path of the shadow tip from sunrise to sunset, with a dot for every clock hour (IST). The 12:00 dot is shown in red.
  - *Analemma* – the position of the shadow tip at the same clock time on every day of the year. Alternate months are labelled (Jan, Mar, May, Jul, Sep, Nov).
  - *Both* – the two drawings together.
- **Current shadow:** a dashed line from the stick to a yellow dot, with the shadow length written next to it.
- **Readouts:** solar altitude, solar azimuth, shadow length, the Sun's declination, the equation of time, and the time of solar noon in IST.

### Sky map (`skymap.html`)

The same place, date and time, shown as a chart of the sky.

- **Chart layout:** the point straight overhead (zenith) is at the centre and the horizon is the outer circle. The chart is drawn as if you are lying on your back looking up, so **north is at the top and east is on the left**. This is the opposite of the shadow board, which looks down at the ground.
- **What is drawn:** 1,627 stars down to magnitude 5, names of 99 bright stars, constellation lines, names of 46 constellations, the ecliptic, the Sun's path across the sky for that date (with hour marks), and the Sun itself. Circles mark altitudes of 30° and 60°.
- **Toggles:** each layer (constellation lines, constellation names, star names, ecliptic, Sun's path) can be switched on or off.
- **Sky always dark:** the sky is drawn dark at all hours, even at noon. This is on purpose, so you can see which constellation the Sun is in front of.
- **Sun below the horizon:** the Sun is not drawn at a fake position. Instead a dashed marker on the rim shows its direction, with a label such as "Sun · 12° below".
- **Readouts:** Sun altitude, Sun azimuth (with compass direction), Sun right ascension, Sun declination, local sidereal time, and sunrise and sunset times in IST.
- **Status line:** says whether it is daytime, twilight (Sun between 0° and 18° below the horizon) or night.

The two pages are linked. When you move from one page to the other using the buttons at the top, the place, date and time you set are carried across.

---

## Terms used in this tool

| Term | Meaning |
|---|---|
| **Gnomon** | The upright stick (or pin) whose shadow is being studied. In a sundial, the part that casts the shadow. |
| **IST** | Indian Standard Time, which is UTC + 5 hours 30 minutes. All times in this tool are IST. |
| **UTC** | Coordinated Universal Time, the world reference time (close to Greenwich time). |
| **Latitude** | How far north (+) or south (−) of the equator a place is, in degrees. |
| **Longitude** | How far east (+) or west (−) of Greenwich a place is, in degrees. |
| **IST meridian (82.5° E)** | The line of longitude that IST is based on. It passes near Mirzapur (Uttar Pradesh). Places west of it see the Sun rise and reach noon later by the clock; places east of it, earlier. |
| **Solar altitude** | Height of the Sun above the horizon, in degrees. 0° is on the horizon, 90° is straight overhead. |
| **Solar azimuth** | Compass direction of the Sun, in degrees, measured from north towards east. North = 0°, east = 90°, south = 180°, west = 270°. |
| **Zenith** | The point in the sky straight above your head (altitude 90°). |
| **Declination** | The Sun's (or a star's) angle north (+) or south (−) of the celestial equator. For the Sun it changes from about −23.4° in December to about +23.4° in June. |
| **Right ascension (RA)** | The east–west coordinate of an object on the sky, like longitude on Earth. Shown in hours : minutes : seconds (24 hours = 360°). |
| **Solar noon** | The moment the Sun is highest in the sky for that day. It is almost never exactly 12:00 by the clock. At solar noon the shadow lies exactly along the north–south line. |
| **Equation of time** | The difference, in minutes, between time kept by the real Sun and time kept by a clock. It changes through the year between about −14 and +16 minutes, because Earth's orbit is not a perfect circle and Earth's axis is tilted. |
| **Analemma** | The figure-of-eight shape you get if you mark the Sun's position (or a shadow tip) at the same clock time every day for a year. |
| **Ecliptic** | The path the Sun appears to follow against the stars over a year. The zodiac constellations lie along it. |
| **Local sidereal time (LST)** | A clock based on the stars instead of the Sun. It tells you which right ascension is crossing your north–south line at that moment. |
| **Magnitude** | A measure of how bright a star looks. Smaller numbers are brighter; negative numbers are very bright. Magnitude 5 stars are faint and need a sky away from city lights. |
| **Precession** | A slow wobble of Earth's axis (one cycle about every 26,000 years) that slowly shifts star coordinates over time. |
| **J2000** | The standard reference date (1 January 2000, 12:00 UT) for which the star positions in this tool are listed. |
| **Twilight** | The period when the Sun is below the horizon but less than 18° below, so the sky is not fully dark. |
| **Stereographic projection** | A way of drawing the round sky on a flat circle. It keeps the shapes of small patterns (like constellations) close to what you see. |

---

## How to use it

### Shadow board

1. Open `index.html` in a web browser.
2. **Choose the place.** Either click one of the city buttons (Delhi, Mumbai, Bengaluru, Kolkata, Chennai, Hyderabad, Ahmedabad, Jaipur, Indore, Ujjain, Nagpur, Thiruvananthapuram, Srinagar, Gangtok), or type your own latitude and longitude in decimal degrees. Use positive numbers for north and east.
3. **Choose the date** in the date box. It starts at today's date.
4. **Choose the time** (IST) using the hour, minute and second boxes. Click **Now** to fill in the current date and time from your device's clock.
5. **Enter the gnomon height** in centimetres. The default is 20 cm.
6. **Pick a view** using the tabs above the board: *Shadow through the day*, *Analemma*, or *Both*.
7. **Read the results.** The six boxes above the board give the Sun's altitude and azimuth, the shadow length, declination, equation of time and solar noon. If the Sun is below the horizon, altitude shows "Below horizon" and no shadow is drawn.
8. Anything you change redraws the board immediately.

### Sky map

1. Click **Sky map** at the top of the shadow board page (this carries your place, date and time across), or open `skymap.html` directly.
2. Change place, date and time in the same way as on the shadow board.
3. Use the tick boxes to show or hide constellation lines, constellation names, bright star names, the ecliptic and the Sun's path.
4. Remember that on this chart east is on the **left**. To match it with the real sky, hold the screen above your head with the "N" at the top pointing north.
5. Read the Sun's position, local sidereal time, and sunrise/sunset times in the boxes above the chart.
6. Click **Shadow board** at the top to go back with the same settings.

---

## Using it with a real stick and board

The shadow board can be printed or copied onto a real board for a classroom or outreach demonstration.

1. **Make the board.** Take a flat board, or a sheet of chart paper on a hard surface. Mark a centre point. Draw circles at 10, 20, 30, 40, 50 and 60 cm from the centre (smaller if your board is smaller; then use a shorter stick so the shadow stays on the board).
2. **Fix the stick.** Stand a straight stick or nail upright at the centre. Use a set square or a plumb line (a thread with a small weight) to check it is exactly vertical. Measure its height from the board surface to its tip, in centimetres.
3. **Level the board.** Place the board in the open where it gets sun for the whole period you want to observe. Use a spirit level (or a small bubble level app on a phone) to check it is flat.
4. **Set up the tool.** Enter your latitude, longitude, today's date and the stick height. Note the solar noon time shown.
5. **Find north without a compass.** A magnetic compass points to magnetic north, which differs from true north. A better way: at the solar noon time shown by the tool, the shadow lies exactly on the north–south line. Mark the shadow at that moment and draw a line through the centre along it. (For places north of the Tropic of Cancer, the noon shadow always points north. For places south of it, the noon shadow points south on the days between its two Zero Shadow Days, around June.)
6. **Or align using any time.** Set the tool to the current time. Rotate the board until the real shadow tip lands on the yellow dot's direction on the screen. The board is then aligned.
7. **Mark the shadow tip.** Every hour on the hour (IST), mark the tip of the real shadow with a dot and write the time next to it.
8. **Compare.** Compare your dots with the blue hour dots on the screen. Small differences are normal (see [Accuracy and limitations](#accuracy-and-limitations)); large differences usually mean the stick is not vertical, the board is not level, or north is not set correctly.

---

## Things to try

- **Zero Shadow Day.** For places between the Tropic of Cancer (about 23.4° N) and the equator, the Sun is exactly overhead at solar noon on two days each year. On those days the midday shadow length becomes zero. Pick Indore or Bengaluru, set the time to solar noon, and change the date until the shadow length is close to 0 cm. Then try Delhi: it never happens there, because Delhi is north of the tropic.
- **Clock noon vs. solar noon.** Compare solar noon for Gangtok (far east) and Ahmedabad (far west) on the same date. The difference comes mostly from longitude (4 minutes for every degree).
- **Analemma shape.** In the *Analemma* view, change the time from 09:00 to 12:00 to 15:00 and watch the figure-of-eight change shape and tilt.
- **Shadow lengths through the year.** Keep the time fixed at 12:00 and compare shadow length on 21 June and 21 December.
- **The Sun's constellation.** On the sky map, find which constellation the Sun is in front of today. Then move the date forward one month at a time and watch the Sun move along the ecliptic, roughly one constellation per month.
- **Summer and winter paths.** On the sky map, compare the Sun's path on 21 June and 21 December: where it rises, how high it gets, and where it sets.

---

## Sharing a link to a place and time

Both pages read settings from the web address (URL). You can share a link that opens at a chosen place, date and time.

| Parameter | Meaning | Example |
|---|---|---|
| `lat` | Latitude in degrees (north positive) | `22.72` |
| `lon` | Longitude in degrees (east positive) | `75.86` |
| `date` | Date in `YYYY-MM-DD` format | `2027-05-19` |
| `h` | Hour, IST (0–23) | `12` |
| `m` | Minute (0–59) | `30` |
| `s` | Second (0–59) | `0` |

Example:

```
index.html?lat=22.72&lon=75.86&date=2027-05-19&h=12&m=30&s=0
skymap.html?lat=22.72&lon=75.86&date=2027-05-19&h=12&m=30&s=0
```

Any parameter you leave out falls back to the default: today's date, the current time from the device, and Mumbai for the place. The gnomon height is not part of the link.





## How the calculations work

All angles below are in degrees unless marked otherwise.

### Shadow board

The Sun's position uses the Fourier series of J. W. Spencer (1971), the same formulas used in the NOAA solar calculator notes.

1. **Day of year** `N`: 1 for 1 January, 365 for 31 December.
2. **Fractional year** `γ` (in radians):
   ```
   γ = 2π / 365 × (N − 1 + (IST_hours − 12) / 24)
   ```
3. **Equation of time** (minutes):
   ```
   EoT = 229.18 × (0.000075 + 0.001868 cos γ − 0.032077 sin γ
                   − 0.014615 cos 2γ − 0.040849 sin 2γ)
   ```
4. **Declination** `δ` (radians):
   ```
   δ = 0.006918 − 0.399912 cos γ + 0.070257 sin γ − 0.006758 cos 2γ
       + 0.000907 sin 2γ − 0.002697 cos 3γ + 0.00148 sin 3γ
   ```
5. **True solar time** (minutes), correcting the clock for the equation of time and for the distance from the 82.5° E meridian:
   ```
   TST = IST_hours × 60 + EoT + 4 × (longitude − 82.5)
   ```
6. **Hour angle** `H` (how far the Sun is from the north–south line; 0° at solar noon):
   ```
   H = TST / 4 − 180
   ```
7. **Altitude** `a`, with latitude `φ`:
   ```
   sin a = sin φ sin δ + cos φ cos δ cos H
   ```
8. **Azimuth** `A` (measured from north towards east):
   ```
   cos A = (sin δ − sin a sin φ) / (cos a cos φ)
   ```
   If `H > 0` (afternoon), `A = 360° − A`.
9. **Shadow**, for a gnomon of height `h`:
   ```
   shadow length   L = h / tan a
   shadow direction  = A + 180°
   ```
   The shadow tip is then placed on the board at `x = L sin(A + 180°)` towards east and `y = L cos(A + 180°)` towards north.
10. **Solar noon** (IST, hours):
    ```
    solar noon = (720 − EoT − 4 × (longitude − 82.5)) / 60
    ```

The daily path is drawn by repeating this every 2 minutes from 04:00 to 20:00 IST. The analemma is drawn by repeating it for days 1 to 365 at the chosen clock time.

### Sky map

1. **Julian Day** (`JD`, a continuous day count used in astronomy) is found from the IST date and time, after subtracting 5.5 hours to get UT.
2. **Greenwich mean sidereal time** (Meeus, *Astronomical Algorithms*), with `D = JD − 2451545.0` and `T = D / 36525`:
   ```
   GMST = 280.46061837 + 360.98564736629 D + 0.000387933 T² − T³ / 38710000
   LST  = GMST + longitude
   ```
3. **Sun's position**, using the low-precision formula from the *Astronomical Almanac*, with `n = JD − 2451545.0`:
   ```
   L = 280.460 + 0.9856474 n          (mean longitude)
   g = 357.528 + 0.9856003 n          (mean anomaly)
   λ = L + 1.915 sin g + 0.020 sin 2g (ecliptic longitude)
   ε = 23.439 − 0.0000004 n           (tilt of Earth's axis)
   RA  = atan2(cos ε sin λ, cos λ)
   Dec = asin(sin ε sin λ)
   ```
4. **Star positions** are stored for J2000 and moved to the chosen date with a simple yearly precession correction (in degrees per year):
   ```
   ΔRA  = 0.0128083 + 0.0055662 sin RA tan Dec
   ΔDec = 0.0055662 cos RA
   ```
5. **Sky coordinates to altitude and azimuth**, with hour angle `H = LST − RA`:
   ```
   sin alt = sin Dec sin φ + cos Dec cos φ cos H
   az      = atan2(−cos Dec sin H, cos φ sin Dec − sin φ cos Dec cos H)
   ```
6. **Drawing on the chart** (stereographic projection), where `R` is the chart radius:
   ```
   r = R × tan((90° − alt) / 2)
   x = centre_x − r sin(az)
   y = centre_y − r cos(az)
   ```
   The minus sign on `x` puts east on the left.
7. **Sunrise and sunset** are found by checking the Sun's altitude every minute from 00:00 to 24:00 IST and noting when it crosses −0.833°. This value allows for the bending of light by the air (refraction) and for the Sun's disc having a size, since sunrise is counted when the top edge appears.

### Labels

On both pages, labels are placed in order of importance (for example: the Sun, then solar noon, then brighter stars, then fainter details). A label that would overlap one already placed is skipped, so the drawing stays readable on small screens.

---

## Accuracy and limitations

- **Good enough for teaching and shadow work.** The shadow board's declination is accurate to within a few hundredths of a degree and its equation of time to within about half a minute. The sky map's Sun is accurate to a few arcminutes (one arcminute is 1/60 of a degree). This is far better than what a hand-marked shadow can show, but it is not a professional ephemeris.
- **Times are always IST.** The tool is built for India. For a place outside India you can still enter its latitude and longitude, but you must give the time converted to IST.
- **The "Now" button uses your device's clock.** It gives the right IST only if the device's time zone is set to India.
- **No refraction in positions.** The air bends sunlight slightly, which lifts the Sun by about half a degree near the horizon. Altitude, azimuth and shadow length do not include this, so shadows near sunrise and sunset will look different from the real ones. The sunrise and sunset times on the sky map *do* include it.
- **Year length.** The shadow board's formulas use a 365-day year, so leap years add a small extra error.
- **Hour dots are clock hours.** The hour dots on the shadow board are for 05:00, 06:00 … 19:00 IST, not for solar hours. The red dot is 12:00 IST, not solar noon.
- **Fixed board size.** The board is always 60 cm in radius. Shadows longer than 60 cm (when the Sun is low, or the stick is tall) go off the board.
- **Real board assumptions.** The results assume a perfectly vertical stick, a level board, and correct alignment with true north.
- **Stars.** Positions ignore the stars' own slow motion across the sky (proper motion) and small effects such as nutation and aberration. The precession correction is a simple approximation. This is fine for a naked-eye chart.
- **Not shown:** the Moon and planets.
- **Near the poles:** if the Sun does not rise or set on the chosen date, sunrise/sunset shows "—".

---

## Files in this repository

```
.
├── index.html    Shadow board (home page)
├── skymap.html   Sky map, with star and constellation data built in
└── README.md     This file
```

Each HTML file is self-contained: styles, code and data are all inside the file.

---

## Credits

- Created by **Pranshu Kurel**, AstroVariable.
- Solar position formulas for the shadow board: J. W. Spencer (1971), "Fourier series representation of the position of the Sun", *Search* 2(5), 172; as presented in NOAA's general solar position calculations.
- Sidereal time: Jean Meeus, *Astronomical Algorithms*.
- Low-precision Sun formula: *The Astronomical Almanac* (US Naval Observatory / HM Nautical Almanac Office).
- Constellation figures: the [d3-celestial](https://github.com/ofrohn/d3-celestial) dataset by Olaf Frohn.
- Fonts: Fraunces, Inter, IBM Plex Mono and Noto Sans Devanagari, via Google Fonts.

---

## Licence

The code in this repository is released under the licence in the [`LICENSE`](LICENSE) file.

The constellation figures in `skymap.html` come from [d3-celestial](https://github.com/ofrohn/d3-celestial), Copyright (c) 2015–2019 Olaf Frohn, and are used under the BSD 3-Clause licence. That licence's terms continue to apply to this data.
