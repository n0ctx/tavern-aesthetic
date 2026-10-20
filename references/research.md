# 设计研究资料

本文记录 Skill 中设计原则的依据与适用范围。执行设计任务时不需要阅读。只在需要判断某条规则从何而来、是否适用于当前作品，或需要补充研究时查阅。

研究时间：2026 年 10 月。

## 1. 范围与局限

**来源**：

- GitHub 上的开源前端卡与状态栏。
- B 站前端卡展示与教程视频，研究时逐帧查看了录屏。
- 酒馆助手（JS-Slash-Runner）文档与源码。
- 英文社区：GitHub、Chub、SillyTavern 文档。
- 叙事游戏的界面设计访谈与演讲。
- 同类 AI 设计 Skill。
- 美术制作流程的资料。

**最大局限**：

- 社区公认的精品前端卡主要在类脑、旅程等 Discord 社区发布和讨论，无法公开访问。Reddit、Game UI Database、贴吧、知乎、小红书在研究时也无法访问。
- 公开渠道找到的作品经审阅确认都不属于精品卡。

**由此带来的结果**：

- 本文没有可作为标杆的精品案例。
- 公开样本只用于观察媒介约束、常见问题和个别值得借鉴的局部手法。
- Skill 中关于"精品级"的标准，主要来自可迁移的专业方法、反例对照与推理，属于有依据的归纳，而不是对精品卡的直接观察。

**后续补充**：如果获得精品卡的卡文件、录屏或作者说明，应优先补充进第 3 节，并复核第 2 节的结论。

## 2. 主要结论

叙事界面与普通网页的实质区别，归纳为六点。每点后面写明证据来源。

1. **界面有身份**：它是故事中的物件或系统，颜色、字体、版式、组件都由这个身份推出。
   - 证据：Fagerholt 与 Lorentzon 的界面分类研究；Suzerain 改编卡的档案册概念（第 3 节）。
   - 落地：design-knowledge.md 1.1、1.2。
2. **信息有原生形态和揭示节奏**：账本、名册、卦象、残页，以及未解锁、待揭晓等状态。
   - 证据：Disco Elysium 思想柜"背面朝上"的设计；Inscryption 用符号加规则书承载规则。
   - 落地：design-knowledge.md 1.3。
3. **文字有声音**：字体、文案和动作词汇表达"谁写的"。
   - 证据：Pentiment 为不同阶层与文化定制字体；Suzerain 卡的"翻开档案""归档保存""销毁文书"等按钮。
   - 落地：design-knowledge.md 1.4、2.2。
4. **情绪与状态驱动视觉变化**，信息本身保持清晰。
   - 证据：Her Story 的灯光随片段情绪变化；Fagerholt 论文对感官型反馈的讨论；Tavo 天气状态栏的昼夜配色。
   - 落地：design-knowledge.md 1.5。
5. **在对话中持续存在**，在窄宽度、重复渲染、非流式渲染的环境中工作。
   - 证据：酒馆助手文档与源码；社区对"只有开场有 UI"的抱怨。
   - 落地：design-knowledge.md 6。
6. **完成度来自统一质量线和分阶段打磨**，而不是一次铺开。
   - 证据：美术制作流程资料；反例中"首屏精致、功能页退化"的落差。
   - 落地：workflow.md。
7. **具象美术依赖插画素材，精度比点子数量更决定观感。**
   - 证据：公开样本中观感最好的部分都来自插画，例如修仙卡的水墨标题页；第 8 节的实际生成测试。
   - 落地：SKILL.md 核心原则 3、6；design-knowledge.md 2.5、第 7 节、第 8 节。

## 3. 公开样本观察（非精品标杆）

画面描述来自研究中实际查看过的视频帧或截图。标"模拟环境"的开源样本是在本地模拟的运行环境中渲染的，使用空数据或默认数据，不等于真实游玩画面。

### 中文社区录屏样本

**Suzerain V0.54（作者：北眺）**

