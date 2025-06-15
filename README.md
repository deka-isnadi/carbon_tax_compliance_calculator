# carbon_tax_compliance_calculator

## Querry 1: Carbon Tax Compliance Check 
### Description 
#### Goal: It checks wether Emission producen by Company exceed limit of Carbon Tax (500 Tonnes CO2)
##### Concept:  if-else, Pandas for reading CSV
##### Output : Tax Status (obligated or not ) for every company

## CODE:
```
# Import Pandas to manage CSV data
import pandas as pd
# according to Government Regulation, Emission >50 Tonnes --> pay carbon tax
# read CSV File 

df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')
limit = 50

# iteration every line in dataframe to check emission 
for index, row in df.iterrows():
    #the value of emission from Emisi_2024 Column
    emission = row['Emisi_2024'] 
    company = row['Nama_Perusahaan']
    # Check if emission  exceed limit by government regulation
    if emission > limit:
        print(f"{company} was OBLIGATED to Carbon Tax because of the {emission} Tonnes Emission of Carbon")
    else:
        print(f"{company} was FREE from Carbon Tax because of the {emission} Tonnes Emisson of Carbon")
```
### run output
```
PT_Textilindo was OBLIGATED to Carbon Tax because of the 62.5 Tonnes Emission of Carbon
PT_Semindo was FREE from Carbon Tax because of the 45.8 Tonnes Emisson of Carbon
PT_EnergiJaya was OBLIGATED to Carbon Tax because of the 78.2 Tonnes Emission of Carbon
PT_Pulpindo was OBLIGATED to Carbon Tax because of the 55.0 Tonnes Emission of Carbon
PT_AgroMakmur was FREE from Carbon Tax because of the 42.3 Tonnes Emisson of Carbon
PT_BajaSentosa was OBLIGATED to Carbon Tax because of the 68.7 Tonnes Emission of Carbon
PT_KimiaFarindo was FREE from Carbon Tax because of the 49.1 Tonnes Emisson of Carbon
PT_MiningCo was OBLIGATED to Carbon Tax because of the 82.4 Tonnes Emission of Carbon
PT_PetroJaya was OBLIGATED to Carbon Tax because of the 60.9 Tonnes Emission of Carbon
PT_SinarLogam was OBLIGATED to Carbon Tax because of the 53.6 Tonnes Emission of Carbon
PT_IndoPlastik was FREE from Carbon Tax because of the 47.2 Tonnes Emisson of Carbon
PT_BumiEnergi was OBLIGATED to Carbon Tax because of the 75.3 Tonnes Emission of Carbon
PT_TextilMakmur was OBLIGATED to Carbon Tax because of the 64.8 Tonnes Emission of Carbon
PT_SemenBerkah was FREE from Carbon Tax because of the 43.5 Tonnes Emisson of Carbon
PT_KertasJaya was OBLIGATED to Carbon Tax because of the 58.9 Tonnes Emission of Carbon
PT_AgroSentosa was FREE from Carbon Tax because of the 41.7 Tonnes Emisson of Carbon
PT_BajaIndo was OBLIGATED to Carbon Tax because of the 70.2 Tonnes Emission of Carbon
PT_KimiaJaya was FREE from Carbon Tax because of the 48.4 Tonnes Emisson of Carbon
PT_TambangMakmur was OBLIGATED to Carbon Tax because of the 80.6 Tonnes Emission of Carbon
PT_PetroMakmur was OBLIGATED to Carbon Tax because of the 63.1 Tonnes Emission of Carbon
PT_LogamBerkah was OBLIGATED to Carbon Tax because of the 54.3 Tonnes Emission of Carbon
PT_PlastikJaya was FREE from Carbon Tax because of the 46.9 Tonnes Emisson of Carbon
PT_EnergiMakmur was OBLIGATED to Carbon Tax because of the 77.8 Tonnes Emission of Carbon
PT_TextilBerkah was OBLIGATED to Carbon Tax because of the 66.4 Tonnes Emission of Carbon
PT_SemenJaya was FREE from Carbon Tax because of the 44.2 Tonnes Emisson of Carbon
...
PT_AgroBerkah was FREE from Carbon Tax because of the 40.8 Tonnes Emisson of Carbon
PT_BajaMakmur was OBLIGATED to Carbon Tax because of the 72.1 Tonnes Emission of Carbon
PT_KimiaMakmur was OBLIGATED to Carbon Tax because of the 50.3 Tonnes Emission of Carbon
PT_TambangJaya was OBLIGATED to Carbon Tax because of the 85.7 Tonnes Emission of Carbon
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
```

