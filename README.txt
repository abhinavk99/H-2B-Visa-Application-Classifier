Relevant Column Names:

CASE_NUMBER (make into indices?)
CERTIFICATION_LENGTH (Difference between CERTIFICATION_END_DATE and CERTIFICATION_BEGIN_DATE)?
AGENT_POC_EMP_REP_BY_AGENT (boolean yes or no)
SOC_TITLE
NAICS_CODE (*A).
NBR_WORKERS_REQUESTED
FULL_TIME_POSITION
NATURE_OF_TEMPORARY_NEED
BASIC_NUMBER_OF_HOURS
BASIC_RATE_OF_PAY
SUPERVISE_OTHER_EMP
EDUCATION_LEVEL
TRAINING_REQUIRED, NUM_OF_MONTHS_TRAINING (but only ~72)
EMP_EXPERIENCE_REQD, EMP_EXP_NUM_MONTHS
WORKSITE_STATE
SWA_NAME (maybe as a boolean YES or NO).



Uncertain Column Names:

EMPLOYER_CITY
EMPLOYER_STATE
EMPLOYER_POSTAL_CODE (needs to be standardized to zipcode only)
LAWFIRM_NAME
AGENT_ATTORNEY_NAME (more bordering on NO for this one)
AGENT_ATTORNEY_CITY
AGENT_ATTORNEY_STATE
HOURLY_WORK_SCHEDULE_AM, HOURLY_WORK_SCHEDULE_PM
OVERTIME_RATE_FROM, OVERTIME_RATE_TO
PAY_RANGE_UNIT (since almost all "Hourly", only 3 as "Annual")
SUPERVISE_HOW_MANY (since only ~98 employees supervise others)
OTHER_EDUCATION (since almost all None)
MAJOR (again, very dirty data)
SECOND_DIPLOMA (only 1 yes), SECOND_DIPLOMA_MAJOR
NAME_REQUIRED_TRAINING (dirty)
WORKSITE_CITY, WORKSITE_COUNTY (dirty)
WORKSITE_POSTAL_CODE (also would need to be standardized), OTHER_WORKSITE_LOCATION
JOB_IDNUMBER, JOB_START_DATE, JOB_END_DATE (all related to SWA_NAME, leaning towards NO here as well).
FEIN (*B)


Irrelevant Column Names:

DECISION_DATE
VISA_CLASS (always H-2B)
SUBMIT_DATE_NEW
EMPLOYER_NAME
TRADE_NAME_DBA
EMPLOYER_ADDRESS_1
EMPLOYER_ADDRESS_2
EMPLOYER_COUNTRY (always USA)
EMPLOYER_PROVINCE
EMPLOYER_PHONE
EMPLOYER_PHONE_EXT
JOB_TITLE (superseded by SOC_TITLE)
SOC_CODE (same as SOC_TITLE)
NBR_CERTIFIED_WORKERS
WORKSITE_ADDRESS_1
WORKSITE_ADDRESS_2

Class Label:

CASE_STATUS



TODO: Listwise deletion?

Appendix:

*A: The North American Industry Classification System (NAICS) is used by the United States, Canada, and Mexico to classify businesses by industry. Each business is classified into a six-digit NAICS code number based on the majority of activity at the business. Seems to be different than SOC_TITLE.

*B: Federal Employer Identification Number, also known as an EIN. This unique, nine-digit number is used by the IRS to identify a business operating in the United States. Not certain of need, may cause overfitting?