- 来源：https://www.bilibili.com/video/BV1xq8b6vEEH，录屏。
- 题材：政治题材，改编自同名游戏。
- 人气：约 1.5 万播放、600 余收藏。热评称"完成度很高"。
- 可取之处：
  - 整个界面就是总统府机密档案：酒红封面配金色衬线标题，按钮是"翻开档案"，打开后是带页签的档案册。
  - 财政页做成账本式收支表，人事页附人像。
  - 按钮使用世界动词，例如"归档保存""销毁文书"。
  - 作者说明里提到，不同类型的事件（聊天、收发文件、签署命令）使用不同样式；另有帮助与索引页。
- 问题：
  - 面板文字过小，表格密度高。
  - 正文区仍是宿主默认暗底。
  - 移动端表现未验证。

**凡人修仙传（作者：KAI）**

- 来源：https://www.bilibili.com/video/BV1jV5u6xEWV，第三方试玩录屏。
- 人气：约 3.4 万播放。热评"这还是酒馆么"。
- 可取之处：标题页是满屏水墨山水和人物插画，配金色书法标题，整体像独立游戏。
- 问题：
  - 进入建卡页和游戏页后，插画完全消失，退回深色底、小字号、描边方块和大量空格子。
  - 首屏和功能页的完成度落差很大。

**Tavo 悬浮天气状态栏**

- 来源：https://www.bilibili.com/video/BV1cAUjBKEcW，录屏。
- 人气：约 3 万播放。
- 可取之处：面板配色随剧情中的时间和天气变化，白天偏樱紫，夜晚偏深蓝，带月亮。
- 问题：
  - 结构仍是"头像、进度条、文字块"，文字量大。
  - 评论担心上下文消耗。

**状态栏美化展示**

- 来源：https://www.bilibili.com/video/BV1qXzsBaEzU，录屏。
- 问题：三套面板骨架完全相同，都是等级、四项属性条加技能标签，只换了配色，其中一套是霓虹渐变。这是"换色不换结构"的典型反例。

**社区评价**（均为评论或帖子）：

- 只有开场有界面，选择之后再无界面（BV1D4QUBSEVr 评论区）。
- 对上下文消耗和平台兼容性的担心。
- 招聘帖要求"既要好看，也要不同的卡看起来不一样"（https://www.v2ex.com/t/1239036）。

### 开源样本（GitHub，均为低星项目）

**matrix4033/tavern-status-bars**

- 来源：源码，模拟环境。
- 问题：六个功能不同的组件使用同一种卡片（1px 边框、8px 圆角、模糊背景），没有题材材质；数据为空时整块消失。

**QINMO7557/young-marcus-ui**

- 来源：源码，模拟环境。
- 可取之处：牛皮纸、胶带、回形针用 CSS 变量加伪元素实现，手写字体单独加载，素材引用固定版本号。
- 问题：日程区在没有数据时只有空横线和"暂无记录"，空状态没有设计。

**feihu-lgtm/watchdogs-london**

- 来源：作者截图、源码、提交记录。
- 可取之处：
  - 近黑底配单一强调色。
  - 字体自托管，附授权文本。
  - 支持减少动态偏好，有窄屏断点。
  - 提交记录中有转屏重排和字体按需加载的修复。

**yjlovegy/xinyuanshe-card**

- 来源：源码。
- 可取之处：数据未就绪时先显示加载外壳，超时后提示；旧消息中的界面按只读快照渲染。

**EnitiyFiaz/jiugui-card**

- 来源：提交记录。
- 可取之处：有手机端的悬浮窗定位、动态视口单位与安全区、缓存回退等修复记录，说明作者确实在手机端做了适配。

**开源样本的共同情况**：多数仓库的提交集中在发布和逻辑层面，看不到视觉打磨的记录。

### 英文社区

- 英文社区少有卡内定制界面，主流做法有两种：
  - 让模型每轮即兴生成 HTML，例如 Stab's EDH 的 Visual Toolkit（https://github.com/Zorgonatis/Stabs-EDH）。
  - 修改 SillyTavern 自身主题。
