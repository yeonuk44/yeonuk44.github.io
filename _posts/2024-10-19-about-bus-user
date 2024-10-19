---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Bus_User
title: 2019 Kakao Developer Winter Internship Problem, Bad User (with.Java)
# title: 2019 Kakao Developer Winter Internship Problem, Bad User (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-19 09:00:00 +0900
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

## This is an article about the 2019 Kakao Developer Winter Internship Problem and Bad User (with.Java).

I want to solve the coding test problem, find out how to solve it differently from the retrospective of the problem I solved, and get to know.

Let's get to the problem first.

{:data-align="center"}

<!-- outline-end -->

### Problem

Muji, who is in charge of event development within the development team, found applicants who tried to win the recently held Kakao Emoticon event in an abnormal way.

We would like to gather these applicants separately, make a list under the name of bad users, and pass it on to "Prodo," the person in charge of the event winner, so that they will be excluded from the winning process.

At this time, some characters of the user ID were covered with '\*' characters to protect personal information.

One '_' character was used for the character you want to cover and at least one '_' character per ID was used.

"Muji" and "Prodo" decided to call the applicant ID mapped to the bad user list as the sanction ID.

For example, if the list of all users who have applied for the event is as follows

Applicant ID

- frodo
- fradi
- crodo
- abc123
- frodoc

If a list of bad user IDs is delivered as follows,

a bad user

- fr*d*
- abc1\*\*
- The list of sanction IDs that should be mapped to rogue users and excluded from the jackpot can be two cases.

Sanctions ID

- frodo
- abc123
- Sanctions ID
- fradi
- abc123

When the array user_id containing the event applicant ID list and the array banned_id containing the bad user ID list are given as parameters, complete the solution function so that the list of sanctioned IDs to be excluded from the win can be returned in how many cases.

#### Restrictions

- The size of the user_id array is 1 or more and 8 or less.
- user_id Array Each element's value is a string with a length of 1 or more and 8 or less.
- The applied user IDs do not overlap each other.
- The applied user ID consists of only alphabetic lowercase letters and numbers.
- The size of the banned_id array is no larger than or equal to the size of the user_id array at least one.
- Banned_id Array Each element's value is a string with a length of 1 or more and 8 or less.
- Bad user ID consists only of alphabetic lowercase letters, numbers, and letters '\*' to hide.
- Bad User ID contains one or more '\*' characters.
- One defective user ID corresponds to one of the applicant IDs, and the same applicant ID is not duplicated and does not enter the sanction ID list.
- When you obtain the sanctions ID lists, if the contents of the ID list are the same regardless of the order in which the IDs are listed, you can process them as the same and count them as one.

#### Input/output Examples

| user_id                                         | banned_id                              | result |
| ----------------------------------------------- | -------------------------------------- | ------ |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["fr*d*", "abc1**"]                    | 2      |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["*rodo", "*rodo", "******"]           | 2      |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["fr*d*", "*rodo", "******", "******"] | 3      |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### Problem solving

```java
import java.util.HashSet;
class Solution {
    HashSet<HashSet<String>> large_storage = new HashSet<>();
    HashSet<String> small_storage = new HashSet<>();

    public int solution(String[] user_id, String[] banned_id) {

        explor(0, small_storage, user_id, banned_id);

        return large_storage.size();
    }

    public void explor(int len, HashSet<String> small_storage, String[] user, String[] ban_user){
        if(ban_user.length == len){
            large_storage.add(new HashSet<>(small_storage));
        }else{
            for(int i = 0; i < user.length; i++){
                if(small_storage.contains(user[i])){
                    continue;
                }

                if(filter(user[i], ban_user[len])){
                    small_storage.add(user[i]);
                    explor(len + 1, small_storage, user, ban_user);
                    small_storage.remove(user[i]);
                }
            }
        }
    }
    public boolean filter(String user_str, String ban_user_str){
        boolean result = true;
        if(user_str.length() != ban_user_str.length()){
            return false;
        }
        for(int i = 0; i < user_str.length(); i++){
            if(ban_user_str.charAt(i) != '*' && user_str.charAt(i) != ban_user_str.charAt(i)){
                result = false;
                break;
            }
        }
        return result;
    }
}
```

#### Solution Description

The problem of finding a list of sanction IDs can be solved by using recursive and hash sets.

In this problem, the goal is to store the sanctions list without duplication, and to find all possible combinations.

