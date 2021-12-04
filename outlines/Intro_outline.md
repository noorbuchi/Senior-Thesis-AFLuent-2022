**Thesis Title: AFLuent: An Implementation and Evaluation of Automated Fault Localization Tool in Python**

**Introduction Outline**

# Introduction

## Overview and Background

- What is automated fault localization?
  - Goal: simplify the debugging process
  - Point the developer to where to start looking for faults
  - Analyse the source code using different indicators
    - syntax trees
    - code coverage
    - other factors
  - Different implementation of existing AFL tools
    - Separate standalone tool
    - Integrated in text editors or testing frameworks

- Overview of test coverage-based fault localization
  - An automated fault localization technique that uses test coverage information
  - Requires per-test statement coverage to make predictions regarding the
    location of faults
  - Uses a variety of equations that calculate suspiciousness scores for every statement
  - Ranks statements from most to least suspicious

## Project Aims

- Implement a test coverage-based fault localization tool
  - Supports using a variety of equations to calculate coverage
    - Ochiai
    - D-Star
    - Tarantula
    - Others can be added and explained easily
  - Easily installable and well documented
    - Published on Python Project Index
    - Integrated with Pytest as a plugin
    - Thorough documentation that explains command line arguments and possible output
- Evaluate the performance and accuracy of the tool
  - Test suite collection from open source projects
    - Projects written in Python and use Pytest
    - A wide range of criticality scores are represented in the picked projects
      - Test that AFLuent can function well on both large and small code bases
  - Mutation testing and data collection
    - Purposefully introduce errors in the code
    - Run test suites and collect data regarding the following aspects:
      - The statement suspiciousness ranking produced by AFLuent using each equation
      - Is the faulty statement included in the top 5 result produced by AFLuent
      - Time taken by AFLuent to parse through coverage information, calculate
        suspicousness scores, and sort the ranks
  - Analysis of the results
    - Compare equations based on their accuracy in ranking faults
    - Create plots and figures that visualize and compare the data
    - Identify the strengths and weaknesses of each equation depending on it's performance
    - Identify performance bottlenecks if they exist, their cause, and how to
      potentially resolve them

## Motivation

- Lack of Pytest plugins that perform coverage based fault localization
- Need for a tool catered for novice developers
