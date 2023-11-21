# Medicare_Geographic_Insights


## Database setup on Postgres DB

Data set links, downloaded 2021 to 2021

**medicare-part-d-prescribers-by-provider:** https://data.cms.gov/provider-summary-by-type-of-service/medicare-part-d-prescribers/medicare-part-d-prescribers-by-provider

**medicare-part-d-prescribers-by-geography-and-drug:** https://data.cms.gov/provider-summary-by-type-of-service/medicare-part-d-prescribers/medicare-part-d-prescribers-by-geography-and-drug

**medicare-part-d-prescribers-by-provider-and-drug:** https://data.cms.gov/provider-summary-by-type-of-service/medicare-part-d-prescribers/medicare-part-d-prescribers-by-provider-and-drug

Create a new database in Postgres, called medical, then

CREATE TABLE Public."geo" (
  Prscrbr_Geo_Lvl TEXT,
  Prscrbr_Geo_Cd TEXT,
  Prscrbr_Geo_Desc TEXT,
  Brnd_Name TEXT,
  Gnrc_Name TEXT,
  Tot_Prscrbrs NUMERIC,
  Tot_Clms NUMERIC,
  Tot_30day_Fills NUMERIC,
  Tot_Drug_Cst NUMERIC,
  Tot_Benes NUMERIC,
  GE65_Sprsn_Flag TEXT,  -- Changed BOOLEAN to TEXT temporarily
  GE65_Tot_Clms NUMERIC,
  GE65_Tot_30day_Fills NUMERIC,
  GE65_Tot_Drug_Cst NUMERIC,
  GE65_Bene_Sprsn_Flag TEXT,  -- Changed BOOLEAN to TEXT temporarily
  GE65_Tot_Benes NUMERIC,
  LIS_Bene_Cst_Shr NUMERIC,
  NonLIS_Bene_Cst_Shr NUMERIC,
  Opioid_Drug_Flag TEXT,  -- Changed BOOLEAN to TEXT temporarily
  Opioid_LA_Drug_Flag TEXT,  -- Changed BOOLEAN to TEXT temporarily
  Antbtc_Drug_Flag TEXT,  -- Changed BOOLEAN to TEXT temporarily
  Antpsyct_Drug_Flag TEXT   -- Changed BOOLEAN to TEXT temporarily
);

COPY Public."geo" FROM 'C:\Users\adity\Desktop\SJSU_work\Sem3\Big Data\Project\Dataset\Geography\Geo.csv' DELIMITER ',' CSV HEADER ;

select * from Public."geo";

