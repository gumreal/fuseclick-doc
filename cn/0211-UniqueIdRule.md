# Unique Click

广告点击数据中，经常会有重复点击。导致点击重复的原因有很多：
* 用户多次点击；
* 广告跳转过程中的某个中转系统重复转发点击数据;
* 某些作弊软件制造虚假点击以获取收益。


一般在固定时间段内将来自于一个独立 IP 的点击， 算作一次 Unique Click。

# 自定义 Unique ID 计算规则
在 FuseClick 平台，参与 Unique ID 计算的参数，除了IP，还可以选择以下参数：
* Offer
* Affiliate
* 子渠道 Sub Affiliate ID （即sub_affid）
* User Agent
* Device ID
* Affiliate Sub ID 1（即s1）
* Affiliate Sub ID 2（即s2）
* Affiliate Sub ID 3（即s3）
* Affiliate Sub ID 4（即s4）
* Affiliate Sub ID 5（即s5）
* Traffic Source

例如：参数选择 Offer、Device ID，则表示一台设备一天之内到某个 Offer 上的点击，只计做一个 Unique ID。
以上条件出现重复点击，在查看数据时，这些点击的 Unique ID均相同。 
针对同一渠道，对比其Unique Click及Gross Click的数量，就可推断出其Click的质量。

## 默认 Unique ID 规则
在系统 Setting 里设置的 Unique ID 规则，属于全局设置，新建 Offer 均默认使用该规则。

## Offer Unique ID 规则
可以按照 Offer 类型、或者广告主要求，为 Offer 设置特定的 Unique ID规则。
例如，广告主要求每个 APP 用户每天不能重复转化， 而渠道对接使用 Sub ID 1 传递 APP 的用户ID，就可以这样设置该 Offer 的 Unique ID 规则：
* Offer
* Sub ID 1

# 使用 Unique ID 约束转化
FuseClick Offer 有个属性，可以使得相同 Unique ID的Click，只有一个转化是有效的。
这个选项是 ”Limit Conversion by Unique ID“。

打开这个选项，接受到转化请求后，FuseClick 平台会搜索具有与该转化相同 Unique ID 的点击数据，如果之前已经有该 Unique ID 的 Click 数据带来转化，则会拒绝当前转化请求。
这个可以在很大程度上，使得重复点击、虚假流量不能获得收益。
