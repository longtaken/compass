# compass
compass用法
* 创建一个Compass项目,compass create myproject

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
    * 行内区块 　　@import "compass/css3"; div { @include inline-block; }
  * layout模块 
    * 指定页面的footer部分总是出现在浏览器最底端 @import "compass/layout"; #footer { @include sticky-footer(54px); }
    * 指定子元素占满父元素的空间 @import "compass/layout"; div { @include stretch; }
  * typography模块
    * @import "compass/typography"; a { @include link-colors(#00c, #0cc, #c0c, #ccc, #cc0); }
  * utilities模块
    * import "compass/utilities/"; .clearfix { @include clearfix; }
    * @import "compass/utilities"; table { @include table-scaffolding; }
  * Helper函数  
    * image-width()和image-height()返回图片的宽和高,inline-image()可以将图片转为data协议的数据<br>
      @import "compass"; .icon { background-image: inline-image("icon.png");}