# Query 2 : Calculate the Carbon Tax
## Goal:  calculate Tax Carbon for each company in CSV file based on the carbon produced in 2024
### Concept : if-else
#### output : Value of Carbon Tax for each Company

##Code :
```
import pandas as pd
df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')

# According to Goverment Regulation
limit = 50
tariff = 20000

# iteration every line in dataframe to check emission 
for index, row in df.iterrows():
    #the value of emission from Emisi_2024 Column
    emission = row['Emisi_2024'] 
    company = row['Nama_Perusahaan']
    # Check if emission  exceed limit by government regulation
    if emission > limit:
        print(f"{company} was OBLIGATED to Carbon Tax of Rp {(emission - limit) * tariff} because of {emission} Tonnes Emission of Carbon")
    else:
        print(f"{company} was FREE from Carbon Tax because of the {emission} Tonnes Emisson of Carbon")
```
## RUN output
```
PT_Textilindo was OBLIGATED to Carbon Tax of Rp 250000.0 because of 62.5 Tonnes Emission of Carbon
PT_Semindo was FREE from Carbon Tax because of the 45.8 Tonnes Emisson of Carbon
PT_EnergiJaya was OBLIGATED to Carbon Tax of Rp 564000.0 because of 78.2 Tonnes Emission of Carbon
PT_Pulpindo was OBLIGATED to Carbon Tax of Rp 100000.0 because of 55.0 Tonnes Emission of Carbon
PT_AgroMakmur was FREE from Carbon Tax because of the 42.3 Tonnes Emisson of Carbon
PT_BajaSentosa was OBLIGATED to Carbon Tax of Rp 374000.00000000006 because of 68.7 Tonnes Emission of Carbon
PT_KimiaFarindo was FREE from Carbon Tax because of the 49.1 Tonnes Emisson of Carbon
PT_MiningCo was OBLIGATED to Carbon Tax of Rp 648000.0000000001 because of 82.4 Tonnes Emission of Carbon
PT_PetroJaya was OBLIGATED to Carbon Tax of Rp 217999.99999999997 because of 60.9 Tonnes Emission of Carbon
PT_SinarLogam was OBLIGATED to Carbon Tax of Rp 72000.00000000003 because of 53.6 Tonnes Emission of Carbon
PT_IndoPlastik was FREE from Carbon Tax because of the 47.2 Tonnes Emisson of Carbon
PT_BumiEnergi was OBLIGATED to Carbon Tax of Rp 505999.99999999994 because of 75.3 Tonnes Emission of Carbon
PT_TextilMakmur was OBLIGATED to Carbon Tax of Rp 295999.99999999994 because of 64.8 Tonnes Emission of Carbon
PT_SemenBerkah was FREE from Carbon Tax because of the 43.5 Tonnes Emisson of Carbon
PT_KertasJaya was OBLIGATED to Carbon Tax of Rp 177999.99999999997 because of 58.9 Tonnes Emission of Carbon
PT_AgroSentosa was FREE from Carbon Tax because of the 41.7 Tonnes Emisson of Carbon
PT_BajaIndo was OBLIGATED to Carbon Tax of Rp 404000.00000000006 because of 70.2 Tonnes Emission of Carbon
PT_KimiaJaya was FREE from Carbon Tax because of the 48.4 Tonnes Emisson of Carbon
PT_TambangMakmur was OBLIGATED to Carbon Tax of Rp 611999.9999999999 because of 80.6 Tonnes Emission of Carbon
PT_PetroMakmur was OBLIGATED to Carbon Tax of Rp 262000.00000000003 because of 63.1 Tonnes Emission of Carbon
PT_LogamBerkah was OBLIGATED to Carbon Tax of Rp 85999.99999999994 because of 54.3 Tonnes Emission of Carbon
PT_PlastikJaya was FREE from Carbon Tax because of the 46.9 Tonnes Emisson of Carbon
PT_EnergiMakmur was OBLIGATED to Carbon Tax of Rp 556000.0 because of 77.8 Tonnes Emission of Carbon
PT_TextilBerkah was OBLIGATED to Carbon Tax of Rp 328000.0000000001 because of 66.4 Tonnes Emission of Carbon
PT_SemenJaya was FREE from Carbon Tax because of the 44.2 Tonnes Emisson of Carbon
...
PT_AgroBerkah was FREE from Carbon Tax because of the 40.8 Tonnes Emisson of Carbon
PT_BajaMakmur was OBLIGATED to Carbon Tax of Rp 441999.9999999999 because of 72.1 Tonnes Emission of Carbon
PT_KimiaMakmur was OBLIGATED to Carbon Tax of Rp 5999.999999999944 because of 50.3 Tonnes Emission of Carbon
PT_TambangJaya was OBLIGATED to Carbon Tax of Rp 714000.0 because of 85.7 Tonnes Emission of Carbon
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
```

