---
layout : post
category : lessons
tags : [Eclipse, phpdocumentor]
title : Eclipse自动注释及导出phpdocumentor
---

Eclipse自动注释

操作位置1：

    Eclipse->preferences->PHP->CodeStyle->CodeTemplats->Code
    

1. **文件注释**

**设置**：展开Code,点击“simple php file”,点击右侧的“edit”，把下面的代码粘进去：

    <?php
    /**
    * Sample PHP File
    * Enter description here...
    * @author ${user} ${date}
    * @version 1.0
    * @update <br>
    * <pre>
    * </pre>
    */

    ?>

**效果**：

 <h2 style="font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; text-align: start; color: rgb(0, 0, 0); word-spacing: 0px; font-style: normal; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal">
      Page Details:
    </h2>
    <font face="tahoma, verdana, arial, sans-serif" color="rgb(0, 0, 0)">Sample PHP File<br style="letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; word-spacing: 0px; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal" align="start"><br style="letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; word-spacing: 0px; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal" align="start"></font>
    <p style="font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; text-align: start; color: rgb(0, 0, 0); font-size: 13px; word-spacing: 0px; font-style: normal; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal; font-weight: normal">
      Enter description here...
    </p>
    <font face="tahoma, verdana, arial, sans-serif" color="rgb(0, 0, 0)"><br style="letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; word-spacing: 0px; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal" align="start">
    </font>
    <h4 style="font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; line-height: normal; text-transform: none; text-indent: 0px; text-align: start; color: rgb(0, 0, 0); font-size: 13px; word-spacing: 0px; font-style: normal; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal">
      Tags:
    </h4>
    <div style="font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; line-height: normal; text-transform: none; padding-left: 15px; text-indent: 0px; text-align: start; color: rgb(0, 0, 0); font-size: 13px; word-spacing: 0px; font-style: normal; background-color: rgb(255, 255, 255); white-space: normal; font-variant: normal; font-weight: normal" class="tags">
      <table border="0" cellpadding="0" cellspacing="0">
        <tr>
          <td style="font-size: 10pt">
            <b>author:</b>&#160;&#160;
          </td>
          <td style="font-size: 10pt">
            zhangxp&#160;&#160;2012-11-5
          </td>
        </tr>
        <tr>
          <td style="font-size: 10pt">
            <b>version:</b>&#160;&#160;
          </td>
          <td style="font-size: 10pt">
            1.0
          </td>
        </tr>
        <tr>
          <td style="font-size: 10pt">
            <b>update:</b>&#160;&#160;
          </td>
          <td style="font-size: 10pt"><br>
          <pre> cj 2011.12
zxp 2012.02</pre>
      </td>
        </tr>
      </table>
    </div>
          
**使用方法**：在eclipse里面进行New PHP File操作，才会自动生成该注释

操作位置2

    Eclipse->preferences->PHP->CodeStyle->CodeTemplats->Comments

1. **Class注释**

**设置**：展开Comments，选中Types，点击右侧的“Edit”，粘上以下代码

    /**
     * Enter description here ...
     * @author ${user}
     * @update <br>
     * <pre>
     * </pre>
     */
     
**示例代码**：

    /**
     *
     * Enter description here ...
     * @author zhangxp
     * @update <br>
     * <pre>
     * </pre>
     */
     class zxp
     {
      .......
     }

**效果**：

 <h3> Class Details
    </h3>
    <div class="tags" style="padding-left: 15px">
      [line 21]<br >Enter description here ...<br ><br >
      <h4>
        Tags:
      </h4>
      <div class="tags" style="padding-left: 15px">
        <table cellpadding="0" cellspacing="0" border="0">
          <tr>
            <td style="font-size: 10pt">
              <b>author:</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              zhangxp
            </td>
          </tr>
          <tr>
            <td style="text-transform: none; line-height: normal; font-weight: normal; word-spacing: 0px; background-color: rgb(255, 255, 255); font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; white-space: normal; font-variant: normal; text-indent: 0px; font-size: 10pt; color: rgb(0, 0, 0); font-style: normal; text-align: start">
              <b>update:</b>&#160;&#160;
            </td>
            <td>
              <br class="Apple-interchange-newline" >
            </td>
          </tr>
        </table>
      </div>
    </div>