First, define two hash sets with class variables.

large_storage is a large repository for storing final sanctions lists.

Small_storage is a temporary repository that stores a list of sanctions that you are currently exploring.

The solution method takes the user ID and sanction ID array as input and returns the number of sanctions lists.

This method initiates a search by invoking a recursive function expander.

The exporter method receives the current discovery depth len and temporary storage small_storage, user ID array user, and sanction ID array ban_user as parameters.

If the navigation depth is equal to the length of the resource ID array, add a copy of the current temporary repository to the larger repository.

Otherwise, it traverses the array of user IDs, skips the IDs already included in the temporary storage, adds the IDs that pass through the filter to the temporary storage, and proceeds with a recursive call.

When the recursive call ends, the current ID is removed from the temporary repository to restore the status.

The filter method compares the given user ID with the sanction ID to verify that the filter conditions are met.

First, if the lengths of the two strings are different, it returns false.

It then compares each character and returns false if the sanction ID has a non \* character and that character is different from the same location character in the user ID.

Returns true if all conditions are met.

This approach can efficiently navigate and store sanctions lists.

Use HashSet to dedupe, find all possible combinations through recursive calls.

In particular, use new HashSet<> (small_storage) to create a copy of the current temporary repository to keep it independent on recursive calls.

This allows you to accurately calculate the number of sanctions lists required by the problem

I learned something while solving it, so I'd like to share it.

The first code you solved

```java
import java.util.HashSet;

class Solution {
    HashSet<HashSet<String>> large_storage = new HashSet<>();
    String[] user;
    String[] ban_user;

    public int solution(String[] user_id, String[] banned_id) {
        user = user_id;
        ban_user = banned_id;
        HashSet<String> small_storage = new HashSet<>();

        explor(0, small_storage);

        return large_storage.size();
    }

    public void explor(int len, HashSet<String> small_storage){
        if(ban_user.length == len){
            large_storage.add(small_storage);
            return;
        }

        for(int i = 0; i < user.length; i++){
            if(small_storage.contains(user[i])){
                continue;
            }

            if(filter(user[i], ban_user[len])){
                small_storage.add(user[i]);
                explor(len + 1, small_storage);
                small_storage.clear();
            }
        }
    }
    public boolean filter(String user_str, String ban_user_str){
        boolean result = true;
        if(user_str.length() != ban_user_str.length()){
            return false;
        }
        for(int i = 0; i < user_str.length(); i++){
            if(ban_user_str.charAt(i) != '*' && user_str.charAt(i) != ban_user_str.charAt(i)){
                result = false;
                break;
            }
        }
        return result;
    }
}
```

The code did not pass, there were 2 reasons.

1. Problems arising from the nature of HashSet

The problem is that the exporter function adds the user ID to the small storage (small_storage) and then initializes the small storage again (clear()) after a recursive call.

Clearing the HashSet will cause the HashSet that is already saved before the end of the current recursive call to disappear.

Because HashSet is a reference type, calling clear() will cause the data to disappear from all references.

2. Do not copy HashSet

There is a problem with handing over small_storage directly to a recursive call and initializing the entire storage while calling clear.

You must hand over the newly copied HashSet to a recursive call, such as new HashSet<> (small_storage).

Let me take a closer look at it!

Addressing the nature of HashSet and the health management issues in recursive calls was key.

- Characteristics of HashSet
  HashSet is one of Java's collection frameworks, used to store data that does not allow duplication.

Importantly, because HashSet is a reference type, it does not copy itself when it is assigned to other variables or passed as a method factor, but rather conveys references to the same object.

- the cause of the problem
  There was a problem with the existing code passing small_storage to the recursive function expander and calling small_storage.clear() from within.

Because calling clear() removes data from everywhere small_storage references it, the already saved state disappears before the recursive call ends.

- Workaround
  To ensure that each recursive call has an independent state, a copy of the small_storage was made using new HashSet<> (small_storage) and passed to the recursive call.

This way, each recursive call will have its own HashSet, and will not affect the other calls.

##### Conclusion

Use copy: use new HashSet<> (small_storage) to copy the current state of small_storage and forward it to a recursive call. This ensures that each recursive call has an independent HashSet, which does not affect the other calls.
Restoring to its original state: When the recursive call ends, call small_storage.remove (user[i]) to return small_storage to its previous state. This ensures that small_storage remains in the correct state on the parent call.
Thank you!
