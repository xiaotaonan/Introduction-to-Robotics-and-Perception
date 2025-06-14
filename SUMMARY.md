# Table of contents

* [Introduction-to-Robotics-and-Perception](README.md)
* [封面](feng-mian.md)
* [前言](qian-yan.md)

## 目录

* [第一章 简介](mu-lu/di-yi-zhang-jian-jie/README.md)
  * [1.1 模型](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/README.md)
    * [1.1.1 状态](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/1.1.1-zhuang-tai/README.md)
      * [1.1.1.1 表示世界状态](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/1.1.1-zhuang-tai/1.1.1.1-biao-shi-shi-jie-zhuang-tai.md)
      * [1.1.1.2 表示机器人状态](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/1.1.1-zhuang-tai/1.1.1.2-biao-shi-ji-qi-ren-zhuang-tai.md)
    * [1.1.2 动作](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/1.1.2-dong-zuo.md)
    * [1.1.3 传感器](mu-lu/di-yi-zhang-jian-jie/1.1-mo-xing/1.1.3-chuan-gan-qi.md)
  * [1.2 推理](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/README.md)
    * [1.2.1 感知](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.1-gan-zhi.md)
    * [1.2.2 规划](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.2-gui-hua/README.md)
      * [1.2.2.1 任务规划](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.2-gui-hua/1.2.2.1-ren-wu-gui-hua.md)
      * [1.2.2.2 路径规划](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.2-gui-hua/1.2.2.2-lu-jing-gui-hua.md)
      * [1.2.2.3 轨迹规划](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.2-gui-hua/1.2.2.3-gui-ji-gui-hua.md)
    * [1.2.3 学习](mu-lu/di-yi-zhang-jian-jie/1.2-tui-li/1.2.3-xue-xi.md)
  * [1.3 机器人数学](mu-lu/di-yi-zhang-jian-jie/1.3-ji-qi-ren-shu-xue/README.md)
    * [1.3.1 概率论与统计学](mu-lu/di-yi-zhang-jian-jie/1.3-ji-qi-ren-shu-xue/1.3.1-gaillun-yu-tong-ji-xue.md)
    * [1.3.2 线性代数](mu-lu/di-yi-zhang-jian-jie/1.3-ji-qi-ren-shu-xue/1.3.2-xian-xing-dai-shu.md)
    * [1.3.3 优化](mu-lu/di-yi-zhang-jian-jie/1.3-ji-qi-ren-shu-xue/1.3.3-you-hua.md)

***

