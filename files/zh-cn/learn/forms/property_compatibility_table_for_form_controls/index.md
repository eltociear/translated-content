---
title: 表单组件兼容性列表
slug: Learn/Forms/Property_compatibility_table_for_form_controls
translation_of: Learn/Forms/Property_compatibility_table_for_form_controls
original_slug: Learn/HTML/Forms/Property_compatibility_table_for_form_widgets
---
<div>{{learnsidebar}}{{PreviousMenu("Learn/HTML/Forms/Advanced_styling_for_HTML_forms", "Learn/HTML/Forms")}}</div>

<p>下面的兼容性表格尝试总结 HTML 表单的 CSS 支持状况。由于 CSS 和 HTML 表单的复杂性，不能把这些表格当作完善的参考。但是，它们可以让你很好地洞察什么能做什么不能做，这将会对你学习使用有很好地帮助。</p>

<h2 id="如何阅读表格">如何阅读表格</h2>

<h3 id="值">值</h3>

<p>对于每个属性，有四种可能地取值：</p>

<dl>
 <dt>YES</dt>
 <dd>此属性具有相当一致的跨浏览器支持。在某些极端情况下，你可能仍然会面临奇怪的副作用。</dd>
 <dt>PARTIAL</dt>
 <dd>尽管这个属性会生效，你还是会经常面对奇怪的副作用和不一致性。你应该尽力避免这些属性，除非你已经深知那些副作用。</dd>
 <dt>NO</dt>
 <dd>此属性就是不工作或者表现得非常不一致，所以并不可靠。</dd>
 <dt>N.A.</dt>
 <dd>此属性对这种类型的组件没有意义。</dd>
</dl>

<h3 id="渲染">渲染</h3>

<p>对于每个属性有两种可能的渲染方式：</p>

<dl>
 <dt>N (Normal)</dt>
 <dd>表示这个属性会像设置的那样应用。</dd>
 <dt>T (Tweaked)</dt>
 <dd>表示这个属性需要通过下列的额外规则来使用：</dd>
</dl>

<pre class="brush: css">* {
/* This turn off the native look and feel on WebKit based browsers */
  -webkit-appearance: none;

/* This turn off the native look and feel on Gecko based browsers */
  -moz-appearance: none;

/* This turn off the native look and feel on several different browsers
   including Opera, Internet Explorer and Firefox */
  background: none;
}</pre>

<h2 id="兼容性表格">兼容性表格</h2>

<h3 id="Global_behaviors">Global behaviors</h3>

<p>对许多浏览器来说，许多行为在全局范围内都是通用的：</p>

<dl>
 <dt>{{cssxref("border")}}, {{cssxref("background")}}, {{cssxref("border-radius")}}, {{cssxref("height")}}</dt>
 <dd>任意属性可能影响组件部分或全部的原生外观。小心使用。</dd>
 <dt>{{cssxref("line-height")}}</dt>
 <dd>不同浏览器支持不同，避免使用</dd>
 <dt>{{cssxref("text-decoration")}}</dt>
 <dd>Opera 表单不支持</dd>
 <dt>{{cssxref("text-overflow")}}</dt>
 <dd>Opera, Safari,  IE9 表单不支持</dd>
 <dt>{{cssxref("text-shadow")}}</dt>
 <dd>Opera 和 IE9 不支持</dd>
</dl>

