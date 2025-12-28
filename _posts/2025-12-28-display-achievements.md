---
layout: post
title: Display Achievements
date: 2025-12-28 07:00:00 -0200
categories: [devlog]
---

Now that we can display each data point that is provided by the Bosch EUDA API it's time to think about additional features on top of that.

As a starting point let's [calculate and display achievements](https://github.com/open-ebike/open-ebike-frontend/issues/36) a user can unlock by riding their eBike.

To do so we need to

* [add function to fetch all activities recursively](https://github.com/open-ebike/open-ebike-frontend/commit/1c3ce1449ffae742cac573418a4de7cbe203a4a9) to be able to bypass the paging mechanism of the EUDA API
* [add an achievement service](https://github.com/open-ebike/open-ebike-frontend/commit/b16b0b259f63275c10cf1c273aa000ad89d30334) that calculates achievements based on the fetched activities
* [add an achievement page](https://github.com/open-ebike/open-ebike-frontend/commit/3d6b61bee04b0f39490a47d6b7cfd52d33855cb7) that displays the unlocked achievements

Some sample achievements can be based on 
* [completed activities](https://github.com/open-ebike/open-ebike-frontend/commit/b9f434153d10c7d5b8434456458c29d39140641b), e.g. first ride, 10 rides, 100 rides
* [completed distance](https://github.com/open-ebike/open-ebike-frontend/commit/1936df68b8bf846e14c99bd60dc22421992d6ab7)
* [elevation gain](https://github.com/open-ebike/open-ebike-frontend/commit/bf8956ec8af4f9f0f1fe8ca9021c6faac3a10149)
* [real world distances](https://github.com/open-ebike/open-ebike-frontend/commit/d2b8f06d195ba0326096d16164be5f64d886804f), e.g. distance around the world
* [registrations of eBikes and components](https://github.com/open-ebike/open-ebike-frontend/commit/d5da239238aaca9bc9f70637560aaead0b81d608)
* [bicycle race distances](https://github.com/open-ebike/open-ebike-frontend/commit/a4b7ba222bc2398622b72732d4826684da1f77fe), e.g. Tour de France
* [battery charge cycles](https://github.com/open-ebike/open-ebike-frontend/commit/1260045fbd07985172476ad0496fabb662eaed03)
* [bike pass](https://github.com/open-ebike/open-ebike-frontend/commit/bc327111d1d4996f483e271547a5597cf4fdd547)
* [times of the day](https://github.com/open-ebike/open-ebike-frontend/commit/504831880d58e18a39e206ef50458be7ee77fc63), e.g. early bird and night owl

To motivate users to ride across the country we add achievements based on regions they have used their bikes in.
To do so we 

* [add a region finder service](https://github.com/open-ebike/open-ebike-frontend/commit/7e1b1e326bcbea4474831fe232126e1af2e47f43) to identify the German federal state of a given GPS coordinate
* add some sample achievements [based on visited German federal states](https://github.com/open-ebike/open-ebike-frontend/commit/23d33054828f56a998cab6a2a1b00aa46bc28250)

To motivate the users to rider continuously over the year we add achievements based on monthly riding activity.
To do so we add achievements
* [based on time periods](https://github.com/open-ebike/open-ebike-frontend/commit/827e725e34fdbdbddb0bb1872cfd962c9965bb7b)

On the achievements page we display all available achievements, but initially we keep their names hidden.
Unlocked ones are highlighted and their name is revealed. 

![web-app-achievements.png](/assets/2025-12-28/web-app-achievements.png)

---

In [the next post](https://open-ebike.github.io/devlog/2025/12/29/add-social-sharing.html) we will add an option to share unlocked achievements for example in social media or messenger apps.