**使用**：在Class代码的上部，敲入【/**】，并回车

2. **Function注释**

**设置**：展开Comments，选中Constructor，粘上以下代码：

    /**
     * Enter description here ...
     * ${tags}
     * @return ${return_type}
     * @author ${user} ${date}
     */
     
**示例代码**：

    /**
     *
     * Enter description here ...
     * @param int $a
     * @param varchar $b
     * @param array $c
     * @return boolean
     * @author zhangxp 2012-11-5
     */
     public function  war($a,$b='speak',$c=array())
     {
        global $enn;
        $pp = 0;
        return $pp;
     }
     
**效果**：

 <h3 style="text-transform: none; line-height: normal; word-spacing: 0px; background-color: rgb(255, 255, 255); font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; white-space: normal; font-variant: normal; text-indent: 0px; color: rgb(0, 0, 0); font-style: normal; text-align: start">
      method war&#160;[line 33]
    </h3>
    <div class="function" style="text-transform: none; line-height: normal; font-weight: normal; word-spacing: 0px; background-color: rgb(255, 255, 255); font-family: tahoma, verdana, arial, sans-serif; letter-spacing: normal; white-space: normal; font-variant: normal; text-indent: 0px; font-size: 13px; color: rgb(0, 0, 0); font-style: normal; text-align: start; padding-left: 15px">
      <table cellpadding="1" cellspacing="0" width="100%" border="0">
        <tr>
          <td class="code_border" style="background-color: rgb(192, 192, 192); font-size: 10pt; color: rgb(0, 0, 0)">
            <table cellpadding="2" cellspacing="0" width="100%" border="0">
              <tr>
                <td class="code" style="background-color: rgb(240, 240, 240); font-size: 10pt; color: rgb(0, 0, 0)">
                  <code>boolean war( int $a, [varchar $b = 'speak'], [array $c = array()])</code>
                </td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
      <br >
      Enter description here ...<br ><br >
      <h4>
        Tags:
      </h4>
      <div class="tags" style="padding-left: 15px">
        <table cellpadding="0" cellspacing="0" border="0">
          <tr>
            <td style="font-size: 10pt">
              <b>author:</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              zhangxp 2012-11-5
            </td>
          </tr>
          <tr>
            <td style="font-size: 10pt">
              <b>access:</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              public
            </td>
          </tr>
        </table>
      </div>
      <br >
      <h4>
        Parameters:
      </h4>
      <div class="tags" style="padding-left: 15px">
        <table cellpadding="0" cellspacing="0" border="0">
          <tr>
            <td class="type" style="font-style: italic; font-size: 10pt">
              int&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              <b>$a</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
            </td>
          </tr>
          <tr>
            <td class="type" style="font-style: italic; font-size: 10pt">
              varchar&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              <b>$b</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
            </td>
          </tr>
          <tr>
            <td class="type" style="font-style: italic; font-size: 10pt">
              array&#160;&#160;
            </td>
            <td style="font-size: 10pt">
              <b>$c</b>&#160;&#160;
            </td>
            <td style="font-size: 10pt">
            </td>
          </tr>
        </table>
      </div>
    </div>

**使用**：当生成注释后，需要手动添加方法的参数的类型以及返回值的类型。function的上部，敲入【/**】，并回车

**其他注意**

1. 修改tab键为4个空格的设置：preference->PHP->Code Style->Formatter，下拉菜单选择Space，并选择4个空格

2. 导出phpdocumentor
进入你的php安装目录下的data文件夹，然后进入phpdocumentor目录，编辑phpDocumentor.ini文件。在【_phpDocumentor_tags_allowed】中添加‘自定义的标签’，我添加的是“update”。保存，退出。这时候，当执行生成doc的命令后，phpdocumentor 会在页面上把“update”加粗显示。【此步骤保证你本地的phpdocumentor能够解析update标签】
我的目录：C:\wamp\bin\php\php5.2.5\data\Phpdocumentor\
我的命令：C:\wamp\bin\php\php5.2.8>phpdoc.bat -o HTML:Smarty:PHP -d d:\123 -t d:\my。其中，【d:\123】是项目目录，【d:\my】是doc文档目录