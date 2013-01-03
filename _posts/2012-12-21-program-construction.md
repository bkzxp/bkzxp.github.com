---
layout : post
category : lessons
tags : [程序构造]
title : 程序构造
---

<p>程序构造</p>
<ul>
  <li>目的
    <ul>
      <li>代码能不能正常跑起来</li>
      <li>数据通讯能不能用</li>
      <li>链接可不可以访问</li>
    </ul>
  </li>
  <li>思路
    <ul>
      <li>做什么的-&gt;用那些工具-&gt;怎么配置</li>
    </ul>
  </li>
  <li>要求
    <ul>
      <li>要有联调构造</li>
    </ul>
  </li>
  <li>检测项
    <ul>
      <li>语法检查
        <ul>
          <li>工具：php命令：php -l</li>
          <li>成功：显示没有语法错误</li>
          <li>有错：提示有错误在**行</li>
        </ul>
      </li>
      <li>注释检查
        <ul>
          <li>项
            <ul>
              <li>生成注释</li>
              <li>生成doc</li>
              <li>其他等等</li>
            </ul>
          </li>
          <li>检测工具
            <ul>
              <li>eclipse 插件checkstyle
                <ul>
                  <li>
                    <p>说明：代码库的可维护性直接影响着软件的整个成本。另外，不佳的可维护性还会让开发人员十分头痛（进而导致开发人员的缺乏）—— 代码越容易修改，就越容易添加新的产品特性。像 CheckStyle 这样的工具可以协助寻找那些可影响到可维护性、与编码标准相冲突的地方，比方说，过大的类、太长的方法和未使用的变量等等。 <br />
                      使用 Eclipse 的 CheckStyle 插件的好处是能够在编码过程中了解到源代码上下文的各种编码冲突，让开发人员更可能在签入该代码前真正处理好这些冲突。您也几乎可以把 CheckStyle 插件视作一个连续的代码复查工具！</p>
                  </li>
                </ul>
              </li>
            </ul>
          </li>
        </ul>
      </li>
      <li>代码检查
        <ul>
          <li>程序命名规范</li>
          <li>重用组件算法</li>
        </ul>
      </li>
      <li>资源检查
        <ul>
          <li>途径：配置文件，本质还是php 函数</li>
          <li>成功：连接成功</li>
          <li>有错：链接失败</li>
        </ul>
      </li>
      <li>导航检查
        <ul>
          <li>anti</li>
          <li>……</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>尝试书写
    <ul>
      <li>程序构造环境
        <ul>
          <li>linux    windows</li>
        </ul>
      </li>
      <li>标准
        <ul>
          <li>编译
            <ul>
              <li>能够成功编译</li>
            </ul>
          </li>
          <li>数据库访问
            <ul>
              <li>能够正确访问</li>
            </ul>
          </li>
          <li>编程规范
            <ul>
              <li>符合编程规范</li>
            </ul>
          </li>
          <li>链接是否有效
            <ul>
              <li>符合链接</li>
            </ul>
          </li>
        </ul>
      </li>
      <li>工具的设置
      </li>
    </ul>
  </li>
</ul>
