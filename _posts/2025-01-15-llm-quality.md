---
title: "Keeping LLMs Classy"
date: 2025-01-15
categories:
  - blog
tags:
  - tech
---

I've seen many posts that 2025 is the year of AI agents - but I think 2025 will come to be the year of the beginning of the AI (read GenAI here) reckoning in hindsight. 
Large companies have spent the last two years focusing on integrating AI into their applications, and now the question will be - how does AI help our topline or bottom line? Is it helping increase revenue, or decrease cost? See - I think AI has been a big reason for the recent layoffs across multiple companies. So that executives can say - through my initiative, I saved the company X% by automating labor (separate question as to whether this actually happened or not).

So let's say you are building an LLM based application. How do you make sure that the product experience you are building around LLMs is not going to be scrapped? For this, you need some way to make sure the application is doing a good job. In this article, I go through the steps involved in doing so - turns out, it is not so simple as (only) making API calls to your favorite LLM provider. 

In 2023, LLM context windows were only up to a thousand tokens or so, which made it impossible to ingest large documents longer than a few pages in a single LLM call. A lot of startups took advantage of this, and built applications that chat over longer documents using retrieval augmented generation (RAG) such as PDF chat. However, within a year, LLM providers like GPT, Anthropic, Google incorporated chat with documents within their system, and also increased context windows by orders of magnitude to hundreds of thousands, and even millions of tokens. Because of this, many of these early startups crashed, or had to significantly modify their strategy. The lesson here is that any company working in the area of generative AI needs to constantly evaluate the product they are building (or built) - and look from the customer perspective. 

If you were a customer, would you use company X's product built on top of an LLM? Or just go to your favorite LLM provider and do the same task there? At the same time, if you are offered to do a very niche, obsecure task powered by LLMs this is uselsess. The trick is to find the right balance to attract users, and grow from there.

<figure >
    <a href="/assets/images2/llm-classy.png"><img src="/assets/images2/llm-classy.png" alt="Skanda Vivek"></a>
</figure>

A good example of an application in the sweet spot is Cursor - which is an AI code editor like GitHub copilot, but much more optimized for autocompletion (go crazy with tab, tab, tab). Cursor is built on top of LLMs like GPT and Claude - so it does not reinvent the wheel, but focuses on this niche of coding autocompletion. At the same time, it is a popular niche, so they have enough traction from users to build something that a lot of people value.

## How Do You Wow Users?

Unless you are a startup with billions of dollars to burn, you can't wow your users through AI alone. That's the hard reality- your users have already been wowed by GPT or Claude or Gemini, etc. But if you are a company that's been in the business for atleast a few years - chances are that your users find something useful, otherwise they would have left. What you can do though - is make users even more impressed by offering them new GenAI features, or making it easier to do whatever task they've come to you for - either on the web or in person. Ultimately, it comes down to data. What do you know about X person, to help them perform Y task? Given that data, LLMs are very capable of making basic decisions, and giving information to users in a consumable way.

Let's say for example you are work at LinkedIn and are tasked with generating LinkedIn content that users can post. Based on a user's behavior, you can give them post suggestions. But if you don't have this, and build a simple wrapper around an LLM - this is not as useful. The same user can just make a LinkedIn post on their favorite LLM app and post it using LinkedIn. In the spirit of integrating user data with LLMs - I also think that recommendation systems are here to stay in a big way. The 'retrieval' aspect of RAG is nothing but a text based recommender. 

<figure >
    <a href="/assets/images2/walmart-rec.png"><img src="/assets/images2/walmart-rec.png" alt="[Walmart Rec Sys](https://arxiv.org/pdf/2410.12228)"></a>
</figure>


