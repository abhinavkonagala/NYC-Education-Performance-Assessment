# NYC-Education-Performance-Assessment
Strategic analysis of NYC public school SAT performance data, identifying top-performing institutions and resource allocation opportunities for education stakeholders. Built with Python, pandas, and statistical analysis.

## Background & Objectives

**Client:** NYC Department of Education Leadership Team  
**Stakeholders:** School District Superintendents, Resource Allocation Committee, Parent Advisory Board  
**Business Challenge:** With 400+ public high schools serving 1.1M students, education leaders need data-driven insights to identify excellence benchmarks, optimize resource allocation, and address performance equity gaps across NYC's five boroughs.

### Key Research Questions:
- Which schools demonstrate math excellence suitable for STEM pathway recommendations?
- What are the top-performing institutions for overall academic achievement benchmarking?
- Where do we see the greatest performance variability requiring targeted intervention?

## Executive Summary

### Performance Landscape Overview
- **Math Excellence Threshold:** Only **10 schools** (2.7% of total) achieved 640+ math scores (80% of maximum 800-point scale)
- **Academic Performance Spread:** Top 10 schools show **255-point gap** between highest (2144) and 10th-place (1889) total SAT scores  
- **Borough Equity Gap:** **Manhattan** exhibits **230.29 standard deviation** in performance—indicating significant performance variability
- **Resource Impact Opportunity:** **89 schools** in high-variability borough present targeted intervention opportunities

### Strategic Impact Metrics
| Metric | Value | Business Implication |
|--------|-------|---------------------|
| Schools Meeting Math Excellence | 10 schools | Elite STEM pathway capacity |
| Performance Variability Range | 230.29 std dev | Resource allocation priority |
| Geographic Coverage Gap | Manhattan outlier | Equity intervention target |

## Data Structure & Methodology

### Dataset Overview
**Source:** NYC Department of Education SAT Performance Data  
**Scope:** 375 public high schools across 5 boroughs  
**Time Period:** Single academic year snapshot  

### Data Schema
| Column | Data Type | Description | Business Relevance |
|--------|-----------|-------------|-------------------|
| school_name | String | Official school identifier | Institutional tracking |
| borough | String | Geographic location (5 boroughs) | Resource allocation zones |
| building_code | String | Facility identifier | Infrastructure planning |
| average_math | Integer | Mean math SAT score (317-754 range) | STEM readiness indicator |
| average_reading | Integer | Mean reading SAT score (302-697 range) | Literacy assessment |
| average_writing | Integer | Mean writing SAT score (284-693 range) | Communication skills |
| percent_tested | Float | Student participation rate (18.5-100%) | Data reliability metric |

### Key Data Quality Metrics
- **Coverage:** 375 schools with complete SAT score data
- **Participation:** 355 schools (94.7%) with testing rate information
- **Score Ranges:** Math (317-754), Reading (302-697), Writing (284-693)
- **Geographic Distribution:** All 5 NYC boroughs represented

## Insight Deep Dive

### 1. **STEM Readiness Assessment: Math Excellence Benchmark**
**Context:** Mathematics proficiency at 640+ (80% of maximum) indicates college STEM readiness  
**Finding:** **10 schools qualify** as high-performing math institutions
- **Top Performer:** Stuyvesant High School - **754 average** (18% above threshold)
- **Geographic Distribution:** Specialized high schools across all boroughs with concentration in technical programs
- **Capacity Analysis:** These schools represent the top 2.7% of NYC's 375 public high schools

**Statistical Significance:** Only 2.7% achievement rate demonstrates exclusive nature of math excellence

### 2. **Academic Excellence Hierarchy: Top-Tier Institution Analysis**  
**Context:** Combined SAT scores identify comprehensive academic strength for flagship recognition
**Finding:** **255-point performance range** among top 10 schools reveals tiered excellence levels
- **Tier 1 (2000+ total):** 5 schools - Premium academic destinations (Stuyvesant: 2144, Bronx Science: 2041, etc.)
- **Tier 2 (1900-1999):** 5 schools - Strong comprehensive programs  
- **Achievement Gap:** **255 points** separate #1 (Stuyvesant: 2144) from #10 position (1889)

**Performance Distribution:** 12% performance variance between top-tier schools indicates distinct excellence levels

### 3. **Geographic Performance Equity: Resource Allocation Priority**
**Context:** High standard deviation indicates inconsistent school quality within borough boundaries
**Finding:** **Manhattan shows 230.29 standard deviation** - highest variability across NYC
- **Schools Affected:** **89 institutions** serving diverse student populations
- **Performance Range:** Wide variability from elite specialized schools to underperforming institutions
- **Average Performance:** **1340.13 total SAT** with significant dispersion around the mean

