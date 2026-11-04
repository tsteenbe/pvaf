# Public Values Check

A browser-based tool for the Public Values Check (PVC; Dutch: Publieke waardencheck). Helps school boards assess the extent to which their applications align with the [public values of Dutch education][waarden-wijzer]. Developed at [SIVON][sivon] as part of its [Open Source Program Office][sivon-ospo].

⚠️ **Final test phase** - This project is in its final test phase. Questions, scores and features may still change. Git force rebases may still occur.

## About

The questionnaire is based on the [DAAF tool][daaf] from the [Utrecht University][university-utrecht] and materials from [SURF][surf] and [SIVON][sivon]. It contains 34 questions across 5 dimensions. Each question has one of three question types:

1. **Strategic importance**: how much is at stake for the school?
2. **Risk**: what is put under pressure?
3. **Mitigation**: how well is the risk controlled?

For every question, score 1 is the least favourable and score 5 the most favourable situation. Based on the answers, the tool calculates a public values score (1-10) per application. Results are presented in a summary table and a public values quadrant that provides immediate insight into which applications require attention.

## Features

- Fully client-side: runs entirely in the browser, no server required
- Data is stored locally in the browser (localStorage)
- Quick scan (9 questions) and full assessment (34 questions)
- Overview dashboard with key figures, filters, a bubble quadrant, lowest scores, data quality and overviews per supplier and organisational unit
- Possible improvements per application and "where is the most to gain?" across applications
- Report for management (print or save as PDF)
- Organisational unit and supplier per application, with shared pick lists that can be renamed and merged
- Organisation profiles with weights and own question texts, shareable as a file
- Assessing together: import several JSON files at once with a preview that recognises newer versions and duplicates
- Import/export via JSON and CSV
- Guided scoring with rubrics per question, keyboard scoring and a radar chart per application
- Adjustable question weights per profile and per application
- Trash with restore, and bulk editing in the overview table
- Sample data of a fictitious school board to explore the tool
- Export reminder to prevent data loss
- Changelog viewer for version history
- Multi-language interface: Danish, Dutch, English, French, German, Italian and Spanish

## Usage

Open `index.html` in a browser of your choice.

### Getting started

1. Click "Add Application" and enter a name
2. Choose Quick scan or Full assessment
3. Answer each question using the provided rubrics
4. View the results in the overview table and public values quadrant

### Data privacy

All data stays in your browser. Nothing is sent to a server. You can export assessments as JSON (for backup or transfer) or CSV (for further analysis).

## Dimensions

| Code | Dimension | Question types |
|------|-----------|----------------|
| A | Use and strategic importance | Strategic importance |
| B | Autonomy | Risk, Mitigation |
| C | Humanity | Risk |
| D | Justice | Risk, Mitigation |
| E | School control and resilience | Mitigation |

## Scoring methodology

Answer scores are converted by question type: strategic importance and risk as `6 - answer`, mitigation as the answer itself. For each of the three axes, the weighted average is taken per dimension, followed by the average across dimensions. The public values score is then calculated using the formula:

```
Score = Mitigation / (Risk exposure x Strategic importance)
```

The result is normalised to a 1-10 scale using a logarithmic function, where 1 indicates the most urgent risks to public values and 10 the least urgent. A high score does not by itself mean that an application aligns with all public values.

The quadrant places each application on risk pressure (risk exposure x strategic importance, 1-25, boundary 9) against mitigation strength (1-5, boundary 3).

Unanswered questions do not count. The score appears once each dimension involved has at least one answered question of the right type. The quick scan only counts dimensions that have questions in it, so mitigation there averages Autonomy and Justice, without School control and resilience.

## Technical details

- Single HTML file, no external dependencies
- Plain JavaScript, no frameworks or external libraries
- Responsive design

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

Based on the [digital autonomy assessment tool][daaf] from the [Utrecht University][university-utrecht].

## Contact

- Thomas Steenbergen, OSPO Advisor at SIVON
- Email: t.steenbergen@sivon.nl

[daaf]: https://github.com/utrechtuniversity/digital-autonomy-assessment-tool/
[sivon]: https://www.sivon.nl
[sivon-ospo]: https://sivon.nl/ospo-voor-het-onderwijs/
[surf]: https://www.surf.nl
[university-utrecht]: https://www.uu.nl/en
[waarden-wijzer]: https://www.kennisnet.nl/tools/waardenwijzer/
