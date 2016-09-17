---
title: 影舞 patch
author: hiroyuki_t
layout: post
date: 2012-01-03T09:17:54+00:00
url: /2012/01/03/181754/
categories:
  - Ruby

---
<div class="section">
  <p>
    影舞を使い始めたが、日本語以外で使用する場合、
  </p>
  
  <p>
    spam対策が行われていないため、spamに狙われる。
  </p>
  
  <p>
    そのためのパッチと個人的な修正を施したパッチ
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    さくらのレンタルサーバ スタンダードで使用
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    パッチ作成
  </p>
  
  <p>
    diff -ur kagemai-0.8.8-orig/ kagemai-0.8.8/ > kagemai.patch
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    パッチ当て
  </p>
  
  <p>
    patch -p1 -d &#8216;/home/taki/kagemai-0.8.8-orig&#8217; < &#8216;/home/taki/kagemai.patch&#8217;
  </p>
  
  <pre class="syntax-highlight"><span class="synType">diff -ur kagemai-0.8.8-orig//html/admin.cgi kagemai-0.8.8//html/admin.cgi</span>
<span class="synType">--- kagemai-0.8.8-orig//html/admin.cgi 2008-03-09 19:36:59.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//html/admin.cgi 2011-12-13 21:11:49.000000000 +0900</span>
<span class="synStatement">@@ -1,4 +1,4 @@</span>
<span class="synSpecial">-#!/usr/bin/env ruby</span>
<span class="synIdentifier">+#! /usr/local/bin/ruby</span>
=begin
admin.cgi -- KAGEMAI CGI Interface (administrator mode).
=end
<span class="synType">diff -ur kagemai-0.8.8-orig//html/guest.cgi kagemai-0.8.8//html/guest.cgi</span>
<span class="synType">--- kagemai-0.8.8-orig//html/guest.cgi 2008-03-09 19:36:59.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//html/guest.cgi 2011-12-13 23:25:58.000000000 +0900</span>
<span class="synStatement">@@ -1,4 +1,4 @@</span>
<span class="synSpecial">-#!/usr/bin/env ruby</span>
<span class="synIdentifier">+#! /usr/local/bin/ruby</span>
=begin
guest.cgi - KAGEMAI CGI main
Copyright(C) 2002-2008 FUKUOKA Tomoyuki, DAIFUKUYA.
<span class="synType">diff -ur kagemai-0.8.8-orig//html/user.cgi kagemai-0.8.8//html/user.cgi</span>
<span class="synType">--- kagemai-0.8.8-orig//html/user.cgi 2008-03-09 19:36:59.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//html/user.cgi 2011-12-13 21:11:57.000000000 +0900</span>
<span class="synStatement">@@ -1,4 +1,4 @@</span>
<span class="synSpecial">-#!/usr/bin/env ruby</span>
<span class="synIdentifier">+#! /usr/local/bin/ruby</span>
=begin
user.cgi -- KAGEMAI CGI Interface (user mode).
=end
<span class="synType">diff -ur kagemai-0.8.8-orig//install_ja.rb kagemai-0.8.8//install_ja.rb</span>
<span class="synType">--- kagemai-0.8.8-orig//install_ja.rb 2008-03-09 19:37:00.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//install_ja.rb 2011-12-13 23:03:16.000000000 +0900</span>
<span class="synStatement">@@ -21,7 +21,7 @@</span>
### ￥〓￥〓￥&#185;￥〓〓&#188;￥〓〓〓〓〓〓〓〓〓
# ±〓〓〓〓〓〓〓〓〓〓〓￥〓￥&#173;￥〓￥〓￥〓￥〓
<span class="synSpecial">-$root_dir = '/usr/local/kagemai' </span>
<span class="synIdentifier">+$root_dir = '/var/www/html/kagemai' </span>
# CGI 〓〓￥&#185;￥〓￥〓￥〓￥&#183;〓&#188;￥〓
$html_dir = '/var/www/html/kagemai'
<span class="synType">diff -ur kagemai-0.8.8-orig//lib/kagemai/cgi/action/new_report.rb kagemai-0.8.8//lib/kagemai/cgi/action/new_report.rb</span>
<span class="synType">--- kagemai-0.8.8-orig//lib/kagemai/cgi/action/new_report.rb 2008-03-09 19:37:00.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//lib/kagemai/cgi/action/new_report.rb 2011-12-31 09:54:17.000000000 +0900</span>
<span class="synStatement">@@ -84,7 +84,7 @@</span>
store_attachments(@project, message, attachments)
begin
<span class="synSpecial">- report = @project.new_report(message)</span>
<span class="synIdentifier">+ report = @project.new_report(message, true, @cgi.get_param("hongera_rarara"))</span>
body   = eval_template('new_report.rhtml', {:report =&gt; report, :message =&gt; message})
title  = MessageBundle[:title_new_report_added]
rescue SpamError
<span class="synType">diff -ur kagemai-0.8.8-orig//lib/kagemai/kcgi.rb kagemai-0.8.8//lib/kagemai/kcgi.rb</span>
<span class="synType">--- kagemai-0.8.8-orig//lib/kagemai/kcgi.rb 2008-03-09 19:37:00.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//lib/kagemai/kcgi.rb 2011-12-13 21:58:59.000000000 +0900</span>
<span class="synStatement">@@ -153,7 +153,7 @@</span>
def self.do_get_param(key)
unless @params_r.has_key?(key) then
@params_r[key] = ''
<span class="synSpecial">- if @cgi.params[key].size &gt; 0 then</span>
<span class="synIdentifier">+ if @cgi.params[key].size &gt; 0 && key != "attachment" then</span>
@params_r[key] = @cgi.params[key].collect{|p| p.read}.join(",\n")
end
end
<span class="synType">diff -ur kagemai-0.8.8-orig//lib/kagemai/project.rb kagemai-0.8.8//lib/kagemai/project.rb</span>
<span class="synType">--- kagemai-0.8.8-orig//lib/kagemai/project.rb 2008-03-09 19:37:00.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//lib/kagemai/project.rb 2011-12-31 21:43:54.000000000 +0900</span>
<span class="synStatement">@@ -244,7 +244,8 @@</span>
@db_manager.count_reports(@report_type, attr_name)
end
<span class="synSpecial">- def new_report(message, mail = true)</span>
<span class="synIdentifier">+ def new_report(message, mail = true, spam_check = false)</span>
<span class="synIdentifier">+ raise SpamError if spam_check == "buster"</span>
raise SpamError if message.is_spam?(spam_filter())
report = nil
<span class="synStatement">@@ -286,22 +287,16 @@</span>
end
def spam_filter()
<span class="synSpecial">- return Proc.new{|strings| false} unless @use_filter</span>
<span class="synSpecial">- </span>
<span class="synSpecial">- # TODO: * &#179;°〓〓〓&#171;〓〓￥〓￥￡￥〓￥〓〓〓〓〓〓〓&#185;〓〓〓〓〓〓〓〓〓〓〓</span>
<span class="synSpecial">- # * ja/en 〓〓〓??〓±〓〓〓〓〓〓〓〓〓〓</span>
<span class="synSpecial">- return Proc.new{|strings| false} if @lang != 'ja'</span>
<span class="synIdentifier">+ return Proc.new{|strings| false} unless @use_filter </span>
Proc.new{|strings|
<span class="synSpecial">- use_japanese = false</span>
<span class="synSpecial">- strings.each do |string|</span>
<span class="synSpecial">- # 〓〓〓〓〓〓〓?機?〓〓〓〓〓〓〓〓〓〓&#171;〓〓￥〓￥§￥〓￥〓</span>
<span class="synSpecial">- if string =~ /[\xA1-\xFE][\xA1-\xFE]/ then</span>
<span class="synSpecial">- use_japanese = true</span>
<span class="synSpecial">- break</span>
<span class="synSpecial">- end</span>
<span class="synIdentifier">+</span>
<span class="synIdentifier">+ spam = false</span>
<span class="synIdentifier">+</span>
<span class="synIdentifier">+ if strings[0].scan("ttp").length &gt;= 2</span>
<span class="synIdentifier">+ spam = true</span>
end
<span class="synSpecial">- use_japanese == false</span>
<span class="synIdentifier">+ spam == true</span>
}
end
<span class="synType">diff -ur kagemai-0.8.8-orig//resource/en/template/_default/message_form.rhtml kagemai-0.8.8//resource/en/template/_default/message_form.rhtml</span>
<span class="synType">--- kagemai-0.8.8-orig//resource/en/template/_default/message_form.rhtml 2008-03-09 19:36:58.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//resource/en/template/_default/message_form.rhtml 2011-12-13 23:14:43.000000000 +0900</span>
<span class="synStatement">@@ -60,9 +60,7 @@</span>
&lt;th&gt;Options&lt;/th&gt;
&lt;td&gt;
<span class="synSpecial">- &lt;input type="checkbox" name="email_notification"</span>
<span class="synSpecial">- &lt;%= email_notification ? 'checked="checked"' : '' %&gt;&gt; Send</span>
<span class="synSpecial">- e-mail when there are replies</span>
<span class="synIdentifier">+ &lt;input type="hidden" name="email_notification"&gt;</span>
&lt;% if project.report_type.use_cookie? %&gt;
&lt;br&gt;
&lt;input type="checkbox" name="allow_cookie"
<span class="synType">diff -ur kagemai-0.8.8-orig//resource/en/template/_default/new_form.rhtml kagemai-0.8.8//resource/en/template/_default/new_form.rhtml</span>
<span class="synType">--- kagemai-0.8.8-orig//resource/en/template/_default/new_form.rhtml 2008-03-09 19:36:58.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//resource/en/template/_default/new_form.rhtml 2011-12-31 19:44:50.000000000 +0900</span>
<span class="synStatement">@@ -35,12 +35,16 @@</span>
&lt;% next if etype.report_attr && !etype.allow_user && Mode::USER.current? %&gt;
&lt;tr&gt;
&lt;% sclass = errors.has_id?(etype.id) ? 'class="error"' : '' %&gt;
<span class="synSpecial">- &lt;% html_input = error ? etype.html_input_with_error(cgi.get_param(etype.id)) : etype.html_input() %&gt;</span>
<span class="synIdentifier">+ &lt;% html_input = error ? etype.html_input_with_error(cgi.get_param(etype.id)) : etype.html_input(cgi.get_param(etype.id)) %&gt;</span>
&lt;th &lt;%= sclass %&gt;&gt;&lt;%= etype.name %&gt;&lt;%= etype.required? ? '&lt;small&gt;*&lt;/small&gt;' : '' %&gt;&lt;/th&gt;
&lt;td&gt;
&lt;%= html_input %&gt;
<span class="synIdentifier">+ &lt;% if etype.id == "attachment" then %&gt;</span>
<span class="synIdentifier">+ &lt;span class="form-desc"&gt;&lt;font color="red" font-weight="700"&gt;&lt;%= etype.html_description() %&gt;&lt;/font&gt;&lt;/span&gt;</span>
<span class="synIdentifier">+ &lt;% else %&gt;</span>
&lt;span class="form-desc"&gt;&lt;%= etype.html_description() %&gt;&lt;/span&gt;
<span class="synIdentifier">+ &lt;% end %&gt;</span>
&lt;/td&gt;
&lt;/tr&gt;
&lt;% end %&gt;
<span class="synStatement">@@ -49,9 +53,8 @@</span>
&lt;th&gt;Options&lt;/th&gt;
&lt;td&gt;
<span class="synSpecial">- &lt;input type="checkbox" &lt;%= email_notification ? 'checked="checked"' : '' %&gt;</span>
<span class="synSpecial">- name="email_notification"&gt; Send e-mail when there are</span>
<span class="synSpecial">- replies</span>
<span class="synIdentifier">+ &lt;input type="hidden" name="email_notification"&gt;</span>
<span class="synIdentifier">+ &lt;input type="checkbox" name="hongera_rarara" value="buster" &lt;%= cgi.get_param("rarara") ? '' : 'checked="checked"' %&gt;&gt; &lt;font color="red" font-weight="700"&gt; Please remove a check in the case of contribution.&lt;/font&gt;</span>
&lt;% if project.report_type.use_cookie? %&gt;
&lt;br&gt;
&lt;input type="checkbox" &lt;%= allow_cookie ? 'checked="checked"' : '' %&gt;
<span class="synType">diff -ur kagemai-0.8.8-orig//resource/en/template/_default/view_report.rhtml kagemai-0.8.8//resource/en/template/_default/view_report.rhtml</span>
<span class="synType">--- kagemai-0.8.8-orig//resource/en/template/_default/view_report.rhtml 2008-03-09 19:36:58.000000000 +0900</span>
<span class="synType">+++ kagemai-0.8.8//resource/en/template/_default/view_report.rhtml 2011-12-13 23:29:18.000000000 +0900</span>
<span class="synStatement">@@ -105,32 +105,5 @@</span>
&lt;% if Mode::ADMIN.current? then %&gt;
&lt;hr&gt;
<span class="synSpecial">-&lt;h2&gt;Change notification recipients&lt;/h2&gt;</span>
<span class="synSpecial">-</span>
<span class="synSpecial">-&lt;p&gt;Check the addresses that you wish to notify when this report is updated.&lt;/p&gt;</span>
<span class="synSpecial">-</span>
<span class="synSpecial">-&lt;form action="&lt;%= project.url %&gt;" </span>
<span class="synSpecial">- method="post" </span>
<span class="synSpecial">- accept-charset="&lt;%= project.charset %&gt;"&gt;</span>
<span class="synSpecial">-</span>
<span class="synSpecial">- &lt;p&gt;</span>
<span class="synSpecial">- &lt;% addresses = report.email_addresses(false) %&gt;</span>
<span class="synSpecial">- &lt;% addresses.each do |addr, notify| %&gt;</span>
<span class="synSpecial">- &lt;% checked = notify ? 'checked="checked"' : '' %&gt;</span>
<span class="synSpecial">- &lt;input type="checkbox" name="&lt;%= addr.escape_h %&gt;" &lt;%= checked %&gt;&gt; &lt;%= addr.escape_h %&gt;&lt;br&gt;</span>
<span class="synSpecial">- &lt;% end %&gt;</span>
<span class="synSpecial">- &lt;/p&gt;</span>
<span class="synSpecial">-</span>
<span class="synSpecial">- &lt;p&gt;&lt;input type="submit" value="Change settings"&gt;&lt;/p&gt;</span>
<span class="synSpecial">-</span>
<span class="synSpecial">- &lt;div&gt;</span>
<span class="synSpecial">- &lt;input type="hidden" name="action" value="&lt;%= SetEmailNotification.name %&gt;"&gt;</span>
<span class="synSpecial">- &lt;input type="hidden" name="project" value="&lt;%= project.id %&gt;"&gt;</span>
<span class="synSpecial">- &lt;input type="hidden" name="id" value="&lt;%= report.id %&gt;"&gt;</span>
<span class="synSpecial">- &lt;% if @lang == 'ja' %&gt;</span>
<span class="synSpecial">- &lt;input type="hidden" name="jp_enc_test" value="〓〓"&gt;</span>
<span class="synSpecial">- &lt;% end %&gt;</span>
<span class="synSpecial">- &lt;/div&gt;</span>
<span class="synSpecial">-&lt;/form&gt;</span>
&lt;% end %&gt;</pre>
</div>