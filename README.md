# 1 Write a Python program to display first 5 rows from COVID-19 dataset. Also print the dataset information and check the missing values

The detail information about the Display_first 
# import pandas as pd
The import pandas portion of the code tells Python to bring the pandas data analysis library into your current environment. The as pd portion of the code then tells Python to give pandas the alias of pd. This allows you to use pandas functions by simply typing pd

For example this data world covid 19 case to read using python .To explor the important information 

# pd.read_csv
 read_csv is an important pandas function to read csv files and do operations on it.

covid_data = pd.read_csv('https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_daily_reports/03-17-2020.csv')


# check out using printing funcation that holds information  
# print(covid_data)
```
    Province/State        Country/Region  ...   Latitude  Longitude
0            Hubei                 China  ...  30.975600  112.27070
1              NaN                 Italy  ...  41.871900   12.56740
2              NaN                  Iran  ...  32.427900   53.68800
3              NaN                 Spain  ...  40.463700   -3.74920
4              NaN               Germany  ...  51.165700   10.45150
..             ...                   ...  ...        ...        ...
297            NaN                 Tonga  ... -21.179000 -175.19820
298            NaN  Winter Olympics 2022  ...  39.904200  116.40740
299            NaN            Antarctica  ... -71.949900   23.34700
300         Jersey        United Kingdom  ...  49.213800   -2.13580
301       Guernsey        United Kingdom  ...  49.448196   -2.58949

[302 rows x 8 columns]

```


print("\nDataSet information: ")
# to get missing value and check missing values 
# print(covid_data.info())

```

DataSet information: 
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 302 entries, 0 to 301
Data columns (total 8 columns):
 #   Column          Non-Null Count  Dtype  
---  ------          --------------  -----  
 0   Province/State  147 non-null    object 
 1   Country/Region  302 non-null    object 
 2   Last Update     302 non-null    object 
 3   Confirmed       302 non-null    int64  
 4   Deaths          302 non-null    int64  
 5   Recovered       302 non-null    int64  
 6   Latitude        300 non-null    float64
 7   Longitude       300 non-null    float64
dtypes: float64(2), int64(3), object(3)
memory usage: 19.0+ KB
None

```


# print(covid_data.isna().sum())
```
 Missing data information:
Province/State    155
Country/Region      0
Last Update         0
Confirmed           0
Deaths              0
Recovered           0
Latitude            2
Longitude           2
dtype: int64



# 2 Get the latest number of confirmed, deaths, recovered and active cases of Novel Coronavirus Country wise
```
                     Country/Region  Confirmed  Deaths  Recovered  Active
0                       Afghanistan         26       0          1      25
1                           Albania         55       1          0      54
2                           Algeria         60       4         12      44
3                           Andorra         39       0          1      38
4                        Antarctica          0       0          0       0
..                              ...        ...     ...        ...     ...
160                      Uzbekistan         10       0          0      10
161                       Venezuela         33       0          0      33
162                         Vietnam         66       0         16      50
163            Winter Olympics 2022          0       0          0       0
164  occupied Palestinian territory          0       0          0       0
```
# 3 import pandas as pd
# Write a Python program to get the latest number of confirmed deaths and recovered people of Novel Coronavirus (COVID-19) cases Country/Region - Province/State wise

 # using  pd.read_csv read data from source 
covid_data= pd.read_csv('https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_daily_reports/03-16-2020.csv')

# group the information based on the Country/Region', 'Province/State'] and check the Country/Region', 'Province/State']

data = covid_data.groupby(['Country/Region', 'Province/State'])['Confirmed', 'Deaths', 'Recovered'].max()
pd.set_option('display.max_rows', None)

# to printe max number of row use max()
# pd.set_option('display.max_rows', None)

```
Australia      Australian Capital Territory          2       0          0
               From Diamond Princess                 0       0          0
               New South Wales                     171       2          4
               Northern Territory                    1       0          0
               Queensland                           68       0          8
               South Australia                      29       0          3
               Tasmania                              7       0          0
               Victoria                             71       0          8
               Western Australia                    28       1          0