- 即兴生成方式在同一作品的不同消息里出现了截然不同的面板语言，例如粉色斜切标签与绿色终端面板并存，缺少持久的美术方向。
- 与媒介相关的约束：
  - Chub 带 HTML 标签的卡很少（https://chub.ai/search?topics=html）。
  - SillyTavern 会清理消息中的 HTML（https://docs.sillytavern.app/for-contributors/writing-extensions/）。
  - 卡内正则需要用户批准才能导入（https://docs.sillytavern.app/extensions/regex/）。

## 4. 叙事游戏界面的可迁移方法

| 方法 | 出处 | 迁移要点 |
| --- | --- | --- |
| 按"是否属于虚构世界"和"是否存在于空间中"给界面分类；完全融入世界不必然更沉浸；写实世界对界面逻辑要求更高；叙事为主时可接受歧义，快速决策时需要清晰 | Fagerholt & Lorentzon, *Beyond the HUD*（2009），https://publications.lib.chalmers.se/records/fulltext/111921.pdf | 先定界面身份；融合深度随任务变化 |
| 先定主色，再定标志与关键字体，最后定副色，副色极少；界面同时承担"为作品包装"的作用；菜单用线条引导视线，重要区域亮、次要区域暗；每个菜单都有即时动画 | Persona 5 界面设计访谈与演讲（转译）：https://personacentral.com/persona-5-panel-concept-development-ui/ 、https://personacentral.com/persona-5-interview-ui-design-sound-music/ | 色彩决策顺序；强调色预算；即时反馈 |
| 为不同文化和阶层的人物定制字体，文字逐笔书写；同时承认难读的字体不适合大量文本的游戏 | Pentiment 演讲报道：https://www.gamedeveloper.com/design/pentiment-director-explains-how-going-all-in-on-fonts-helped-elevate-the-medieval-detective-rpg- | 字体即声音；装饰字体只用于短文本 |
| 统一的操作系统外壳中，各个网页内页风格迥异 | Hypnospace Outlaw 访谈：https://filmstories.co.uk/gaming/hypnospace-outlaw-the-indie-game-that-simulates-the-90s-web/ | 外壳统一，内页随作者与内容变化 |
| 宁可更风格化、更易辨认；用描边保证边界可读；抑制动态画面中的抖动噪点 | Return of the Obra Dinn 开发日志：https://dukope.com/devlogs/obra-dinn/tig-00/ | 风格强度不能压过可读性 |
| 用有清晰隐喻的符号替代文字说明，规则书中埋藏叙事线索 | Inscryption 演讲报道：https://www.gamedeveloper.com/marketing/-i-inscryption-s-i-journey-from-game-jam-joint-to-cult-classic | 符号配图例，图例本身也可以叙事 |
| 思想先"背面朝上"、只露名字，内化后才揭晓；同时因颜色无图例、小字难读而被无障碍评测批评 | Disco Elysium：https://www.gamebanshee.com/news/122863-disco-elysium-introducing-the-thought-cabinet.html ；评测：https://caniplaythat.com/2021/03/31/disco-elysium-the-final-cut-can-i-play-that-accessibility-review/ | 揭示节奏；风格不能牺牲可读性 |
| 骰子代表精力，时钟代表进度，用抽象符号而不是拟真；强调色只给可选项 | Citizen Sleeper 访谈：https://oldmenrunningtheworld.com/an-interview-with-citizen-sleeper-creator-gareth-damian-martin/ | 资源符号化；强调色只给可操作项 |
| 环境灯光随片段情绪变化；整个界面是一台可信的旧警局电脑，只保留一处有意的不真实 | Her Story 访谈：https://www.vice.com/en/article/watching-as-detectives-the-truth-behind-her-story-400/ | 情绪走感官通道；一处有意的不真实 |

Persona 5 的资料是日文媒体的英文转译，不是逐字引文。

## 5. AI 生成界面的同质化

