# Seeing is Believing: Data Visualization in Action

Welcome to the FUN part! 🎉 Time to get your hands dirty with real data. No more theory—today we PRACTICE!

{{1}}
> **Dr. Chen's Mantra:** You don't really learn statistics by listening. You learn by DOING (and occasionally making glorious mistakes that teach you more than anything else)!

---

## Today's Mission 🎯

**By the end of this hour, you will:**
- Calculate descriptive statistics from a real dataset
- Create histograms and box plots
- Interpret what those visualizations are screaming at you
- Feel like a data detective 🔍

{{1}}
**The Rules:**
1. Work in pairs (two brains > one brain)
2. Ask questions—there are NO stupid questions!
3. If Excel/your software misbehaves, deep breath and call me over
4. Celebrate your "aha moments" loudly!

---

## Meet Your Dataset 📊

**Student Well-being Survey (n=50)**

We surveyed 50 Master's students about their habits and well-being. Here's what we collected:

{{1}}
**Variables:**
- `hours_sleep`: Average hours of sleep per night (ratio data)
- `stress_level`: Self-rated 1-10 scale (ordinal/treated as interval)
- `study_hours`: Hours studied per week (ratio data)
- `exercise_frequency`: Never, Rarely, Sometimes, Often, Daily (ordinal)
- `major`: Business, Social Sciences, Engineering, Other (nominal)

{{2}}
**Your dataset file:** `student_wellbeing_data.csv`  
(Don't worry—I'll walk you around to help with setup!)

---

## Exercise 1: Calculate Descriptive Statistics (20 min)

**Part A: Hours of Sleep** ⏰

{{1}}
Using the `hours_sleep` variable, calculate:

1. **Mean** (average sleep)
2. **Median** (middle value)
3. **Mode** (most common)
4. **Range** (max - min)
5. **Standard Deviation**

{{2}}
**Tools you can use:**
- Excel: `=AVERAGE()`, `=MEDIAN()`, `=MODE()`, `=STDEV.S()`
- Calculator + paper (old school but effective!)
- R, Python, SPSS if you're feeling fancy

---

### Group Discussion: Sleep Findings

After calculating, discuss with your partner:

{{1}}
**Questions to ponder:**
- Is the mean close to the median? What does that tell you?
- What's the standard deviation? Are sleep patterns pretty similar or all over the place?
- Did anyone sleep WAY more or less than average? (outliers!)

{{2}}
> **Dr. Chen's Hint:** If mean ≠ median by much, you might have outliers pulling the mean around. That's your detective work starting!

---

## Exercise 2: Stress Levels Deep Dive (20 min)

**Part B: Exploring Stress** 😰

{{1}}
Now tackle the `stress_level` variable (1=no stress, 10=maximum stress):

1. Calculate mean and median
2. Create a **frequency table** (how many students rated each level?)
3. Identify the mode (most common stress level)

{{2}}
**Bonus challenge:** Calculate the stress level for each major separately. Do Business students stress more than Social Science students? 🤔

---

### Quick Quiz!

You notice the mean stress level is 7.2, but the median is 8. What might this suggest?

    [( )] Everyone is equally stressed
    [(X)] Some students with LOW stress are pulling the mean down
    [( )] Most students are very stressed
    [( )] The data is wrong

{{1}}
✅ Exactly! If median > mean, you've got some lower values dragging the average down. Most students are at 8 or higher, but a few lucky folks are chilling at 3-4!

---

## Exercise 3: Visualization Time! 📈

Now the REALLY fun part—making pictures!

---

### Part C: Create a Histogram

**What's a histogram?** A bar chart showing how data is distributed across different ranges (bins).

{{1}}
**Your task:** Create a histogram for `study_hours`

**Steps (Excel example):**
1. Select your data
2. Insert → Chart → Histogram
3. Adjust bin sizes (try 5-hour bins: 0-5, 5-10, 10-15, etc.)
4. Add labels and title!

{{2}}
**Other tools:**
- **R:** `hist(data$study_hours)`
- **Python:** `plt.hist(study_hours, bins=10)`
- **SPSS:** Graphs → Legacy Dialogs → Histogram

---

### Interpreting Your Histogram

Look at your histogram and answer:

{{1}}
**Shape Questions:**
- Is it roughly bell-shaped (normal distribution)?
- Skewed left or right?
- Multiple peaks (bimodal)?

{{2}}
**Story Questions:**
- Where do MOST students fall?
- Are there any students studying way more/less than others?
- If you had to describe study habits in one sentence, what would you say?

