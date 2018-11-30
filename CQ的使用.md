---


---

<h1 id="cq-website">cq website</h1>
<p><a href="http://isam-cq.web.alcatel-lucent.com/cqweb/">http://isam-cq.web.alcatel-lucent.com/cqweb/</a></p>
<h1 id="fault-report-status">Fault report status</h1>

<table>
<thead>
<tr>
<th>FR status</th>
<th>comment</th>
</tr>
</thead>
<tbody>
<tr>
<td>New</td>
<td>PT新提交一个bug时的状态</td>
</tr>
<tr>
<td>Accepted</td>
<td>bug经过IA初步分析，认为可能是问题，分给AE</td>
</tr>
<tr>
<td>Rejected</td>
<td>AE分析不是问题，和PT沟通一致后reject</td>
</tr>
<tr>
<td>Delivered</td>
<td>是AE提交代码后，应该把bug设置到Delivered的状态。具体是pullme之后就置状态</td>
</tr>
<tr>
<td>Build</td>
<td>AE分析问题，修改已经提交并编译</td>
</tr>
<tr>
<td>Resolved</td>
<td>修改已经merge到库</td>
</tr>
<tr>
<td>Verified</td>
<td>修改经过PT确认，已经得到解决</td>
</tr>
<tr>
<td>Duplicate/clone</td>
<td>该bug已经有提交，或者和某个提交是同一问题</td>
</tr>
<tr>
<td>hold</td>
<td>问题由于其他原因pending</td>
</tr>
<tr>
<td>Unplanned</td>
<td>由于其他原因，该问题不在本发布计划里</td>
</tr>
</tbody>
</table><blockquote>
<ol>
<li>
<p>同样的solution提交一次reviewme就可以</p>
</li>
<li>
<p>如果是我们引入的就详细填写下RCA Report(root cause analysis),不然的话可以和problem solution差不多</p>
</li>
<li>
<p>AE正常情况下只需要置deliver，后面Build/Resolved等状态是build系统自动做</p>
</li>
</ol>
</blockquote>
<h1 id="提交代码流程">提交代码流程</h1>
<ol>
<li>hg commit–&gt;code review</li>
<li>buildme</li>
<li>change state of FR from accepted to Delivered</li>
<li>pulleme<br>
这个的操作系统会自动修改FR后面的状态</li>
</ol>
<p>如果代码已经入库，需要自己手动修改状态：<br>
5. change state of FR from accepted to Delivered<br>
6. 中间根据提示填入信息<br>
7. 修改为build<br>
8. 修改为Resolved</p>
<p>![enter image description here](file:///C:/Users/daocain/Desktop/tmp/attachment.png)</p>
<p>![enter image description here](file:///C:/Users/daocain/Desktop/tmp/clone.png)</p>
<p>![enter image description here](file:///C:/Users/daocain/Desktop/tmp/general.png)</p>
<h1 id="cq中几种角色说明">CQ中几种角色说明</h1>

<table>
<thead>
<tr>
<th>rule</th>
<th>comment</th>
</tr>
</thead>
<tbody>
<tr>
<td>IA</td>
<td>Implementation Authority,需求或者bug的owner,有责任去跟踪记录的状态。</td>
</tr>
<tr>
<td>AE</td>
<td>Assigned Engineer，实际解决该问题的人。</td>
</tr>
<tr>
<td>Submitter</td>
<td>需求或者bug的提出者，可以是测试人员或者开发人员</td>
</tr>
<tr>
<td>TPM</td>
<td>technology project management,每个项目有自己的TPM</td>
</tr>
</tbody>
</table><h1 id="平台的ia是谁">平台的IA是谁</h1>

<table>
<thead>
<tr>
<th>erea</th>
<th>who</th>
<th>userid</th>
</tr>
</thead>
<tbody>
<tr>
<td>Plt service</td>
<td>chen bin</td>
<td></td>
</tr>
<tr>
<td>Plt service</td>
<td>zhang huiyong</td>
<td></td>
</tr>
<tr>
<td>Plt low level</td>
<td>liu wei</td>
<td>wliu034</td>
</tr>
</tbody>
</table><p>平台分四个FDT(feature development team):<br>
刘伟 1591，陈彬 1395， 宋志敏 1297， chuzhuliang 1592</p>
<h1 id="fr等级">FR等级</h1>

<table>
<thead>
<tr>
<th>level</th>
<th>comment</th>
</tr>
</thead>
<tbody>
<tr>
<td>1-Critical</td>
<td>最严重的等级</td>
</tr>
<tr>
<td>2-Major</td>
<td></td>
</tr>
<tr>
<td>3-Minor</td>
<td>最低的等级</td>
</tr>
</tbody>
</table>
