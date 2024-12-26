# BPDA

## BPDA: Bidirectional Path and Data Flow Analysis-Driven Vulnerability Discovery in IoT Firmware

## Abstract
The rapid proliferation of Internet of Things (IoT) devices has revolutionized various sectors, from smart homes to industrial automation. However, this growth has also introduced significant security vulnerabilities. Unfortunately, current vulnerability detection methods suffer from inefficiencies and high false positive rates, making vulnerability analysis labor-intensive and time-consuming.

To alleviate above problems, we propose a bidirectional path and data flow analysis method to efficiently detect buffer overflow and command injection vulnerabilities in IoT devices. 
During the analysis of IoT vulnerabilities, we found that vulnerabilities arise in non-standard library sinks, and not all user inputs can reach each corresponding sink. Guided by these insights, we design a more comprehensive sinks identification algorithm and leverage backward data flow tracking to eliminate the non-vulnerable paths. After that, we execute forward taint analysis and generate final Proof of Concepts (PoCs). 
To evaluate the effectiveness of our method, we implement a prototype system, named BPDA. We evaluated it on 56 firmware samples from 7 major brands, comparing it with state-of-the-art methods (i.e., SaTC and Mango).
During our evaluation, we discovered 163 real vulnerabilities, including 34 0-day vulnerabilities, of which 32 have been confirmed by CVE/CNVD.
Besides, experiment results show that BPDA completed its analysis in just 6% of the time required by SaTC, and remarkably identified 21 vulnerabilities that SaTC and Mango had failed to detect. It also resolved the issue of Mango failing to analyze specific firmware.
These results have demonstrated the superiority of BPDA in terms of effectiveness and efficiency in IoT vulnerability detection.

## Core work
1. We have enhanced the identification and localization of implicit taint sources, thereby improving the coverage of taint source detection.
2. We proposed a novel method for identifying custom vulnerable functions by recognizing specific loop structure, which can detect more sink points than existing methods.
3. We introduced a static vulnerability discovering approach combined with forward and backward analysis, which improves analysis efficiency over existing tools.
4. We implemented a prototype system, BPDA, and evaluated it against the state-of-the-art solutions for finding taint-style vulnerabilities in firmware binaries.

## Time Line
2024.5.1: Some problems found in SaTc.  
2024.7.1: The code has been made and ready to make experiments.  
2024.8.31: Experiment has been achieved and ready to make the paper.  
2024.11.15：The paper has been made and submitted to S&P 2025.