{{3}}
> **Dr. Chen's Reality Check:** Most student study-hour distributions are right-skewed. Most study a moderate amount, but there are always those overachievers pulling all-nighters! 📚☕

---

### Part D: Create a Box Plot

**What's a box plot?** A compact visualization showing:
- Median (line in the middle)
- Quartiles (the box)
- Range (the whiskers)
- Outliers (dots floating outside)

{{1}}
**Your task:** Create a box plot for `hours_sleep`

**Steps (Excel 2016+):**
1. Select data
2. Insert → Statistical Chart → Box and Whisker
3. Marvel at its beauty!

{{2}}
**What you're looking for:**
- Where's the median line?
- How big is the box? (interquartile range = middle 50% of data)
- Any outliers? (dots beyond the whiskers)
- Is it symmetric or skewed?

---

### Box Plot Challenge! 🥊

Create box plots comparing stress levels across different majors.

{{1}}
**Steps:**
1. Group data by major
2. Create box plots side-by-side
3. Compare!

{{2}}
**Questions:**
- Which major has the highest median stress?
- Which has the most variability in stress?
- Any majors with outliers (students way more/less stressed than peers)?

{{3}}
**Pair Discussion:** Why might certain majors show different patterns? Share your theories!

---

## Exercise 4: The Real Research Challenge (15 min)

**Your Mini Research Project** 🔬

{{1}}
**Scenario:** You're writing a report on student well-being. You need to describe:

1. **Typical sleep patterns** (which statistic and why?)
2. **Study hour distribution** (show a visualization)
3. **Relationship between exercise and stress** (compare groups)

{{2}}
**Work with your partner to:**
- Choose appropriate statistics
- Create 1-2 visualizations
- Write 2-3 sentences interpreting your findings

{{3}}
**Presentation:** Share your findings with another pair. Practice explaining like you're talking to someone who doesn't know statistics!

---

### Sample Student Response

{{1}}
**Example findings:**

"Students sleep an average of 6.5 hours per night (SD=1.2), though the median is slightly higher at 6.8 hours, suggesting a few students getting very little sleep are pulling the average down. The histogram shows most students cluster around 6-7 hours, with a couple outliers sleeping only 4-5 hours.

Study hours show a right-skewed distribution—most students study 10-15 hours weekly, but some dedicated souls are hitting 25-30 hours. Box plots revealed that students who exercise 'Often' or 'Daily' report lower median stress levels (6) compared to those who exercise 'Rarely' (8)."

{{2}}
**Notice:** They chose appropriate statistics, interpreted in context, and told a clear story. That's the goal! 🎯

---

## Common Pitfalls & How to Fix Them 🛠️

Let me share the mistakes I see EVERY semester (and how to avoid them):

---

### Pitfall #1: Calculating Mean of Ordinal Data

{{1}}
**The Crime:** "The average major is 2.3"

Wait, what? You can't average "Business, Social Sciences, Engineering"!

{{2}}
**The Fix:** Use mode for nominal data, median for ordinal. Save mean for interval/ratio!

---

### Pitfall #2: Ignoring Outliers

{{1}}
**The Crime:** "Average income is $85k" (when one person makes $500k)

{{2}}
**The Fix:** 
- Check for outliers first!
- Report median when outliers exist
- Or report BOTH: "Mean=$85k, but median=$35k, indicating some high earners skewing the distribution"

---

### Pitfall #3: Making Histograms Ugly

{{1}}
**The Crime:** No labels, weird colors, bins too small/large

{{2}}
**The Fix:**
- Always label axes!
- Choose bin sizes that show the pattern clearly
- Keep it simple—not every chart needs to look like a rainbow exploded 🌈

---

### Pitfall #4: Forgetting Units

{{1}}
**The Crime:** "The standard deviation is 5"

Five what? Apples? Points? Hours?

{{2}}
**The Fix:** "The standard deviation is 5 hours" or "SD=5 points"

Context is KING! 👑

---

## Troubleshooting Corner 🔧

**Excel isn't cooperating?**

{{1}}
- Make sure data is in one column
- No empty cells in the middle
- Numbers stored as numbers, not text (look for green triangle)

{{2}}
**Histogram looks weird?**
- Try different bin sizes
- Check for data entry errors (like "99999" for missing data)
- Make sure you selected the right column!

{{3}}
**Can't find the median?**
- Sort data first (makes it easier to check manually)
- Use `=MEDIAN()` for the range
- Remember: if even number of values, average the middle two!