* [第二章 垃圾分类机器人](di-er-zhang-la-ji-fen-lei-ji-qi-ren/README.md)
  * [2.1 世界状态建模](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/README.md)
    * [2.1.1 使用概率来模拟不确定性](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.1-shi-yong-gaillai-mo-ni-bu-que-ding-xing.md)
    * [2.1.2 概率分布](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.2-gailfen-bu.md)
    * [2.1.3 先验概率分布](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.3-xian-yan-gailfen-bu.md)
    * [2.1.4  Python 中的概率分布](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.4-python-zhong-de-gailfen-bu.md)
    * [2.1.5 通过采样进行模拟](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.5-tong-guo-cai-yang-jin-xing-mo-ni/README.md)
      * [2.1.5.1 累积分布函数](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.5-tong-guo-cai-yang-jin-xing-mo-ni/2.1.5.1-lei-ji-fen-bu-han-shu.md)
      * [2.1.5.2 示例](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.5-tong-guo-cai-yang-jin-xing-mo-ni/2.1.5.2-shi-li.md)
    * [2.1.6 GTSAM101](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.1-shi-jie-zhuang-tai-jian-mo/2.1.6-gtsam101.md)
  * [2.2 垃圾分类行为](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei.md)
    * [2.2.1 建模动作及其效果](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.1-jian-mo-dong-zuo-ji-qi-xiao-guo.md)
    * [2.2.2 离散随机变量](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.2-li-san-sui-ji-bian-liang.md)
    * [2.2.3 期望](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.3-qi-wang.md)
    * [2.2.4 通过采样进行模拟](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.4-tong-guo-cai-yang-jin-xing-mo-ni.md)
    * [2.2.5 概率论与统计学](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.5-gaillun-yu-tong-ji-xue.md)
    * [2.2.6 总结](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.2-la-ji-fen-lei-xing-wei/2.2.6-zong-jie.md)
  * [2.3 垃圾分类传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/README.md)
    * [2.3.1 二进制传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.1-er-jin-zhi-chuan-gan-qi.md)
    * [2.3.2 条件概率](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.2-tiao-jian-gai-l.md)
    * [2.3.3 多值传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.3-duo-zhi-chuan-gan-qi.md)
    * [2.3.4 连续值传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.4-lian-xu-zhi-chuan-gan-qi.md)
    * [2.3.5 通过采样进行模拟](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.5-tong-guo-cai-yang-jin-xing-mo-ni.md)
    * [2.3.6 模拟多个传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.6-mo-ni-duo-ge-chuan-gan-qi.md)
    * [2.3.7 GTSAM 101](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.7-gtsam-101/README.md)
      * [2.3.7.1 离散条件](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.7-gtsam-101/2.3.7.1-li-san-tiao-jian.md)
      * [2.3.7.2 离散值](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.7-gtsam-101/2.3.7.2-li-san-zhi.md)
      * [2.3.7.3 采样](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.3-la-ji-fen-lei-chuan-gan-qi/2.3.7-gtsam-101/2.3.7.3-cai-yang.md)
  * [2.4 感知](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi.md)
    * [2.4.1 最大似然法](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4.1-zui-da-si-ran-fa.md)
    * [2.4.2 似然函数](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.2-si-ran-han-shu.md)
    * [2.4.3 探索可能性](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.3-tan-suo-ke-neng-xing.md)
    * [2.4.4 离散传感器的可能性](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.4-li-san-chuan-gan-qi-de-ke-neng-xing.md)
    * [2.4.5 可能性因素](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.5-ke-neng-xing-yin-su.md)
    * [2.4.6 联合分布](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.6-lian-he-fen-bu.md)
    * [2.4.7 边际分布](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.7-bian-ji-fen-bu.md)
    * [2.4.8 贝叶斯定理](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.8-bei-ye-si-ding-li.md)
    * [2.4.9 MAP 估计](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.9-map-gu-ji.md)
    * [2.4.10  融合多个测量值](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.10-rong-he-duo-ge-ce-liang-zhi.md)
    * [2.4.11 GTSAM 101](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.11-gtsam-101/README.md)
      * [2.4.11.1 因素](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.11-gtsam-101/2.4.11.1-yin-su.md)
      * [2.4.11.2 枚举和离散值](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.11-gtsam-101/2.4.11.2-mei-ju-he-li-san-zhi.md)
      * [2.4.11.3 条件积和因子积](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.4-gan-zhi/2.4.11-gtsam-101/2.4.11.3-tiao-jian-ji-he-yin-zi-ji.md)
  * [2.5 决策理论](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/README.md)
    * [2.5.1 使用先验进行简单的决策](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.1-shi-yong-xian-yan-jin-xing-jian-dan-de-jue-ce.md)
    * [2.5.2 针对最坏情况进行优化](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.2-zhen-dui-zui-huai-qing-kuang-jin-xing-you-hua.md)
    * [2.5.3 最小化预期成本](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.3-zui-xiao-hua-yu-qi-cheng-ben/README.md)
      * [2.5.3.1 Python 实现](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.3-zui-xiao-hua-yu-qi-cheng-ben/2.5.3.1-python-shi-xian.md)
      * [2.5.4 合并传感器信息](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.3-zui-xiao-hua-yu-qi-cheng-ben/2.5.4-he-bing-chuan-gan-qi-xin-xi.md)
  * [2.6 学习](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.5-jue-ce-li-lun/2.5.3-zui-xiao-hua-yu-qi-cheng-ben/2.6-xue-xi.md)
    * [2.6.1 估计离散 PMF](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.1-gu-ji-li-san-pmf/README.md)
      * [2.6.1.1 平滑](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.1-gu-ji-li-san-pmf/2.6.1.1-ping-hua.md)
    * [2.6.2 根据数据建模传感器](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.2-gen-ju-shu-ju-jian-mo-chuan-gan-qi.md)
    * [2.6.3 拟合高斯](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.3-ni-he-gao-si/README.md)
      * [2.6.3.1 比较](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.3-ni-he-gao-si/2.6.3.1-bi-jiao.md)
    * [2.6.4 总结](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.6-xue-xi/2.6.4-zong-jie.md)
  * [2.7 章节小结](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.7-zhang-jie-xiao-jie/README.md)
    * [2.7.1 模型](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.7-zhang-jie-xiao-jie/2.7.1-mo-xing.md)
    * [2.7.2 推理](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.7-zhang-jie-xiao-jie/2.7.2-tui-li.md)
    * [2.7.3 背景和历史](di-er-zhang-la-ji-fen-lei-ji-qi-ren/2.7-zhang-jie-xiao-jie/2.7.3-bei-jing-he-li-shi.md)
