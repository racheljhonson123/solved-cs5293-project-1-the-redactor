Download Link: https://assignmentchef.com/product/solved-cs5293-project-1-the-redactor
<br>



<h1>Introduction</h1>

Whenever sensitive information is shared with the public, the data must go through a redaction process. That is, all sensitive names, places, and other sensitive information must be hidden. Documents such as police reports, court transcripts, and hospital records all containing sensitive information. Redacting this information is often expensive and time consuming.

<h1>Task Overview</h1>

In this project, you will use your knowledge of Python and Text Analytics to design a system that accept plain text documents then detect and redact “sensitive” items. Below is an example execution of the program.

Running the program with this command line argument should read all files given by the glob — in this case all the files ending in .txt in the current folder. All these files will be redacted by the program. The program will look to redact all <em>names </em>and <em>dates</em>, and <em>phone numbers</em>. Notice the flag –concept, this flag asks the system to redact all portions of text that have anything to do with a particular concept. In this case, all sentences that contain information about <em>kids</em> should be redacted. <em>It is up *you* to determine what represents a concept.</em>

Each redacted files should be transformed to new files of the same name with the .redacted extension, and written to the folder described by –output flag. The final parameter, –stats, describes the file or location to write the statistics of the redacted files. Below we discuss each of the parameter in additional detail.

<h2>Parameters</h2>

<h3>–input</h3>

This parameter takes a <a href="https://docs.python.org/3/library/glob.html">glob</a> that represents the files that can be accepted. More than one input flag may be used to specify groups of files. If a file cannot be read or redacted an appropriate error message should be displayed to the user.

<h3>–output</h3>

This flag should specify a directory to store all the redacted files. The redacted files, regardless of their input type should be written to text files. Each file should have the same name as the original file with the extension .redacted appended to the file name.

<h3>Redaction flags</h3>

The redaction flags list the entity types that should be extracted from all the input documents. The list of flags you are required to implements are:

–names

–genders

–dates

–phones

You are free to add you own! –names correspones to any type of name, it is up to you to define this. –genders should be any term that reveals the gender of an entity (e.g. him, her, father, mother, etc.). –dates correspond to any written dates (4/9/2022, April 9th, etc.) –phones describes any phone number in its various forms. In your README discussion file <strong>clearly </strong>give the parameters you apply to each of the flags. The redacted characters in the document should be replaced with a character of your choice. Some popular characters include the unicode <a href="https://unicode-table.com/en/2588/">full block character</a> █ (U+2588). You may choose to redact both words and the whitespaces between phrases. If you believe that one should also redact whitespaces between words (e.g. in a first and last name) please discuss why in your README.md.

<h4>–concept</h4>

This flag, which can be repeated one or more times, takes one word or phrase that represents a concept. A concept is either an idea or theme. Any section of the input files that refer to this concept should be redacted. For example, if the given concept word is prison, a sentence (or paragraph) either containing the word or similar concepts, such as jail or incarcerated, that <em>whole sentence</em> should be redacted. In your README file, make your definition of a concept clear. Also, clearly state how you create the context of a concept and justify your method. You may be creative here!

<h3>—stats</h3>

Stats takes either the name of a file, or special files (stderr, stdout), and writes a summary of the redaction process. Some statistics to include are the types and counts of redacted terms and the statistics of each redacted file. Be sure to describe the format of your outfile to in your README file. Stats should help you while developing your code. Stats may also include the begining and end index of each redacted item. It is up to you to design your stats output.

<h2>COLLABORATORS file</h2>

This file should contain a comma separated list describing who you worked with and a small text description describing the nature of the collaboration. This information should be listed in three fields as in the example is below:

Katherine Johnson, <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="9af1f0daf4fbe9fbb4fdf5ec">[email protected]</a>, Helped me understand calculations

Dorothy Vaughan, <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="adc9c2dfc2edc9c2c983cac2db">[email protected]</a>, Helped me with multiplexed time management <strong>Project Descriptions</strong>

Your code structure should be in a directory with something similar to the following format:

<h2>setup.py</h2>

Note, the setup.cfg file should have at least the following text inside:

<h2>Tests</h2>

The general rule is you should aim to have a test for each feature. Including tests help people understand how your code works, in addition to verifying assumptions during development. Tests should be runnable by using pipenv run python -m pytest. You should discuss your tests in the README.

<h1>Extra links and Notes</h1>

It is expected that you will use Spacy or NLTK to complete this assignment. However, you are welcomed to use other popular

APIs. Some of these API’s a larger instance may require a larger instance, please let us know if you plan to do this. Also, some APIs require specialied keys, please let the TA know how you plan to use your keys. Below is the information for using Google tools.

Creating API Keys https://cloud.google.com/docs/authentication/api-keys

<a href="https://spacy.io/">Spacy 3.0</a>

Google NLP https://googlecloudplatform.github.io/google-cloud-python/latest/language/usage.html#annotate-text

Using Google Natural Language Client <a href="https://cloud.google.com/natural-language/docs/reference/libraries#setting_up_authentication">GCP</a>

<a href="http://www.nltk.org/">NLTK</a>

<h1>Create a repository for your project on GitHub</h1>

Create a private repository GitHub called cs5293sp21-project1

Add collaborators cegme, Shejeebhomee by going to Settings &gt; Collaborators.

We will be testing your code on the VM instances described in class. Please ensure your code runs correctly on the instances. If any extra information is necessary such as an extra large instance size you must specify that in your intances.

You should regularly git add &lt;file&gt;, git commit -m, and git push origin main your code changes to GitHub.


