# 高保真参数化人脸头部模型——HeadNeRF
2021年12月份，Epic公司发布了基于它们自家虚幻5打造的《黑客帝国: 觉醒》的演示[Demo](https://www.bilibili.com/video/BV1rY411p7Tg?spm_id_from=333.337.search-card.all.click)，其中展示的主演人物的毛孔毛发级的高真实感建模着实让人惊叹Epic的技术强大。

https://user-images.githubusercontent.com/49339865/166149034-942c38e1-f458-4fe1-a59d-2d3211c88ca1.mp4

据悉，以上演示Demo中的人物形象是由Epic名下应用[MetaHuman Creator](https://www.unrealengine.com/zh-CN/metahuman-creator)创建生成的，该应用可以让用户自由编辑调整目标数字形象的各种面部特征和皮肤细节，甚至于精确编辑调整发型、眼型、妆容等各个局部语义属性，且调整结果具有超逼真的显示渲染效果。

https://user-images.githubusercontent.com/49339865/166149045-ffae6443-2082-4910-97c7-f7a33c87daca.mp4

对比之前的游戏建模，MetaHumane Creator的渲染效果，可以说已经非常逼近图形学一直追求的以假乱真的CG技术。

<p align="center">
    <img src="laola_images.jpg" alt> <br>
    <em>游戏古墓丽影历代劳拉形象</em>
</p>

略有瑕疵的是，尽管 MetaHuman构建的虚拟数字人呈现了超逼真的成像渲染效果，但当我们怀着列文虎克的态度去刻意地观察其合成结果，却总是能发现那么几处隐隐难言语的不够真实的地方。不知大家看下图会不会有同样的感觉。

![image](https://user-images.githubusercontent.com/49339865/166150656-2e3fd09e-4764-4fd7-be82-dac4f037d651.png)

这边认为，上述谈到的不真实感可能是由MetaHuman的渲染假设导致的。具体的，随着图形相关研究技术的发展，该领域其实是在不断的修正三维模型的光照渲染模型的，在该过程中也是提出多种三维光照类型，如朗伯光照模型，Phong光照模型以及BRDF光照模型等，但由于真实世界的复杂性，这些假设的渲染模型仍是不可避免的会与真实世界的真实渲染方法存在差异，从而导致相关渲染结果不够真实。
