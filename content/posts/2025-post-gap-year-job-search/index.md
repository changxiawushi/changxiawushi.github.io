---
title: "Gap一年后的找工总结"
date: 2025-11-25T16:40:24-08:00
draft: false
ShowToc: true
tags: []
---

我的背景：程序员，6年多大厂经验，从2024年下半年开始gap，2025年11月找到新工作。
2025年的找工时间线：
- 6月中下旬：做找工的心理建设，开始制定计划
- 7-8月：不那么投入地刷题和学习system design，改了第一版简历
- 9-10月：投入地学习，改简历，投简历，mock interview，正式面试，间歇性崩溃
- 11月：找到新工作

平均下来，我每天大概花3-4个小时专注地学习。总共投了二十几个岗位，最终拿到的offer是朋友内推的岗位。
本篇内容有：
- 我找工作的几个阶段
- 我准备了的几个板块和推荐资料
- 我的经历

写在前面的disclaimer：个人经验仅供参考，分享经历不代表我认同任何一步，或是整个找工的机制。关于找工作的更深的思考按下不表，本篇绝大部分只到事实性的陈述为止。
## 前期准备

### 做好心理准备
推荐：[Preparing Mentally for the Interview Process](https://interviewguide.dev/preparing-mentally)

很少看到有人提这个部分，我也只在上面的链接里看到过相关的内容，但我觉得做好心理准备是找工作**必不可少**的一个步骤。如果能有这一步，后续的找工过程对人的消磨会少那么一点。可以在这个阶段思考记录：我为什么需要/想要找新工作？我想要找什么样的工作？之后反复回看，会帮助你重新评估状况或是做决定。

从时间上来讲，找工作是**好几个月**的事情。如果在职跳槽的话，我觉得要**至少预留半年的时间**。可以参考别人的时间线，但不要给自己不切实际的目标。就算订好了目标，也要做好准备根据实际状况随时调整。比如我预计自己一天能写完简历，但因为自new grad找工以来就没有改过简历，所以最后花了快一周才写完第一版。

另外，为找工作而做的学习是很不一样的。个人觉得程序员找工需要的学习更像是备考，大部分都是理论，而工作中的学习主要是快速掌握新技能并运用实践起来。我自己是在开始学习后很快就意识到，我好像需要先学习如何学习，所以花了一段时间摸索学习方法和模式。

我想强调的是，**找工作的过程对人就是非常消磨的！** 我自己找工的过程中压力就很大，特别是后期几乎没有心情和精力去做别的事情。这还是没有全职工作的情况，我难以想象在职找工作得有多累。所以如果你也在为此准备，或是正在跳槽中，绝对不是只有你一个人在苦苦挣扎。只是因为大多数时候，我们看到的都是别人找工作的最终结果。

### 了解面试流程
先简要介绍一下常见的面试环节和流程，然后再详细分享每一部分的准备。由于我自己的经历有限，部分环节就不展开说了。这篇介绍得更多更全面：[Software Engineer interviews: Everything you need to prepare](https://www.techinterviewhandbook.org/software-engineering-interview-guide/##find-out-the-interview-format)
#### Initial HR Call
不管是通过海投还是内推申请，通常会和recruiter先联系上，双方聊上5-30分钟。双方都简短地自我介绍以后，recruiter会初步了解申请者的情况，评估和工作岗位是否适配。recruiter也会介绍一下这家公司、这个岗位以及接下来的面试流程。可以在这个环节问清楚面试形式、时间线、onsite/hybrid/remote等等。
#### Online Assessment, Take-Home Assignment
有些公司会发来Online Assessment (OA)，需要在规定时间内完成题目，可能会得到一个分数。或者是发一个小项目让你做，也就是take-home assignment。这一次找工我并没有做过这两个，所以没什么经验可以分享。
#### Technical Phone Screen
通常考leetcode，很可能是手写且无法运行代码。我也碰到过在这一轮考code review的。一般是45-50分钟的面试，最后会有5-10分钟问问题的时间。现在也有一些公司在这一轮就加入了AI，我没有这个经验。
#### System Design
通常在technical screen通过以后，才会有system design的部分。这类面试中，面试官会让你设计一个产品或者工具。你需要从确定具体需求开始，一步步做出technical design。New grad/junior 通常不需要准备，但从mid-level开始就必须准备。
#### Behavioral Interview
通常也在technical screen通过以后才有。这可能是一个单独的面试，也可能和System Design合并。通常面试官会问一些behavioral questions (BQ)，比如过去的工作经历，或是提出一些情况问你怎么应对。由于phone screen和system design都重点考察了technical skills，这轮主要考察non-technical skills。

## 主要板块
下面根据我的准备顺序分享一下主要的几个板块。
### 刷题（Leetcode）
推荐：
- [Grind 75](https://www.techinterviewhandbook.org/grind75/): 刷这些题足够了
- [NeetCode](https://www.youtube.com/c/neetcode): 看他的解题思路，尤其是intuition的部分
- [Hello Interview](https://www.hellointerview.com/learn/code): 看pattern overview，记下pattern对应的代码模版

#### 要不要刷题？
由于第一轮技术面通常会涉及leetcode，这是我开始准备的第一个板块。我的经验是leetcode还是有必要准备的，因为准备了的话选择会更多一些。当然这个看个人，我以前也非常抗拒刷题，所以很理解直接跳过刷题，只选择不考leetcode的公司。
#### 刷题的重点是什么？
在准备的过程中，我发现刷题的重点不是死记硬背尽可能多的题和解法，并且寄希望于面试碰到刷过的题。现在Leetcode的题越来越多，如果想在面试前刷足够多这家公司tag的题，并且在面试时碰到原题，这种心态反而会让人在碰到新题时很慌乱。所以我自己觉得比较好的心态是干脆放弃这种期待。

**刷题的重点应该是pattern recognition**。在最初的学习阶段，最重要的是熟悉常见的pattern，然后开始慢慢练习见到新题能够pattern match的能力。所以如果刚开始刷题，对各类pattern都还不熟悉，就不要在一道题上花太久的时间思考，差不多20分钟还没有思路就可以直接看答案学习了。当然具体思考多久后看答案因人而异，重要的是不要花太久时间卡在一道题上，这样会消耗太多的脑力和时间，这两者都是有限的。更不要给做不做得出题上价值，解算法题的能力和工作能力没什么关系，跟一个人的价值更没什么关系。

在熟悉pattern的阶段，可以一边做题一边补全pattern，也可以学完并且练完一个pattern再继续下一个pattern，这个看个人选择，我是按照Grind 75的顺序边做边学的。

在做题时，多多探索不同的思路，去找到自己的思路和正确解法之间到底差别在哪里？是哪一步没想到？是不是应该多试几个例子？可以参考NeetCode的视频，关注一下他的解题思路，intuition的部分通常是最难但是最重要的。
#### Mock Coding Interview
当你发现自己碰到新的题已经比较大概率能够识别出pattern，就可以开始转向mock coding interview的练习了。我大概是在Grind 75刷了75%以后开始这部分的练习。
**面试解题的练习重点是边说边解题**，并且解释清楚自己的思路。在面试的场景下，你很难一下子就想到正确答案，而且要边想边说确实是一个很大的难点，所以我会练习把思考的过程说出来。比如我认为这道题可能可以怎么解我想到了哪些思路，并且一个一个去试。

#### 我的经验
我碰到的公司基本都在考leetcode medium或者hard，所以我会建议重点练习medium的题。

我总结出了下面这些面试解题的步骤/框架：

1. Read the problem
2. Ask for clarifications
3. Mention brute force solution
4. Try different patterns with examples
5. Dry run
6. Code
7. Test
8. Big O

{{< toggle "👉 点击展开每一步更具体的解释" >}}
1. Read the problem

把题读一遍，确保自己理解了题目的意思。

2. Ask for clarifications

开始问一些问题，比如edge case/base case应该怎么处理？input/output的type, range, limitations等等。题目一般只会提供有限的例子，所以还可以自己想一些额外的test case。
这一步结束时，你应该完全理解了这个题目的要求，但你很可能还不知道算法的具体步骤，也就是还没想出一个比较好的解法。

3. Mention brute force solution

不管你有没有想到具体怎么解，都可以快速说一下brute force的解法应该怎么做，然后解释为什么不能用brute force，比如一个常见的理由是太慢了。这是你展示思路的一部分，让面试官知道你具体在思考什么。

4. Try different patterns with examples

如果你已经知道最优解，直接跳过这一步进入下一步。

这一步可以开始回忆学习过的pattern，边想边口头说出来，比如：It seems like we have repeating subproblems, so maybe something like DFS/BFS or Dynamic Programming would work. 同时试验一些不同的例子，一步一步拆分需要做的事情。
这一部分的目标是整理思路，初步摸清楚解法，同时让面试官知道你熟悉不同的pattern。至少确定算法的大框架，一些细节可以在后面边写边想。

5. Dry run

有了解法的大框架以后，再用一个例子，按照你想的算法跑一遍。把每一步都说出来，确保你的算法是可行的。如果这一步没有问题，可以和面试官确认一下说我接下来开始写代码可以吗？这样可以在开始写代码前给面试官一个纠正你的机会。


6. Code

在前面这些都走了一遍之后，我才会开始写代码。我的经验是tech screen最容易犯的错就是太早开始写代码，所以我倾向于先确认了做法再开始写。当然这是理想情况，有时候就是想不到最优解，那也只能硬着头皮开始……

7. Test

写完代码以后，我会抓两个test来一行一行过自己写的代码，确保每一行都是符合预期的。test cases可以用之前用过的。这一步通常还会抓出一两个bug。

8. Big O

全部都确认且跑完test以后，就可以分析一下space & time complexity了。面试官可能会开始问一些follow-up，或者指出代码还有bug之类的。

{{< /toggle >}}

### System Design
推荐：Hello Interview
- System Design in a Hurry - Introduction: https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction
- How I'd Prepare for a System Design Interview if I Were Starting From Scratch: https://www.hellointerview.com/blog/how-id-prepare

由于我过去工作的内容和分布式系统没什么关系，所以我几乎是从零基础开始学习system design的。有多零基础呢？在此之前我连redis都没听说过。

在前期搜罗网上的推荐时我尝试过不少资料，包括很多人推荐的Alex Xu的书，但都看得很吃力。我想可能大多数人都有分布式系统的经验吧，所以他们能看进去的资料未必适合我。还好我最终发现了**Hello Interview**。他们的内容是我读的所有system design interview guide中**逻辑最清晰、最容易看进去的**。介绍完基础知识以后，每一篇design writeup的都按照他们的delivery framwork，一步一步从最简单的设计开始，越来越深入地对比不同选择。

我认为他们的内容有几大优点。一个是他们提供了非常清晰且实用的框架（delivery framework），基本上使用这个框架在面试时就不会跑太偏。另一个是他们提供的信息是最贴近现实的，不像那些出版了好几年的书，难免会有一些过时的内容。还有一点是他们提供了很多帮助大家学习的辅助工具，比如每一篇文章结尾都有quiz，这一看就是想让人真的理解内容才设计的。guided practice，AI tutor等付费功能也都很不错，且一直在改进。

#### 我的经验
前面说到我几乎是从零开始学的，导致我花了很多时间在system design上。光是补基础知识就花了接近两个月，虽然这期间也有按照hello interview的推荐顺序开始看design writeups，但是吸收信息的速度非常缓慢。但是到了第三第四个月，我开始上道了。虽然我的知识都是纸上谈兵，但至少我已经熟悉了一些常见的pattern，比如real-time updates，blob storage等等，读writeup的速度也快了很多。

学习过程中，我基本上是哪里不懂就去问AI。我的经验是AI对system design的学习还是比较有帮助的，不像leetcode，AI能给解法，但经常解释得不太清楚。

另外，我觉得在学习中不断寻找知识点之间的联系很重要。如果只是阅读新知识而不思考，那就很难真的学会什么。在学到新的东西以后，我会时不时问自己，这和之前看到的东西有什么联系吗？我在Claude里建了一个system design project，在project instructions里让它提醒我寻找各个概念间的联系。

### 改简历
这是我最最不擅长的一部分。对我而言，最大的难点是我过去的工作经历有点小众，不像backend/frontend/mobile engineer这么常见，所以把简历改得符合各类job posting就变得很难。另外就是正反馈很少，ghost和秒拒的占大多数。

我用的简历模版： https://www.reddit.com/r/EngineeringResumes/wiki/templates/

几年前我找工作的时候并没有现在这么强调ATS-friendly，也就是确保简历可以被程序读取，这回才发现全网都在强调这点，所以我乖乖选了一个最无聊但是最安全的模版。

改简历的过程中我还找了过去几年写的职场评估，和AI反反复复聊才确认了每一个项目和每一条的内容。有点遗憾的是没有保存更多过去工作的内容，比如technical design doc，不过好在最终也没有在面试中被深挖那么多。

我自己的经验是如果是通过内推申请，那么简历就没有那么重要。所以有条件的话，还是建议多找一找内推（我知道这也不容易！）。

### Behavioral Questions
推荐：[Mastering Behavioral Interviews](https://thebehavioral.substack.com/)
- Roadmap to Behavioral Interview Prep - Mastering Behavioral Interviews: https://thebehavioral.substack.com/p/roadmap-to-behavioral-interview-prep

Behavioral的部分，我主要准备了下面的几个部分：
- 自我介绍 + 解释 gap year
- 梳理过去的工作项目
- Conflict stories

#### 自我介绍 + 解释 gap year
自我介绍的参考： https://thebehavioral.substack.com/p/death-taxes-and-tmay

我主要思考了一下我最想让面试官知道什么信息。除了简短介绍自己过去的经历以外，我知道自己过去的工作内容比较小众，所以我想强调的就是我的flexibility和adaptability。也可以根据面试岗位调整，如果有很符合的经历，那就可以重点强调这个。

另外，我知道自己肯定会需要解释employment gap。我的结论是应该结合自我介绍主动提起，早早消除面试官可能有的疑虑。主要参考了下面的两个链接：
- How to handle sticky situations in Behavioral interviews: https://thebehavioral.substack.com/p/how-to-handle-sticky-situations-in
- Explain an Employment Gap in a Job Interview: https://www.youtube.com/watch?v=cr6ptEK-Mgs

#### 梳理过去的工作项目

有一大部分的整理已经在改简历的时候完成了，只是针对behavioral interview的重点不同。

Mastering Behavioral Interviews 推荐根据 impact, scope, and personal contribution by you 来选一个favorite project，于是我选了一个自己积极参与且最终上线的项目。我回忆了这个项目中我主要做了什么，整理出了一个script来描述这个项目是什么、我的contributions和项目结果。

另外还准备了这个项目中碰到了什么conflict，详见下面。

#### Conflict stories

推荐：
- [Conflict Stories 1 of 5: Workplace Conflicts That Make Great Interview Stories](https://thebehavioral.substack.com/p/conflict-stories-1-of-5-workplace)
- [Conflict Stories 2 of 5: Critical Elements for Choosing Your Conflict Story](https://thebehavioral.substack.com/p/conflict-stories-2-of-5-critical)
- [Conflict Stories 3 of 5: Actions That Show Strong Conflict Resolution Skills](https://thebehavioral.substack.com/p/conflict-stories-3-of-5-actions-that)
- [Conflict Stories 4 of 5: How to Tell Your Conflict Story Like a Movie](https://thebehavioral.substack.com/p/conflict-stories-4-of-5-how-to-tell)
- [Conflict Stories 5 of 5: Mistakes to Avoid in Your Conflict Stories](https://thebehavioral.substack.com/p/conflict-stories-5-of-5-mistakes)

我一共准备了三个conflict stories，一个是上面的favorite project中的technical conflict，另一个是带intern时碰到的问题（同样是technical conflict），最后一个是和前同事远程合作的人际关系conflict。

其实距离做项目已经过了很久，过去我又没有详细记录工作内容，所以我已经想不起来很多具体细节了。我最终决定编一个和favorite project有关的conflict story，故事中我采取的行动是我在其他项目中做过的事情，但是相关的技术讨论没有发生过。另外两个conflict story主要是为了展示我有带intern的经验并且在过程中有成长，以及添加非 technical conflict的故事。人际关系的故事也有很大程度的美化，但面试嘛，我认为就是一场表演，有些细节省略也罢。

## Misc / 其他
我最开始的目标是投小公司，但是开始找工作才发现，小公司更注重过去经历的匹配度。比如我投的一个小公司，直接告诉我他们需要找用过某个技术的人，如果我有经验可以聊一聊。这就让我很为难，因为我相信自己肯定能学会，但要为了一个岗位新学的话时间上又划不来。当然，有回复都还算好的情况了，大多数小公司/创业公司都直接ghost或是秒拒了。


可能是因为这个，也可能是因为内推的缘故，兜兜转转我还是要去大公司工作。这也挺巧了。


现在回顾起来，准备找工的过程也没有那么长，但是真的很煎熬。很幸运在这期间看到一个gap比我更久但顺利找到工作的帖子，给了我很大的信心。当时我就决定，找到工作后我也要写一篇文章分享自己的经验。

最后，让我们重温云五老师的刺客理论！
{{< mastodon url="https://go5.dev/@yun5s/106818735668076145" >}}


祝大家想找工的都能顺利找工，不想工的都能舒舒服服躺着。

