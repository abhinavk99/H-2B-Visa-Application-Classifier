# CS363D-Final-Project

## Members
- Abhinav Kasamsetty
- Matthew Zhao
- Trent Phan
- Samarth Desai

## Class Label

CASE_STATUS

## Column Names

### Relevant Column Names

- AGENT_POC_EMP_REP_BY_AGENT
    - Convert to 1 or 0
- **[One hot encode]** SOC_CODE
    - remove dash, either pad with 00s (move over by 2)
    - https://www.bls.gov/soc/2018/major_groups.htm
- **[One hot encode]** NAICS_CODE (*A)
- NBR_WORKERS_REQUESTED
- FULL_TIME_POSITION
    - Convert to 1 or 0
    - consider dropping if effect is marginal, prove in notebook
- **[One hot encode]** NATURE_OF_TEMPORARY_NEED
- BASIC_NUMBER_OF_HOURS 
- BASIC_RATE_OF_PAY
    - remove dollar sign
- SUPERVISE_HOW_MANY
    - 0 if supervise none, otherwise use value, replace SUPERVISE_OTHER_EMP
- **[One hot encode]** EDUCATION_LEVEL
    - consider dropping if effect is marginal, blah blah 
- NUM_OF_MONTHS_TRAINING
    - input 0 if no training required
- EMP_EXP_NUM_MONTHS
    - similarly to ^, input 0 if no experience required
- **[One hot encode]** WORKSITE_STATE
    - consider dropping if effect is marginal, prove in notebook
- SWA_NAME
    - Convert to 1 or 0
- **[One hot encode]** AGENT_ATTORNEY_CITY
    - consider matching with WORKSITE_CITY as well?
- WORKSITE_CITY
    - in conjunction with ^
- AGENT_ATTORNEY_STATE
    - try matching with WORKSITE_STATE for 1 or 0
- HOURLY_WORK_SCHEDULE_AM, HOURLY_WORK_SCHEDULE_PM
    - feature engineer, start at PM vs AM)
- OVERTIME_RATE_FROM, OVERTIME_RATE_TO
    - categorize, check IF overtime or not

### Irrelevant Column Names

- CERTIFICATION_END_DATE, CERTIFICATION_BEGIN_DATE (only shows up for records with CASE_STATUS of Certified)
- VISA_CLASS (always H-2B)
- SUBMIT_DATE_NEW
- EMPLOYER_NAME
- TRADE_NAME_DBA
- EMPLOYER_ADDRESS_1
- EMPLOYER_ADDRESS_2
- EMPLOYER_COUNTRY (always USA)
- EMPLOYER_PROVINCE
- EMPLOYER_PHONE
- EMPLOYER_PHONE_EXT
- JOB_TITLE (superseded by SOC_TITLE)
- SOC_TITLE (same as SOC_CODE )
- NBR_CERTIFIED_WORKERS
- WORKSITE_ADDRESS_1
- WORKSITE_ADDRESS_2
- CASE_NUMBER
- TRAINING_REQUIRED (taken care of using NUM_OF_MONTHS_TRAINING)
- EMP_EXPERIENCE_REQD (EMP_EXP_NUM_MONTHS )
- EMPLOYER_CITY
- EMPLOYER_STATE
- EMPLOYER_POSTAL_CODE (needs to be standardized to zipcode only)
- AGENT_ATTORNEY_NAME
- LAWFIRM_NAME
- DECISION_DATE
- SUPERVISE_OTHER_EMP (replaced by SUPERVISE_HOW_MANY)
- PAY_RANGE_UNIT (since almost all "Hourly", only 3 as "Annual")
- OTHER_EDUCATION (since almost all None)
- MAJOR (again, very dirty data)
- NAME_REQUIRED_TRAINING (dirty)
- SECOND_DIPLOMA (only 1 yes), SECOND_DIPLOMA_MAJOR
- WORKSITE_COUNTY (dirty)
- WORKSITE_POSTAL_CODE (also would need to be standardized), OTHER_WORKSITE_LOCATION
- JOB_IDNUMBER, JOB_START_DATE, JOB_END_DATE (all related to SWA_NAME, leaning towards NO here as well).
- FEIN (*B)

## TODO

- Listwise deletion?

## Appendix

*A: The North American Industry Classification System (NAICS) is used by the United States, Canada, and Mexico to classify businesses by industry. Each business is classified into a six-digit NAICS code number based on the majority of activity at the business. Seems to be different than SOC_TITLE.

*B: Federal Employer Identification Number, also known as an EIN. This unique, nine-digit number is used by the IRS to identify a business operating in the United States. Not certain of need, may cause overfitting?
