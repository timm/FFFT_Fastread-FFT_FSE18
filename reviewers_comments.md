Reviewers' Comments

  Please note that some reviewers may have included additional comments in a separate file. If a review contains the note "see the attached file" under Section III A - Public Comments, you will need to log on to ScholarOne Manuscripts  to view the file. After logging in, select the Author Center, click on the "Manuscripts with Decisions" queue and then clicking on the "view decision letter" link for this manuscript. You must scroll down to the very bottom of the letter to see the file(s), if any.  This will open the file that the reviewer(s) or the Associate Editor included for you along with their review.

Reviewer: 1

Public Comments (these will be made available to the author)
  3This paper proposed to exploit two new techniques (i.e., FASTREAD and FAST FRUGAL TREES) to facilitate the task of commit labelling and just-in-time defect prediction respectively. The central insight of this paper is that the commit labeling problem is analogous to reading research papers. With an such intuition, the authors proposed to leverage an active learning approach, FASTREAD, to label “worrying” commits. The evaluation over 9 open source projects demonstrated the benefits of using the proposed “F3T” technique.

 Defect prediction has attracted huge research attention a decade ago. Although it gets less and less attention recently, many research efforts are still being made to advance this direction. Labelling commits, on the other hand, seems to be more important since it is the foundation of many mining-based software engineering researches. Therefore, the motivation of this work, as emphasized in Section 2.3, is clear to me. 

 However, many enhancements could be made to improve this manuscript. Especially for its approach (i.e., not clearly explained) and evaluations (i.e., missing important state-of-the-art techniques). 

- 1.  The approach, including its intuition and insights, is too brief and confusing. 

The authors spent lots of efforts in describing motivations and different learning models. However, the description of the approach itself is too brief, which prevent me from understanding the novelty of this work clearly. For instance, the central insight of this paper is “Commit labelling problem is analogous to reading research papers”.  However, there is no justification or examples why this insight might be valid. This poses significant threats to the validity of the proposed approach. Besides, what is the intuition of use “FAST and FRUGAL TREES” in classifying buggy commits? Since it is a major component of the F3T approach, justifications are required.

If we only look at the commit log messages, they are only text tokens. In such case, the approach FASTREAD can process the data of log messages if it can process research papers. However, the characteristics of log messages and research papers diverge a lot. Will that affect the effectiveness of FASTREAD in labelling commits?

Besides, details of FASTREAD are also not clearly explained. In the description of Section 3, it seems that FASTREAD integrates some sampling techniques and machine learner (e.g., SVM) together. However, what are the features used here for the learner SVM? If FASTREAD requires generating a set of features to label commit, then what are the features generated for research papers in the original setting of FASTREAD? 

In page 4 at line 41, “until N2=30 relevant examples are found”. Here, are these 30 examples declared by human or automatically?

Many notations in Table 3 have not been explained. It is not a good practice to present a table without explaining the items listed in it. 

The current description of Section 3 confused me in many aspects. I suggest the authors to enhance the explanation why FASTREAD can be applied in labelling commit, and use a diagram to better explain the workflow of FASTREAD.

-  2.      Some details are not well-explained.

- In RQ2, RQ3 and RQ4, the authors should discuss more details about whether the evaluation results on the manually labelled four projects are different from those on the other five automated labelled projects. 

- The authors claimed that using FASTREAD, humans only need to read a small percentage of the commits (Page 4). However, the authors did not present the exact data that how many commits have been manually reviewed for each project. I think such information should be listed in the experimental setup. 

3. Evaluation does not include the state-of-the-art.

-       The authors first proposed to leverage FASTREAD to identify which commit is bug-fixing. In the evaluations, the authors compared with a keyword-based approach. However, there are many approaches have been proposed to identify bug-fixing commits automatically, such as Relink [4] and [5]. Especially, in the work proposed by Tian et al. [5], they also compared with the keyword-based approach, which has already demonstrated an average improvement from 22.05% to 50.07%. Therefore, such important related works should be selected as baselines for comparison. 

-       The authors should also compare with the-state-of-the-art approaches for predicting bug-inducing commits. For example, Yang et al., proposed to leverage deep learning techniques to predict which commit is buggy [3].

-       Recent studies have pointed out that the SZZ algorithm is not accurate. For instance, Böhme et al. [1] found that, for nearly one third of their studied bugs, SZZ cannot identify any real bug-inducing commits via “blaming” the statements modified by the bug-fixing commits. Costa et al. [2] later proposed a framework to evaluate the results of SZZ. They found that for 46.0% of their studied bugs, the bug-inducing commits identified by SZZ are years apart from one another while it is unlikely that code changes committed years apart will induce the same bug. Have the authors checked such bias in their evaluation? 

