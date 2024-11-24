## <ALIPAY_TAG_TMPL>

```json
{"tag.profile.name":"支付宝_<ALIPAY_TAG_TMPL_NAME><ALIPAY_TAG_TMPL_WITHOUT_NOTTAG>_<ALIPAY_TAG_TMPL_DATE>","tag.profile.date":"<ALIPAY_TAG_TMPL_DATE>","tag.profile.length":2,"tag.profile.size":<ALIPAY_TAG_TMPL_LENGTH>,"tag.profile.data":[{"tag.profile.fields":{"field1":"<ALIPAY_TAG_TMPL_URL_TMPL>","field2":"1"},"tag.profile.config":{"requestType":"2","itemRecordExtra":"","itemDescription":"https://<ALIPAY_TAG_TMPL_URL_TMPL>","itemRecord":"https://<ALIPAY_TAG_TMPL_URL_TMPL>"}},{"tag.profile.fields":{"field1":"com.eg.android.AlipayGphone"},"tag.profile.config":{"requestType":"3","itemRecordExtra":"","itemDescription":"com.eg.android.AlipayGphone","itemRecord":"com.eg.android.AlipayGphone"}}]}
```


## <ALIPAY_TAG_TMPL_NAME>

标签名字, 收款码/红包码/收款码_无标识/收款码+红包码/收款码_无标识+红包码/自定义链接


## <ALIPAY_TAG_TMPL_WITHOUT_NOTTAG>

不带有 noT 参数的提示语, 默认为 _无标识


## <ALIPAY_TAG_TMPL_DATE>

生成日期, 应为 NFC Tools PRO 的日期格式 20241124T184000


## <ALIPAY_TAG_TMPL_LENGTH>

标签内容长度, 应该为 urlencode 完的不带 https:// 的链接(即 <ALIPAY_TAG_TMPL_URL_TMPL> )的字符长度 + 50


## <ALIPAY_TAG_TMPL_URL_TMPL>

链接模板, 应为: 
`render.alipay.com/p/s/ulink/<ALIPAY_TAG_TMPL_URL_TYPE>?s=dc&scheme=alipay%3A%2F%2Fnfc%2Fapp%3Fid%3D10000007%26actionType%3Droute%26codeContent%3D<ALIPAY_TAG_TMPL_URL_TARGET>`
其中的参数如下


## <ALIPAY_TAG_TMPL_URL_TYPE>

链接类型, sn 为收款码, nrps 为红包码, dc0 为点餐码


## <ALIPAY_TAG_TMPL_URL_TARGET>

标签的 url 目标, 带协议头. 
收款码链接示例: `https%253A%252F%252Fqr.alipay.com%252F<ALIPAY_TAG_TMPL_URL_TARGET_CODE>%253FnoT%253Dntagtqp`
应该 urlencode 两次, 支持 http/https 但不建议 http, 也支持 ip 但是使用 ip 支付宝会弹窗提醒
其中 <ALIPAY_TAG_TMPL_URL_TARGET_CODE> 为任意收款码中的 23 位数小写字母数字, 或者碰一下红包码的 23 位小写字母数字, 其他红包码 (30 位大小写字母数字)不支持
注意. noT=ntagtqp 参数在红包码必须要有; 收款码中可有可无, 有则可以享受碰一下优惠, 但是收款商户要有碰一下权限, 无则反之; 点餐码中可有可无, 有则会展示 碰一下点餐 splash, 无则没有此提示
