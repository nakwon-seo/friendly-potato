# friendly-potato
learning Python and interested in data-visualisation and analytics

current Project with Python
Visualising GDP data of the World

{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 235,
   "metadata": {},
   "outputs": [],
   "source": [
    "import numpy as np\n",
    "import pandas as pd"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 236,
   "metadata": {},
   "outputs": [],
   "source": [
    "%matplotlib inline\n",
    "import matplotlib as mpl\n",
    "import matplotlib.pyplot as plt"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 237,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp=pd.read_excel(\"http://api.worldbank.org/v2/en/indicator/NY.GDP.MKTP.CD?downloadformat=excel\",skiprows=range(3))\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 238,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "(264, 64)"
      ]
     },
     "execution_count": 238,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_gdp.shape"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 239,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp = df_gdp.drop(['Country Code','Indicator Name','Indicator Code'],axis=1)\n",
    "df_gdp = df_gdp.drop('2019', axis=1)\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 240,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp.rename(columns={'Country Name':'Country'}, inplace=True)\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 241,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp.set_index(['Country'], inplace=True)\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 242,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp.drop(df_gdp.loc[:,'1960':'1979'].columns,axis=1, inplace=True)\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 243,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp.drop(['Arab World','Central Europe and the Baltics','East Asia & Pacific (excluding high income)',\n",
    "             'Early-demographic dividend','East Asia & Pacific','Europe & Central Asia (excluding high income)',\n",
    "             'Europe & Central Asia','Euro area','European Union','Fragile and conflict affected situations','High income',\n",
    "             'Heavily indebted poor countries (HIPC)','IBRD only','IDA & IBRD total','IDA total','IDA blend','IDA only',\n",
    "             'Latin America & Caribbean (excluding high income)','Lao PDR','Latin America & Caribbean',\n",
    "             'Least developed countries: UN classification','Low income','Lower middle income','Low & middle income',\n",
    "             'Late-demographic dividend','Middle East & North Africa','Middle income','Middle East & North Africa (excluding high income)',\n",
    "             'OECD members','Other small states','Pre-demographic dividend','West Bank and Gaza','Pacific island small states',\n",
    "             'Post-demographic dividend','South Asia','Sub-Saharan Africa (excluding high income)','Small states',\n",
    "             'Turks and Caicos Islands','East Asia & Pacific (IDA & IBRD countries)','Europe & Central Asia (IDA & IBRD countries)',\n",
    "             'Latin America & the Caribbean (IDA & IBRD countries)','Middle East & North Africa (IDA & IBRD countries)',\n",
    "             'South Asia (IDA & IBRD)','Sub-Saharan Africa (IDA & IBRD countries)','Upper middle income','World','North America','Sub-Saharan Africa'], \n",
    "            axis=0, inplace=True)\n",
    "#df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 244,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "True"
      ]
     },
     "execution_count": 244,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "all(isinstance(column, str) for column in df_gdp.columns)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 245,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "True"
      ]
     },
     "execution_count": 245,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_gdp.columns = list(map(str, df_gdp.columns))\n",
    "all(isinstance(column, str) for column in df_gdp.columns)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 246,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "data dimensions: (216, 39)\n"
     ]
    }
   ],
   "source": [
    "print ('data dimensions:', df_gdp.shape)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 247,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp.columns=list(map(str,df_gdp.columns))\n",
    "years=list(map(str,range(1980,2019)))\n",
    "#years"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 248,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp['Total'] = df_gdp.sum(axis=1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 249,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp = df_gdp.fillna(0)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 250,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp = df_gdp.sort_values(by='2018', ascending=False, axis=0)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 251,
   "metadata": {},
   "outputs": [],
   "source": [
    "#df_gdp.sort_values(['Total'], ascending=False)\n",
    "\n",
    "df_gdp_top15 = df_gdp['2018'].head(15)\n",
    "#df_gdp_top15"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 252,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_top15 = df_gdp[years].head(15)\n",
    "#df_gdp_top15"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 253,
   "metadata": {},
   "outputs": [],
   "source": [
    "years_80s=list(map(str,range(1980,1990)))\n",
    "years_90s=list(map(str,range(1990,2000)))\n",
    "years_00s=list(map(str,range(2000,2010)))\n",
    "years_10s=list(map(str,range(2010,2018)))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 254,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_80s=df_gdp_top15.loc[:,years_80s].mean(axis=1)\n",
    "df_90s=df_gdp_top15.loc[:,years_90s].mean(axis=1)\n",
    "df_00s=df_gdp_top15.loc[:,years_00s].mean(axis=1)\n",
    "df_10s=df_gdp_top15.loc[:,years_10s].mean(axis=1)\n",
    "\n",
    "new_df_gdp = pd.DataFrame({'1980s': df_80s, '1990s': df_90s, '2000s':df_00s,'2010s':df_10s}) \n",
    "#new_df_gdp.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 255,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>1980s</th>\n",
       "      <th>1990s</th>\n",
       "      <th>2000s</th>\n",
       "      <th>2010s</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>count</td>\n",
       "      <td>1.500000e+01</td>\n",
       "      <td>1.500000e+01</td>\n",
       "      <td>1.500000e+01</td>\n",
       "      <td>1.500000e+01</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>mean</td>\n",
       "      <td>7.296921e+11</td>\n",
       "      <td>1.504947e+12</td>\n",
       "      <td>2.393222e+12</td>\n",
       "      <td>3.737991e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>std</td>\n",
       "      <td>1.051871e+12</td>\n",
       "      <td>1.974921e+12</td>\n",
       "      <td>3.024871e+12</td>\n",
       "      <td>4.299314e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>min</td>\n",
       "      <td>1.061214e+11</td>\n",
       "      <td>3.535083e+11</td>\n",
       "      <td>6.541588e+11</td>\n",
       "      <td>1.179324e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>25%</td>\n",
       "      <td>2.170417e+11</td>\n",
       "      <td>4.366282e+11</td>\n",
       "      <td>8.483836e+11</td>\n",
       "      <td>1.538744e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>50%</td>\n",
       "      <td>2.733753e+11</td>\n",
       "      <td>6.427365e+11</td>\n",
       "      <td>1.102224e+12</td>\n",
       "      <td>2.060247e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>75%</td>\n",
       "      <td>6.769944e+11</td>\n",
       "      <td>1.378911e+12</td>\n",
       "      <td>2.458038e+12</td>\n",
       "      <td>3.171702e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>max</td>\n",
       "      <td>4.173163e+12</td>\n",
       "      <td>7.577130e+12</td>\n",
       "      <td>1.259074e+13</td>\n",
       "      <td>1.718126e+13</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "              1980s         1990s         2000s         2010s\n",
       "count  1.500000e+01  1.500000e+01  1.500000e+01  1.500000e+01\n",
       "mean   7.296921e+11  1.504947e+12  2.393222e+12  3.737991e+12\n",
       "std    1.051871e+12  1.974921e+12  3.024871e+12  4.299314e+12\n",
       "min    1.061214e+11  3.535083e+11  6.541588e+11  1.179324e+12\n",
       "25%    2.170417e+11  4.366282e+11  8.483836e+11  1.538744e+12\n",
       "50%    2.733753e+11  6.427365e+11  1.102224e+12  2.060247e+12\n",
       "75%    6.769944e+11  1.378911e+12  2.458038e+12  3.171702e+12\n",
       "max    4.173163e+12  7.577130e+12  1.259074e+13  1.718126e+13"
      ]
     },
     "execution_count": 255,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "new_df_gdp.describe()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 256,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 720x432 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "new_df_gdp.plot(kind='box', figsize=(10,6))\n",
    "plt.title('GDP from top 15 countries for decades 80s, 90s, 2000s and 2010s')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 257,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>1980s</th>\n",
       "      <th>1990s</th>\n",
       "      <th>2000s</th>\n",
       "      <th>2010s</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Country</th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>United States</td>\n",
       "      <td>4.173163e+12</td>\n",
       "      <td>7.577130e+12</td>\n",
       "      <td>1.259074e+13</td>\n",
       "      <td>1.718126e+13</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>China</td>\n",
       "      <td>2.626079e+11</td>\n",
       "      <td>6.863142e+11</td>\n",
       "      <td>2.592138e+12</td>\n",
       "      <td>9.559601e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Japan</td>\n",
       "      <td>1.815785e+12</td>\n",
       "      <td>4.327938e+12</td>\n",
       "      <td>4.663733e+12</td>\n",
       "      <td>5.280374e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Germany</td>\n",
       "      <td>9.900306e+11</td>\n",
       "      <td>2.177681e+12</td>\n",
       "      <td>2.764824e+12</td>\n",
       "      <td>3.596108e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>United Kingdom</td>\n",
       "      <td>6.244775e+11</td>\n",
       "      <td>1.326610e+12</td>\n",
       "      <td>2.323938e+12</td>\n",
       "      <td>2.747296e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>France</td>\n",
       "      <td>7.295113e+11</td>\n",
       "      <td>1.431213e+12</td>\n",
       "      <td>2.096976e+12</td>\n",
       "      <td>2.668358e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>India</td>\n",
       "      <td>2.364114e+11</td>\n",
       "      <td>3.535083e+11</td>\n",
       "      <td>8.303781e+11</td>\n",
       "      <td>2.033552e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Italy</td>\n",
       "      <td>5.934750e+11</td>\n",
       "      <td>1.216282e+12</td>\n",
       "      <td>1.756476e+12</td>\n",
       "      <td>2.060247e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Brazil</td>\n",
       "      <td>2.733753e+11</td>\n",
       "      <td>6.427365e+11</td>\n",
       "      <td>9.709591e+11</td>\n",
       "      <td>2.233893e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Canada</td>\n",
       "      <td>3.835417e+11</td>\n",
       "      <td>6.145255e+11</td>\n",
       "      <td>1.102224e+12</td>\n",
       "      <td>1.699578e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Russian Federation</td>\n",
       "      <td>1.061214e+11</td>\n",
       "      <td>3.984282e+11</td>\n",
       "      <td>7.870291e+11</td>\n",
       "      <td>1.796111e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Korea, Rep.</td>\n",
       "      <td>1.201236e+11</td>\n",
       "      <td>4.368263e+11</td>\n",
       "      <td>8.085874e+11</td>\n",
       "      <td>1.320629e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Australia</td>\n",
       "      <td>1.976719e+11</td>\n",
       "      <td>3.584317e+11</td>\n",
       "      <td>6.541588e+11</td>\n",
       "      <td>1.377911e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Spain</td>\n",
       "      <td>2.516406e+11</td>\n",
       "      <td>5.901462e+11</td>\n",
       "      <td>1.089771e+12</td>\n",
       "      <td>1.335622e+12</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>Mexico</td>\n",
       "      <td>1.874451e+11</td>\n",
       "      <td>4.364301e+11</td>\n",
       "      <td>8.663890e+11</td>\n",
       "      <td>1.179324e+12</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                           1980s         1990s         2000s         2010s\n",
       "Country                                                                   \n",
       "United States       4.173163e+12  7.577130e+12  1.259074e+13  1.718126e+13\n",
       "China               2.626079e+11  6.863142e+11  2.592138e+12  9.559601e+12\n",
       "Japan               1.815785e+12  4.327938e+12  4.663733e+12  5.280374e+12\n",
       "Germany             9.900306e+11  2.177681e+12  2.764824e+12  3.596108e+12\n",
       "United Kingdom      6.244775e+11  1.326610e+12  2.323938e+12  2.747296e+12\n",
       "France              7.295113e+11  1.431213e+12  2.096976e+12  2.668358e+12\n",
       "India               2.364114e+11  3.535083e+11  8.303781e+11  2.033552e+12\n",
       "Italy               5.934750e+11  1.216282e+12  1.756476e+12  2.060247e+12\n",
       "Brazil              2.733753e+11  6.427365e+11  9.709591e+11  2.233893e+12\n",
       "Canada              3.835417e+11  6.145255e+11  1.102224e+12  1.699578e+12\n",
       "Russian Federation  1.061214e+11  3.984282e+11  7.870291e+11  1.796111e+12\n",
       "Korea, Rep.         1.201236e+11  4.368263e+11  8.085874e+11  1.320629e+12\n",
       "Australia           1.976719e+11  3.584317e+11  6.541588e+11  1.377911e+12\n",
       "Spain               2.516406e+11  5.901462e+11  1.089771e+12  1.335622e+12\n",
       "Mexico              1.874451e+11  4.364301e+11  8.663890e+11  1.179324e+12"
      ]
     },
     "execution_count": 257,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "new_df_gdp.head(15)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 386,
   "metadata": {},
   "outputs": [],
   "source": [
    "#'Scatter plots'"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 387,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>year</th>\n",
       "      <th>total</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <td>0</td>\n",
       "      <td>1980</td>\n",
       "      <td>1.069390e+13</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>1</td>\n",
       "      <td>1981</td>\n",
       "      <td>1.107674e+13</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>2</td>\n",
       "      <td>1982</td>\n",
       "      <td>1.097108e+13</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>3</td>\n",
       "      <td>1983</td>\n",
       "      <td>1.118908e+13</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <td>4</td>\n",
       "      <td>1984</td>\n",
       "      <td>1.159689e+13</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   year         total\n",
       "0  1980  1.069390e+13\n",
       "1  1981  1.107674e+13\n",
       "2  1982  1.097108e+13\n",
       "3  1983  1.118908e+13\n",
       "4  1984  1.159689e+13"
      ]
     },
     "execution_count": 387,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_gdp_tal = pd.DataFrame(df_gdp[years].sum(axis=0))\n",
    "\n",
    "df_gdp_tal.index = map(int, df_gdp_tal.index)\n",
    "\n",
    "df_gdp_tal.reset_index(inplace = True)\n",
    "\n",
    "df_gdp_tal.columns = ['year', 'total']\n",
    "\n",
    "df_gdp_tal.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 388,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Text(0, 0.5, 'GDP(current US$)')"
      ]
     },
     "execution_count": 388,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 720x432 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "df_gdp_tal.plot(kind='scatter', x='year', y='total', figsize=(10, 6), color='#800000')\n",
    "\n",
    "plt.title('World GDP from 1980 - 2018')\n",
    "plt.xlabel('Year')\n",
    "plt.ylabel('GDP(current US$)')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 389,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_top3 = df_gdp.loc[['United States','Japan','China'], years].transpose()\n",
    "#df_gdp_top3.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 390,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_tal2 = pd.DataFrame(df_gdp_top3.sum(axis=1))\n",
    "df_gdp_tal2.reset_index(inplace=True)\n",
    "\n",
    "df_gdp_tal2.columns = ['year', 'total']\n",
    "df_gdp_tal2['year'] = df_gdp_tal2['year'].astype(int)\n",
    "\n",
    "#df_gdp_tal2.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 391,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_mi3 = df_gdp.loc[['India','Italy','Brazil'], years].transpose()\n",
    "#df_gdp_mi3.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 392,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_tal3 = pd.DataFrame(df_gdp_mi3.sum(axis=1))\n",
    "df_gdp_tal3 = df_gdp_tal3.reset_index()\n",
    "\n",
    "df_gdp_tal3.columns = ['year', 'total']\n",
    "df_gdp_tal3['year'] = df_gdp_tal3['year'].astype(int)\n",
    "\n",
    "#df_gdp_tal3.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 393,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_least3 = df_gdp.loc[['Australia','Spain','Mexico'], years].transpose()\n",
    "#df_gdp_least3.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 394,
   "metadata": {},
   "outputs": [],
   "source": [
    "df_gdp_tal4 = pd.DataFrame(df_gdp_least3.sum(axis=1))\n",
    "df_gdp_tal4 = df_gdp_tal4.reset_index()\n",
    "\n",
    "df_gdp_tal4.columns = ['year', 'total']\n",
    "df_gdp_tal4['year'] = df_gdp_tal4['year'].astype(int)\n",
    "\n",
    "#df_gdp_tal4.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 395,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "\"fig = plt.figure()\\n\\nax0 = fig.add_subplot(2, 2, 1)\\nax1 = fig.add_subplot(2, 2, 2)\\nax2 = fig.add_subplot(2, 2, 3)\\nax3 = fig.add_subplot(2, 2, 4)\\n\\n\\n\\n\\ndf_gdp_tal.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#800000', ax=ax0)\\nax0.set_title('Total GDP from 1980 - 2018')\\nax0.set_xlabel('Year')\\nax0.set_ylabel('GDP(current US$)')\\n\\ndf_gdp_tal2.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#00CED1', ax=ax1)\\nax1.set_title ('GDP from United States, Japan and China from 1980-2018')\\nax1.set_ylabel('GDP(current US$)')\\nax1.set_xlabel('Year')\\n\\ndf_gdp_tal3.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='pink', ax=ax2)\\nax2.set_title ('GDP from India, Italy and Brazil from 1980-2018')\\nax2.set_xlabel('Year')\\nax2.set_ylabel('GDP(current US$)')\\n\\ndf_gdp_tal4.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#90EE90', ax=ax3)\\nax3.set_title ('GDP from Australia, Spain and Mexico from 1980-2018')\\nax3.set_xlabel('Year')\\nax3.set_ylabel('GDP(current US$)')\\n\\nplt.show()\""
      ]
     },
     "execution_count": 395,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "'''fig = plt.figure()\n",
    "\n",
    "ax0 = fig.add_subplot(2, 2, 1)\n",
    "ax1 = fig.add_subplot(2, 2, 2)\n",
    "ax2 = fig.add_subplot(2, 2, 3)\n",
    "ax3 = fig.add_subplot(2, 2, 4)\n",
    "\n",
    "\n",
    "\n",
    "\n",
    "df_gdp_tal.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#800000', ax=ax0)\n",
    "ax0.set_title('Total GDP from 1980 - 2018')\n",
    "ax0.set_xlabel('Year')\n",
    "ax0.set_ylabel('GDP(current US$)')\n",
    "\n",
    "df_gdp_tal2.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#00CED1', ax=ax1)\n",
    "ax1.set_title ('GDP from United States, Japan and China from 1980-2018')\n",
    "ax1.set_ylabel('GDP(current US$)')\n",
    "ax1.set_xlabel('Year')\n",
    "\n",
    "df_gdp_tal3.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='pink', ax=ax2)\n",
    "ax2.set_title ('GDP from India, Italy and Brazil from 1980-2018')\n",
    "ax2.set_xlabel('Year')\n",
    "ax2.set_ylabel('GDP(current US$)')\n",
    "\n",
    "df_gdp_tal4.plot(kind='scatter', x='year', y='total', figsize=(20, 15), color='#90EE90', ax=ax3)\n",
    "ax3.set_title ('GDP from Australia, Spain and Mexico from 1980-2018')\n",
    "ax3.set_xlabel('Year')\n",
    "ax3.set_ylabel('GDP(current US$)')\n",
    "\n",
    "plt.show()'''"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 406,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAq8AAAIrCAYAAADBQHBTAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADh0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uMy4xLjEsIGh0dHA6Ly9tYXRwbG90bGliLm9yZy8QZhcZAAAgAElEQVR4nOzdeXxU1cH/8c9JMgkwAwSVKmBAK4hLQHYIQiaEpRgUBaPwUBd8FKvGHWpxeXAriki0igTsT4WKWFAE7SNKBMMMFHgQlzS0pSpYLIIgSwaYAMkk3N8fdzJOVsISkiHf9+uVF5m7nHvmzAz5zrnn3mMsy0JEREREJBJE1XUFRERERERqSuFVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqcRowxvzbGfFLX9ThRxhiPMea2k1TWHGPM709GWSdYj7HGmL/WdT1ONmPMDmNMvyrWbTbGJJ3qOlXFGNPGGLPGGHPAGDO5rutzLOpbW4rUJYVXkUoYY8YYYz43xviNMT8aYz6u6g90fWJZ1jzLsobU9nGMMZYxpn1tbd+QGGP6B99nfmNMQbCt/GE/beu6jsfLsqwLLMtaW9f1CHMXsMWyrKaWZT1a15UBMMbMN8Y8drTt6mFbitQZhVeRcowxDwJ/AJ4BzgbaAlnA1XVZr6MxxsTUdR3k2FmWtcqyLJdlWS7g0uDi+NJllmX9p7aO3QDfM+2Af9Z1JY5FA3yNRI5K4VUkjDGmOfAUkGFZ1iLLsgosywpYlvW/lmX9NrhNnDHmD8aY7cGfPxhj4oLrUowxPxhjHjLG/BTstb3GGJNmjPnGGLPXGPNI2PGeMMYsNMYsCJ7K/NIYc1nY+onB04UHjDH/NMaMCFs31hiz2hjzojFmL/BE+KlpY3sxWI99xpg8Y0xicN0cY0xWsEfZHyznnOBzyTfG/MsY07WKNloZ/PVvwX1HBZePM8ZsCj7HvxhjWle1vTGmhTHmQ2PMruDxPjTGnFvD16ixMeZPwf02Btv6h7D1XYPteMAYswBoFLau9PV5xBiz2xizxRjz62qOdUvwGAeMMd8ZY35TSVnjw17rW8LWnxlsh/3GmM+AC2ry/KqoR1tjzEfBtv3GGHNz2Lopxpg/G2PeC9ZzvTHm0irKaRTs2b3TGLMZ+Htw+czgc9lvjPnMGNOnXPnzgsc4EHwfdami/E7BNh0ZfBwaUnC0cowxvYwxfwuue9sYs8gEeySD782lxhifMWaPMSanmrZyB1//fcaY/zPG9Awu/zMwCvif4PuwfyX7Oo0xLxtjtgb395pgeDTGXGvsz6DPGLPcGNOhXJueG1bO/LC6Dw1+Lh4Jvt+3lb7njDH3AteG1endsHabYIz5B7C/kraMNsb8T/A9uTvYrvFhz2F+8L3iM8asM8a0qKq9RCKSZVn60Y9+gj/AUKAYiKlmm6eA/wN+AbQE1gBPB9elBPefBDiAccAu4G2gKXbP2mHgl8HtnwACQHpw+wnAvwFHcP11QGvsL5qjgAKgVXDd2OCx7gFigMbBZX8Nrv8V8AUQDxjg4rB95wC7ge7Y4S4neNybgGjg98CKatrAAtqHPU4NltcNiAOmAyur2f5M7D/aTYLt8i7wfth6D3BbFceeAniBFsC5QB7wQ3BdLPA98ECwPdOD7fv7cq/PC8F6uoNt2rGKYw3DDp0muO1BoFu5sp4KHistuL5FcP184B3ACSQC20pfm2ra9bxgW8WUW74OeDFY5x7AXuDysPYoAoYH6/EY8DUQXUn5jYLlLwm+LxoHl98UbE8H8CiwlZ/fg1OCz2tw8L3xIuAJK3MH0A/oHdxvSPl1RysnWK/twB3Y7+XRwdftseD6F4GXgutigeQq2u8X2GHv+uC2Y7E/f83DXpPHqmn/14FPgHOCdewf/DcROBB8zWOB/wE2Bo9R2qbnhpUTOg72/ymBYLs6gBHBslxV1SnYbuuxP/uNK2nLicCq4PpG2J/n2cF19wELsf8/iAF6As66/r9VP/o5mT91XoEKFYI3gJ+Av9dg22TgS+w/IOlhy9th/9HOBf4B3FHXz0s/kfED/BrYcZRtNgNpYY9/hT2OjuAft0MEgwN2MLOA3mHbfwFcE/z9CeD/wtZFAT8C/as4di5wdfD3scB/yq0fy8/hNRX4BugDRJXbbg7w/8Ie3wNsDHvcCfBV0wblw+jrwNSwx67gH+zzKtu+kvK6APlhjz1UHV6/A34V9vg2fg6vydghyIStX0PF8OoMW/8O8D81fH+8D9xX7rWOCVv/U7C9o4PP/6Kwdc9wHOEV6ID9hadx2LIXgVnB36dQNkzGAHuAnpWUXxq0+lZTB4MdMjuGlf9h2Ppu4e8N7FD1OPADwUBdbl2/o5UDDAG+K7fv5/wcAKdif8H55VHabxxhX5qCy74CRgd/rzK8YgfLAJV8kQEmA2+GPY7GDsV9qFl43UfYZxA7YHepqk7BdhtTTVv+O7ytgfODr5nBHtfrBRJr8p7Wj34i8ac+DhuYg/1hr4n/YP+xfrvc8h+x/3Pugt0bMNEET2GKHMUe4CxT/Tiz1ti9e6W+Dy4LlWFZVknw90PBf3eGrT+EHe5KbS39xbKsI9ghoPSU+03GmNzg6T8fdg/QWZXtW55lWTnAK8AMYKcx5o/GmGZhm5SvU3V1PJoybWJZlh+7LdtUtrExpokx5lVjzPfGmP3ASiDeGBNdw2OFP++t5dZtsyzLClsW/lqBHZILyq2v9P8HY8wVwVPPe4Ptn0bZ9t9jWVZx2OOD2O3WEjtEhtetfD1qqjWwy7KsQ2HLvqds24a/h4qxA3x1/+eVed8YYx42xnxtjNkH5GMHsvDnuSPs99LnGO4uIMeyrNVHeS5VldMa+31fVR0nYz+nFcFT8A9WUX75zyZUbKuqtMJ+zb47WrnBz/e2GpYL9ut3JOxxZW1YXqWfbWOMARKAj8L+X/gK+4vvmdhfJL3AwuBQkGdq+LkSiRj1LrxalrUS+5RYiDHmguB4py+MMauMMRcFt91iWVYecKRcGUWWZRUGH8ZRD5+n1FtrsXu5rqlmm+3Yvful2gaXHa+E0l+MMVHYp8K3G2PaAf8PuBs407KseOwxiiZs3/CQVoFlWS9bltUde7jChcBvT6Ce1SnTJsYYJ/Yf0m1VbD8e6IjdI90Mu8cUyj63qvyI3UalEsqtaxP8A1+q/NX6LYL1C19f4fUz9jjm94BpwNnB9v+ohnXchd3DG163471rwHagpTGmcbmywts2/D0UjR22qntPht43xpjB2D3vI7CHEpyB/eWlJs+z1K1AojHm2WPYJ1z51xTCnpNlWfssy7rPsqx22MNNHjPGXF5JOeU/m1CxraqrQzHwy6OVG2zjNsFyi7B7bJuEbX9ODY5XqqrPcKXLg1/MtgGplmXFh/00sixrt2VZhZZlTbIs6yLsz9V12MMwRE4bkRLq/gjcE/wjPAH7yu9qGWMSjDF52N9en7Ms60TChTQQlmXtwx6vOsPYF1o1McY4gj1wU4Ob/Rn7j2dLY8xZwe3fOoHDdjfGjAz29t4PFGKPqXVi/wHbBfbFQ9g9rzVijOlpjOltjHFgj+s8DJQcZbea2knZP/JvA7cYY7oEQ98zwDrLsrZUsX1T7IDkM8acgX3auabeAR429kVfbbDDfam12AHkXmNMjLEvHOpVSRlPGmNigxftXIl9Srq8WOwvv7uAYmPMFdint48q2DO3CPsiuibGmEuAm2v4/MrbhD2u9/fGvliwW7CseWHb9DXGXBl8rR/C7vX+soblN8UOX7uwn/NThF3kVkM+7LGsw4wxTx7jvmD3vDc2xtwefN2uB8IvXBxujDk/+KVkH/b7uLL38l+ArsaY9GA5N2GH16VHq4BlWQHgTeAlY8zZwYui+gWD6gJghDEmOdjGE7Hb+PNgj+oG4NfBfa4CjuV+rOU/GzUxC5hijEkAMMb8InhcjDGDjDGXBL8I78f+PJysz71IvVDvw6sxxgX0Bd41xuQCr2Kf3qmWZVlbLcvqDLQHbjbGnF27NZXThWVZLwAPYl/4sgv7C9Dd2OMdwb6Y6XPsQLEBOyScyE3wP8C+GCsfuBEYadl3OPgnkIkdyHZij0M92mnZcM2we27zsU957sHuRTwZngD+FDxteb1lWZ9iX8TyHnYP1gWU7e0psz32rcgaY1/k9X/UIFyEeQr7FPO/geXYF6cUgn3WBRiJPZwoH7tdF5Xbf0dw3XbsAHiHZVn/Kn8Qy7IOAPdih+V8YAx2OKqpu7FPDe8geEHNMewbXg8L+wKkS4JlLQB+a1nWqrDN3gP+O1jPa4Frw4auHM3/YofHzdinzHcT/MJ0jPXcAwwCrjPGHNM9VINDIkZi9wDnY5/5yCb4umJfbOjBvtBpJTDNsqz/q6ScndgXrj2K/X6/G7jSsixfDatyL3Y7fBXc/2ns8dN52L3Lr2K3zUDsseelQ0bu5ufP8AjgwxoeD+zOmZ7Bz8b8Gu4zFfu9n2OMOYA9rrtbcF0b7P9TDmCfqfkI+z0sctowZYeG1Q/GmPOwB/YnBsfofW1ZVpWB1RgzJ7j9wirWzwaWVLVepK4YY57AvpDphrquS6QyxtyJfUGOuwbbpgBvWZZVo9tyRQJjzBTgLMuyTsqMZPWFMeZvwBTLsv5c13URkfql3ve8Wpa1H/i3MeY6CN278rLq9jHGnFs6PszY97e7HPvWMSIS4YwxrYwxlxtjoowxHbHHzy6u63rJiTHGDAie/nYYY27H7r1fVtf1EpH6p96FV2PfSHot0DF4peSt2LcvujX4TfwfBGc6Co7p+wF7QPqrxr6hM9inmNYFt/din2LacKqfi4jUiljs07cHsO9P+wE1GAcv9d6l2Ke587HvXjDSsqzddVslEamP6uWwARERERGRytS7nlcRERERkaoovIqIiIhIxKhuFqFT7qyzzrLOO++8uq6GiIiIiJxkX3zxxW7LslqeaDn1Kryed955fP7553VdDRERERE5yYwxxztNdhkaNiAiIiIiEUPhVUREREQiRr0aNlDezp072bt3b11XQ6TeO+OMMzj7bM2ALCIip796HV737t3LhRdeSHR0dF1XRaTeKikp4ZtvvlF4FRGRBqHeDxtQcBWpnj4jIiLSkNT78CoiIiIiUkrhFSgqKiIlJYWUlBSaNm0a+t3v95fZbu/evSxcuLDasvr168fhw4fLLDt06BD33HMPycnJuN1ubrjhBvx+P5s2beIXv/gFqampDBgwgCeffJLi4uJQOcnJyXTv3p3XX3+9THlHjhxh2LBhJCcns2/fvpPQAj+bOHEirVq1YuLEiaFlubm59OvXj/79+/POO+8AUFBQQFpaGm63myFDhpCfnw/A22+/Td++fRk4cCDbtm2r0TFfe+01+vbtS58+fXj++edDyx988EH69+/PTTfdRCAQAODGG2/krLPOYtasWaHtPB4PvXr1Iikpid///vcn3AYiIiJSf50W4bWgoIht2w5QUFB0XPvHxsbi8XjweDx07Ngx9LvL5SqzXU3Ca2WefPJJ2rZty8qVK/F6vTz00EOhkJqamkpOTg45OTkcPnyY6dOnh/b75JNPWLVqFU8//TQlJSWh5du2baNRo0asXLmS5s2bh5YfOXLkmOtW3v3338+bb75ZZtnDDz/M3LlzWbFiBa+88gqFhYUsWbKEbt264fV6GTFiBG+//TZFRUW8/PLLeL1eJk2axOTJk2t0zIEDB7J69WrWrl3LokWL2LNnD+vXr2fv3r2sWrWKCy64gMWLFwMwdepUpkyZUmb/qVOn8vbbb7N27VqWLFlS4UuHiIiInD4iPrzm5e1i/HgvkyatZvx4Lxs27Dop5QYCAUaPHo3b7WbYsGHk5+czc+ZMcnJySElJYdOmTTzwwAOkpKTQu3dv8vLyqixr8eLFPPDAA6HHnTt3Jj4+vsw2xhgmTZoUCmmlmjRpQsuWLfH5fKFl9913H6tWrWL06NEsX76c4cOHM3z4cN5++22WLVtGnz596N27N3PnzgXghhtu4Pbbb8ftdnPPPffw+OOPk5yczIMPPlihrueccw7GmDLLdu/ezfnnn09MTAytW7dm48aNdOjQgYKCAgB8Ph8tW7bkX//6F507d8bhcJCcnExubm6N2vr888/HGIMxBofDQXR0NGvXrmXIkCEADB06lDVr1gDQqlWrCvtfcskl7Nu3j6KiIhwOB7GxsTU6roiIiESeiA6vBQVFZGXl4nLFkJDQFJcrhhkzco+7BzbcwoULad++PV6vl5EjR5KVlcWdd95JamoqHo+H9u3bM3nyZDweDzNnziQzM7PKsgKBADEx9o0dfv3rX9OlSxe8Xm+F7Ro3bsyhQ4fKLPvpp5/Yu3cvZ5xxRmjZ1KlTSU1NZf78+QD4/X4++OADbrjhBh555BE++ugjVq5cSWZmJoWFhYDdu+n1evniiy/o1asXK1euZMWKFaHT8dVp3bo1X375JQcOHGDdunX4fD4uvPBCvvzySxITE5k/fz5XXXUVPp+PZs2aAXYYL+1drqlFixaRmJhIfHx8mbKaN29e7S3TRowYwdVXX81FF13E4MGDFV5FREROYxEdXn2+QgKBElwuO6y4XLEEAiX4fIUnXPbmzZvp2bMnAL1792bTpk0Vtpk6dSr9+vXjvvvuY/v27VWWFRMTEwqJ8+bN48orr6wQUsEeG9uoUaPQ4yFDhnDdddcxffr0Cr2h4Xr06BFab4zhjDPOIC4ujvbt27Njxw7A7u0FO4iW/n722Wezf//+atsBYNq0aTzyyCOMGTOGSy+9lHPOOYc33niDX/3qV/z973/n0UcfZfLkybRo0SJUnmVZFa6Cnzt3LikpKTz88MMVjvHVV1+RlZXFCy+8AFCmLJ/PVya8lzd+/HhWr17Npk2bWL9+Pd98881Rn5OIiIhEpogOr/HxcTgc0fj9dk+r31+EwxFNfHzcCZfdvn171q9fD8C6devo0KEDDocjNPZ0586dLFu2jL/+9a+89NJLWJZVZVkjR44s0zNbWY+kZVlMnjyZESNGhJZ98skneL1e0tLSqq1rVNTPL6NlWezdu5eioiI2bdrEOeecA1Am/Ib/Xl29S3Xo0IGlS5cyf/58YmJi6NixI0AoUJb2lHbs2JG8vDwCgQArV66kW7duZcq58cYb8Xg8PPvss2WWb9u2jbvuuou33norFN779OnDJ598AkB2djaXX355lfWLjo6mefPmREVF4XK5ahTIRUREJDLV60kKjsbpjCUjowszZuSSn1+IwxFNRkYXnM4TP2187bXX8v7775OcnEzTpk156623aNasGfv27SM9PZ2pU6fSokULUlJSSEpKqrasxx9/nIceeoh+/frhcrlo2bIl3bp1Y//+/eTk5JCamkpJSUloTOqJmDx5MldccQVg90jGxR1bkH/hhRd466232Lt3Lz/++CN/+tOfeP3113nrrbdwOBxMnToVYww33XQTo0ePZv78+ZSUlDB79mxiY2O59957cbvdNGrUKDTm9mgmTZrErl27GD16NGDffaBnz56cccYZ9O/fn/POO49HHnkEgIceeogPP/wQy7L47rvvmDp1Ko8//jhDhw4lOjqaSy+9lB49ehzTcxYREZHIYWrS83aq9OjRw/r8889Djzdu3MjFF1981P0KCorw+QqJj487KcFVJNLU9LMiIiJSV4wxX1iWdcI9TBHd81rK6YxVaBURERFpACJ6zKuIiIiINCwKryIiIiISMRReRURERBqAE52RtL44Lca8ioiIiEjV8vJ2kZWVSyBQEro7U6dOLeu6WsdFPa9Bq1evZsCAAaSkpOB2u3nvvfcAGDt2LD179mTQoEGkpaXx5ZdfAuDxeEhISMDtdjNw4EB2795dprzs7Gy6du0auun+yTJnzhxeeeWV0OOJEyfi8Xiq3P43v/lNqL7HcvP+Pn36VFg2YcIELr/8cpKSknj88cdD9SkqqvobXG5uLp999lmNj1uVLVu2kJ6efsLl1JbRo0ezZcuWMssOHz7MPffcQ//+/enbty+PPfYYQKW38pozZw5r1649FVUVEZEGpjZnJK0Lp0XPa0HJEXwlJcRHR+OMPvY8vmfPHu666y6WLl1Kq1atCAQChN+ya/bs2SQmJvL9998zcuTIUFgcNWoU06ZNIzMzk1dffZVHH300tM+iRYt444036Nq1a2jZkSNHykwocCq8+uqrgB1ee/TowYUXXnhc5fzjH//g+++/Z/Xq1QDk5+cDduhKT0+vckrW3Nxc/H4/vXr1Oq7jRrKnn36aVq1aMX36dABWrFhR5bZjx449RbUSEZGG5ucZSZsA9oyk+fmF+HyFEXm3pojvec07eIjx27Yz6ccdjN+2nQ0HK067ejRLlixhxIgRtGrVCgCHw1HpxAPt2rVj2LBh/PWvfy2zPDExkR9++CH0OCcnhw8++IDbb7+dJUuWkJKSwvjx47niiisoLi5mzJgxuN1u0tLS2Lt3L1u2bCEpKYn09HQuueQSFi1axMiRI+ncuTMbN26s0XPweDwMHTqUq6++mssuu4wNGzYAdi/foUOHmDNnDg8//DC33HILlmVxzz33MGDAAAYPHhyq+zPPPENSUhJ33313aCaxUo0aNWLz5s18/fXXgD1969q1a8nNzeWKK67gpZdeYtmyZaSmptKrVy+mTJkCwMyZM3nppZdCEyc888wzuN1ukpOT2bBhA0VFRVx55ZWhZYcPHz7qc33++edJTU2le/fuLFu2DLDD3x133EFqaio333wzABs2bCA1NZW+ffty9913V9tOpXbu3MmgQYNITk4mPT2dkpIStmzZQt++fUlPT6dz584sX74csGdA69q1K+np6ezcubNCPd977z3Gjx8fejxgwADA/hJz55130rt379BsY0888QQffvhhlceq7DmLiIjURG3OSFoXIjq8FpQcIWv3HlxRUSTEOnBFRTFj9x4KSo4cUzk//vhjKLjm5OSQkpLC8OHDK922devWbN++vcyyVatWhaZMBUhNTWXo0KHMnj2bYcOGAZCWlkZ2djaLFy+mbdu2eL1eRo0aFeqVy8/PZ8GCBUyfPp3JkyezcOFCnn766RrPUgUQCAT44IMPmDZtGrNnzw4tb9y4MWPHjuXZZ59l9uzZLFmyhBYtWrBixQqmTJnClClT2LFjB9nZ2axZs4Z7772XPXv2lCn7ggsuYOLEidxxxx107NiR//3f/yUpKYkuXbrw8ccfc99993H55ZeTk5PDunXreP/99zl06BB33nkn9913Hx9//DEbNmzg66+/xuv18s477zBp0iS2bt1Ko0aN8Hq9eL3e0PSw1cnIyCAnJ4fs7GyeeeaZ0PJu3bqRk5NDXFwcHo+H9u3b8+mnn7JmzRq2b9/Ot99+W207gR3Kly5dysqVK2nbti05OTmA3Ts/f/583nvvPbKysgB7ZrBPP/2UefPm8f3331eoZ2FhYaUznPl8PiZOnMjatWuZP39+hfWVHauq5ywiInI0pTOS+v3FbN16AL+/+KTNSFoXInrYgK+khIBl4QoOFXBFR5FfUoKvpOSYhg+0bt06FGxSU1NJTU2tcorR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0SLeeOMNHnzwwdCyI0eOHFf9ylu9enVoYoVjVVl4tSyr2skQACZOnMj5559f4+McOHCABQsWsHbtWlavXs1zzz13TPXs0qULd9555zHtczJ079499MVl0aJFdOvW7ZjLKP9eEBGR+qegoIht2w5EzGl3pzOWjIwu+P3FbN16AL+/mIyMLg3yoq1anWHLsqzHLcu6yLKsRMuybrQs66T3bedtzWP8O+OZ9MEkxr8zng0/bDjmMpYsWcKIESNo1aoVAA6Hg6SkpArbtWvXjmHDhvHXv/61zPLExER++OGH0OOcnBw++OADbr/9dpYsWUJKSgrjx4/niiuuoLi4mDFjxuB2u0lLS2Pv3r1s2bKFpKQk0tPTueSSS1i0aBEjR46kc+fObNxYsbP63Xff5b777qOwsBC/3w/YPcR///vfATtoejwe1q5dS69evXC73UyaNInFixeHbu6/YMECxo4dy5133smgQYPYu3cvQ4YMISUlhcGDB1eYOKG0/J07dzJo0CCSk5NJT0+vcjayqKgo9uzZQ25uLpZlhW7FNXbsWO644w5SU1O5+eabAdiwYQOpqan07duXu+++G7B7QSdMmABAt27duPPOO+nduzfPPvtshWNNmDCBlJQUevXqRW5uLgApKSncf//9JCcnc9dddwHg8/kYMmQIQ4cO5d1336203v379w+9vsuXL2fQoEGhdc888wxut5vk5GQ2bNjAwYMH6devH7t37yY7O5tx48YBP/dWb9q0iYEDB+J2u/ntb38L2DOcJSUl0bdvX7744otK6yAiIrUrL28X48d7mTRpNePHe9mwYVddV6lGOnVqSWamm6eeupzMTHeDvFgLInx62ILCArI8WbgauUg4IwFXIxczVsw45h7YH3/8MRRcc3JySElJYfjw4ZVu27p169A0sqVWrVpFx44dQ49TU1MZOnQos2fPZtiwYYA9BW12djaLFy+mbdu2eL1eRo0axfTp0wHIz89nwYIFTJ8+ncmTJ7Nw4UKefvpp5s6dW+ZYlmXx9ddfc+mll3LNNdewZMmSKp/XRx99xKRJk/B6vTzxxBOMGDGCjh074vF4GDVqFGAHrU8//ZQzzzyTDz74AI/Hw1VXXcWCBQsqLbNFixYsXbqUlStX0rZtW3Jycirdzul0MnPmTB599FHat2/Pa6+9FlrXrVs3cnJyiIuLw+Px0L59ez799FPWrFnD9u3b+fbbb8uU5fP5mDhxImvXrmX+/PkVjvXUU0/h8Xh47bXXeP7550PLR44cycqVK8nLy2Pfvn289tprpKens3TpUs4555xK6x0VFUWrVq346quvaNasGbGx9jfaDRs28PXXX+P1ennnnXeYNGkSTZo04fnnn2fcuHE8/fTTZGZmlinrt7/9LdOmTcPr9fLcc8+xY8cO/vKXv7B69Wreeustfve731VaBxERqT2RfuGT0xlLmzZNG2SPa6mIDq++gz4CJQFccfYUn644F4GSAL6DvmMqp3Xr1mzbtg2wg6fH46kQUEtt3749FHQXLFiA2+3mP//5T6jXrSo9e/YEYPPmzaHfe/fuzaZNmwC49NJLiY6Opk2bNiQmJhIVFUWbNm3Iz88vU86aNWvYvHkzQ4cOZe7cubz//vsA2MOKbaVDADIyMli2bBk33XQTS5curbZeBQUFjBs3juTkZF577bUqn//evXtJT0/H7Xbz4YcfVrkdwKBBg/joo4/Izc1lxowZoV7i7t27h/7dvHkzW7ZsIS0tDbfbzeeff16hzBYtWtCuXTuioqJo3LhxheNkZmbSr18/7r777jL7du3aFYBzzz0Xn8/Hpk2bQsfu1atXlfUeOXIk//3f/80111wTWrZx40bWrFlDSkoKo0ePDvVMJyUlsX37dq666qrQdLulfvjhh1AdoqKi2LJlC5dddhlRUVH88pe/ZN++fVXWQUREaocufIp8ER1e45vE44h24C+0Q5G/0I8j2kF8k/hjKqd0/Ghp8KnqVPjWrVtZsmQJ/fv3B34e8/rmm2/idDqrPUZUlN3U7du3Z/369QCsW7eODh06AGXDZ2VBtNS7777LO++8w9KlS8nJycHv91NQUECLFi3YunUrQOiisubNm/PSSy/x2muvhXr5wssOr9fSpUtp3bo1K1eu5LbbbqtyDOy8efMYMmQIXq+XK6+8MrRd+LAJsKeJLa2Py+WiUaNGoXVfffVV6N8LLriArKws7rnnHrxeLz169Khw7PJ1Drdnzx4+/PBDVq1axSuvvFJm3/Lt2L59+9Cxw6chLm/AgAF07tyZoUOHhpZddNFFuN1uPB4PHo8n9GXgzTffJCUlhY8//pidO3eWKSchIYG//e1vgD3e+bzzziM3N5cjR47w3XffER9/bO9TERE5cbrwKfLV9gxbtcoZ5yRjQAYzVswgvyAfR7SDjAEZOOOqD5LlnXnmmcyaNYsxY8ZgjCEmJob7778/tP6WW26hefPmOBwOZs2aRdOmTY+7ztdccw2LFi0iOTkZp9PJvHnzKowvrYplWeTk5JS5g0FSUhIfffQRY8eO5cYbb2TmzJk4HA7AvnBo0aJFFBQUMHbsWMAOZsOHD6/QU9ynTx8mT57MsGHDaNWqFeeee26ldRg4cCA33ngj2dnZOJ1OOnfuDMB1113H2rVrQ9sFAgFuueUWDh8+TElJCWPGjMHlsnvIP/vsM+bNm0fbtm1JSUmhqKiIBx54gNdff73KLw5VadGiBWeffTYDBgygb9/q78R22223cf311/Puu+/SunVr2rVrV+l2MTEx/OlPfyqzrHPnznTo0AG3201UVBSDBw/mpptu4o033mDZsmXk5eVx9913lxlLO3XqVMaNG4dlWfTu3ZvnnnuOq6++mssvvxxjTGjIiIiInDqlFz7NmJFLfn5h6Gb/Dfk0fKQxR7vK/FTq0aOHFd4jtnHjRi6++OKj7ldQWIDvoI/4JvHHHFzlxP3000+8/PLL/P73vz/qtmPHjmXChAkkJiaegpo1HDX9rIiIiE3TrJ56xpgvLMvqcaLlRHTPaylnnFOhtQ794he/qFFwFRERqS+czliF1gh1WoRXiRxz5syp6yqIiIhIBKv3F2zVp2ENIvWRPiMiItKQ1Ovw6nA4OHz4cF1XQ6ReO3z4cOgiPRERkdNdvR42cNZZZ7Fly5a6roZIvVd672ERkYZEF101TPU6vMbHx+temCIiIlJBXt4usrJyCQRKQre7aqjTpTY09XrYgIiIiEh5kT7Fq5wYhVcRERGJKJritWFTeBUREZGIoileGzaFVxEREYkopVO8+v3FbN16AL+/WFO8NiD1+oItERERkcp06tSSzEy37jbQACm8ioiISETSFK8Nk4YNiIiIiEjEUHgVEREROYUKCorYtu2Abu11nDRsQEREROQU0eQKJ049ryIiIiKngCZXODkUXkVERKTONKRT6Jpc4eTQsAERERGpEw3tFHr45AouV6wmVzhO6nkVERGRUy6ST6Efb2+xJlc4OdTzKiIiIqfcz6fQmwD2KfT8/EJ8vsJ6HeZOtLdYkyucOPW8ioiIyCkXfgodiIhT6Cert9jpjKVNm6YKrsdJ4VVEREROuUg8ha4LruoHDRsQERGROhFpp9B1wVX9oJ5XERERqTORdAo9EnuLT0fqeRURERGpoUjrLT4dKbyKiIjICSkoKGpQYc7pjG0Qz7O+UngVERGR49bQJhqQuqcxryIiInJcInmiAYlcCq8iIiJyXHTrKKkLCq8iIiJyXCJxogGJfAqvIiIiclx06yipC7pgS0RERI6bbh0lp5rCq4iIiJwQ3TpKTiUNGxARERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiIhIxFB4FREREZGIofAqIiIiIhFD4VVEREREIobCq4iIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURERCRiKLyKiIiISMRQeBURERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiAgFBUVs23aAgoKiuq6KSLVi6roCIiIiUrfy8naRlZVLIFCCwxFNRkYXOnVqWdfVEqmUel5FREQasIKCIrKycnG5YkhIaIrLFcOMGbnqgZV6S+FVRESkAfP5CgkESnC5YgFwuWIJBErw+QrruGYilVN4FRERacDi4+NwOKLx++2eVr+/CIcjmvj4uDqumUjlFF5FREQaMKczloyMLvj9xWzdegC/v5iMjC44nbF1XTWRSumCLRERkQauU6eWZGa68fkKiY+PU3CVek3hVURERHA6YxVaJSJo2ICIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiNQjBQVFbNt2QDNciVRBdxsQERGpJ/LydpGVlUsgUILDEU1GRhc6dWpZ19USqVfU8yoiIlIPFBQUkZWVi8sVQ0JCU1yuGGbMyFUPrEg5Cq8iIiL1gM9XSCBQgstl32vV5YolECjB5yus45qJ1C8KryIiIvVAfHwcDkc0fr/d0+r3F+FwRBMfH1fHNROpXxReRURE6gGnM5aMjC74/cVs3XoAv7+YjIwumvVKpBxdsCUiIlJPdOrUksxMNz5fIfHxcQquIpVQeBUREalHnM5YhVaRamjYgIiIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQihsKriIiIiESMWg2vxph4Y8xCY8y/jDEbjTFJtXk8ERERETm91fb0sC8BSy3LSjfGxAJNavl4IiIiDVZBQRE+XyHx8XGaYlZOW7UWXo0xzYBkYCyAZVlFQFFtHU9ERKQhy8vbRVZWLoFACQ5HNBkZXejUqWVdV0vkpKvNYQO/BHYBs40xXxljXjPGOMtvZIy53RjzuTHm8127dtVidURERE5PBQVFZGXl4nLFkJDQFJcrhhkzcikoUJ+RnH5qM7zGAN2AmZZldQUKgInlN7Is64+WZfWwLKtHy5b6higiInKsfL5CAoESXC57qIDLFUsgUILPV1jHNRM5+WozvP4A/GBZ1rrg44XYYVZEREROovj4OByOaPx+u6fV7y/C4YgmPj6ujmsmcvLVWni1LGsHsNUY0zG4aCDwz9o6noiISEPldMaSkdEFv7+YrVsP4PcXk5HRRRdtyWmptu82cA8wL3inge+AW2r5eCIiIg1Sp04tycx0624Dctqr1fBqWVYu0KM2jyEiIiI2pzNWoVVOe5phS0REREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURETrKCgiK2bTugGa5EakFt3ypLRESkQcnL20VWVi6BQAkORzQZGV3o1EkzSIqcLOp5FREROUkKCorIysrF5YohIaEpLlcMM2bkqgdW5CRSeBURETlJfL5CAoESXC77XqsuVyyBQAk+X2Ed10zk9KHwKiIicpLEx8fhcETj99s9rX5/EQ5HNPHxcXVcM5HTh8KriIjISeJ0xpKR0QW/v5itWw/g9xeTkdFFs16JnES6YEtEROQk6tSpJZmZbny+QuLj4xRcRU4yhVcREZGTzOmMVWgVqSUaNiAiIiIiEUPhVUREREQihsKriIiIiEQMhVcRERERiRgKryIiIiISMRReRURERCRiKLyKiIiISMRQeBURERGRiKHwKiIiIiIRQ+FVRERERCKGwquIiIiIRAyFVxERERGJGAqvIiIiIhIxFF5FREREJGIovIqIiIhIxFB4FREREZGIofAqIiIiIhFD4VVEREREIobCq4iIiIhEDIVXEREREYkYCq8iIiIiEjEUXkVEREQkYii8ioiIiEjEUHgVERERkYih8CoiIiIiEUPhVUREREQi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\n",
      "text/plain": [
       "<Figure size 1800x1440 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "import pylab as plt\n",
    "\n",
    "'''x = np.random.randint(low=1,high=5,size=50)\n",
    "y = np.random.randint(low=0,high=2,size=50)\n",
    "jittered_y = y + 0.1 * np.random.rand(len(y)) -0.08\n",
    "jittered_x = x + 0.1 * np.random.rand(len(x)) -0.08'''\n",
    "\n",
    "fig = plt.figure()\n",
    "\n",
    "ax0 = fig.add_subplot(2, 2, 1)\n",
    "'''ax1 = fig.add_subplot(2, 2, 2)\n",
    "ax2 = fig.add_subplot(2, 2, 2)\n",
    "ax3 = fig.add_subplot(2, 2, 2)'''\n",
    "\n",
    "df_gdp_tal.plot(kind='scatter', x='year', y='total', figsize=(25, 20), color='darkblue',alpha=0.5, ax=ax0, label='Total GDP from 1980 - 2018')\n",
    "ax0.set_xlabel('Year')\n",
    "ax0.set_ylabel('GDP(current US$)')\n",
    "\n",
    "df_gdp_tal2.plot(kind='scatter', x='year', y='total', figsize=(25, 20), color='#00CED1',alpha=0.5, ax=ax0, label='GDP from United States, Japan and China')\n",
    "\n",
    "df_gdp_tal3.plot(kind='scatter', x='year', y='total', figsize=(25, 20), color='firebrick',alpha=0.5,ax=ax0, label='GDP from India, Italy and Brazil')\n",
    "\n",
    "df_gdp_tal4.plot(kind='scatter', x='year', y='total', figsize=(25, 20), color='darkgreen',alpha=0.5, ax=ax0, label='GDP from Australia, Spain and Mexico')\n",
    "ax0.set_title ('Comparism total gdp and Top rankings of countries')\n",
    "\n",
    "plt.legend(loc='upper left');\n",
    "\n",
    "plt.show()"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.4"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
