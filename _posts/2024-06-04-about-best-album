---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Best_Album
title: Best Album (with.Java)
# title: Best Album (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, hash]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-06-04 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## This article looks into the “Best Album (with.Java)” issue.

As I solve coding test problems, I look back on the problems I solved and look into different solution methods to learn more.

Let's look at the problem first.

{:data-align="center"}

<!-- outline-end -->

### problem

The streaming site is planning to release a best album by collecting the two most played songs from each genre.

Songs are classified by unique numbers, and the criteria for including songs are as follows.

- Genres with the most played songs are listed first.
- The most played songs within the genre are listed first.
- Among songs with the same number of plays within a genre, songs with lower unique numbers are included first.
- Given the string array genres representing the genre of the song and the integer array plays representing the number of plays for each song, complete the solution function to return the unique numbers of the songs in the best album in order.

#### Restrictions

- genres[i] is the genre of the song with unique number i.
- plays[i] is the number of times the song with unique number i was played.
- Genres and plays have the same length, which must be between 1 and 10,000.
- There are less than 100 genres.
- If there is only one song in the genre, select only one song.
- Every genre has a different number of plays.

#### Input/Output Example

<!--
| lines | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]] | 2 |
| [[-1, 1], [1, 3], [3, 9]] | 0 |
| [[0, 5], [3, 9], [1, 10]] | 8 | -->

| genres                                          | plays                      | return       |
| ----------------------------------------------- | -------------------------- | ------------ |
| ["classic", "pop", "classic", "classic", "pop"] | [500, 600, 150, 800, 2500] | [4, 1, 3, 0] |

### My solution to the problem

```java
import java.util.*;

class Solution {
 public int[] solution(String[] genres, int[] plays) {
 HashMap<String, Integer> map = new HashMap<>();
 for(int i = 0; i < genres.length; i++){
 map.put(genres[i], map.getOrDefault(genres[i], 0) + plays[i]);
 }

 ArrayList<String> arrStringList = new ArrayList<>();
 for(String key : map.keySet()){
 arrStringList.add(key);
 }
 Collections.sort(arrStringList, (key_1, key_2) -> map.get(key_2) - map.get(key_1));

 ArrayList<Integer> arrIntegerList = new ArrayList<>();
 for(int i = 0; i < arrStringList.size(); i++){
 String str = arrStringList.get(i);
 int max = 0;
 int idx_0 = -1;
 for(int j = 0; j < genres.length; j++){
 if(str.equals(genres[j]) && max < plays[j]){
 max = plays[j];
 idx_0 = j;
 }
 }

 max = 0;
 int idx_1 = -1;
 for(int j = 0; j < genres.length; j++){
 if(str.equals(genres[j]) && max < plays[j] && idx_0 != j){
 max = plays[j];
 idx_1 = j;
 }
 }

 arrIntegerList.add(idx_0);
 if(idx_1 > -1){
 arrIntegerList.add(idx_1);
 }
 }

 int[] answer = new int[arrIntegerList.size()];
 for(int i = 0; i < arrIntegerList.size(); i++){
 answer[i] = arrIntegerList.get(i);
 }
 return answer;
 }
}
```

### Solved review

The solution method takes as input two arrays: genres and plays.

The first for loop uses a HashMap<String, Integer> object map to calculate the total number of plays for each genre. Here, key represents the genre and value represents the total number of plays of that genre.

In the second for loop, we add the genres stored in the map to the ArrayList<String> to sort them in descending order according to the number of plays.

For descending sorting, use Collections.sort() and set the sorting criteria using a lambda expression.

The third for loop finds the indices of the most played song and the next most played song for each genre. To do this, we find the index of the most played song and the next most played song for each genre.

Add the index of the most played song for each genre to ArrayList<Integer>, and also add the index of the next most played song.

Finally, we convert ArrayList<Integer> to an array and return the result.
This code solves the problem of finding and returning the indices of the most played song and the next most played song for each genre.
