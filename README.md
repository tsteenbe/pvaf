# Public Values Assessment Tool

A browser-based assessment tool that implements the Public Values Assessment Framework (PVAF). Helps organisations evaluate the conformance of their application landscape with the [public values of Dutch education][waarden-wijzer]. Developed at [SIVON][sivon] as part of its [Open Source Program Office][sivon-ospo].

⚠️ **Warning: Prototype** - This project is a proof of concept under active development. Breaking changes and git force rebases will occur. Not recommended for production use.

## About

The Public Values Assessment Framework (PVAF) is a structured approach to assessing applications across three levels:

1. **Risk exposure**: how significant are the dependencies and associated risks?
2. **Mitigation capacity**: what measures are in place to manage those risks?
3. **Strategic importance**: how critical is the application to the organisation?

This tool implements the framework as an interactive, browser-based assessment. Based on 30 indicators across 8 dimensions, it calculates an public values score (1-10) per application. Results are presented in a summary table and an public values quadrant that provides immediate insight into which applications require attention.

> **Note:** The tool interface is currently in Dutch. An English version is planned for a future release.

## Features

- Fully client-side: runs entirely in the browser, no server required
- Data is stored locally in the browser (localStorage)
- Quick scan (9 indicators) and full assessment (22 indicators)
- Assess and compare multiple applications side by side
- Import/export via JSON and CSV
- Guided scoring with rubrics per indicator

## Usage

Open `index.html` in a browser of your choice.

### Getting started

1. Click "Nieuwe applicatie" (New application) and enter a name
2. Choose Quick scan or Full assessment
3. Score each indicator using the provided rubrics
4. View the results in the overview table and public values quadrant

### Data privacy

All data stays in your browser. Nothing is sent to a server. You can export assessments as JSON (for backup or transfer) or CSV (for further analysis).

## Dimensions

| Code | Dimension | Level |
|------|-----------|-------|
| A | Geopolitical and regulatory risk | Risk exposure |
| B | Vendor and supplychain dependency | Risk exposure |
| C | Technical resilience | Mitigation capacity |
| D | Organisational resilience | Mitigation capacity |
| E | Contractual resilience | Mitigation capacity |
| F | Organisational importance | Strategic importance |
| G | Data sensitivity | Strategic importance |
| H | Educational impact | Strategic importance |

## Scoring methodology

The public values score is calculated using the formula:

```
Score = Mitigation / (Risk exposure x Strategic importance)
```

The result is normalised to a 1-10 scale using a logarithmic function, where 1 indicates low conformance with public values (urgent) and 10 indicates high conformance (optimal).

## Technical details

- Single HTML file, no external dependencies
- Plain JavaScript, no frameworks or external libraries
- Responsive design

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

Based on the [digital autonomy assessment tool][daaf] from the [University of Utrecht][university-utrecht].

## Contact

- Thomas Steenbergen, OSPO Advisor at SIVON
- Email: t.steenbergen@sivon.nl

[daaf]: https://github.com/utrechtuniversity/digital-autonomy-assessment-tool/
[sivon]: https://www.sivon.nl
[sivon-ospo]: https://sivon.nl/ospo-voor-het-onderwijs/
[university-utrecht]: https://www.uu.nl/en
[waarden-wijzer]: https://www.kennisnet.nl/tools/waardenwijzer/