* [第三章 机器人吸尘器](di-san-zhang-ji-qi-ren-xi-chen-qi.md)
  * [3.1. 对扫地机器人的状态进行建模](di-san-zhang-ji-qi-ren-xi-chen-qi/3.1.-dui-sao-di-ji-qi-ren-de-zhuang-tai-jin-xing-jian-mo/README.md)
    * [3.1.1. 定义机器人的状态](di-san-zhang-ji-qi-ren-xi-chen-qi/3.1.-dui-sao-di-ji-qi-ren-de-zhuang-tai-jin-xing-jian-mo/3.1.1.-ding-yi-ji-qi-ren-de-zhuang-tai.md)
    * [3.1.2. 扫地机器人的状态空间](di-san-zhang-ji-qi-ren-xi-chen-qi/3.1.-dui-sao-di-ji-qi-ren-de-zhuang-tai-jin-xing-jian-mo/3.1.2.-sao-di-ji-qi-ren-de-zhuang-tai-kong-jian.md)
    * [3.1.3. 贝叶斯 vs. 概率论解释或概率](di-san-zhang-ji-qi-ren-xi-chen-qi/3.1.-dui-sao-di-ji-qi-ren-de-zhuang-tai-jin-xing-jian-mo/3.1.3.-bei-ye-si-vs.-gaillun-jie-shi-huo-gai-l.md)
    * [3.1.4. GTSAM 101](di-san-zhang-ji-qi-ren-xi-chen-qi/3.1.-dui-sao-di-ji-qi-ren-de-zhuang-tai-jin-xing-jian-mo/3.1.4.-gtsam-101.md)
  * [3.2. 随时间推移的行动](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/README.md)
    * [3.2.1. 行动的概率结果](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.1.-xing-dong-de-gailjie-guo/README.md)
      * [3.2.1.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.1.-xing-dong-de-gailjie-guo/3.2.1.1.-lian-xi.md)
    * [3.2.2. 了解动作序列](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.2.-liao-jie-dong-zuo-xu-lie.md)
    * [3.2.3. 状态转换矩阵和置信状态](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.3.-zhuang-tai-zhuan-huan-ju-zhen-he-zhi-xin-zhuang-tai.md)
      * [3.2.3.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.3.-zhuang-tai-zhuan-huan-ju-zhen-he-zhi-xin-zhuang-tai/3.2.3.1.-lian-xi.md)
    * [3.2.4. 受控马尔可夫链](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.4.-shou-kong-ma-er-ke-fu-lian/README.md)
      * [3.2.4.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.4.-shou-kong-ma-er-ke-fu-lian/3.2.4.1.-lian-xi.md)
    * [3.2.5. 正向模拟](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.5.-zheng-xiang-mo-ni/README.md)
      * [3.2.5.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.5.-zheng-xiang-mo-ni/3.2.5.1.-lian-xi.md)
    * [3.2.6. 贝叶斯网络](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.6.-bei-ye-si-wang-luo/README.md)
      * [3.2.6.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.6.-bei-ye-si-wang-luo/3.2.6.1.-lian-xi.md)
    * [3.2.7. 因式分解状态表示](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.7.-yin-shi-fen-jie-zhuang-tai-biao-shi/README.md)
      * [3.2.7.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.7.-yin-shi-fen-jie-zhuang-tai-biao-shi/3.2.7.1.-lian-xi.md)
    * [3.2.8. GTSAM 101](di-san-zhang-ji-qi-ren-xi-chen-qi/3.2.-sui-shi-jian-tui-yi-de-xing-dong/3.2.8.-gtsam-101.md)
  * [3.3. 动态贝叶斯网络](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/README.md)
    * [3.3.1. 传感器模型](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.1.-chuan-gan-qi-mo-xing/README.md)
      * [3.3.1.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.1.-chuan-gan-qi-mo-xing/3.3.1.1.-lian-xi.md)
    * [3.3.2. 动态贝叶斯网络简介](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.2.-dong-tai-bei-ye-si-wang-luo-jian-jie.md)
    * [3.3.3. 祖先采样](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.3.-zu-xian-cai-yang.md)
    * [3.3.4. 机器人的模拟](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.4.-ji-qi-ren-de-mo-ni/README.md)
      * [3.3.4.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.4.-ji-qi-ren-de-mo-ni/3.3.4.1.-lian-xi.md)
    * [3.3.5. 使用 GTSAM 进行祖先采样](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.5.-shi-yong-gtsam-jin-xing-zu-xian-cai-yang/README.md)
      * [3.3.5.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.5.-shi-yong-gtsam-jin-xing-zu-xian-cai-yang/3.3.5.1.-lian-xi.md)
    * [3.3.6. GTSAM 101](di-san-zhang-ji-qi-ren-xi-chen-qi/3.3.-dong-tai-bei-ye-si-wang-luo/3.3.6.-gtsam-101.md)
  * [3.4. 使用图形模型的感知](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/README.md)
    * [3.4.1. 贝叶斯网络中的推理](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.1.-bei-ye-si-wang-luo-zhong-de-tui-li.md)
      * [3.4.1.1.完全后验推理](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.1.-bei-ye-si-wang-luo-zhong-de-tui-li/3.4.1.1.-wan-quan-hou-yan-tui-li.md)
      * [3.4.1.2. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.1.-bei-ye-si-wang-luo-zhong-de-tui-li/3.4.1.2.-lian-xi.md)
      * [3.4.1.3. 最大后验估计](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.1.-bei-ye-si-wang-luo-zhong-de-tui-li/3.4.1.3.-zui-da-hou-yan-gu-ji.md)
      * [3.4.1.4. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.1.-bei-ye-si-wang-luo-zhong-de-tui-li/3.4.1.4.-lian-xi.md)
    * [3.4.2. 隐马尔可夫模型](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.2.-yin-ma-er-ke-fu-mo-xing/README.md)
      * [3.4.2.1. 示例：描述 robot 的 HMM](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.2.-yin-ma-er-ke-fu-mo-xing/3.4.2.1.-shi-li-miao-shu-robot-de-hmm.md)
    * [3.4.3. HMM 中的朴素推理](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.3.-hmm-zhong-de-pu-su-tui-li.md)
    * [3.4.4. 因子图](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.4.-yin-zi-tu.md)
    * [3.4.5. 将贝叶斯网络转换为因子图](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.5.-jiang-bei-ye-si-wang-luo-zhuan-huan-wei-yin-zi-tu/README.md)
      * [3.4.5.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.5.-jiang-bei-ye-si-wang-luo-zhuan-huan-wei-yin-zi-tu/3.4.5.1.-lian-xi.md)
    * [3.4.6. GTSAM 中的因子图](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.6.-gtsam-zhong-de-yin-zi-tu.md)
    * [3.4.7. 使用因子图进行计算](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.7.-shi-yong-yin-zi-tu-jin-xing-ji-suan.md)
    * [3.4.8. HMM 的 max-product 算法](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.8.-hmm-de-maxproduct-suan-fa.md)
      * [3.4.8.1. GTSAM 中的最大乘积](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.8.-hmm-de-maxproduct-suan-fa/3.4.8.1.-gtsam-zhong-de-zui-da-cheng-ji.md)
    * [3.4.9. HMM 的 Sum-Product 算法](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.9.-hmm-de-sumproduct-suan-fa.md)
    * [3.4.10. GTSAM 中的 sum-product](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.10.-gtsam-zhong-de-sumproduct.md)
    * [3.4.11. 采样和后验均值\*](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.11.-cai-yang-he-hou-yan-jun-zhi/README.md)
      * [3.4.11.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.11.-cai-yang-he-hou-yan-jun-zhi/3.4.11.1.-lian-xi.md)
    * [3.4.12. GTSAM 101](di-san-zhang-ji-qi-ren-xi-chen-qi/3.4.-shi-yong-tu-xing-mo-xing-de-gan-zhi/3.4.12.-gtsam-101.md)
  * [3.5. 马尔可夫决策过程](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng.md)
    * [3.5.1. 奖励函数](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.1.-jiang-li-han-shu.md)
    * [3.5.2. 预期奖励](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.2.-yu-qi-jiang-li.md)
    * [3.5.3. 用于定义作序列的实用程序](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.3.-yong-yu-ding-yi-zuo-xu-lie-de-shi-yong-cheng-xu.md)
    * [3.5.4.使用控制带展开来近似预期效用](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.4.-shi-yong-kong-zhi-dai-zhan-kai-lai-jin-si-yu-qi-xiao-yong/README.md)
      * [3.5.4.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.4.-shi-yong-kong-zhi-dai-zhan-kai-lai-jin-si-yu-qi-xiao-yong/3.5.4.1.-lian-xi.md)
    * [3.5.5. 策略](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.5.-ce-le.md)
    * [3.5.6. Value 函数（针对给定策略）](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.6.-value-han-shu-zhen-dui-gei-ding-ce-le/README.md)
      * [3.5.6.1. 思维练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.6.-value-han-shu-zhen-dui-gei-ding-ce-le/3.5.6.1.-si-wei-lian-xi.md)
    * [3.5.7. 逼近 Value 函数](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.7.-bi-jin-value-han-shu.md)
    * [3.5.8. 计算值函数](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.8.-ji-suan-zhi-han-shu/README.md)
      * [3.5.8.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.8.-ji-suan-zhi-han-shu/3.5.8.1.-lian-xi.md)
    * [3.5.9. 小结](di-san-zhang-ji-qi-ren-xi-chen-qi/3.5.-ma-er-ke-fu-jue-ce-guo-cheng/3.5.9.-xiao-jie.md)
  * [3.6. 学会以最佳方式行事](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/README.md)
    * [3.6.1. 最优值函数](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.1.-zui-you-zhi-han-shu.md)
    * [3.6.2.操作值和最优策略](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.2.-cao-zuo-zhi-he-zui-you-ce-le.md)
      * [3.6.2.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.2.-cao-zuo-zhi-he-zui-you-ce-le/3.6.2.1.-lian-xi.md)
    * [3.6.3. 策略迭代](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.3.-ce-le-die-dai.md)
    * [3.6.4. 值迭代](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.4.-zhi-die-dai/README.md)
      * [3.6.4.1. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.4.-zhi-die-dai/3.6.4.1.-lian-xi.md)
    * [3.6.5. 基于模型的强化学习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.5.-ji-yu-mo-xing-de-qiang-hua-xue-xi.md)
    * [3.6.6. 无模型强化学习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.6.-wu-mo-xing-qiang-hua-xue-xi/README.md)
      * [3.6.6.1. 勘探与开发](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.6.-wu-mo-xing-qiang-hua-xue-xi/3.6.6.1.-kan-tan-yu-kai-fa.md)
      * [3.6.6.2. 练习](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.6.-wu-mo-xing-qiang-hua-xue-xi/3.6.6.2.-lian-xi.md)
    * [3.6.7. 小结](di-san-zhang-ji-qi-ren-xi-chen-qi/3.6.-xue-hui-yi-zui-jia-fang-shi-xing-shi/3.6.7.-xiao-jie.md)
  * [3.7. 章节总结](di-san-zhang-ji-qi-ren-xi-chen-qi/3.7.-zhang-jie-zong-jie/README.md)
    * [3.7.1. 模型](di-san-zhang-ji-qi-ren-xi-chen-qi/3.7.-zhang-jie-zong-jie/3.7.1.-mo-xing.md)
    * [3.7.2. 推理](di-san-zhang-ji-qi-ren-xi-chen-qi/3.7.-zhang-jie-zong-jie/3.7.2.-tui-li.md)
    * [3.7.3. 背景和历史](di-san-zhang-ji-qi-ren-xi-chen-qi/3.7.-zhang-jie-zong-jie/3.7.3.-bei-jing-he-li-shi.md)