# Query 3 : Save data into list
## output : List of company emission 
## Code:
```
import pandas as pd
df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')
# Initiating empty list to save the list
emission_list =[]

# According to Goverment Regulation
limit = 50
tariff = 20000

# iteration every line in dataframe to check emission 
for index, row in df.iterrows():
    #the value of emission from Emisi_2024 Column
    emission = row['Emisi_2024'] 
    #input value of emission_list with "append" command
    emission_list.append(emission)
#print emission list
print("Company emission Data : ", emission_list)
```
## RUN output
```
Company emission Data :  [62.5, 45.8, 78.2, 55.0, 42.3, 68.7, 49.1, 82.4, 60.9, 53.6, 47.2, 75.3, 64.8, 43.5, 58.9, 41.7, 70.2, 48.4, 80.6, 63.1, 54.3, 46.9, 77.8, 66.4, 44.2, 57.5, 40.8, 72.1, 50.3, 85.7]
```

# Query 4: Emission Compliance Analysis list (LOOKUP in Spreedsheet)
## Goal : Company Emission Compliance Check
### Output : Carbon Tax Status  
## Code
```
import pandas as pd
df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')
# Initiating empty list to save the list
emission_list =[]

# According to Goverment Regulation
limit = 50
tariff = 20000

# iteration every line in dataframe to check emission 
for index, row in df.iterrows():
    #the value of emission from Emisi_2024 Column
    emission = row['Emisi_2024'] 
    #input value of emission_list with "append" command
    emission_list.append(emission)

#iteration  emission list for compliance 
for i, emission in enumerate(emission_list):
    company = df.iloc[i]['Nama_Perusahaan']
    
    # Check if emission  exceed limit by government regulation
    if emission > limit:
        print(f"{company} was OBLIGATED to Carbon Tax because of the {emission} Tonnes Emission of Carbon")
    else:
        print(f"{company} was FREE from Carbon Tax because of the {emission} Tonnes Emisson of Carbon")
```
## RUN output
```
PT_Textilindo was OBLIGATED to Carbon Tax because of the 62.5 Tonnes Emission of Carbon
PT_Semindo was FREE from Carbon Tax because of the 45.8 Tonnes Emisson of Carbon
PT_EnergiJaya was OBLIGATED to Carbon Tax because of the 78.2 Tonnes Emission of Carbon
PT_Pulpindo was OBLIGATED to Carbon Tax because of the 55.0 Tonnes Emission of Carbon
PT_AgroMakmur was FREE from Carbon Tax because of the 42.3 Tonnes Emisson of Carbon
PT_BajaSentosa was OBLIGATED to Carbon Tax because of the 68.7 Tonnes Emission of Carbon
PT_KimiaFarindo was FREE from Carbon Tax because of the 49.1 Tonnes Emisson of Carbon
PT_MiningCo was OBLIGATED to Carbon Tax because of the 82.4 Tonnes Emission of Carbon
PT_PetroJaya was OBLIGATED to Carbon Tax because of the 60.9 Tonnes Emission of Carbon
PT_SinarLogam was OBLIGATED to Carbon Tax because of the 53.6 Tonnes Emission of Carbon
PT_IndoPlastik was FREE from Carbon Tax because of the 47.2 Tonnes Emisson of Carbon
PT_BumiEnergi was OBLIGATED to Carbon Tax because of the 75.3 Tonnes Emission of Carbon
PT_TextilMakmur was OBLIGATED to Carbon Tax because of the 64.8 Tonnes Emission of Carbon
PT_SemenBerkah was FREE from Carbon Tax because of the 43.5 Tonnes Emisson of Carbon
PT_KertasJaya was OBLIGATED to Carbon Tax because of the 58.9 Tonnes Emission of Carbon
PT_AgroSentosa was FREE from Carbon Tax because of the 41.7 Tonnes Emisson of Carbon
PT_BajaIndo was OBLIGATED to Carbon Tax because of the 70.2 Tonnes Emission of Carbon
PT_KimiaJaya was FREE from Carbon Tax because of the 48.4 Tonnes Emisson of Carbon
PT_TambangMakmur was OBLIGATED to Carbon Tax because of the 80.6 Tonnes Emission of Carbon
PT_PetroMakmur was OBLIGATED to Carbon Tax because of the 63.1 Tonnes Emission of Carbon
PT_LogamBerkah was OBLIGATED to Carbon Tax because of the 54.3 Tonnes Emission of Carbon
PT_PlastikJaya was FREE from Carbon Tax because of the 46.9 Tonnes Emisson of Carbon
PT_EnergiMakmur was OBLIGATED to Carbon Tax because of the 77.8 Tonnes Emission of Carbon
PT_TextilBerkah was OBLIGATED to Carbon Tax because of the 66.4 Tonnes Emission of Carbon
PT_SemenJaya was FREE from Carbon Tax because of the 44.2 Tonnes Emisson of Carbon
...
PT_AgroBerkah was FREE from Carbon Tax because of the 40.8 Tonnes Emisson of Carbon
PT_BajaMakmur was OBLIGATED to Carbon Tax because of the 72.1 Tonnes Emission of Carbon
PT_KimiaMakmur was OBLIGATED to Carbon Tax because of the 50.3 Tonnes Emission of Carbon
PT_TambangJaya was OBLIGATED to Carbon Tax because of the 85.7 Tonnes Emission of Carbon
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
```
# Query 5 : How to save Emission Data in Dictionary
#### Outpus : Dictionary containing Company emission data
## CODE
```
import pandas as pd
df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')

# Initiating Dictionary list to save the list
emission_dict ={}

# According to Goverment Regulation
limit = 50
tariff = 20000

# iteration every line in dataframe to check emission 
for index, row in df.iterrows():
    #the value of emission from Emisi_2024 Column
    emission = row['Emisi_2024'] 
    company = row['Nama_Perusahaan']
    #input value of emission_list with "append" command
   
    emission_dict[company] = emission
#print emission list
print("Company emission Data : ", emission_dict)
```
##RUN Output
```
Company emission Data :  {'PT_Textilindo': 62.5, 'PT_Semindo': 45.8, 'PT_EnergiJaya': 78.2, 'PT_Pulpindo': 55.0, 'PT_AgroMakmur': 42.3, 'PT_BajaSentosa': 68.7, 'PT_KimiaFarindo': 49.1, 'PT_MiningCo': 82.4, 'PT_PetroJaya': 60.9, 'PT_SinarLogam': 53.6, 'PT_IndoPlastik': 47.2, 'PT_BumiEnergi': 75.3, 'PT_TextilMakmur': 64.8, 'PT_SemenBerkah': 43.5, 'PT_KertasJaya': 58.9, 'PT_AgroSentosa': 41.7, 'PT_BajaIndo': 70.2, 'PT_KimiaJaya': 48.4, 'PT_TambangMakmur': 80.6, 'PT_PetroMakmur': 63.1, 'PT_LogamBerkah': 54.3, 'PT_PlastikJaya': 46.9, 'PT_EnergiMakmur': 77.8, 'PT_TextilBerkah': 66.4, 'PT_SemenJaya': 44.2, 'PT_KertasMakmur': 57.5, 'PT_AgroBerkah': 40.8, 'PT_BajaMakmur': 72.1, 'PT_KimiaMakmur': 50.3, 'PT_TambangJaya': 85.7}
```

