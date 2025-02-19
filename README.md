# EOTGC
NLPCC2025 Evaluation of Essay On-Topic Graded Comments
## 声明
比赛中获得的数据仅限于本次比赛，**禁止**商用，如有科研需求请联系组织者。
## 联系方式
董昊翔（华东师范大学，hx_dong@stu.ecnu.edu.cn）
## 任务内容
作文写作是中学语文教育的重要组成部分，不仅是学生语言表达能力的体现，更是学生思维逻辑与审题能力的重要展示。切题性作为作文评价的重要维度之一，直接关系到学生分析问题与组织思路的能力，也是教师开展写作教学和指导的关键参考点。切题性是作文写作中评估学生是否准确理解题意、是否能围绕题目要求展开行文的核心指标。一方面，切题性要求学生能够在写作中紧扣题目内容或任务目标展开阐述，避免偏离主题或泛泛而谈；另一方面，也要求学生准确理解题目隐含的思维方向或探讨角度，从而展现出较高的审题能力和立意水平。同时，教师可以基于学生切题性的表现，设计更具针对性的教学方案，帮助学生强化审题能力和文章逻辑结构。

随着自然语言处理技术在教育领域的广泛应用，越来越多自动化的作文分析工具被用于支持写作教学和评估。一些早期研究关注于从整篇作文中识别中心思想，也有研究试图分析作文的段落结构与逻辑连贯性。然而，关于如何通过自动化方法准确评价作文切题性，仍有较大研究空间。切题性不仅需要考虑文章与题目之间的内容关联，还需分析语言表达是否明确围绕题目展开论述。因此，需要通过定义更为细化的切题评价标准，结合句子和段落的语义信息，分析作文与题目的相关性。

本次评测任务以中小学生作文为对象，重点关注文章的切题性评价和基于切题性分析的评语生成。具体而言，本次任务将对作文中是否紧扣题目展开行文进行多维度评分，包括对题目理解的准确性、行文内容的相关性与完整性等维度，同时结合切题性分析自动生成适当的评语，以辅助教师进行作文评价与教学指导。本次工作旨在为切题性评价建立统一标准，为自动化作文评分与教学提供技术支持。
## 赛道一

### 任务描述
**作文切题性评分**。评估作文是否符合所给主题，提供分类结果与预测分数。分类结果包括“优秀”、“较好”、“一般”、“合格”和“不合格”；预测分数范围在0到100之间。

### 任务定义
作文切题性评分可视为一个多分类问题，其核心任务是对一篇作文进行切题性评估，预测其所属的切题性类别，并生成相应的评分。本次评测任务定义了5个切题性类别，分别为“优秀”、“较好”、“一般”、“合格”和“不合格”，同时结合分类结果给出对应的评分，评分范围在0-100分之间。具体类别定义及评分标准见下表。
<table align="center">
  <tr>
    <th width="20%" align="center">切题等级</th>
    <th width="80%" align="center">切题等级的描述规范</th>
  </tr>
  <tr>
    <td align="center">优秀</td>
    <td>该文章完美契合作文要求，选题极为贴切，中心思想鲜明突出，所选用的素材更是恰到好处，相得益彰。</td>
  </tr>
  <tr>
    <td align="center">较好</td>
    <td>该文章较好地满足了作文要求，选题相当贴切，中心思想相对清晰明确，所选用的材料也颇为恰当，与主题相辅相成。</td>
  </tr>
  <tr>
    <td align="center">一般</td>
    <td>该文章大体上满足了选题的要求，选题尚算恰当，中心思想在一定程度上较为清晰，所选用的材料也基本符合主题需求，整体表现尚可。</td>
  </tr>
  <tr>
    <td align="center">合格</td>
    <td>该文章虽未偏离主题，但选题稍显不够贴切；中心思想不够突出，提取起来有一定难度；所选用的材料亦与主题匹配度不高，整体而言，材料的适用性有待加强。</td>
  </tr>
  <tr>
    <td align="center">不合格</td>
    <td>该文章严重偏离了选题的要求，选题极为不妥；中心思想模糊不清，难以把握；所选用的材料更是与主题大相径庭，极不相符。</td>
  </tr>
</table>