* [第四章 2D 仓库机器人](di-si-zhang-2d-cang-ku-ji-qi-ren.md)
  * [4.1. 连续状态](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/README.md)
    * [4.1.1. 高斯密度](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.1.-gao-si-mi-du.md)
    * [4.1.2. 有限元法](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.2.-you-xian-yuan-fa.md)
    * [4.1.3. 基于 Sampling 的表示。](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.3.-ji-yu-sampling-de-biao-shi.md)
    * [4.1.4. 计算概率](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.4.-ji-suan-gai-l.md)
    * [4.1.5. GTSAM 101](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.5.-gtsam-101.md)
    * [4.1.6. GTbook 101](di-si-zhang-2d-cang-ku-ji-qi-ren/4.1.-lian-xu-zhuang-tai/4.1.6.-gtbook-101.md)
  * [4.2. 在 2D 中移动](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong.md)
    * [4.2.1. 全向轮](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.1.-quan-xiang-lun.md)
    * [4.2.2.Omni Wheels 的运动学](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.2.omni-wheels-de-yun-dong-xue.md)
    * [4.2.3. 雅可比矩阵](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.3.-ya-ke-bi-ju-zhen.md)
    * [4.2.4. 全向运动实践](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.4.-quan-xiang-yun-dong-shi-jian.md)
    * [4.2.5. 高斯动态贝叶斯网络](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.5.-gao-si-dong-tai-bei-ye-si-wang-luo.md)
    * [4.2.6. 代码中的高斯 DBN](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.6.-dai-ma-zhong-de-gao-si-dbn/README.md)
      * [4.2.6.1. 练习](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.6.-dai-ma-zhong-de-gao-si-dbn/4.2.6.1.-lian-xi.md)
    * [4.2.7. 模拟 ContinuousTrajectory](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.7.-mo-ni-continuoustrajectory.md)
    * [4.2.8. GTSAM 101](di-si-zhang-2d-cang-ku-ji-qi-ren/4.2.-zai-2d-zhong-yi-dong/4.2.8.-gtsam-101.md)
  * [4.3. 具有连续状态的传感器模型](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/README.md)
    * [4.3.1. 接近传感器](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.1.-jie-jin-chuan-gan-qi.md)
    * [4.3.2. 雷达传感器](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.2.-lei-da-chuan-gan-qi.md)
    * [4.3.3. 感知范围内无信标的情况](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.3.-gan-zhi-fan-wei-nei-wu-xin-biao-di-qing-kuang.md)
    * [4.3.4. 类似 GPS 的位置传感器](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.4.-lei-si-gps-de-wei-zhi-chuan-gan-qi.md)
    * [4.3.5. 模拟状态和测量](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.5.-mo-ni-zhuang-tai-he-ce-liang.md)
    * [4.3.6. GPS 风格的似然函数](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.6.-gps-feng-ge-de-si-ran-han-shu.md)
    * [4.3.7. GTbook 101](di-si-zhang-2d-cang-ku-ji-qi-ren/4.3.-ju-you-lian-xu-zhuang-tai-de-chuan-gan-qi-mo-xing/4.3.7.-gtbook-101.md)
  * [4.4. 定位](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/README.md)
    * [4.4.1. 一个运行示例](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.1.-yi-ge-yun-xing-shi-li.md)
    * [4.4.2. 贝叶斯滤波器](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.2.-bei-ye-silbo-qi.md)
    * [4.4.3. 马尔可夫定位](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/README.md)
      * [4.4.3.1. 一个一维示例](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.3.1.-yi-ge-yi-wei-shi-li.md)
      * [4.4.3.2. 仓库示例](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.3.2.-cang-ku-shi-li.md)
      * [4.4.3.3. 练习](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.3.3.-lian-xi.md)
    * [4.4.4. 蒙特卡洛定位](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.4.-meng-te-ka-luo-ding-wei/README.md)
      * [4.4.4.1. 预测步骤](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.4.-meng-te-ka-luo-ding-wei/4.4.4.1.-yu-ce-bu-zhou.md)
      * [4.4.4.2. 更新步骤中评估似然](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.4.-meng-te-ka-luo-ding-wei/4.4.4.2.-geng-xin-bu-zhou-zhong-ping-gu-si-ran.md)
      * [4.4.4.3. MCL 仓库示例](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.3.-ma-er-ke-fu-ding-wei/4.4.4.-meng-te-ka-luo-ding-wei/4.4.4.3.-mcl-cang-ku-shi-li.md)
    * [4.4.5. 卡尔曼平滑和滤波](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.5.-ka-er-man-ping-hua-helbo/README.md)
      * [4.4.5.1. 因子图和最小二乘](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.5.-ka-er-man-ping-hua-helbo/4.4.5.1.-yin-zi-tu-he-zui-xiao-er-cheng.md)
      * [4.4.5.2. 数值示例](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.5.-ka-er-man-ping-hua-helbo/4.4.5.2.-shu-zhi-shi-li.md)
      * [4.4.5.3. 练习](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.5.-ka-er-man-ping-hua-helbo/4.4.5.3.-lian-xi.md)
      * [4.4.5.4. 稀疏最小二乘法](di-si-zhang-2d-cang-ku-ji-qi-ren/4.4.-ding-wei/4.4.5.-ka-er-man-ping-hua-helbo/4.4.5.4.-xi-shu-zui-xiao-er-cheng-fa.md)