# Query 6 : Greenwashing Status
Code: 
```
import pandas as pd
df = pd.read_csv('/Users/deka/GreenEnergy2025/emisi_perusahaan.csv')

# Initiating Dictionary list to save the list
emission_dict ={}

# ITeration every rows
for index, row in df.iterrows():
    #Company name as dictionary key
    company = row['Nama_Perusahaan']
    #save Emission and claim in dictionary
    emission_dict[company] = {
            'emission' : row['Emisi_2024'],
            'green_claim' : row['Klaim_Hijau']
    }


# Green washing Detection
# Dictionary iteration to check greenwashing

for company, data in emission_dict.items():
    emission = data['emission']
    green_claim = data['green_claim']
    #check if company claim green but carbon produce >50 Tonnes
    if data['green_claim'] == 'ya' and data['emission'] > 50:
        print(f"{company} was detected performing GREENWASHING with emission of {emission} tonnes in 2024 and Claiming {green_claim} on Green Practice")
    else:
        print(f"{company} was NOT Performing Greenwashing, emissions produced were {emission} tonnes of carbon in 2024 ")
```
##RUN Output
```
PT_Textilindo was detected performing GREENWASHING with emission of 62.5 tonnes in 2024 and Claiming ya on Green Practice
PT_Semindo was NOT Performing Greenwashing, emissions produced were 45.8 tonnes of carbon in 2024 
PT_EnergiJaya was detected performing GREENWASHING with emission of 78.2 tonnes in 2024 and Claiming ya on Green Practice
PT_Pulpindo was detected performing GREENWASHING with emission of 55.0 tonnes in 2024 and Claiming ya on Green Practice
PT_AgroMakmur was NOT Performing Greenwashing, emissions produced were 42.3 tonnes of carbon in 2024 
PT_BajaSentosa was detected performing GREENWASHING with emission of 68.7 tonnes in 2024 and Claiming ya on Green Practice
PT_KimiaFarindo was NOT Performing Greenwashing, emissions produced were 49.1 tonnes of carbon in 2024 
PT_MiningCo was detected performing GREENWASHING with emission of 82.4 tonnes in 2024 and Claiming ya on Green Practice
PT_PetroJaya was NOT Performing Greenwashing, emissions produced were 60.9 tonnes of carbon in 2024 
PT_SinarLogam was detected performing GREENWASHING with emission of 53.6 tonnes in 2024 and Claiming ya on Green Practice
PT_IndoPlastik was NOT Performing Greenwashing, emissions produced were 47.2 tonnes of carbon in 2024 
PT_BumiEnergi was detected performing GREENWASHING with emission of 75.3 tonnes in 2024 and Claiming ya on Green Practice
PT_TextilMakmur was detected performing GREENWASHING with emission of 64.8 tonnes in 2024 and Claiming ya on Green Practice
PT_SemenBerkah was NOT Performing Greenwashing, emissions produced were 43.5 tonnes of carbon in 2024 
PT_KertasJaya was detected performing GREENWASHING with emission of 58.9 tonnes in 2024 and Claiming ya on Green Practice
PT_AgroSentosa was NOT Performing Greenwashing, emissions produced were 41.7 tonnes of carbon in 2024 
PT_BajaIndo was detected performing GREENWASHING with emission of 70.2 tonnes in 2024 and Claiming ya on Green Practice
PT_KimiaJaya was NOT Performing Greenwashing, emissions produced were 48.4 tonnes of carbon in 2024 
PT_TambangMakmur was detected performing GREENWASHING with emission of 80.6 tonnes in 2024 and Claiming ya on Green Practice
PT_PetroMakmur was NOT Performing Greenwashing, emissions produced were 63.1 tonnes of carbon in 2024 
PT_LogamBerkah was detected performing GREENWASHING with emission of 54.3 tonnes in 2024 and Claiming ya on Green Practice
PT_PlastikJaya was NOT Performing Greenwashing, emissions produced were 46.9 tonnes of carbon in 2024 
PT_EnergiMakmur was detected performing GREENWASHING with emission of 77.8 tonnes in 2024 and Claiming ya on Green Practice
PT_TextilBerkah was detected performing GREENWASHING with emission of 66.4 tonnes in 2024 and Claiming ya on Green Practice
PT_SemenJaya was NOT Performing Greenwashing, emissions produced were 44.2 tonnes of carbon in 2024 
...
PT_AgroBerkah was NOT Performing Greenwashing, emissions produced were 40.8 tonnes of carbon in 2024 
PT_BajaMakmur was detected performing GREENWASHING with emission of 72.1 tonnes in 2024 and Claiming ya on Green Practice
PT_KimiaMakmur was NOT Performing Greenwashing, emissions produced were 50.3 tonnes of carbon in 2024 
PT_TambangJaya was detected performing GREENWASHING with emission of 85.7 tonnes in 2024 and Claiming ya on Green Practice
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
```