### 数据样例
```json
[
  {
        "grade": "8",
        "requirement": "我们可能都有过旅游的经历。旅途中，我们不仅观赏自然风光，了解民风民俗，同时也会有许多新奇的感受，产生很多思考和遐想。选择一处自己游览过的景点，自拟题目，写一篇游记。不少于600字。提示：1.先画出当时的游览路线图，按游览顺序拟出写作提纲。2.回想游览时最深的印象及总体感受，据此确定材料取舍与叙述详略。3.在记叙或描写中融入自己的情感，也可以适当加入一些人文景观的介绍或引用他人的描写、评价等，以丰富文章内容。",
        "title": "春日登山",
        "content": "几乎每年的春暖花开时，妈妈总是会带我回老家玩，老家其实没什么太好看的风景，但是到处坐落着的山，也有一种别样的美。\n春天里的气候总是那么的阳光明媚，温暖宜人，更别提在乡下了，空气十分的清新里面好像夹杂着泥土以及芳草鲜花的香气。\n家乡的山分布得散散落落，东一座西一座，有的排成一排，有的排成了看不出形状的奇怪图形。每座山都不是那么的高，坡度也不陡，看着还挺娇小可爱，所以我和妈妈在乡下最喜欢做的事情便是去爬山，几乎每个下午我们都要去。\n吃过中饭之后，我们便踏上了旅途。没走几步路，我们便来到了一处山脚下。眼前的山并不显得很高甚至能用娇小来形容。面前一条小溪缓缓流过，发出汩汩的流水声，能清晰地倒映出蓝天和白云，河底的小石头和泥沙也直视无碍，不时有几条小鱼流过，倒也别有一番情趣。\n环顾了四周的春景，我们没有过多停留，便开始登山。途中能清楚地感觉到那独属于春的芬芳和生机。就这样，我们一路看着景，便来到了半山腰。\n半山腰处栽种了许多花，叫得出名字的，叫不出名字的，红的、粉的、紫的在阳光的照耀下交相辉映，仿佛编织成了一件闪着光的彩色的霓裳。路边还有几块农田，里面的作物刚刚长出嫩绿的芽，田边斜斜的椅着稻草人，给景色添了些许童趣。\n我们接着往上走，很快便来到了山顶上。此时的太阳也升到最高，和煦的阳光照到身上，暖洋洋的，使人舒适得忍不住想呻吟一声。我和妈妈在一棵大树下稍作歇息，地下是如茵一般的草地。此时，微风拂面，四周的鸟儿的鸣叫，仿佛在奏一阵和谐的交响曲，让人心旷神怡。\n时间不知不觉之间流逝，我和妈妈也踏上了回归之路，太阳也刚好和我们一起下山，夕阳的余晖照在景物上，仿佛给世界染上了一层金黄的纱衣，我们的影子被拉得长长的。\n提笔写到这里，脑海中便浮现出无数的画面，仿佛我又回到了老家，又是一年的春天，我又开始了登山之路。",
        "result": {
            "classification": "较好"
        }
  },
  {
        "grade": "7",
        "requirement": "在《土地的誓言》里，作者以饱满的热情描绘了他那美丽而丰饶的家乡。你的家乡是什么样的？你对它怀有怎样的情感？以《乡情》为题，写一篇作文。不少于500字。提示：关于家乡，你应该有许多内容可写：家乡的景色、物产、风俗，以及你在家乡的生活……不必面面俱到，要有侧重地写作。直接抒情应基于相关的记叙、描写，顺势而发；间接抒情时，所写内容要与表达的情感相协调。写完初稿后，读给同学听听，看看你的作文是否能打动人。如果效果不好，和同学讨论，看看问题出在什么地方，然后做出相应的修改。",
        "title": "乡情",
        "content": "我的家乡在江苏南京，那是个风景秀丽的地方。\n南京是一座百年古诚，它曾是东吴、东晋、南朝、南唐、太平天园。南京的旧称有许多，如冶城、越城、石头城、丹阳、金陵、建邺等70个之多。南京的风景也是一绝的如孙中山先生的墓陵中山陵、现在改为中国近代史遗址博物院。中国第一所由国家兴建的现化综合大型博物馆的南京博物院。中国第十高、江苏最高的大楼紫峰大厦。江南三名湖的玄武湖，还有南京大屠杀遇难同胞纪念馆、紫金山、明孝陵、夫子庙、明故宫等等都是外乡人到南京一定会去看看的地方。\n白天，整城的道路上车水马龙，人们脚步匆匆。马路两边栽着一排的梧桐树，就像有无数个士兵整齐的站在城市的各个地方守护着这座美丽繁华的城市。喧闹声犹如一曲城市交响乐。月明星捧的夜晚，家家户户的窗户里射出明亮的灯光，犹如天上的群星陨落人间。夜色中长江大桥显的更加雄伟壮观，淡淡的薄雾使得这座城市充满神秘感。\n在南京出生长大的我最喜欢地方就是夫子庙老门东。不要说处地人，就是南京人设事都会去转一转，实际上是满足自己的口腹之欲。老门东美食大多都是百年老店，祖辈祖传的手艺。我每一次去老门东必定每一个去小郑酥烧饼店，这家的鸭油酥烧饼是秦淮八绝之一。买好烧饼再到“陆氏梅花糕“，他家的赤豆小元宵是我的最爱的。转到”鸡鸣汤包”和“张氏生煎“给奶奶打包一份，再从“徐家鸭子店买半只盐水鸭留着吃晚饭时吃。噢，还有样也是每次去无论排队排多久都一定要买的，就是南京第一冰糖蜜汁藕。\n这就是我的家乡，一座让人来了就不愿离开的地方，南京不但景色使人流连忘返，美食也让人欲罢不能，还有许多东西欢迎你慢慢来发掘。",
        "result": {
            "classification": "合格"
        }
  }
]
```
### 评测数据集

