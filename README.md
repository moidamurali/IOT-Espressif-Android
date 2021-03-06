<b>ESPRSSIF MIT License</b>

Copyright © 2015 <ESPRESSIF SYSTEMS (SHANGHAI) PTE LTD>

Permission is hereby granted <b>for use on ESPRESSIF SYSTEMS ESP8266 only, in which case, it is free of charge,</b> to any person obtaining a copy of this software and
associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute,
sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

<b>乐鑫 MIT 许可证</b>

版权 © 2015  <乐鑫信息科技（上海）有限公司>

<b>该许可证授权仅限于乐鑫信息科技 ESP8266 产品的应用开发。</b>在此情况下，该许可证免费授权任何获得该软件及其相关文档（统称为“软件”）的人无限制地经营该软件，包括无限制
的使用、复制、修改、合并、出版发行、散布、再授权、及贩售软件及软件副本的权利。被授权人在享受这些权利的同时，需服从下面的条件：

在软件和软件的所有副本中都必须包含以上的版权声明和授权声明。

该软件按本来的样子提供，没有任何明确或暗含的担保，包括但不仅限于关于试销性、适合某一特定用途和非侵权的保证。作者和版权持有人在任何情况下均不就由软件或软件使用引起的以合同形式、民事侵权或其它方式提出的任何索赔、损害或其它责任负责。

=============================USER MANUAL=================================

IOT_Espressif_Android source code is used to control ESP8266 device by

Android pad or phone. It support local and online. More info about how

to use the Android apk, please follow the step:

1. install the apk by source code

2. register an espressif account or skip ( register automatically )

3. tap the "question mark" button on the top right corner,

   it will tell you how to use it step by step

4. tap the "setting" button at the bottom, you could set your own

   preference and see change logs.

5. enjoy yourself

==================================v0.9.2==================================

1. Esptouch Demo version is v0.2.1

    ( The indepedent Esptouch Demo, please refer to
     
     https://github.com/EspressifApp/EsptouchForAndroid )

2. How to use python and log4j to turn on/off log

    2.1 cd PROJECT_DIR/python 
    
        PROJECT_DIR means the directory of the project where contains '.project'

    2.2 python xml_file_search.py

        ( generate log4j.xml )

    2.3 vi log4j.xml and modify it as you like

        ( Our log4j support "OFF FATAL ERROR WARN INFO DEBUG TRACE ALL"
     
        Besides, we support "IGNORE" which means its level is depended upon

        its parent's level. ) 

    2.4 python xml_parse.py 
    
        ( it will change InitLogger.java according to log4j.xml automatically )
3. DB

    We use greendao as our ORM database
    
    ( More info about greendao, please refer to 
      
      https://github.com/greenrobot/greenDAO and http://greendao-orm.com/ )

4. The framework of the source code

        The layer of our source code are seperated as:

        UI, INTERFACE, TYPE, MODEL, ACTION, COMMAND, BASE, OPEN, DB, DB-gen, UTIL, LOG, ESPTOUCH

    4.1 UI:

        UI layer is just the UI, it shouldn't contain complex business logical.

    4.2 INTERFACE:

        INTERFACE layer contains the interfaces, it defines the interface to be implemented.

    4.3 TYPE:

        TYPE layer contains the property type, including device's type, device's state,

        device's status, device's timer and etc.

    4.4 MODEL:

        MODEL layer contains various models. The differece between TYPE and MODEL is that

        TYPE just stores the property but model contains business logical.

    4.5 ACTION:

        ACTION layer contains various actions. The action is based upon command.

        ACTION = COMMANDS + BUSINESS LOGICAL

    4.6 COMMAND:

        COMMAND layer contains various commands. The command is the basis of action.

        COMMAND is pure command without any logical.

    4.7 BASE:

        BASE layer is the basic layer, which is the base of the iot espressif apk.

    4.8 OPEN:

        OPEN layer is used to store open api and source code, such as zxing, from others.

    4.9 DB:

        DB layer is used to make the intermediate layer between DB-gen and upper layer.

    4.10 DB-gen:

        DB-gen layer is generated by greendao to implement ORM.

    4.11 UTIL:

        UTIL layer contains various utilities classes.

    4.12 LOG:

        LOG layer is the layer about logging. Log4j is used at present.

    4.13 ESPTOUCH:

        ESPTOUCH layer contains the source code of esptouch. ESPTOUCH layer is an indepent layer.

        At present, only UI layer depends upon it. And it is just used to display a ESPTOUCH demo.


