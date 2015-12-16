# 好的开始

## iPython是个好东西

```python
import numpy as np
import pandas as pd
import pandas.io.data as web


goog = web.DataReader('GOOG', data_source='google', start='3/14/2009', end='4/14/2014')
goog.tail()
goog['Log_Ret'] = np.log(goog['Close'].shift(1))
goog['Volatility'] = pd.rolling_std(goog['Log_Ret'], window=252) * np.sqrt(252)

%matplotlib inline
goog[['Close', 'Volatility']].plot(subplots=True,color='blue',figsize=(8,6))
```


## 准备酷炫之前
```bash
gosber@freedamadeMBP  ~  vim ~/.ipython/profile_default/ipython_config.py
 gosber@freedamadeMBP  ~  cat ~/.ipython/profile_default/ipython_config.py
c.InteractiveShellApp.matplotlib = 'inline'
```
## 再往前一点，别忘记
```bash
gosber@freedamadeMBP  ~  pip3 install  matplotlib
Collecting matplotlib
  Downloading matplotlib-1.5.0-cp35-cp35m-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl (49.6MB)
    100% |████████████████████████████████| 49.6MB 12kB/s
Requirement already satisfied (use --upgrade to upgrade): pyparsing!=2.0.0,!=2.0.4,>=1.5.6 in /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (from matplotlib)
Collecting cycler (from matplotlib)
  Downloading cycler-0.9.0-py2.py3-none-any.whl
Requirement already satisfied (use --upgrade to upgrade): python-dateutil in /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (from matplotlib)
Requirement already satisfied (use --upgrade to upgrade): pytz in /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (from matplotlib)
Requirement already satisfied (use --upgrade to upgrade): numpy>=1.6 in /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (from matplotlib)
Requirement already satisfied (use --upgrade to upgrade): six in /Library/Frameworks/Python.framework/Versions/3.5/lib/python3.5/site-packages (from cycler->matplotlib)
Installing collected packages: cycler, matplotlib
Successfully installed cycler-0.9.0 matplotlib-1.5.0
 gosber@freedamadeMBP  ~  pip3 install  inline
Collecting inline
  Downloading inline-0.0.1.tar.gz
Installing collected packages: inline
  Running setup.py install for inline
Successfully installed inline-0.0.1
```

## 总结一下
1. 别忘记安装这两个东东：
  * matplotlib
  * inline
2. 别忘记把inline模式设置一下，或者：

```python
  In [1]: %pylab inline
UsageError: Invalid GUI request u'inline', valid ones are:[None, 'osx', 'qt4', 
'glut',   'gtk3', 'pyglet', 'wx', 'none', 'qt', 'gtk', 'tk']
In [2]: %matplotlib inline 
UsageError: Invalid GUI request u'inline', valid ones are:  [None, 'osx', 'qt4',
'glut', 'gtk3', 'pyglet', 'wx', 'none', 'qt', 'gtk', 'tk']`
```

3. 等着看酷炫的效果图吧