**Equity Impact:** 17.2% coefficient of variation indicates substantial opportunity gaps within single borough

## Methodology & Technical Implementation

### Data Processing Pipeline
```python
# Excellence threshold calculation (80% of 800-point maximum)
math_threshold = 800 * 0.80  # 640 points
best_math_schools = schools[schools['average_math'] >= math_threshold]

# Comprehensive performance ranking
schools['total_SAT'] = schools[['average_math', 'average_reading', 'average_writing']].sum(axis=1)
top_10_schools = schools.nlargest(10, 'total_SAT')

# Geographic variability analysis  
borough_analysis = schools.groupby('borough')['total_SAT'].agg(['count', 'mean', 'std']).round(2)
```

### Key Performance Indicators (KPIs)
- **Math Excellence Rate:** % schools ≥640 math score (2.7% baseline)
- **Academic Tier Distribution:** Schools by total SAT ranges
- **Geographic Equity Index:** Borough standard deviation rankings

## Strategic Recommendations

### 1. **STEM Pipeline Development** (Based on Math Excellence Analysis)
**Insight Driver:** Only 10 schools (2.7%) meet STEM readiness threshold
- **Action:** Designate 10 high-performing math schools as "STEM Centers of Excellence"
- **Investment:** $500K per school for advanced STEM programming and equipment
- **Timeline:** 6-month setup, 18-month implementation
- **Expected ROI:** 25% increase in STEM college enrollment from target schools
- **Success Metric:** Expand STEM-ready schools from 10 to 15 by year 2

### 2. **Academic Benchmarking Program** (Based on Top 10 Performance Gap)
**Insight Driver:** 255-point gap between top performers indicates knowledge transfer opportunity
- **Action:** Establish peer learning network among top-tier institutions
- **Investment:** $200K platform development + $50K annual operations
- **Timeline:** 3-month platform build, ongoing collaboration
- **Expected ROI:** Reduce performance gap from 255 to 200 points within 2 years
- **Success Metric:** 90% participation rate among top 20 schools

### 3. **Equity Intervention Initiative** (Based on Manhattan Variability Analysis)
**Insight Driver:** 230.29 standard deviation indicates 89 schools with inconsistent performance
- **Action:** Deploy targeted support to underperforming schools in Manhattan's 89-school network
- **Investment:** $2.5M intervention fund focused on closing performance gaps
- **Timeline:** 6-month assessment, 18-month intervention, 6-month evaluation
- **Expected ROI:** Reduce Manhattan standard deviation from 230.29 to 180.00
- **Success Metric:** 40 schools show 10%+ SAT improvement within 24 months

## Data Limitations & Assumptions

### Key Caveats
- **Sample Bias:** Analysis based on schools with complete SAT data only (excludes 20 schools with missing scores)
- **Temporal Scope:** Single-year snapshot may not reflect multi-year performance trends
- **Demographic Controls:** Results not adjusted for socioeconomic or demographic variables
- **Score Inflation:** SAT redesign impacts may affect historical comparisons

### Analytical Assumptions
- 640+ math score threshold represents meaningful STEM readiness benchmark
- Combined SAT scores provide valid proxy for comprehensive academic performance  
- Standard deviation effectively measures within-borough performance equity
- Geographic boundaries (boroughs) represent meaningful policy/resource allocation units

## Business Impact Potential

**Immediate Actions (0-6 months):**
- STEM Center designation and resource allocation: **$5M**
- Manhattan performance assessment and intervention planning: **$500K**
- Academic benchmarking platform development: **$200K**

**Medium-term Outcomes (6-18 months):**
- **15% improvement** in Manhattan borough performance consistency
- **50 additional students** meeting STEM readiness threshold annually
- **200-point reduction** in top-tier performance gap

**Long-term Strategic Value (18+ months):**
- **$10M saved** through optimized resource allocation to high-impact schools
- **20% increase** in college-ready graduates from intervention schools
- **5 additional schools** achieving math excellence threshold

## Implementation Timeline

### Phase 1: Foundation (Months 1-6)
- **Month 1-2:** STEM Center designation and stakeholder alignment
- **Month 3-4:** Intervention school selection and baseline assessment
- **Month 5-6:** Platform development and pilot program launch

### Phase 2: Execution (Months 7-18)
- **Month 7-12:** Full program implementation across all initiatives
- **Month 13-18:** Mid-program assessment and strategy refinement

### Phase 3: Evaluation (Months 19-24)
- **Month 19-21:** Impact assessment and ROI analysis
- **Month 22-24:** Program optimization and expansion planning

## Project Lead Contact

**[Abhinav Konagala] - Data Analyst**  
[abhinavkonagala@duck.com]  
[LinkedIn Profile]([https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/abhinav-konagala/))