### 评价标准
- **近似准确率:**

$$ACC_A = \frac{1}{N} \sum_{i=1}^{N} S(d_i)$$

其中，N为样本数量，
$$S(d_i) = (1 - \frac{d_i}{4})$$
，
$$d_i = \lvert y_i - \hat{y}_i \rvert$$
，
$$y_i$$
为真实标签，
$$\hat{y}_i$$
为预测结果。

- **皮尔逊相关系数**

$$r = \frac{\sum (y_i - \bar{y})(\hat{y}_i - \bar{\hat{y}})}{\sqrt{\sum (y_i - \bar{y})^2} \sqrt{\sum (\hat{y}_i - \bar{\hat{y}})^2}}$$

其中，
$$\bar{y}$$
为真实标签的均值，
$$\bar{\hat{y}}$$
为预测结果的均值。

- **最终得分**

$$Score = 0.5 * ACC_A + 0.5 * (\frac{1+r}{2})$$
## 赛道2

### 任务描述
**生成切题性评语**。根据作文是否切题生成评语，内容仅聚焦于文章的中心思想及其与所给主题的相关性。

### 任务定义
生成切题性评语可以视为一个生成任务，其核心任务为针对作文是否切合题干、符合中心立意生成相关评语。生成的评语应当符合以下条件：
1. 参照该“年级”写作训练的“作文要求”给出作文中心与切题方面的分级评语。
2. 生成的评语内容不得涉及政治、人种、宗教信仰、民族、暴力、歧视等信息，不得违反相关法律政策。
3. 生成的评语字符数不超过250。
### 数据样例
```json
[
  {
        "grade": "8",
        "requirement": "我们可能都有过旅游的经历。旅途中，我们不仅观赏自然风光，了解民风民俗，同时也会有许多新奇的感受，产生很多思考和遐想。选择一处自己游览过的景点，自拟题目，写一篇游记。不少于600字。提示：1.先画出当时的游览路线图，按游览顺序拟出写作提纲。2.回想游览时最深的印象及总体感受，据此确定材料取舍与叙述详略。3.在记叙或描写中融入自己的情感，也可以适当加入一些人文景观的介绍或引用他人的描写、评价等，以丰富文章内容。",
        "title": "春日登山",
        "content": "几乎每年的春暖花开时，妈妈总是会带我回老家玩，老家其实没什么太好看的风景，但是到处坐落着的山，也有一种别样的美。\n春天里的气候总是那么的阳光明媚，温暖宜人，更别提在乡下了，空气十分的清新里面好像夹杂着泥土以及芳草鲜花的香气。\n家乡的山分布得散散落落，东一座西一座，有的排成一排，有的排成了看不出形状的奇怪图形。每座山都不是那么的高，坡度也不陡，看着还挺娇小可爱，所以我和妈妈在乡下最喜欢做的事情便是去爬山，几乎每个下午我们都要去。\n吃过中饭之后，我们便踏上了旅途。没走几步路，我们便来到了一处山脚下。眼前的山并不显得很高甚至能用娇小来形容。面前一条小溪缓缓流过，发出汩汩的流水声，能清晰地倒映出蓝天和白云，河底的小石头和泥沙也直视无碍，不时有几条小鱼流过，倒也别有一番情趣。\n环顾了四周的春景，我们没有过多停留，便开始登山。途中能清楚地感觉到那独属于春的芬芳和生机。就这样，我们一路看着景，便来到了半山腰。\n半山腰处栽种了许多花，叫得出名字的，叫不出名字的，红的、粉的、紫的在阳光的照耀下交相辉映，仿佛编织成了一件闪着光的彩色的霓裳。路边还有几块农田，里面的作物刚刚长出嫩绿的芽，田边斜斜的椅着稻草人，给景色添了些许童趣。\n我们接着往上走，很快便来到了山顶上。此时的太阳也升到最高，和煦的阳光照到身上，暖洋洋的，使人舒适得忍不住想呻吟一声。我和妈妈在一棵大树下稍作歇息，地下是如茵一般的草地。此时，微风拂面，四周的鸟儿的鸣叫，仿佛在奏一阵和谐的交响曲，让人心旷神怡。\n时间不知不觉之间流逝，我和妈妈也踏上了回归之路，太阳也刚好和我们一起下山，夕阳的余晖照在景物上，仿佛给世界染上了一层金黄的纱衣，我们的影子被拉得长长的。\n提笔写到这里，脑海中便浮现出无数的画面，仿佛我又回到了老家，又是一年的春天，我又开始了登山之路。",
        "result": {
            "comment": "作文围绕作者春日登山的经历展开写作，先介绍了老家山的特点，接着通过移步换景的写作手法描述了作者从山脚到半山腰再到山顶一路的风景见闻，多次运用比喻的修辞手法，感官体验充分。建议作者增加一些自己的感受描写，使文章更富有真情实感。总体来看，作文主题鲜明，切题恰当。"
        }
  },
  {
        "grade": "7",
        "requirement": "在《土地的誓言》里，作者以饱满的热情描绘了他那美丽而丰饶的家乡。你的家乡是什么样的？你对它怀有怎样的情感？以《乡情》为题，写一篇作文。不少于500字。提示：关于家乡，你应该有许多内容可写：家乡的景色、物产、风俗，以及你在家乡的生活……不必面面俱到，要有侧重地写作。直接抒情应基于相关的记叙、描写，顺势而发；间接抒情时，所写内容要与表达的情感相协调。写完初稿后，读给同学听听，看看你的作文是否能打动人。如果效果不好，和同学讨论，看看问题出在什么地方，然后做出相应的修改。",
        "title": "乡情",
        "content": "我的家乡在江苏南京，那是个风景秀丽的地方。\n南京是一座百年古诚，它曾是东吴、东晋、南朝、南唐、太平天园。南京的旧称有许多，如冶城、越城、石头城、丹阳、金陵、建邺等70个之多。南京的风景也是一绝的如孙中山先生的墓陵中山陵、现在改为中国近代史遗址博物院。中国第一所由国家兴建的现化综合大型博物馆的南京博物院。中国第十高、江苏最高的大楼紫峰大厦。江南三名湖的玄武湖，还有南京大屠杀遇难同胞纪念馆、紫金山、明孝陵、夫子庙、明故宫等等都是外乡人到南京一定会去看看的地方。\n白天，整城的道路上车水马龙，人们脚步匆匆。马路两边栽着一排的梧桐树，就像有无数个士兵整齐的站在城市的各个地方守护着这座美丽繁华的城市。喧闹声犹如一曲城市交响乐。月明星捧的夜晚，家家户户的窗户里射出明亮的灯光，犹如天上的群星陨落人间。夜色中长江大桥显的更加雄伟壮观，淡淡的薄雾使得这座城市充满神秘感。\n在南京出生长大的我最喜欢地方就是夫子庙老门东。不要说处地人，就是南京人设事都会去转一转，实际上是满足自己的口腹之欲。老门东美食大多都是百年老店，祖辈祖传的手艺。我每一次去老门东必定每一个去小郑酥烧饼店，这家的鸭油酥烧饼是秦淮八绝之一。买好烧饼再到“陆氏梅花糕“，他家的赤豆小元宵是我的最爱的。转到”鸡鸣汤包”和“张氏生煎“给奶奶打包一份，再从“徐家鸭子店买半只盐水鸭留着吃晚饭时吃。噢，还有样也是每次去无论排队排多久都一定要买的，就是南京第一冰糖蜜汁藕。\n这就是我的家乡，一座让人来了就不愿离开的地方，南京不但景色使人流连忘返，美食也让人欲罢不能，还有许多东西欢迎你慢慢来发掘。",
        "result": {
            "comment": "作文围绕作者家乡南京展开写作，详细介绍了南京历史背景、人文景观，后半段介绍了作者最喜欢的地方夫子庙老门东，表达了对期间美食的喜爱之情。但是作文体裁是抒情，要求表达出对家乡怀有的情感，文章前面大半篇幅没有一句表达了作者的感情，只是单纯的介绍，后半段也只提到喜爱之情，较为片面，建议作者仔细审题。总体来说，作文偏离题目要求。"
        }
  }
]
```
### 评测数据集

### 评价标准