{{4}}
> **Dr. Chen's Wisdom:** Software is great until it isn't. Always do a sanity check—does your answer make sense? If average age is 247, something went wrong! 😄

---

## Wrap-Up & Reflection ✨

**What we practiced today:**
✅ Calculated all major descriptive statistics  
✅ Created histograms to see distributions  
✅ Made box plots to compare groups  
✅ Interpreted real data in context  
✅ Chose appropriate statistics for different data types

{{1}}
**The Big Takeaway:**
Numbers alone don't tell the story—you need to LOOK at the data (visualizations) and INTERPRET in context. That's what makes you a researcher, not just a calculator!

---

### Quick Self-Assessment

How confident do you feel about...

{{1}}
**Calculating descriptive statistics?**

    [(1)] Not confident - need more practice
    [(2)] Somewhat confident - getting there!
    [(3)] Confident - I've got this!
    [(4)] Very confident - bring on more data!

{{2}}
**Creating visualizations?**

    [(1)] Still confused
    [(2)] Can do it with help
    [(3)] Can do it independently
    [(4)] Ready to teach others!

{{3}}
**Interpreting results?**

    [(1)] Struggling
    [(2)] Making progress
    [(3)] Feeling good!
    [(4)] Nailing it!

{{4}}
**Be honest!** If you're at 1-2, that's okay! That's why we practice. Come to office hours, we'll work through more examples together! 💪

---

## Next Steps & Resources 🚀

**Want more practice?**

{{1}}
**Datasets available for self-study:**
1. World Happiness Report data
2. Olympic athlete statistics  
3. Movie ratings and box office
4. Climate data by city

{{2}}
**Online tools for practice:**
- Google Sheets (free Excel alternative)
- Seeing Theory (interactive stats visualizations)
- Real Statistics Using Excel (free add-in)

{{3}}
**Challenge yourself:**
Find a dataset that interests YOU (sports, music, gaming, whatever!) and practice describing it. Make it fun! The best way to learn statistics is to apply it to something you actually care about. 🎮📚🎵

---

## Your Homework 📝

**Optional but recommended:**

{{1}}
1. **Find one news article** that uses statistics. What statistics did they report? Did they choose appropriately? What's missing?

2. **Practice with your own data:** Track something for a week (sleep hours, coffee cups, screen time) and describe it with stats + visualization.

3. **Help a friend:** Explain mean, median, and mode to someone who wasn't in class. Teaching = deepest learning!

{{2}}
> **Dr. Chen's Promise:** If you do these three things, statistics will start making sense in a way that lectures alone never could. You've got this! 🌟

---

## Final Thoughts 💭

{{1}}
You did it! You survived descriptive statistics and lived to tell the tale! 🎉

{{2}}
**Remember:**
- Statistics is a SKILL, not a talent. You get better with practice.
- Mistakes are your best teachers (trust me, I've made them all!)
- Every expert was once a beginner who didn't give up.

{{3}}
**Questions? Confusions? Cool discoveries?**  
Hit me up in office hours, via email, or catch me after class. I LOVE talking about this stuff (yes, I'm a stats nerd, and I own it)!

{{4}}
Now go forth and describe some data! You're officially a data detective! 🔍📊✨

---

## Dataset & Materials 📦

**Included files:**
- `student_wellbeing_data.csv` - Main dataset
- `exercise_worksheet.pdf` - Guided questions
- `answer_key.pdf` - Solutions (instructor copy)
- `quick_reference_sheet.pdf` - Formulas and tips
- `sample_visualizations.pdf` - Examples of good charts

{{1}}
**Software tutorials:**
- Excel Quick Start Guide
- R for Beginners Cheat Sheet
- Python/Pandas Basics
- SPSS Step-by-Step

{{2}}
**Additional Resources:**
- Agresti & Finlay Chapter 2 (descriptive stats)
- Field Chapter 5 (visualizations)
- Khan Academy: Describing Data module
- YouTube: StatQuest (seriously, these videos are gold!)

---

## Thank You! 🙏

You all did amazing work today! I saw great collaboration, creative problem-solving, and genuine curiosity. That's what learning looks like!

{{1}}
Keep being curious. Keep asking "why?" Keep playing with data.

{{2}}
And remember: behind every number is a story. Your job as a researcher is to tell that story clearly, honestly, and compellingly.

{{3}}
See you next time! Stay stats-tastic! 📈✨

*- Dr. Sarah Chen*

{{4}}
P.S. If you created an especially beautiful visualization today, send it my way—I love seeing your work! 📊❤️
