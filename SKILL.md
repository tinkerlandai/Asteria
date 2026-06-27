---
name: Asteria Astrology
description: |
  Calculate and interpret natal charts, synastry, composites, planetary returns,
  transits, and eclipses using Swiss Ephemeris precision and astrological tradition.
---

# Asteria Astrology -- Chart Calculator and Interpreter

Provenance: shaped from [Asteria](https://github.com/alamahant/Asteria), a C++/Qt
desktop astrological chart calculator and analyzer by alamahant. The original app
uses Swiss Ephemeris for astronomical precision and Mistral AI for interpretations.
This skill replicates Asteria's analytical workflow as a conversational tool.

Source URL: https://github.com/alamahant/Asteria

## What This Skill Does

Calculate and interpret astrological charts from birth data. The user provides
date, time, and location of birth; the skill computes planetary positions, house
cusps, aspects, element/modality balance, and delivers a structured interpretation.

Supported chart types:

- **Natal chart** -- planets in signs and houses, aspect grid, angles (ASC, MC,
  DSC, IC), element and modality distribution
- **Synastry** -- two natal charts compared, inter-chart aspects, compatibility
  analysis
- **Composite chart** -- midpoint composite of two charts for relationship dynamics
- **Planetary returns** -- Solar, Lunar, Saturn, Jupiter, Venus, Mars, Mercury,
  Uranus, Neptune, Pluto returns for a given year or return number
- **Transits** -- current or future transits to the natal chart over a date range
- **Eclipse search** -- solar and lunar eclipses within a date range with type and
  magnitude

## Required Inputs

The user must provide for any chart calculation:

1. **Date of birth** -- day, month, year (the skill handles dates from 3000 BC to
   3000 AD)
2. **Time of birth** -- hour and minute, with timezone or UTC offset
3. **Place of birth** -- city/country or geographic coordinates (latitude, longitude)

For synastry and composites, birth data for both individuals is needed.
For planetary returns, also specify the return year or return number.
For transits, specify the transit start date and number of days.
For eclipses, specify a date range and whether to include solar, lunar, or both.

If the user provides incomplete data, ask for the missing fields before computing.

## House System

Default house system is Placidus. The user may request Whole Sign, Equal, Koch,
Regiomontanus, Campanus, Porphyry, or Morinus. State the house system used in the
output.

## Calculation Method

Use Swiss Ephemeris conventions for planetary longitudes. Include the standard
ten planets (Sun, Moon, Mercury, Venus, Mars, Jupiter, Saturn, Uranus, Neptune,
Pluto) plus the North Node (True Node), Chiron, Part of Fortune, and the prenatal
Syzygy point. Mark retrograde planets. Compute aspects with a default orb of 8
degrees: conjunction (0), opposition (180), trine (120), square (90), sextile (60),
quincunx (150), semi-sextile (30), semi-square (45), sesquiquadrate (135).

## Output Structure

Present results in a clear, structured format:

1. **Chart header** -- date, time, location, house system, Julian Day
2. **Planetary positions table** -- planet, sign, degree, house, retrograde flag
3. **House cusps table** -- house number, sign, degree
4. **Angles** -- ASC, MC, DSC, IC with sign and degree
5. **Aspect grid** -- planet pairs, aspect type, orb
6. **Element and modality balance** -- fire/earth/air/water counts; cardinal/fixed/mutable counts
7. **Interpretation** -- synthesized reading covering:
   - Sun, Moon, and Ascendant as the personality triad
   - Stelliums or empty houses worth noting
   - Dominant element and modality themes
   - Key aspect patterns (T-squares, grand trines, yods, grand crosses)
   - Planetary dignity and debility highlights
   - For synastry: compatibility dynamics, challenging and harmonious inter-aspects
   - For composites: relationship purpose and shared themes
   - For returns: the year's themes based on the return chart
   - For transits: upcoming activations and their timing

## Tone and Style

Write interpretations in a warm, insightful tone accessible to both beginners and
experienced astrologers. Use traditional astrological vocabulary but explain
technical terms when first introduced. Avoid deterministic language ("you will") in
favor of tendency language ("this placement tends to," "you may find").

## Limitations

This skill performs astrological calculations and interpretations. It does not
provide medical, legal, or financial advice. Astrology is presented as a symbolic
and reflective framework, not a predictive science.