Canada         Alberta                              56       0          0
               British Columbia                    103       4          4
               Grand Princess                        2       0          0
               Manitoba                              7       0          0
               New Brunswick                         6       0          0
               Newfoundland and Labrador             1       0          0
               Nova Scotia                           5       0          0
               Ontario                             427       5          5
               Prince Edward Island                  1       0          0
               Quebec                               85       0          0
               Saskatchewan                          7       0          0
China          Anhui                               990       6        984
               Beijing                             452       8        360
               Chongqing                           576       6        570
               Fujian                              296       1        295
               Gansu                               133       2         91
               Guangdong                          1361       8       1306
               Guangxi                             252       2        248
               Guizhou                             146       2        144
               Hainan                              168       6        161
               Hebei                               318       6        310
               Heilongjiang                        482      13        455
               Henan                              1273      22       1250
               Hong Kong                           155       4         84
               Hubei                             67798    3099      55142
               Hunan                              1018       4       1014
               Inner Mongolia                       75       1         73
               Jiangsu                             631       0        631
               Jiangxi                             935       1        934
               Jilin                                93       1         92
               Liaoning                            125       1        115
               Macau                                11       0         10
               Ningxia                              75       0         75
               Qinghai                              18       0         18
               Shaanxi                             245       2        233
               Shandong                            760       7        746
               Shanghai                            355       3        325
               Shanxi                              133       0        133
               Sichuan                             539       3        516
               Tianjin                             136       3        133
               Tibet                                 1       0          1
               Unknown                               0       0          0
               Xinjiang                             76       3         73
               Yunnan                              176       2        172
               Zhejiang                           1231       1       1216
Cruise Ship    Diamond Princess                    696       7        325
Denmark        Denmark                             914       3          1
               Faroe Islands                        18       0          0
France         France                             6633     148         12
               French Guiana                         5       0          0
               French Polynesia                      3       0          0
               Guadeloupe                            3       0          0
               Mayotte                               1       0          0
               Saint Barthelemy                      3       0          0
               St Martin                             2       0          0
Malaysia       Johor                                 0       0          0
               Kedah                                 0       0          0
               Kelantan                              0       0          0
               Melaka                                0       0          0
               Negeri Sembilan                       0       0          0
               Pahang                                0       0          0
               Perak                                 0       0          0
               Perlis                                0       0          0
               Pulau Pinang                          0       0          0
               Sabah                                 0       0          0
               Sarawak                               0       0          0
               Selangor                              0       0          0
               Terengganu                            0       0          0
               Unknown                               0       0          0
               W.P. Kuala Lumpur                     0       0          0
               W.P. Labuan                           0       0          0
               W.P. Putrajaya                        0       0          0
Netherlands    Curacao                               1       0          0
               Netherlands                        1413      24          2
New Zealand    Cook Islands                          0       0          0
US             Alabama                              29       0          0
               Alaska                                1       0          0
               Arizona                              18       0          1
               Arkansas                             22       0          0
               California                          557       7          6
               Colorado                            160       1          0
               Connecticut                          30       0          0
               Delaware                              8       0          0
               Diamond Princess                     47       0          0
               District of Columbia                 22       0          0
               Florida                             155       5          0
               Georgia                             121       1          0
               Grand Princess                       20       0          0
               Guam                                  3       0          0
               Hawaii                                7       0          0
               Idaho                                 5       0          0
               Illinois                            105       0          2
               Indiana                              25       1          0
               Iowa                                 23       0          0
               Kansas                               11       1          0
               Kentucky                             21       1          1
               Louisiana                           136       3          0
               Maine                                17       0          0
               Maryland                             41       0          3
               Massachusetts                       197       0          1
               Michigan                             53       0          0
               Minnesota                            54       0          0
               Mississippi                          13       0          0
               Missouri                              6       0          0
               Montana                               7       0          0
               Nebraska                             18       0          0
               Nevada                               45       1          0
               New Hampshire                        17       0          0
               New Jersey                          178       2          1
               New Mexico                           17       0          0
               New York                            967      10          0
               North Carolina                       38       0          0
               North Dakota                          1       0          0
               Ohio                                 50       0          0
               Oklahoma                             10       0          0
               Oregon                               39       1          0
               Pennsylvania                         77       0          0
               Puerto Rico                           5       0          0
               Rhode Island                         21       0          0
               South Carolina                       33       1          0
               South Dakota                         10       1          0
               Tennessee                            52       0          0
               Texas                                85       0          0
               Utah                                 39       0          0
               Vermont                              12       0          0
               Virgin Islands                        1       0          0
               Virginia                             49       1          0
               Washington                          904      48          1
               West Virginia                         0       0          0
               Wisconsin                            47       0          1
               Wyoming                               3       0          0