4.  Some other typos.
There are many typos in this manuscript. Please carefully fix these writing issues. Some examples are listed as follows:
-       Page 5 line 37: “since many of these projects a simple one-person prototypes”
-       Page 6 line 36: “oroject data was divided into”
-       Page 8 line 14: “It method is applied and …”


[1]. Marcel Böhme and Abhik Roychoudhury. 2014. Corebench: Studying complex- ity of regression errors. In Proceedings of the 2014 International Symposium on Software Testing and Analysis. ACM, 105–115.
[2]. DanielAlencardaCosta,ShaneMcIntosh,WeiyiShang,UiráKulesza,Roberta Coelho, and Ahmed E Hassan. 2017. A framework for evaluating the results of the szz approach for identifying bug-introducing changes. IEEE Transactions on Software Engineering 43, 7 (2017), 641–657.
[3]. Yang, Xinli, et al. "Deep learning for just-in-time defect prediction." 2015 IEEE International Conference on Software Quality, Reliability and Security. IEEE, 2015.
[4]. Wu, Rongxin, et al. "Relink: recovering links between bugs and changes." Proceedings of the 19th ACM SIGSOFT symposium and the 13th European conference on Foundations of software engineering. ACM, 2011. 
[5]. Tian, Yuan, Julia Lawall, and David Lo. "Identifying linux bug fixing patches." Proceedings of the 34th International Conference on Software Engineering. IEEE Press, 2012.







Reviewer: 2

Public Comments (these will be made available to the author)
In this paper, the authors propose to use an active learning approach to label whether a commit is a bug fixing commit. Such a labelled data is often crucial for various bug prediction tasks in software quality assurance and analytics. The authors compare the use of the active learning approach and keyword based labelling on software defect prediction with a combination of other techniques, such as balancing and other classifiers/regression modeling. The results show the value of the more accurate labeling from the active learning approach.

I have several major comments of the paper while my other ones are quite minor. 
1. The contribution of the paper. The paper in all contributes in proposing using active learning in labeling commits.
I do see the contribution part at the end of intro. However, honestly, number 1, i.e., “we bring this idea to you”, is not a contribution, but rather the paper itself. Number 3 is a bit weak since some of the subjects in this paper is also in Java and trying software defect prediction on a domain of software is although indeed a contribution, but not significant. Otherwise one can just pick a new domain, try it out and claim contribution. 
I hope the authors can support their contribution more in the rebuttal and convince me the significance of it (not just emphasizing the ones in page 3). 

> need a better list of controbutuobns

2. The need of the approach. This is another major concern of mine. This technique, although useful in cases, may not be needed at all in many cases. Using issue tracking system to link issue reports to the commits and use the data in the issue reports to label the commit is a very common practice in software prediction. I understand there are always projects that are without an issue tracker. This makes me remember once upon a time, people study how to combine changes in CVS into change sets. If you ask me are those techniques useful, of course. There are still projects on the planet using CVS. But the relevance is decreasing. 
In fact, I checked some of the subjects that the authors study, some of them have issue ids right in their commit messages and some do have an issue tracker, that you can mine to link back to the commits. 
Hence I would like to ask the authors how useful is their approach considering the fact that one may link issue tracker to the version control and label commits based on that. My suggested way may be study how often a project (say in github) do not use internal issue tracker or an external one. Or even the ones that use, how often the commits cannot be linked to an issue to be labelled, in order to better motivate the work.

3. Unclearness of the bug prediction models. By reading through RQ2 to RQ4, I am a bit confused about whether each RQ is doing commit level or file level bug prediction. 
I assume RQ2 is commit level bug prediction. But the highlight box of RQ2 in top left of page 9, says, buggy code. Also, the first line of page 9, “such code” should be “such commit”, I assume.
Then RQ3, in the question, you say “buggy code” but in the highlight box, you say, “buggy commits”. Now I am completely confused. Or do you mean the same thing?
Now in RQ4, the authors say, for RQ1 and 2, the target is for prediction task and for RQ3 it’s for analytic task. Does it mean that RQ1 and 2 are for commit-level and RQ3 if for file level? But now, is RQ4 commit level or file level?
I would suggest the authors clarify this up and clearly lay this out in the paper ahead of time to avoid confusion. 
If there are file-level prediction, are the authors doing post release bug? If so, how is the post release determined? If the authors doing the commit-level prediction, did the authors pre-check the data generated by szz to avoid clear mistakes from szz and how do you control it? For example, sometimes, the szz would say a large number of commits are bug inducing to one bug. How is training and testing data split?