In October 2024, Walmart [released a paper](https://arxiv.org/pdf/2410.12228) where they aligned text, visual, and graph data for leveraging LLM based recommendations to users. On a light hearted note - this could be thought of as flipping RAG on it's head or generative augmented recommendation (GAR :grin:).
I think we will see more and more of these types of products where LLMs are closely integrated with existing ML pipelines.

## Deliver With A Bang

Ok, so you've figured out how to wow your users using GenAI, and decided to develop this further. But how do you make sure your app delivers as expected? And how do you define what "good" is? This question turns out to be extremely important, and often underestimated for a few different reasons:

1. Traditional ML applications have well defined purposes and labels to train on. Whereas GenAI opens up the UX to all sorts of user inputs.

2. GenAI is by definition "generative" meaning the outputs are not bounded. A polar example is a classification task such as sentiment classification - which has a few output categories.

3. The bar is extremely high. If you promise customers a more natural experience for interacting - they expect human-like conversations. And turns out, humans are extremely good at detecting subtle patterns. 

You need a way to benchmark your model before putting it out to users. This is where internal testing helps. A way to assess quality is by getting quick feedback, and iterating fast. In the Lex Fridman podcast featuring Dario and Amanda from Anthropic - Anthropic uses a similar method to test quality, though they have the ability to actually test with large audiences. For a smaller user base, this approach might mean more leveraging internal opinions across multiple groups before putting it in production.
<figure >
    <a href="/assets/images2/lex-dario-amanda.png"><img src="/assets/images2/lex-dario-amanda.png" alt="Lex Fridman Podcast | [Lex Fridman Podcast](https://lexfridman.com/dario-amodei-transcript/#chapter15_constitutional_ai)"></a>
</figure>


However, while it is possible for humans to grade a few tens or hunderds of examples, this becomes hard to scale. One problem is that grading just takes a lot of time. Each time you deploy a small variation, grading tens or hundreds of examples becomes expensive. Let's think about how to automate this. One option is if your task has well defined constaints. Let's say your users are asking questions based on a user manual - maybe a fridge product. Here answering the user query happens in two steps. First, the relevant context needs to be retrieved from the user manual, and second the answer generated from the context. In this case, the [RAG triad](https://docs.confident-ai.com/docs/guides-rag-triad#:~:text=What%20is%20the%20RAG%20Triad,is%20using%20the%20optimal%20hyperparameters) comes in handy. The idea is that you evaluate how relevant the output answer is to both the user query and retrieved context, as well as the relevance of retrieved context to the user query. 

<figure >
    <a href="/assets/images2/rag-triad.png"><img src="/assets/images2/rag-triad.png" alt="[RAG Triad](https://docs.confident-ai.com/docs/guides-rag-triad#:~:text=What%20is%20the%20RAG%20Triad,is%20using%20the%20optimal%20hyperparameters)"></a>
</figure>

If you do use the RAG triad, you still need to find out a way to accuractely score the outputs relative to query or context. In case the response is more open-ended (e.g. generating a marketing or sales message), evaluation becomes more nuanced - potentially domain specific. The best path forward would be to first get human domain experts to judge a bunch of responses, and subsequently develop a model to replicate these scores. Typically, the way you do this is through an LLM judge. The key here is to use a good LLM judge and develop an LLM judge prompt that does a good job of representing the human judge. Before going down this path - consider the data you are collecting from human judgement as well. I've seen that humans can differ in scoring methods especially in complex tasks. Additionally, the same person can give different scores at different times based on how the data they have seen has influenced them. It happens to all of us at some point. Try to get multiple humans to judge the same content - trust me, you will be grateful down the line as you will have a solid dataset.

Next, lets talk about how you develop an LLM judge. This becomes a typical data science problem once you have enough data - you distribute into a train and test set. There are multiple ways you can use the train set. You can distill this into a set of rules for an LLM judge prompt. Let's say you had scores from 1-5, 1 being horrible fail, and 5 being excellent. You could send 10s or 100s of these examples through a prompt and distill rules for evaluating content. You could also add few-shot examples to the judge prompt.

The second part is evaluating the performance of the LLM judge. Correlation between the judge and human scores using metrics like Kendall’s correlation and Spearman’s correlation give a quick indicator of how well the two match each other. However, I like to look closer at metrics like class based precision and recall. Often, a quick view at a confusion matrix can be illuminating. It could also make sense to binarize the response - e.g. 1-3 denote fail, and 4-5 are pass. In this case, you could look at which category the LLM judge is performing well in and which it is failing, and also what is important to capture. Is it important to have high precision? Is the data skewed? These are all important factors while evaluating performance and seeing if you need to change the judge prompt.

Often, you might have imbalanced data. After all, didn't you build your prompt to be really good? Here again LLMs can be used to generate synthetic data. The approach I like to use is to take a decent response, and slightly modify it to be bad. Now, you've bootstrapped your dataset to handle diverse cases. One final thing I want to say here, is that you might decide to use a smaller model such as an embeddings based classifier, as your judge. One thing to note is that this would have less interpretability. Another issue is that it cannot easily be scaled to a scenario where there is less data. This is where synthetic data helps, as you can use it to bootstrap edge cases.

## Learning And Constantly Improving
Now you've deployed your model. Give yourself a pat on the back, sit back, and let the wins come in as customer after customer is wowed by your application. That has to be the case - right? After all, haven't you tested it out on internal experts, and your project has been given a green light by the higher-ups? Unfortunately your customers didn't know that (or didn't care that you put in your heart and soul - maybe not their top priority). So what now - one option is to scrap what you did, return back to the drawing board, and try again. And again, and again. Until you are exhausted, and the entire org is exhausted - not knowing what went wrong and where.

While this sounds funny, it's unfortunately something I've seen mutiple times. It is important to learn from what went wrong, and improve. This is why it is important to have a robust data storage process - so that you can go back, and understand why your application was not as hot as you thought. Maybe its something simple that you can fix next time. A/B testing is a common practice, where you segment your user base into two groups - one receives the experiment, the other receives the control. Try to make life as simple as possible - make populations large and well defined. Don't have too many variants that can confuse these analyses. And don't change so many things at once, that you can't make a coherent analysis at the end. Remember ultimately you need to convince your peers and decision makers. While you might be able to do a complex analysis of multiple different variants and experiments and list 10 key takeaways, decision makers are more easily convinced by simple takeaways, and are more skeptical, the more complex your conclusions are.

Let's say you are a startup - and don't have the same access to data as a larger company. A/B testing works once you've had initial success and a meaningful chunk of active users - but might not work so well in the beginning. Dean Pleban, Co-Founder & CEO at DagsHub mentions that he's seen startups get to that point by doing gradual rollouts with people they trust to give them tons of feedback and do quick iterations until they see something super sticky. Chances are once a few people find your product important, others will too.

## Takeaways
Most of the learnings that stood out for me have been through trial by fire. I hope that these learnings can help you preemptively put your best foot forwards and produce amazing AI based applications that drive progress. AI is here to stay - and can really help those of us who are busy getting pulled in different directions - to delegate tasks. But it is important to properly delegate - otherwise you are left with a larger mess to clean up than you started off with. Keep it simple, remember that nothing has really changed in how you approach problems. You still have to solve for customers, learn through data, and keep improving. Don't get pressured into making hasty decisions. Everyone that matters will be thankful for it.

Shoutout to Dean Pleban, Co-Founder & CEO at DagsHub 🐶 (a company that helps AI teams manage unstructured data and build better models) for his review and great suggestions.

Subscribe to my mailing list!

<div id="mc_embed_shell">
      <link href="//cdn-images.mailchimp.com/embedcode/classic-061523.css" rel="stylesheet" type="text/css">
  <style type="text/css">
        #mc_embed_signup{background:#fff; false;clear:left; font:14px Helvetica,Arial,sans-serif; width: 600px;}
        /* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
           We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
    <form action="https://chaoscontrol.us7.list-manage.com/subscribe/post?u=cd3eef2d66d1a86e7eba23eb3&amp;id=fb46f3513a&amp;f_id=000fd7e4f0" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank">
        <div id="mc_embed_signup_scroll"><h2>Subscribe</h2>
            <div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
            <div class="mc-field-group"><label for="mce-EMAIL">Email Address <span class="asterisk">*</span></label><input type="email" name="EMAIL" class="required email" id="mce-EMAIL" required="" value=""></div>
        <div id="mce-responses" class="clear foot">
            <div class="response" id="mce-error-response" style="display: none;"></div>
            <div class="response" id="mce-success-response" style="display: none;"></div>
        </div>
    <div aria-hidden="true" style="position: absolute; left: -5000px;">
        /* real people should not fill this in and expect good things - do not remove this or risk form bot signups */
        <input type="text" name="b_cd3eef2d66d1a86e7eba23eb3_fb46f3513a" tabindex="-1" value="">
    </div>
        <div class="optionalParent">
            <div class="clear foot">
                <input type="submit" name="subscribe" id="mc-embedded-subscribe" class="button" value="Subscribe">
                <p style="margin: 0px auto;"><a href="http://eepurl.com/iNSD4w" title="Mailchimp - email marketing made easy and fun"><span style="display: inline-block; background-color: transparent; border-radius: 4px;"><img class="refferal_badge" src="https://digitalasset.intuit.com/render/content/dam/intuit/mc-fe/en_us/images/intuit-mc-rewards-text-dark.svg" alt="Intuit Mailchimp" style="width: 220px; height: 40px; display: flex; padding: 2px 0px; justify-content: center; align-items: center;"></span></a></p>
            </div>
        </div>
    </div>
</form>
</div>
<script type="text/javascript" src="//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js"></script><script type="text/javascript">(function($) {window.fnames = new Array(); window.ftypes = new Array();fnames[0]='EMAIL';ftypes[0]='email';fnames[1]='FNAME';ftypes[1]='text';fnames[2]='LNAME';ftypes[2]='text';fnames[4]='PHONE';ftypes[4]='phone';fnames[3]='MMERGE3';ftypes[3]='text';}(jQuery));var $mcj = jQuery.noConflict(true);</script></div>