<h3 id="Text_fields">Text fields</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>WebKit 浏览器 (主要在 Mac OSX and iOS 上) 的搜索域使用原生的样式和行为。因此，需要使用 <code>-webkit-appearance:none</code> 才能将这个属性应用到搜索域上。</li>
     <li>在 Windows 7, Internet Explorer 9 不会应用到边框上，除非 <code>background:none</code> 已应用。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>WebKit 浏览器 (主要在 Mac OSX and iOS 上) 的搜索域使用原生的样式和行为。因此，需要使用 <code>-webkit-appearance:none</code> 才能将这个属性应用到搜索域上。</li>
     <li>在 Windows 7, Internet Explorer 9 不会应用到边框上，除非 <code>background:none</code> 已应用。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>WebKit 浏览器 (主要在 Mac OSX and iOS 上) 的搜索域使用原生的样式和行为。因此，需要使用 <code>-webkit-appearance:none</code> 才能将这个属性应用到搜索域上。</li>
     <li>在 Windows 7, Internet Explorer 9 不会应用到边框上，除非 <code>background:none</code> 已应用。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}<sup>[1]</sup></th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>如果 {{cssxref("border-color")}} 属性没有设置，一些基于 WebKit 的浏览器会将 {{cssxref("color")}} 属性应用到边框上，颜色和 {{HTMLElement("textarea")}} 的字体颜色一样。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>查看有关 {{cssxref("line-height")}} 的注释</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td>查看有关 Opera 的注释</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 只在 {{HTMLElement("textarea")}} 上支持这个属性，而 Opera 只在单行文本域中支持。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>WebKit 浏览器 (主要在 Mac OSX and iOS 上) 的搜索域使用原生的样式和行为。因此，需要使用 <code>-webkit-appearance:none</code> 才能将这个属性应用到搜索域上。</li>
     <li>在 Windows 7 上，Internet Explorer 9 不会应用到边框上，除非 <code>background:none</code> 已应用。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>WebKit 浏览器 (主要在 Mac OSX and iOS 上) 的搜索域使用原生的样式和行为。因此，需要使用 <code>-webkit-appearance:none</code> 才能将这个属性应用到搜索域上。</li>
     <li>在 Windows 7 上，Internet Explorer 9 不会应用到边框上，除非 <code>background:none</code> 已应用。</li>
     <li>在 Opera 上，只有当边框明确设定时 {{cssxref("border-radius")}} 属性才会应用</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Buttons">Buttons</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>这个属性不能应用于 Mac OSX or iOS 上基于 WebKit 的浏览器。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>这个属性不能应用于 Mac OSX or iOS 上基于 WebKit 的浏览器。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>查看{{cssxref("line-height")}} 的注意事项。</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Opera 上，只有当边框明确设定时 {{cssxref("border-radius")}} 属性才会应用</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Number">Number</h3>

<p>在实现了 <code>number</code> 组件的浏览器上，并没有一种标准的方式改变数字组件的样式，值得注意的是 Safari 上的数字输入框不在这个范围内。</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Opera 上，数字选择器缩小时，可能会隐藏域中内容。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Opera 上，数字选择器缩小时，可能会隐藏域中内容。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>查看{{cssxref("line-height")}} 的注意事项。</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td colspan="1" rowspan="3">
    <p>支持，但浏览器之间的不一致性太多，所以并不可靠。</p>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
  </tr>
 </tbody>
</table>

<h3 id="Check_boxes_and_radio_buttons">Check boxes and radio buttons</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>一些浏览器会添加额外的边缘，另一些会拉伸组件。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>一些浏览器会添加额外的边缘，另一些会拉伸组件。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="Select_boxes_(single_line)">Select boxes (single line)</h3>

<p>Firefox 不提供任何方式改变 {{HTMLElement("select")}} 元素的下箭头。</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>这个属性在 {{HTMLElement("select")}} 元素上一切正常，但不能用于 {{HTMLElement("option")}} 或者 {{HTMLElement("optgroup")}} 元素。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[2]</sup></td>
   <td>
    <ol>
     <li>属性可以应用，但 Mac OSX 上浏览器之间的以不一致的方向显示，所以并不可靠。</li>
     <li>这个属性在 {{HTMLElement("select")}} 元素上一切正常，但不能用于 {{HTMLElement("option")}} 或者 {{HTMLElement("optgroup")}} 元素。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Mac OSX 上， 基于 WebKit 的浏览器 不支持将这个属性用于原生组件。它们和 Opera, 在 {{HTMLElement("option")}} 和 {{HTMLElement("optgroup")}} 元素上根本不支持这个属性。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Mac OSX 上， 基于 WebKit 的浏览器 不支持将这个属性用于原生组件。它们和 Opera, 在 {{HTMLElement("option")}} 和 {{HTMLElement("optgroup")}} 元素上根本不支持这个属性。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 不支持将这个属性用于 {{HTMLElement("select")}}, {{HTMLElement("option")}}, 和 {{HTMLElement("optgroup")}} 元素；Mac OSX 上基于 WebKit 的浏览器不支持将这个属性应用于 {{HTMLElement("option")}} 和 {{HTMLElement("optgroup")}} 元素。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>Windows 7 上的 IE9 和 Mac OSX 上基于 WebKit 的浏览器，不支持这个组件上的这个属性。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>只有 Firefox 提供了对这个属性的完全支持。Opera 根本不支持这个属性，而其他浏览器只提供了对 {{HTMLElement("select")}} 元素的支持。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td>
    <ol>
     <li>大部分浏览器仅仅支持将这个属性用于 {{HTMLElement("select")}} 元素。</li>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1][2]</sup></td>
   <td>
    <ol>
     <li>大部分浏览器仅仅支持将这个属性用于 {{HTMLElement("select")}} 元素。</li>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>大部分浏览器仅仅支持将这个属性用于 {{HTMLElement("select")}} 元素。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>大部分浏览器仅仅支持将这个属性用于 {{HTMLElement("select")}} 元素。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
  </tr>
 </tbody>
</table>

