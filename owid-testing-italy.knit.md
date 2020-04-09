---
title: "Checklist for COVID-19 Testing Data: Italy"
subtitle: "Answers for Our World in Data"
author: "Pietro Monticone & Riccardo Valperga"
date: "2020-04-09 | Turin University"
output:
 prettydoc::html_pretty:
    theme: cayman
    highlight: github
    toc: true
fontsize: 11pt
bibliography: bibliography.bibtex # https://doi2bib.org
biblio-style: apalike
link-citations: yes
---


1. **Is there any data?**

Yes. 

* [Protezione Civile Github repository](https://github.com/pcm-dpc/COVID-19)
* [Istituto Superiore di Sanità](https://www.epicentro.iss.it/coronavirus/).

2. **Do numbers refer to ‘performed tests’ or ‘individuals tested’?**

In Italy "swabs" ("tamponi") refers to ["performed tests"](https://github.com/pcm-dpc/COVID-19): the same person is tested multiple times (even 5/6 times). In particular patients who are recovered from COVID-19 are tested at least 3 times (1 positive and 2 negative).

It should be taken into account the fact that "recovered" ("guariti") in the official data refers not only to those actually recovered (who tested negative twice), but to all those discharged from hospital.

* [I “guariti” annunciati dalla Protezione Civile ogni giorno non sono tutti guariti, *Il Post*](https://www.ilpost.it/2020/04/02/guariti-coronavirus-protezione-civile/)
* [GIMBE & YouTrend study](https://www.sanita24.ilsole24ore.com/art/aziende-e-regioni/2020-04-02/coronavirus-cartabellotta-fondazione-gimbe-sovrastimato-numero-guariti-rischi-serve-chiarezza-orientare-scelte-103855.php?uuid=ADkV6eH)

3. **Are negative results included? Are pending results included?**

The total number of tests performed includes negative test results, but it  doesn't include the number of tests that are pending results.

* [Protezione Civile Github repository](https://github.com/pcm-dpc/COVID-19) 

4. **Do the figures include all tests conducted in the country, or only some?** 
Figures reported by Italy include all tests conducted in all working laboratories of the country. 

* [Ministerial testing protocol, 27-02](http://www.trovanorme.salute.gov.it/norme/renderNormsanPdf?anno=2020&codLeg=73444&parte=1%20&serie=null)
* [Ministerial testing protocol, 09-03](https://www.fnopi.it/wp-content/uploads/2020/03/Circolare_9_marzo_2020.pdf)
* [Ministerial testing protocol, 03-04](http://www.trovanorme.salute.gov.it/norme/renderNormsanPdf?anno=2020&codLeg=73799&parte=1%20&serie=null)

5. **Are all regions and laboratories within a country submitting data on the same basis?**

Yes, all Italian regions and labs submit testing data on the same basis (i.e. tests performed).

* [Protezione Civile Github repository](https://github.com/pcm-dpc/COVID-19).

6. **What period do the published figures refer to?**

The figures published at a given date attempt to include all tests conducted up to that date, but significant and variable delays are present: both from symptom onset to lab confirmation ($\Delta T_{symptoms}$) and from lab confirmation to official database update ($\Delta T_{lab}$). 

* [Istituto Superiore di Sanità, Bollettino Sorveglianza Integrata](https://www.epicentro.iss.it/coronavirus/bollettino/Bollettino-sorveglianza-integrata-COVID-19_6-aprile-2020.pdf). 

For example, in [Lombardy](https://arxiv.org/ftp/arxiv/papers/2003/2003.09320.pdf) $\Delta T_{symptoms}= 7.3 \text{ days } (1,20)_{95\% \text{CI}}$ and $\Delta T_{lab} = 3.6 \text{ days } (1,10)_{95\% \text{CI}}$

7. **Are there any issues that affect the comparability of the data over time?**

There have been significant changes over time in the ministerial testing protocol.

* [Istituto Superiore di Sanità, Infographic](https://www.epicentro.iss.it/en/coronavirus/bollettino/Infografica_8aprile%20ENG.pdf)
* [Ministerial testing protocol, 27-02](http://www.trovanorme.salute.gov.it/norme/renderNormsanPdf?anno=2020&codLeg=73444&parte=1%20&serie=null)
* [Ministerial testing protocol, 09-03](https://www.fnopi.it/wp-content/uploads/2020/03/Circolare_9_marzo_2020.pdf)
* [Ministerial testing protocol, 03-04](http://www.trovanorme.salute.gov.it/norme/renderNormsanPdf?anno=2020&codLeg=73799&parte=1%20&serie=null)
* [The early phase of the COVID-19 outbreak in Lombardy, Italy, *arXiv*](https://arxiv.org/ftp/arxiv/papers/2003/2003.09320.pdf)

8. **What are the typical testing practices in the country?**

Since not all Italian regions follow the ministerial protocol of the central government there is significant regional heterogeneity in testing practices (e.g. Veneto and Lombardia adopted two completely different testing strategies). 

* [Quante sono davvero le persone contagiate?, *Il Post*](https://www.ilpost.it/2020/03/31/contagi-coronavirus-imperial-college-london/)
* [La Lombardia non fa tutti i tamponi che dovrebbe, *Il Post*](https://www.ilpost.it/2020/03/27/tamponi-lombardia-fontana-coronavirus/)
* [La differenza tra il numero di tamponi e il numero delle persone testate, *Il Post*](https://www.ilpost.it/2020/03/26/coronavirus-tamponi-eseguiti-persone-testate/)

Up to 20-03 we could identify 3 classes of testing practices described by the following pseudocode:

Consider two patients $A$ and $B$ living in the same house in the region $R \in \{X, Y, Z\}$ such that

* $A$ has no symptoms;
* $B$ suffers from symptoms compatible with **COVID-19**;
* $X$ respects the [ministerial document](https://www.fnopi.it/wp-content/uploads/2020/03/Circolare_9_marzo_2020.pdf) dated 9-03 (e.g. Piedmont);
* $Y$ makes more tests than those recommended by the [ministerial document](https://www.fnopi.it/wp-content/uploads/2020/03/Circolare_9_marzo_2020.pdf) dated 9-03 (e.g. Veneto)
* $Z$ makes fewer tests than those recommended by the [ministerial document](https://www.fnopi.it/wp-content/uploads/2020/03/Circolare_9_marzo_2020.pdf) dated 9-03 (e.g. Lombardy). 

If $A$ and $B$ live in $X \Rightarrow$

1. ASL sends an ambulance team of health-workers who perform the test on him, but not to $A$ as he does not show any symptoms.
2. $A$ ends up in isolation, since in contact with a person who is definitely infected.

If $A$ and $B$ live in $Y \Rightarrow$

1. Test to $B$ 
2. Test to $A$ 
3. Test to the first and second neighbors (e.g. parents, friends, condominiums) in the hope of finding and isolating all the positives.

If $A$ and $B$ live in $Y \Rightarrow$

1. No test to $B$ (unless $B$ needs hospital care)
2. No test to $A$
3. No isolation from $A$ because there is no evidence that $B$ is positive despite its symptoms.

9. **Might any of the information above be lost in translation?**

The most important documents are translated in English by the official sources ( [Protezione Civile](https://github.com/pcm-dpc/COVID-19), [Istituto Superiore di Sanità](https://www.epicentro.iss.it/coronavirus/), [Ministero della Salute](http://www.salute.gov.it/portale/home.html) ). 
