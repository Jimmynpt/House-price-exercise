# House-price-exercise
Practicing Data Preparation and Feature Engineering

#display the complete output in jupyter notebook
pd.set_option("display.max_rows", None, "display.max_columns", None)

df = pd.read_csv('https://raw.githubusercontent.com/samsontai/Data/main/HousingPrice.csv')
df.set_index('Id', inplace=True)
dt= df
dt.head(710)

dt.info()
