<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>

<title>Download dataset and unzip data</title>

<script type="text/javascript">
window.onload = function() {
  var imgs = document.getElementsByTagName('img'), i, img;
  for (i = 0; i < imgs.length; i++) {
    img = imgs[i];
    // center an image if it is the only element of its parent
    if (img.parentElement.childElementCount === 1)
      img.parentElement.style.textAlign = 'center';
  }
};
</script>





<style type="text/css">
body, td {
   font-family: sans-serif;
   background-color: white;
   font-size: 13px;
}

body {
  max-width: 800px;
  margin: auto;
  padding: 1em;
  line-height: 20px;
}

tt, code, pre {
   font-family: 'DejaVu Sans Mono', 'Droid Sans Mono', 'Lucida Console', Consolas, Monaco, monospace;
}

h1 {
   font-size:2.2em;
}

h2 {
   font-size:1.8em;
}

h3 {
   font-size:1.4em;
}

h4 {
   font-size:1.0em;
}

h5 {
   font-size:0.9em;
}

h6 {
   font-size:0.8em;
}

a:visited {
   color: rgb(50%, 0%, 50%);
}

pre, img {
  max-width: 100%;
}
pre {
  overflow-x: auto;
}
pre code {
   display: block; padding: 0.5em;
}

code {
  font-size: 92%;
  border: 1px solid #ccc;
}

code[class] {
  background-color: #F8F8F8;
}

table, td, th {
  border: none;
}

blockquote {
   color:#666666;
   margin:0;
   padding-left: 1em;
   border-left: 0.5em #EEE solid;
}

hr {
   height: 0px;
   border-bottom: none;
   border-top-width: thin;
   border-top-style: dotted;
   border-top-color: #999999;
}

@media print {
   * {
      background: transparent !important;
      color: black !important;
      filter:none !important;
      -ms-filter: none !important;
   }

   body {
      font-size:12pt;
      max-width:100%;
   }

   a, a:visited {
      text-decoration: underline;
   }

   hr {
      visibility: hidden;
      page-break-before: always;
   }

   pre, blockquote {
      padding-right: 1em;
      page-break-inside: avoid;
   }

   tr, img {
      page-break-inside: avoid;
   }

   img {
      max-width: 100% !important;
   }

   @page :left {
      margin: 15mm 20mm 15mm 10mm;
   }

   @page :right {
      margin: 15mm 10mm 15mm 20mm;
   }

   p, h2, h3 {
      orphans: 3; widows: 3;
   }

   h2, h3 {
      page-break-after: avoid;
   }
}
</style>



</head>

<body>
<p>library(plyr)</p>

<h1>Download dataset and unzip data</h1>

<p>if(!file.exists(&ldquo;./data&rdquo;)){dir.create(&ldquo;./data&rdquo;)}
download.file(&ldquo;<a href="https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip%22,destfile=%22./data/Dataset.zip%22">https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip&rdquo;,destfile=&ldquo;./data/Dataset.zip&rdquo;</a>)
unzip(zipfile=&ldquo;./data/Dataset.zip&rdquo;,exdir=&ldquo;./data&rdquo;)</p>

<h1>1. Merges the training and the test sets to create one data set</h1>

<h1>Read files with read.table()</h1>

<h1>Train tables</h1>

<p>subjectTrain &lt;- read.table(&ldquo;./data/UCI HAR Dataset/train/subject_train.txt&rdquo;)
xTrain &lt;- read.table(&ldquo;./data/UCI HAR Dataset/train/X_train.txt&rdquo;)
yTrain &lt;- read.table(&ldquo;./data/UCI HAR Dataset/train/y_train.txt&rdquo;)</p>

<h1>Test tables</h1>

<p>subjectTest &lt;- read.table(&ldquo;./data/UCI HAR Dataset/test/subject_test.txt&rdquo;)
xTest &lt;- read.table(&ldquo;./data/UCI HAR Dataset/test/X_test.txt&rdquo;)
yTest &lt;- read.table(&ldquo;./data/UCI HAR Dataset/test/y_test.txt&rdquo;)</p>

<h1>Features</h1>

<p>features &lt;- read.table(&#39;./data/UCI HAR Dataset/features.txt&#39;)</p>

<h1>Activities labels</h1>

<p>activityLabels = read.table(&#39;./data/UCI HAR Dataset/activity_labels.txt&#39;)</p>

<h1>Assign column names - part of &ldquo;4&rdquo;</h1>

<p>colnames(xTrain) &lt;- features[,2] 
colnames(yTrain) &lt;-&ldquo;activityId&rdquo;
colnames(subjectTrain) &lt;- &ldquo;subjectId&rdquo;</p>

<p>colnames(xTest) &lt;- features[,2] 
colnames(yTest) &lt;- &ldquo;activityId&rdquo;
colnames(subjectTest) &lt;- &ldquo;subjectId&rdquo;</p>

<p>colnames(activityLabels) &lt;- c(&#39;activityId&#39;,&#39;activityType&#39;)</p>

<h1>Merging all data in one set</h1>

<p>mergedTrain &lt;- cbind(yTrain, subjectTrain, xTrain)
mergedTest &lt;- cbind(yTest, subjectTest, xTest)
mergedTrainAndTest &lt;- rbind(mergedTrain, mergedTest)</p>

<h1>2. Extracts only the measurements on the mean and standard deviation for each measurement</h1>

<h1>Reading column names</h1>

<p>colNames &lt;- colnames(mergedTrainAndTest)</p>

<h1>Create vector for defining ID, mean and standard deviation</h1>

<h1>Also part of &ldquo;4&rdquo;</h1>

<p>meanAndStandard &lt;- (grepl(&ldquo;activityId&rdquo; , colNames) | 
                      grepl(&ldquo;subjectId&rdquo; , colNames) | 
                      grepl(&ldquo;mean..&rdquo; , colNames) | 
                      grepl(&ldquo;std..&rdquo; , colNames) 
)</p>

<h1>Subset from mergedTrainAndTest</h1>

<p>meanAndStandardSubset &lt;- mergedTrainAndTest[ , meanAndStandard == TRUE]</p>

<h1>3. Uses descriptive activity names to name the activities in the data set</h1>

<h1>4. Appropriately labels the data set with descriptive variable names.</h1>

<p>mergedActivityNames &lt;- merge(meanAndStandardSubset, activityLabels,
                              by=&#39;activityId&#39;,
                              all.x=TRUE)</p>

<h1>5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.</h1>

<h1>Tidy data set</h1>

<p>tidy &lt;- aggregate(. ~subjectId + activityId, mergedActivityNames, mean)
tidy &lt;- tidy[order(tidy$subjectId, tidy$activityId),]</p>

<h1>Write tidy data set in txt file</h1>

<p>write.table(tidy, &ldquo;tidy.txt&rdquo;, row.name=FALSE)</p>

<p>library(knitr)
knit2html(&ldquo;run_analysis.R&rdquo;,&ldquo;codebook.Rmd&rdquo;)</p>

</body>

</html>