In short, please add more details into the paper to avoid confusion. 



My other comments
1. The title of the paper misses the important context of the paper, i.e., bug prediction. The authors should clear that up in the title. In addition, F3T, only the first F is about the labeling. The rest is not about the enhanced labelling. I wouldn’t put F3T in the title.
2. In the paper, the authors use “buggy” or “not buggy” to describe the commits. I think it’s misleading. Maybe consider use “bug fixing” or “none bug fixing”. Also in the fist line of the conclusion, the authors should also mean “bug fixing” or “none bug fixing”. “Worrying” or not is an internal state in the active learning. 
3. The table 11 and 12 in discussion, would the author provide the details how is calculated? Especially for table 12? Seems like you only can do double the commits per hour and the saving is huge (to less than 1/10). 
4. Table 10, the p20 part, first line, none of them wins?
5. Citation 24 in page 3 top left. I don’t understand how it supports the claim. Please clarify.
6. Personally I don’t see the value of section 2.3. I understand the authors may have their own concerns, but I personally would save that space to provide more details about the RQs.
7. Some typos, grammar issues, bad wordings:
Page 1: abstract: humans *the* apply
Abstract: “very effective” “very” is a vague word 
Page 2, RQ3 maybe What => Which?
RQ4, which identification and prediction system perform*s* *the* best for …
Page 5, right column first line, than=> then
Page 8, bottom left, “RQ2,RQ3”=> missing a white space before “RQ3”


Reviewer: 3

Public Comments (these will be made available to the author)
Summary

The authors introduce an approach for classifying commits into worrying and not-worrying using an incremental combination of machine learning and human labelling by combining previous work on FASTREAD and FFT trees. Evaluating their approach with nine computational science software projects and using CommitGuru and keyword labelling as a baseline, the authors find that their approach significantly outperforms related work in terms of reproducing the ground truth and generates better predictors for buggy code and buggy commits.

Review

The authors' work is well motivated. Keyword approaches are widely used for the task which the authors are working on, and it is unsurprising that ad-hoc keyword lists do not produce the best possible results. Also, many research areas, in particular related to defect prediction, rely on accurate labelling. The results in the paper are convincing, clearly outperforming baselines in terms of accuracy and time needed to produce the results. 

While the combination of previously established techniques is a strength of this paper on one hand, it also raises concerns about the size of the contribution of this work. Indeed, the most intriguing contribution of this work is the manual labelling of commit messages from a domain which is often overlooked in Software Engineering research, but I wonder if this is sufficient for a TSE publication. For a journal paper, I would expect a more detailed investigation of *why* FASTREAD and FFT work better than the baseline techniques in this scenario. What do they learn that other learners did not pick up on, for example?

I found some of the vocabulary used in the paper confusing:

* The title of the paper refers to labelling of issue reports, yet the paper appears to be about commit message labelling. Should the title be adjusted?

* I found the terminology of "worrying" vs. "not-worrying" confusing. Why is a commit message which contains the words "fix", "better", or "test" (for example) worrying? If anything, I would argue that these indicate commits which would make me worry less.

Related to the previous point, the authors claim that Table 1 (the worrying keywords) are taken from reference 33. This does not appear to be correct -- although the Commit Guru paper claims the same. Would the authors be able to point out exactly where in reference 33 these keywords are to be found? A quick search didn't come up with anything, but I may have missed it. I suspect that the keywords were introduced in the Commit Guru paper instead of the Hindle 2008 work.

While the focus on computational science software is a nice feature of this paper, it does beg the question whether the same improvements would be achieved on the projects that have been studied in related work. I would suggest that the authors report the results of their approach on at least one of the projects that were used by related work. This would also provide some data on the extent to which the domain affects the performance of different approaches.

For the manual labelling, the authors report "very low" observed disagreement and that it was under 15%. Please provide the exact numbers, ideally along with a representative example of a disagreement. 

For the labels generated by FASTREAD, the recall on the PCMSOLVER data set is quite a bit lower than for the other four data sets (Table 6). It would be good to provide an explanation for this difference.

The quality of the writing is really low. I would strongly encourage the authors to proofread papers before submission -- it is quite irritating to review a manuscript which was prepared without care. A few examples mostly from the first page, but note that this list is nowhere near complete:

* Humans the apply -> Humans then apply
* commits that they guess is -> ... are
* bugs labels -> bug labels
* commits that indicates -> ... indicate
* squares of Figure 1 shows -> ... show
* a semi-automatic methods -> ... method
* oroject -> project
* ahve -> have