- **成因**：模型落在训练数据的统计中心，Anthropic 称之为 distributional convergence。禁用某种字体或配色后，模型会转向另一个局部最优，例如禁用 Inter 后转向 Space Grotesk。
  - https://claude.com/resources/articles/improving-frontend-design-through-skills
- **Anthropic 官方前端设计 Skill 的演变**：从"选一个极端风格、禁用特定字体"，改为列出 AI 默认风格簇，并用"相似提示是否得到相同结果"自检。
  - https://github.com/anthropics/skills/blob/main/skills/frontend-design/SKILL.md
- **修复清单本身会变成新套路**，例如"奶油底、衬线、陶土色"。因此应教判断过程，而不是给替代清单。
  - taste-skill：https://github.com/Leonxlnx/taste-skill
- **NN/g 的测试**：多种 AI 原型工具的输出外观相似、扁平、可互换，缺少层级与分组。
  - https://www.nngroup.com/articles/ai-prototyping/
- **从构图而不是组件开始**；去掉边框、阴影、圆角后不影响理解的内容，就不该做成卡片。这是摘要转述。
  - https://developers.openai.com/blog/designing-delightful-frontends-with-gpt-5-4
- **未经主题化的浏览器默认表面**，例如滚动条、焦点环、选中色，是界面被"拼装"而非"建造"的明显信号；不要把一个角落打磨到完美而让其余部分低于同一质量线。
  - Impeccable：https://github.com/pbakaus/impeccable

## 6. 制作与打磨方法

| 方法 | 出处 | 在 Skill 中的形式 |
| --- | --- | --- |
| 美术方向需要共享参照，否则每个人会退回自己的风格 | https://www.gamedeveloper.com/art/five-secrets-of-game-art-direction | 设计记录、统一质量线 |
| "Beautiful corner"：先把一小块做到成品质量，用来验证方向 | https://www.ryantreadwell.com/post/beautiful-corners | 核心样板阶段 |
| 灰盒、美术化、打磨分阶段推进；把全部组件并排检查一致性；精力按重要性分配 | https://book.leveldesignbook.com/process/env-art | 整体构图阶段、并排比较、统一质量线 |
| 原型、alpha、beta 分阶段，每阶段有不同的完成标准 | https://gameworldobserver.com/2023/11/22/game-production-stages-prototype-alpha-beta-ship-tim-cain | 阶段门槛 |
| 从已经做完的资产中提炼规则，而不是先写规则再做资产 | https://blog.makko.ai/art-bible-game-development/ ；https://designcaitlin.substack.com/p/how-to-write-a-ui-art-bible | 样板通过后才写设计语言规则 |
| 独立评审者对照固定标准评分，自评容易偏宽；评分措辞会影响输出风格；中间轮可能优于最终轮，需要保留快照以便回滚 | https://www.anthropic.com/engineering/harness-design-long-running-apps | 最终验收的独立评审、复查时保留可回退状态 |
| Agent 容易一次做太多，或看到已有进展就宣告完成；需要逐项推进并端到端验证 | https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents | 分模块扩展、真实环境验收 |
| 同一问题纠正两次仍失败时，应重新开始，而不是继续叠加修正 | https://code.claude.com/docs/en/best-practices | 回退规则 |

## 7. 媒介约束（酒馆助手环境）

来源：酒馆助手文档 https://n0vi028.github.io/JS-Slash-Runner-Doc/ 与源码 https://github.com/N0VI028/JS-Slash-Runner 。

**渲染方式**：

- 界面在聊天楼层中以独立内嵌页渲染。
- 除个别情况外，`vh`、`vw` 以该内嵌页为基准，不是浏览器窗口。

**高度**：

- 内嵌页高度跟随 `body` 的内容高度自动调整。
- 依赖视口或父级高度的写法会互相撑高。
- 社区模板的 Agent 指引建议：
  - 避免 `vh`。
  - 用宽度加 `aspect-ratio` 控制比例。
  - 主体不用绝对定位。
  - 适配容器宽度，不出现横向滚动条。