<h3 id="Select_boxes_(multiline)">Select boxes (multiline)</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>Opera 在 {{HTMLElement("select")}} 元素上 不支持 {{cssxref("padding-top")}} 和 {{cssxref("padding-bottom")}} 。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>查看{{cssxref("line-height")}} 的注意事项。</td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 在 {{HTMLElement("select")}}, {{HTMLElement("option")}}, 和{{HTMLElement("optgroup")}} 元素上不支持这个属性；Mac OSX 上基于 WebKit 的浏览器在 {{HTMLElement("option")}} 和{{HTMLElement("optgroup")}} 元素上不支持这个属性。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>Windows 7 上的 IE9 和 Mac OSX 上基于 WebKit 的浏览器，不支持这个组件上的这个属性。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>只被 Firefox and IE9+ 支持。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>大部分浏览器仅仅支持将这个属性用于 {{HTMLElement("select")}} 元素。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes<sup>[1]</sup></td>
   <td>
    <ol>
     <li>在 Opera 上，只有当边框明确设定时 {{cssxref("border-radius")}} 属性才会应用</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Datalist">Datalist</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="File_picker">File picker</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>支持，但浏览器之间的不一致性太多，所以并不可靠。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>许多浏览器将这个属性应用到选择按钮上。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>它表现的或多或少的像一个组件左侧的边缘。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td>
    <ol>
     <li>支持，但浏览器之间的不一致性太多，所以并不可靠。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Date_pickers">Date pickers</h3>

<p>许多属性都支持但是浏览器之间的不一致性太多，所以并不可靠。</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="Color_pickers">Color pickers</h3>

<p>There is currently not enough implementation to get realiable behaviors.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>Opera 将它像一个选择组件一样，以同样的限制处理。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li>Opera 将它像一个选择组件一样，以同样的限制处理。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>支持，但浏览器之间的不一致性太多，所以并不可靠。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
 </tbody>
</table>

<h3 id="Meters_and_progress">Meters and progress</h3>

<p>There is currently not enough implementation to get realiable behaviors.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>当 {{cssxref("padding")}} 属性应用于一个 tweaked 元素时，Chrome 会隐藏 {{HTMLElement("progress")}} 和{{HTMLElement("meter")}} 元素。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>支持，但浏览器之间的不一致性太多，所以并不可靠。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
 </tbody>
</table>

<h3 id="Range">Range</h3>

<p>There is no standard way to change the style of the range grip and Opera has no way to tweak the default rendering of the range widget.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td>
    <ol>
     <li>Chrome 和 Opera 在组件周围添加了一些额外的空白，而 Windows 7 上的 Opera 则拉伸范围选择器的滑块。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td>
    <ol>
     <li> {{cssxref("padding")}} 属性被运用，但是没有任何的视觉效果。</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>支持，但浏览器之间的不一致性太多，所以并不可靠。</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 153, 153); vertical-align: top;">No<sup>[1]</sup></td>
  </tr>
 </tbody>
</table>

<h3 id="Image_buttons">Image buttons</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">T</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>CSS box model</em></th>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("width")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("height")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("border")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("margin")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="vertical-align: top;">{{cssxref("padding")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Text and font</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Border and background</em></th>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("background")}}</th>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td style="text-align: center; background-color: rgb(204, 255, 102); vertical-align: top;">Yes</td>
   <td colspan="1"> </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("border-radius")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td colspan="1">
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row" style="white-space: nowrap; vertical-align: top;">{{cssxref("box-shadow")}}</th>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td style="text-align: center; background-color: rgb(255, 255, 102); vertical-align: top;">Partial<sup>[1]</sup></td>
   <td colspan="1">
    <ol>
     <li>IE9 不支持这个属性</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<p>{{PreviousMenu("Learn/HTML/Forms/Advanced_styling_for_HTML_forms", "Learn/HTML/Forms")}}</p>

<p> </p>

<h2 id="在本单元中">在本单元中</h2>

<ul>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Your_first_HTML_form">Your first HTML form</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/How_to_structure_an_HTML_form">How to structure an HTML form</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/The_native_form_widgets">The native form widgets</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Sending_and_retrieving_form_data">Sending form data</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Form_validation">Form data validation</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/How_to_build_custom_form_widgets">How to build custom form widgets</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Sending_forms_through_JavaScript">Sending forms through JavaScript</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/HTML_forms_in_legacy_browsers">HTML forms in legacy browsers</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Styling_HTML_forms">Styling HTML forms</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Advanced_styling_for_HTML_forms">Advanced styling for HTML forms</a></li>
 <li><a href="/en-US/docs/Learn/HTML/Forms/Property_compatibility_table_for_form_widgets">Property compatibility table for form widgets</a></li>
</ul>

<p> </p>