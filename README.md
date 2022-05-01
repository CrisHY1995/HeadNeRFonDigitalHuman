# 高保真参数化人脸头部模型——HeadNeRF
2021年12月份，Epic公司发布了基于它们自家虚幻5打造的《黑客帝国: 觉醒》的演示[Demo](https://www.bilibili.com/video/BV1rY411p7Tg?spm_id_from=333.337.search-card.all.click)，其中展示的主演人物的毛孔毛发级的高真实感建模着实让人惊叹Epic的技术强大。

https://user-images.githubusercontent.com/49339865/166149034-942c38e1-f458-4fe1-a59d-2d3211c88ca1.mp4

据悉，以上演示Demo中的人物形象是由Epic名下应用[MetaHuman Creator](https://www.unrealengine.com/zh-CN/metahuman-creator)创建生成的，该应用可以让用户自由编辑调整目标数字形象的各种面部特征和皮肤细节，甚至于精确编辑调整发型、眼型、妆容等各个局部语义属性，且调整结果具有超逼真的显示渲染效果。

https://user-images.githubusercontent.com/49339865/166149045-ffae6443-2082-4910-97c7-f7a33c87daca.mp4

对比之前的游戏建模，MetaHumane Creator的渲染效果，可以说已经非常逼近图形学一直追求的以假乱真的CG技术。