United Kingdom Cayman Islands                        1       1          0
               Channel Islands                       0       0          0
               Gibraltar                             1       0          1
               Guernsey                              0       0          0
               Jersey                                0       0          0
               United Kingdom                     1543      55         20

 ```

 
 
 # 4 Write a Python program to get the Chinese province wise cases of confirmed, deaths and recovered cases of Novel Coronavirus (COVID-19            

 
c_data = covid_data[covid_data['Country/Region']=='Country']

 Databased on the based on the  Province/State', 'Confirmed', 'Deaths', 'Recovered' 

then group based on the ascending order 

result = c_data.sort_values(by='Confirmed', ascending=False)

# pandas. reset_index in pandas is used to reset index of the dataframe object to default indexing (0 to number of rows minus 1) or to reset multi level index.
result = result.reset_index(drop=True)

```
print(result)
    Province/State  Confirmed  Deaths  Recovered
0            Hubei      67799    3111      56003
1        Guangdong       1364       8       1307
2            Henan       1273      22       1250
3         Zhejiang       1232       1       1216
4            Hunan       1018       4       1014
5            Anhui        990       6        984
6          Jiangxi        935       1        934
7         Shandong        761       7        746
8          Jiangsu        631       0        631
9        Chongqing        576       6        570
10         Sichuan        540       3        520
11    Heilongjiang        482      13        456
12         Beijing        456       8        369
13        Shanghai        358       3        325
14           Hebei        318       6        310
15          Fujian        296       1        295
16         Guangxi        253       2        248
17         Shaanxi        246       3        236
18          Yunnan        176       2        172
19          Hainan        168       6        161
20       Hong Kong        162       4         88
21         Guizhou        147       2        144
22         Tianjin        136       3        133
23           Gansu        133       2         91
24          Shanxi        133       0        133
25        Liaoning        125       1        120
26           Jilin         93       1         92
27        Xinjiang         76       3         73
28  Inner Mongolia         75       1         73
29         Ningxia         75       0         75
30         Qinghai         18       0         18
31           Macau         12       0         10
32           Tibet          1       0          1
33         Unknown          0       0          0

```


```
# import pandas as pd
# 5 Get the latest country wise deaths cases of Novel Coronavirus

to get this solution 
#  = data[data['Deaths']>0][['Country/Region', 'Deaths']]
# print(result)
         Country/Region  Deaths
1               Albania       1
2               Algeria       4
6             Argentina       2
9             Australia       5
10              Austria       3
11           Azerbaijan       1
12              Bahrain       1
16              Belgium      10
21               Brazil       1
23             Bulgaria       2
27               Canada      12
30                China    3230
37          Cruise Ship       7
41              Denmark       4
42   Dominican Republic       1
43              Ecuador       2
44                Egypt       4
49              Finland       4
50               France     148
54              Germany      24
56               Greece       5
60            Guatemala       1
63               Guyana       1
66              Hungary       1
67              Iceland       1
68                India       3
69            Indonesia       5
70                 Iran     988
71                 Iraq      11
72              Ireland       2
74                Italy    2503
76                Japan      29
82         Korea, South      81
86              Lebanon       3
90           Luxembourg       1
94           Martinique       1
102             Morocco       2
105         Netherlands      43
109              Norway       3
113              Panama       1
115                Peru       9
116         Philippines      12
117              Poland       5
118            Portugal       1
128          San Marino       9
135            Slovenia       1
138               Spain     533
140               Sudan       1
143              Sweden       7
144         Switzerland      40
145             Taiwan*       1
147            Thailand       1
154              Turkey       1
155                  US     108
156             Ukraine       2
158      United Kingdom      56

```