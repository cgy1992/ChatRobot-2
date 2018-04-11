# A simple chart robot

This is a chart robot collectiong data corpus from tieba.baidu.com, the world's largest chinese forum.

Some algorithms are implemeted :
**maximum probability word segmentation model,Bayes classifier, SVM.**
The dictionary for probability word segmentation is get from [sougou input](https://pinyin.sogou.com/dict/).

### How to add this robot as a friend
~~please scan the QR code using the Wechat.~~


### Building
you need a web server which can run servlet and a wechat subscription account and enable the develop model
TOMCAT server
MYSQL database

 1. import hte tieba.sql structure to your database.
 2. deploy the web directory to the tomcat server. config the
    web.xml,add the database name and the password to the web.xml
 3. add the word dic and the stopword to the sys

   ` java -jar xx.jar insertWords`
   ` java -jar xx.jar insertStopWords`

 4. train the classifier

    `java -jar xx.jar DEBUG <URL> <FirstPage> <LastPage> <Class>`

 5. collect the FAQ Corpus

  `java -jar xx.jar COLLECT <URL> <FirstPage> <LastPage>`

 6. build the invert index

 `java -jar xx.jar BUILDINDEX`

 7. change the wechat account to the develop mode,add your tomcat url

    [http://your.url.here/index.jsp](http://your.url.here/index.jsp) to
    the wechat API.note change the token to yours.
 8. restart the tomcat and enjoy it
