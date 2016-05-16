# cppPlotGL
Keisuke Sugawara

C++ で matplotlib のようなグラフを描くためのライブラリ。

##必要なもの
* OpenGL  
* Eigen (C++ 用の行列計算ライブラリ)
* c++ のコンパイラ  


## Eigen インストール (Windows と Linux で共通)
[ここ](http://eigen.tuxfamily.org/index.php?title=Main_Page)からEigenの最新版をダウンロード。  
圧縮ファイルを展開して、"Eigen"ディレクトリを適当なところにコピー

## OpenGLのインストールとプログラムのコンパイル (Win と Linux で別々)

### Windows と Visual Studio を使う場合  

インストールは難、コンパイルは易

#### OpenGL インストール

難しいので次のサイトを参照  
  [GLUTによる「手抜き」OpenGL入門](http://www.wakayama-u.ac.jp/~tokoi/opengl/libglut.html#2.3)
  
  
#### コンパイル  

WindowsでVisual Studioを使うなら、F5押すだけでOK  


### Linux(RedHat) を使う場合  

インストールは易、コンパイルは難

#### OpenGL インストール

コマンドで簡単にインストール可能  

    yum install -y freeglut  
    yum install -y freeglut-devel  

これでコンパイルしてもだめなときは  

    yum install -y libXmu-devel
    yum install -y libXi-devel  

この2つをインストールすればたぶんうまくいく  
RedHat以外のOSを使う場合、エラーが起きる場合、インストーラを使う必要がある場合などは次のページを参照  
[GLUTによる「手抜き」OpenGL入門](http://www.wakayama-u.ac.jp/~tokoi/opengl/libglut.html#2.2)

#### コンパイル

以下のMakefileを作る  

    CFLAGS = -I/usr/X11R6/include
    LDLIBS = -L/usr/X11R6/lib -lglut -lGLU -lGL -lXmu -lXi -lXext -lX11 -lm -lpthread
    a.out: program.c
    --Tab-->$(CXX) $(CFLAGS) program.c $(LDLIBS)

