---
layout: post
title: Java字节码表
pid: 568
tags: [java]

---

### Java指令集（按功能分类）



<table style="border-right: medium none; border-top: medium none; border-left: medium none; border-bottom: medium none; border-collapse: collapse" cellspacing="0" cellpadding="0" border="1">
<tbody>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: black 1pt solid; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">常量入栈指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aconst_null</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>null<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_m1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>-1(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>0(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>1(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>2(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>3(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_4</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>4(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iconst_5</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>5(int)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lconst_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>0(long)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lconst_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>1(long)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fconst_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>0(float)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fconst_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>1(float)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fconst_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>2(float)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dconst_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>0(double)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dconst_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>1(double)<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>bipush</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>valuebyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>valuebyte<span style="font-family: 宋体">值带符号扩展成</span>int<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>sipush</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>valuebyte1</p>
<p>valuebyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>(valuebyte1 &lt;&lt; 8) | valuebyte2 <span style="font-family: 宋体">值带符号扩展成</span>int<span style="font-family: 宋体">值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ldc</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">常量池中的常量值（</span>int, float, string reference, object reference<span style="font-family: 宋体">）入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ldc_w</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">常量池中常量（</span>int, float, string reference, object reference<span style="font-family: 宋体">）入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ldc2_w</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fde9d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">常量池中常量（</span>long, double<span style="font-family: 宋体">）入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">局部变量值转载到栈中指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)aload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>indexbyte<span style="font-family: 宋体">中装载引用类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aload_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>0<span style="font-family: 宋体">中装载引用类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aload_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>1<span style="font-family: 宋体">中装载引用类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aload_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>2<span style="font-family: 宋体">中装载引用类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aload_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>3<span style="font-family: 宋体">中装载引用类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)iload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>indexbyte<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iload_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>0<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iload_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>1<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iload_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>2<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iload_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>3<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)lload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>indexbyte<span style="font-family: 宋体">中装载</span>long<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lload_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>0<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lload_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>1<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lload_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>2<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lload_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>3<span style="font-family: 宋体">中装载</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)fload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>indexbyte<span style="font-family: 宋体">中装载</span>float<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fload_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>0<span style="font-family: 宋体">中装载</span>float<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fload_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>1<span style="font-family: 宋体">中装载</span>float<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fload_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>2<span style="font-family: 宋体">中装载</span>float<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fload_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>3<span style="font-family: 宋体">中装载</span>float<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)dload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>indexbyte<span style="font-family: 宋体">中装载</span>double<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dload_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>0<span style="font-family: 宋体">中装载</span>double<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dload_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>1<span style="font-family: 宋体">中装载</span>double<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dload_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>2<span style="font-family: 宋体">中装载</span>double<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dload_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从局部变量</span>3<span style="font-family: 宋体">中装载</span>double<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aaload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从引用类型数组中装载指定项的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iaload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>int<span style="font-family: 宋体">类型数组中装载指定项的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>laload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>long<span style="font-family: 宋体">类型数组中装载指定项的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>faload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>float<span style="font-family: 宋体">类型数组中装载指定项的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>daload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>double<span style="font-family: 宋体">类型数组中装载指定项的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>baload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>boolean<span style="font-family: 宋体">类型数组或</span>byte<span style="font-family: 宋体">类型数组中装载指定项的值（先转换为</span>int<span style="font-family: 宋体">类型值，后压栈）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>caload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>char<span style="font-family: 宋体">类型数组中装载指定项的值（先转换为</span>int<span style="font-family: 宋体">类型值，后压栈）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>saload</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #daeef3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从</span>short<span style="font-family: 宋体">类型数组中装载指定项的值（先转换为</span>int<span style="font-family: 宋体">类型值，后压栈）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">将栈顶值保存到局部变量中指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)astore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到局部变量</span>indexbyte<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>astroe_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到局部变量</span>0<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>astore_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到局部变量</span>1<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>astore_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到局部变量</span>2<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>astore_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到局部变量</span>3<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)istore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到局部变量</span>indexbyte<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>istore_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到局部变量</span>0<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>istore_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到局部变量</span>1<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>istore_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到局部变量</span>2<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>istore_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到局部变量</span>3<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)lstore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到局部变量</span>indexbyte<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lstore_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到局部变量</span>0<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lstore_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到局部变量</span>1<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lstore_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到局部变量</span>2<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lstroe_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到局部变量</span>3<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)fstore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到局部变量</span>indexbyte<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fstore_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到局部变量</span>0<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fstore_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到局部变量</span>1<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fstore_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到局部变量</span>2<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fstore_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到局部变量</span>3<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)dstore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到局部变量</span>indexbyte<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dstore_0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到局部变量</span>0<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dstore_1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到局部变量</span>1<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dstore_2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到局部变量</span>2<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dstore_3</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到局部变量</span>3<span style="font-family: 宋体">中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>aastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶引用类型值保存到指定引用类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值保存到指定</span>int<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值保存到指定</span>long<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值保存到指定</span>float<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值保存到指定</span>double<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>bastroe</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>boolean<span style="font-family: 宋体">类型值或</span>byte<span style="font-family: 宋体">类型值保存到指定</span>boolean<span style="font-family: 宋体">类型数组或</span>byte<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>castore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>char<span style="font-family: 宋体">类型值保存到指定</span>char<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>sastore</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #b6dde8; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>short<span style="font-family: 宋体">类型值保存到指定</span>short<span style="font-family: 宋体">类型数组的指定项。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong>wide</strong><strong><span style="font-family: 宋体">指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>wide</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">使用附加字节扩展局部变量索引（</span>iinc<span style="font-family: 宋体">指令特殊）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">通用（无类型）栈操作指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>nop</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">空操作。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>pop</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从栈顶弹出一个字长的数据。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>pop2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">从栈顶弹出两个字长的数据。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶一个字长的数据，将复制后的数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup_x1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶一个字长的数据，弹出栈顶两个字长数据，先将复制后的数据压栈，再将弹出的两个字长数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup_x2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶一个字长的数据，弹出栈顶三个字长的数据，将复制后的数据压栈，再将弹出的三个字长的数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶两个字长的数据，将复制后的两个字长的数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup2_x1</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶两个字长的数据，弹出栈顶三个字长的数据，将复制后的两个字长的数据压栈，再将弹出的三个字长的数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dup2_x2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">复制栈顶两个字长的数据，弹出栈顶四个字长的数据，将复制后的两个字长的数据压栈，再将弹出的四个字长的数据压栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>swap</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5dfec; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">交换栈顶两个字长的数据的位置。</span>Java<span style="font-family: 宋体">指令中没有提供以两个字长为单位的交换指令。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">类型转换指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2f</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值转换为</span>float<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2l</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值转换为</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2d</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值转换为</span>double<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>f2i</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值转换为</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>f2l</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值转换为</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>f2d</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值转换为</span>double<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>l2i</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值转换为</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>l2f</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值转换为</span>float<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>l2d</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值转换</span>double<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>d2i</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值转换为</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>d2f</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值转换为</span>float<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>d2l</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值转换为</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2b</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值截断成</span>byte<span style="font-family: 宋体">类型，后带符号扩展成</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2c</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值截断成</span>char<span style="font-family: 宋体">类型值，后带符号扩展成</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>i2s</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ccc0d9; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值截断成</span>short<span style="font-family: 宋体">类型值，后带符号扩展成</span>int<span style="font-family: 宋体">类型值入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">整数运算</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iadd</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>int<span style="font-family: 宋体">类型数相加，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>isub</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>int<span style="font-family: 宋体">类型数相减，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>imul</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>int<span style="font-family: 宋体">类型数相乘，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>idiv</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>int<span style="font-family: 宋体">类型数相除，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>irem</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>int<span style="font-family: 宋体">类型数取模，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ineg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>int<span style="font-family: 宋体">类型值取负，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ladd</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>long<span style="font-family: 宋体">类型数相加，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lsub</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>long<span style="font-family: 宋体">类型数相减，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lmul</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>long<span style="font-family: 宋体">类型数相乘，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ldiv</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>long<span style="font-family: 宋体">类型数相除，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lrem</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>long<span style="font-family: 宋体">类型数取模，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lneg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>long<span style="font-family: 宋体">类型值取负，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)iinc</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p>
<p>constbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #f2dbdb; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将整数值</span>constbyte<span style="font-family: 宋体">加到</span>indexbyte<span style="font-family: 宋体">指定的</span>int<span style="font-family: 宋体">类型的局部变量中。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">浮点运算</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fadd</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>float<span style="font-family: 宋体">类型数相加，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fsub</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>float<span style="font-family: 宋体">类型数相减，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fmul</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>float<span style="font-family: 宋体">类型数相乘，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fdiv</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>float<span style="font-family: 宋体">类型数相除，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>frem</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>float<span style="font-family: 宋体">类型数取模，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fneg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>float<span style="font-family: 宋体">类型值取反，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dadd</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>double<span style="font-family: 宋体">类型数相加，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dsub</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>double<span style="font-family: 宋体">类型数相减，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dmul</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>double<span style="font-family: 宋体">类型数相乘，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ddiv</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>double<span style="font-family: 宋体">类型数相除，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>drem</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶两</span>double<span style="font-family: 宋体">类型数取模，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dneg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #e5b8b7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">将栈顶</span>double<span style="font-family: 宋体">类型值取负，结果入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">逻辑运算——移位运算</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ishl</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">左移</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lshl</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">左移</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ishr</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">算术右移</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lshr</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">算术右移</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iushr</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">逻辑右移</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lushr</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">逻辑右移</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">逻辑运算——按位布尔运算</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iand</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>int<span style="font-family: 宋体">类型按位与运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>land</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>long<span style="font-family: 宋体">类型的按位与运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ior</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>int<span style="font-family: 宋体">类型的按位或运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lor</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>long<span style="font-family: 宋体">类型的按位或运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ixor</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>int<span style="font-family: 宋体">类型的按位异或运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lxor</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">对</span>long<span style="font-family: 宋体">类型的按位异或运算。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">控制流指令——条件跳转指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifeq</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值为</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifne</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值不为</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>iflt</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值小于</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifle</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值小于等于</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifgt</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值大于</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifge</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶</span>int<span style="font-family: 宋体">类型值大于等于</span>0<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmpeq</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值相等则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmpne</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值不相等则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmplt</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值前小于后则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmple</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值前小于等于后则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmpgt</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值前大于后则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_icmpge</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两</span>int<span style="font-family: 宋体">类型值前大于等于后则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifnull</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶引用值为</span>null<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ifnonnull</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶引用值不为</span>null<span style="font-family: 宋体">则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_acmpeq</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两引用类型值相等则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>if_acmpne</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #7f7f7f; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">若栈顶两引用类型值不相等则跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">控制流指令——比较指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lcmp</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">比较栈顶两</span>long<span style="font-family: 宋体">类型值，前者大，</span>1<span style="font-family: 宋体">入栈；相等，</span>0<span style="font-family: 宋体">入栈；后者大，</span>-1<span style="font-family: 宋体">入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fcmpl</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">比较栈顶两</span>float<span style="font-family: 宋体">类型值，前者大，</span>1<span style="font-family: 宋体">入栈；相等，</span>0<span style="font-family: 宋体">入栈；后者大，</span>-1<span style="font-family: 宋体">入栈；有</span>NaN<span style="font-family: 宋体">存在，</span>-1<span style="font-family: 宋体">入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>fcmpg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">比较栈顶两</span>float<span style="font-family: 宋体">类型值，前者大，</span>1<span style="font-family: 宋体">入栈；相等，</span>0<span style="font-family: 宋体">入栈；后者大，</span>-1<span style="font-family: 宋体">入栈；有</span>NaN<span style="font-family: 宋体">存在，</span>-1<span style="font-family: 宋体">入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dcmpl</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">比较栈顶两</span>double<span style="font-family: 宋体">类型值，前者大，</span>1<span style="font-family: 宋体">入栈；相等，</span>0<span style="font-family: 宋体">入栈；后者大，</span>-1<span style="font-family: 宋体">入栈；有</span>NaN<span style="font-family: 宋体">存在，</span>-1<span style="font-family: 宋体">入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dcmpg</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">比较栈顶两</span>double<span style="font-family: 宋体">类型值，前者大，</span>1<span style="font-family: 宋体">入栈；相等，</span>0<span style="font-family: 宋体">入栈；后者大，</span>-1<span style="font-family: 宋体">入栈；有</span>NaN<span style="font-family: 宋体">存在，</span>-1<span style="font-family: 宋体">入栈。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">控制流指令——无条件跳转指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>goto</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">无条件跳转到指定位置。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>goto_w</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p>
<p>branchbyte3</p>
<p>branchbyte4</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c4bc96; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">无条件跳转到指定位置（宽索引）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">控制流指令——表跳转指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>tableswitch</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&lt;0-3bytepad&gt;</p>
<p>defaultbyte1</p>
<p>defaultbyte2</p>
<p>defaultbyte3</p>
<p>defaultbyte4</p>
<p>lowbyte1</p>
<p>lowbyte2</p>
<p>lowbyte3</p>
<p>lowbyte4</p>
<p>highbyte1</p>
<p>highbyte2</p>
<p>highbyte3</p>
<p>highbyte4</p>
<p>jump offsets...</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">通过索引访问跳转表，并跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lookupswitch</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&lt;0-3bytepad&gt;</p>
<p>defaultbyte1</p>
<p>defaultbyte2</p>
<p>defaultbyte3</p>
<p>defaultbyte4</p>
<p>npairs1</p>
<p>npairs2</p>
<p>npairs3</p>
<p>npairs4</p>
<p>match offsets</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #95b3d7; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">通过键值访问跳转表，并跳转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">控制流指令——异常和</span>finally</strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>athrow</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">抛出异常。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>jsr</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">跳转到子例程序。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>jsr_w</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>branchbyte1</p>
<p>branchbyte2</p>
<p>branchbyte3</p>
<p>branchbyte4</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">跳转到子例程序（宽索引）。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>(wide)ret</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #92cddc; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回子例程序。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">对象操作指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>new</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">创建新的对象实例。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>checkcast</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">类型强转。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>instanceof</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">判断类型。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>getfield</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">获取对象字段的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>putfield</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">给对象字段赋值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>getstatic</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">获取静态字段的值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>putstatic</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #d99594; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">给静态字段赋值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">数组操作指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>newarray</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>atype</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">创建</span>type<span style="font-family: 宋体">类型的数组。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>anewarray</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">创建引用类型的数组。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>arraylength</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">获取一维数组的长度。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>multianewarray</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p>
<p>dimension</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #c2d69b; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">创建</span>dimension<span style="font-family: 宋体">维度的数组。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">方法调用指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>invokespecial</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">编译时方法绑定调用方法。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>invokevirtual</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">运行时方法绑定调用方法。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>invokestatic</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">调用静态方法。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>invokeinterface</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>indexbyte1</p>
<p>indexbyte2</p>
<p>count</p>
<p>0</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #ddd9c3; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">调用接口方法。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">方法返回指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>ireturn</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回</span>int<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>lreturn</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回</span>long<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>freturn</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回</span>float<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>dreturn</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回</span>double<span style="font-family: 宋体">类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>areturn</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">返回引用类型值。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>return</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #8db3e2; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p>void<span style="font-family: 宋体">函数返回。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p>&nbsp;</p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 426.1pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="568" colspan="3">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">线程同步指令</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作码（助记符）</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">操作数</span></strong></p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #bfbfbf; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p style="text-align: center" align="center"><strong><span style="font-family: 宋体">描述（栈指操作数栈）</span></strong></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>monitorenter</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">进入并获得对象监视器。</span></p></td></tr>
<tr>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: black 1pt solid; width: 90.45pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="121">
<p>monitorexit</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 70.9pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="95">
<p>&nbsp;</p></td>
<td style="border-right: black 1pt solid; padding-right: 5.4pt; border-top: medium none; padding-left: 5.4pt;background: #fbd4b4; padding-bottom: 0cm; border-left: medium none; width: 264.75pt; padding-top: 0cm; border-bottom: black 1pt solid" valign="top" width="353">
<p><span style="font-family: 宋体">释放并退出对象监视器。</span></p></td></tr></tbody></table>


# 参考

+ [Java二进制指令代码解析](http://www.blogjava.net/DLevin/archive/2011/09/13/358497.html)