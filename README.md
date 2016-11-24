# compass
compass用法

##编译
  * Compass的编译命令是compass compile.(该命令在项目根目录下运行，会将sass子目录中的scss文件，编译成css文件，保存在stylesheets子目录中)
  * 生产环境需要压缩后的css文件，使用--output-style参数。compass compile --output-style compressed
  * Compass只编译发生变动的文件，重新编译未变动的文件需要使用--force参数。compass compile --force
  * 可以在配置文件config.rb中指定编译模式。
    * :expanded模式表示编译后保留原格式 output_style = :expanded 
    * :compressed进入生产模式 output_style = :compressed
    * 指定environment的值（:production或者:development），智能判断编译模式。
      environment = :development
　　  output_style = (environment == :production) ? :compressed : :expanded
  * compass自动编译命令 compass watch
  
##Compass的模块
  * reset模块
    * 重置浏览器的默认样式 @import "compass/reset";
  * CSS3模块
    * 圆角 @import "compass/css3"; div { @include border-radius(5px); }
    * 透明 @import "compass/css3"; div { @include opacity(0.5); }
    