- 模板 Agent 指引：https://github.com/StageDog/tavern_helper_template/blob/main/.agents/skills/tavern-helper-frontend/SKILL.md

**逐楼层渲染与性能**：

- 渲染深度设置会让旧楼层不再显示界面。
- 其他 HTML 注入插件可能导致同一界面重复出现。
- 代码越多越卡，作者建议楼层中只放加载链接。
- 出处：https://stagedog.github.io/青空莉/工具经验/实时编写前端界面或脚本/进阶技巧/

**流式输出**：界面要等文本输出完成才渲染。

**素材与字体**：

- 常见做法是通过 jsDelivr 镜像托管素材，缓存刷新可能有延迟。
- 字体通过在线字体服务嵌入。

**社区模板自带的前端 Skill**：

- 内容只覆盖工程与适配规则，设计层面几乎没有指导。
- 示例样式容易被照抄，导致界面趋同（推断）。

## 8. 实际生成测试

**测试方式**：

- 2026 年 10 月，用同一模型，分别按两个题材生成前端卡：赛博朋克地下诊所、修仙宗门外门弟子。
- 两题材各用两种 Skill 版本生成一次。
- 测试环境没有生图工具，并禁止使用外部图片，所有美术都由 CSS/SVG 实现。

**观察**：

- 两种版本都从需求中的具体设定推导出了相近的概念，例如"面馆点菜单即病历"。概念层面的指导对这一模型增益有限。
- AI 评审按"辨识度、叙事融合"等标准打分时，偏好隐喻和道具更多的版本。人工审阅却认为两者看不出区别，都有明显的"AI 手搓 AVG"粗糙感。这说明评审标准如果复述 Skill 自身的重点，会形成循环论证。
- 人工审阅指出的粗糙感，主要来源有四个：
  - CSS/SVG 几何块拼出的场景与人物。
  - 每个模块一个仿制道具。
  - 模型惯用的游戏化套件，例如红框歪章、小标签串、步骤节点、雷达图。
  - 想法多、单个元素精度低。

**结论**：精品观感依赖插画素材和单个元素的精度。代码手绘的具象美术只能作为概念验证占位。评审应判断"是否像经过专门美术打磨的成品"，而不是数隐喻。

**第二轮**（插画优先，网络收集素材，仍无生图工具）：

- **素材**：修仙卡用了宋画、《天工开物》版画、《八十七神仙卷》和博物馆器物照片；赛博朋克卡用了香港夜景与后巷照片、义体手照片和瓷砖纹理。均为公有领域、CC0 或 CC BY。
- **人工审阅结论**：方向正确，手搓感基本消失。
- **新出现的问题**：
  - 过度克制。修仙卡的插画只占顶栏，其余是深色面板和文字，显得素。
  - 建档页像登记表。
  - 两张来源不同的照片装在方框里并排，有拼贴感。
  - 通用游戏图标与纪实照片风格冲突。
  - 网络收集无法提供与角色设定相符的专属人物立绘。
- **实际工作时长**：约 50～75 分钟。两个代理在同一时段出现过约 6 小时的同步停顿，属于外部原因，不计入。

## 9. 未能验证

- **精品案例**：类脑、旅程等 Discord 社区中的精品卡及其评价，无法访问。
- **被拦截的站点**：Reddit、Game UI Database、贴吧、知乎、小红书、linux.do 被拦截或要求登录。
- **B 站数据**：只取到少量评论；字幕需要登录。
- **开源样本的画面**：多在模拟环境中渲染，未见真实游玩画面。万界商店、SSR 召唤物、心愿社、Astraea 等样本渲染失败或未查看画面，不下结论。
- **游戏资料**：
  - Hades、视觉小说文本框惯例、Dead Space 等资料没有找到可靠的一手来源，未采用。
  - "target render / key art / style frame"等术语没有找到可靠的一手定义，Skill 中以"核心样板"和"设计记录"代替。
- **统计数据**：同类 Skill 的统计数据和星标数为项目自述或二手资料，未独立核对。
