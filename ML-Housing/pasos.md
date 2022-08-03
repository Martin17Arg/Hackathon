# Pasos

1) EDA: Tipos de datos, valores faltantes (aun no se modifica nada)

Columnas
```
#   Column         Non-Null Count  Dtype        Tipo
---  ------         --------------  -----      -------
 0   Id             1460 non-null   int64   
 1   MSSubClass     1460 non-null   int64       cat
 2   MSZoning       1460 non-null   object      cat
 3   LotFrontage    1201 non-null   float64     num (correlacionar con LotArea?)
 4   LotArea        1460 non-null   int64       num
 5   Street         1460 non-null   object      cat (2)
 6   Alley          91 non-null     object      cat (muchos nulos)
 7   LotShape       1460 non-null   object      cat (4)
 8   LandContour    1460 non-null   object      cat (4)
 9   Utilities      1460 non-null   object      cat / ordinal (1 a 4 servicios)
 10  LotConfig      1460 non-null   object      cat (5)
 11  LandSlope      1460 non-null   object      cat (3) / ordinal
 12  Neighborhood   1460 non-null   object      cat (muchos)
 13  Condition1     1460 non-null   object      cat (muchos) -> Combinar
 14  Condition2     1460 non-null   object      cat (relacionado con anterior)
 15  BldgType       1460 non-null   object      cat (5)
 16  HouseStyle     1460 non-null   object      cat (7)
 17  OverallQual    1460 non-null   int64       ordinal (10: best, 1:worst)
 18  OverallCond    1460 non-null   int64       ordinal (10: best, 1:worst)
 19  YearBuilt      1460 non-null   int64       Date(YYYY)
 20  YearRemodAdd   1460 non-null   int64       Date(YYYY)
 21  RoofStyle      1460 non-null   object      cat (6)
 22  RoofMatl       1460 non-null   object      cat(8)
 23  Exterior1st    1460 non-null   object      cat(muchos)
 24  Exterior2nd    1460 non-null   object      cat(adicional al anterior)
 25  MasVnrType     1452 non-null   object      cat - Nan validos
 26  MasVnrArea     1452 non-null   float64     cat(relacionado al anterior)
 27  ExterQual      1460 non-null   object      cat / ordinal
 28  ExterCond      1460 non-null   object      cat / ordinal
 29  Foundation     1460 non-null   object      cat (6)
 30  BsmtQual       1423 non-null   object      cat / ordinal - Nan validos
 31  BsmtCond       1423 non-null   object      cat / ordinal - Nan validos
 32  BsmtExposure   1422 non-null   object      cat / ordinal - Nan validos
 33  BsmtFinType1   1423 non-null   object      cat / ordinal - Nan validos
 34  BsmtFinSF1     1460 non-null   int64       num - Nan validos (fill with 0)
 35  BsmtFinType2   1422 non-null   object      cat / ordinal - Nan validos
 36  BsmtFinSF2     1460 non-null   int64       num - Nan validos (fill with 0)
 37  BsmtUnfSF      1460 non-null   int64       num
 38  TotalBsmtSF    1460 non-null   int64       num (engloba al resto?)
 39  Heating        1460 non-null   object      cat (6)
 40  HeatingQC      1460 non-null   object      cat (5) / ordinal
 41  CentralAir     1460 non-null   object      cat (2)
 42  Electrical     1459 non-null   object      cat (5)
 43  1stFlrSF       1460 non-null   int64       num
 44  2ndFlrSF       1460 non-null   int64       num
 45  LowQualFinSF   1460 non-null   int64       num
 46  GrLivArea      1460 non-null   int64       num
 47  BsmtFullBath   1460 non-null   int64       num
 48  BsmtHalfBath   1460 non-null   int64       num
 49  FullBath       1460 non-null   int64       num
 50  HalfBath       1460 non-null   int64       num
 51  BedroomAbvGr   1460 non-null   int64       num
 52  KitchenAbvGr   1460 non-null   int64       num
 53  KitchenQual    1460 non-null   object      cat (5) / ordinal
 54  TotRmsAbvGrd   1460 non-null   int64       num
 55  Functional     1460 non-null   object      cat (8) / ordinal
 56  Fireplaces     1460 non-null   int64       num
 57  FireplaceQu    770 non-null    object      cat / ordinal
 58  GarageType     1379 non-null   object      cat - Nan validos
 59  GarageYrBlt    1379 non-null   float64     Date (YYYY)
 60  GarageFinish   1379 non-null   object      cat (4) / ordinal - Nan validos
 61  GarageCars     1460 non-null   int64       num
 62  GarageArea     1460 non-null   int64       num
 63  GarageQual     1379 non-null   object      cat (6) / ordinal
 64  GarageCond     1379 non-null   object      cat (6) / ordinal
 65  PavedDrive     1460 non-null   object      cat (3)
 66  WoodDeckSF     1460 non-null   int64       num
 67  OpenPorchSF    1460 non-null   int64       num
 68  EnclosedPorch  1460 non-null   int64       num
 69  3SsnPorch      1460 non-null   int64       num
 70  ScreenPorch    1460 non-null   int64       num
 71  PoolArea       1460 non-null   int64       num
 72  PoolQC         7 non-null      object      cat / ordinal (muchos nulos->Drop)
 73  Fence          281 non-null    object      cat (5) - Nan validos
 74  MiscFeature    54 non-null     object      cat (6)
 75  MiscVal        1460 non-null   int64       num
 76  MoSold         1460 non-null   int64       Date (MM)
 77  YrSold         1460 non-null   int64       Date (YYYY)
 78  SaleType       1460 non-null   object      cat (10)
 79  SaleCondition  1460 non-null   object      cat (6)
 80  SalePrice      1460 non-null   int64       num
 ```

2) Separar set de train y test.

