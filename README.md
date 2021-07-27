# 20210727

1. CSV: Comma-separated values
1> 읽기

      iphone_df = pd.read_csv('data/iphone.csv)
      type(iphone_df) // pandas.core.frame.DataFrame
      
      iphone_df = pd.read_csv('data/iphone.csx', header=None)
      iphone_df = pd.read_csv('data/iphone.csv', index_col=0)
      
#1
      
      import pandas as pd
      
      names_df = pd.read_csv('data/popular_baby_names.csv')
      names_df

#2

      import pandas as pd

      df = pd.read_csv('data/mega_millions.csv', index_col=0)

      df

2. DataFrame 인덱싱
1> .loc[row, coloumn]

      iphone_df.loc['iPhone 8, '메모리'] // '2GB'
      iphone_df.loc['iPhone X', :] // 출시일, 디스플레이, 메모리, 출시 버전 모든 coloumn에 대한 정보 출력
      iphone_df.loc['iphone X'] // 위와 동일
      type(iphone_df.loc['iPhone X']) // pandas.core.series.Series
      
      iphone_df.loc[:, '출시일'] // 모든 row에 대한 출시일 출력
      iphone_df['출시일'] // 위와 동일 (loc 없음)
      
#1

      import pandas as pd

      df = pd.read_csv('data/broadcast.csv', index_col=0)

      df.loc[2016, 'KBS']
#2
      
      import pandas as pd
      
      df = pd.read_csv('data/broadcast.csv', index_col=0)

      df.loc[:, 'JTBC']

#3

    import pandas as pd

    df = pd.read_csv('data/broadcast.csv', index_col=0)

    df.loc[:, ['SBS', 'JTBC']]
    
#4

    import pandas as pd

    samsong_df = pd.read_csv('data/samsong.csv')
    hyundee_df = pd.read_csv('data/hyundee.csv')

    samsong_file = samsong_df.loc[:, '문화생활비']
    hyundee_file = hyundee_df.loc[:, '문화생활비']
    day_file = samsong_df.loc[:, '요일']
    final_file = {'day': day_file, 'samsong': samsong_file, 'hyundee': hyundee_file}
    pd.DataFrame(final_file)
