<!-- wp:heading -->
<h2>Online News Popularity of Mashable articles </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We have a dataset of articles published by mashable, and we
want to predict the popularity of a given article.&nbsp; This is a classification problem.&nbsp; Some of the features fall into various
categories such as quantitative information about the article—such things as
number of images, number of videos, etc.—and qualitative information about the
article—such as which day it was published and which topic the article falls
under.&nbsp; </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Comparing the number of images with the number of shares, we
get the following bar graph:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":353} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/07/Online-news-images-1.png" alt="" class="wp-image-353"/></figure>
<!-- /wp:image -->
<!-- wp:paragraph -->
<p>As you can see, articles that have 1 image do better
overall.&nbsp; Then, articles that have no
images are second-best; and, articles that have 2 images come in third
place.&nbsp; The number of shares for articles
that have more than 2 images is negligible.&nbsp;
Given this insight, it would be wise to include either 0 or 1 image in
an article.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Comparing the number of videos with the number of shares, we
get the following image:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":354} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/07/online-news-videos-1.png" alt="" class="wp-image-354"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Notice that articles that have no videos tend to do best,
with articles that have 1 video doing second-best and articles that have 2
videos doing third-best.&nbsp; The articles
that have more than 2 videos are negligible in comparison.&nbsp; </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can also see which days of the week have the highest
number of shares.&nbsp; Here is a bar chart
for days of the week:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":355} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/07/online-news-days-of-week-1.png" alt="" class="wp-image-355"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>As you can see, the weekdays have the highest number of
shares.&nbsp; Wednesday, Monday, Tuesday, and
Thursday have the highest number of shares, with Friday having a significant
drop.&nbsp; </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can also see which category or topic does the best.&nbsp; Here is a pie chart for the six categories
Tech, Entertainment, World, Business, Social Media, and Lifestyle:</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":356} -->
<figure class="wp-block-image"><img src="https://www.onlinemathtraining.com/wp-content/uploads/2019/07/online-news-pie-chart-1.png" alt="" class="wp-image-356"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The best performing category is Tech, followed by
Entertainment, World, and Business.&nbsp; The
least popular categories are Social Media and Lifestyle.&nbsp; </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Using Tableau, we can create the above visualizations and do
some basic data mining.&nbsp; The insights
we’ve derived can tell us how many images and videos to include in an article,
on which day to publish the article, and which category the article should be
about.&nbsp; </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Next, using Python, I applied some machine learning to the
dataset.&nbsp; First, to formulate a
classification problem, I used the threshold of 1400 shares to create two
classes: if the number of shares is greater than 1400, then the article is
classified as popular; if the number of shares is less than or equal to 1400,
then the article is classified as unpopular.&nbsp;
</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To prepare the csv file, I created a new column—a popularity
column--after the shares column using the IF function; if the number of shares
is greater than 1400, then the class is 4 (popular), and otherwise the class is
2 (unpopular).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Our goal is to create a machine learning model that will
classify articles as popular or unpopular.&nbsp;
To do this, I used the gradient boosting classifier.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>First, I split the dataset into a training set and a test
set—taking 80% of the dataset as the training set and 20% of the dataset as the
test set.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We fit the gradient boosting classifier to our training
set.&nbsp; Then, we apply the fitted gradient
boosting classifier to our test set.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>According to the confusion matrix gotten by comparing the
predicted classes to the test classes, our model got 5277 correct
classifications out of 7929 test classifications.&nbsp; This gives an accuracy of 67%. </p>
<!-- /wp:paragraph -->
