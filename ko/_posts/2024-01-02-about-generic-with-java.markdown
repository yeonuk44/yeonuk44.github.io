---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Generic
title: Generic에 대해서(with. Java)
# title: About Generic (with. Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-02 09:00:00 +0900
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

## "Generic에 대해서" 문제에 대하여 알아본 글입니다.

다른 분들의 작업물을 구경하던 중 <T> 타입에 대해서 보게 되었습니다.

학부생 시절 정적언어(Java, C 등)을 학습하며 봤던 기억이 있습니다.

시간이 흘러 다시 한 번 제대로 알아보아 공유하고자 합니다.

{:data-align="center"}

<!-- outline-end -->

### 개념

제네릭(Generic)은 자바 프로그래밍 언어의 중요한 특징 중 하나입니다.

이는 클래스나 메서드를 정의할 때 타입을 파라미터화하는 기능을 제공합니다.

제네릭을 사용하면 클래스나 메서드를 선언할 때 타입을 지정하지 않고, 사용할 때 구체적인 타입을 지정할 수 있습니다.

이를 통해 코드의 재사용성과 타입 안정성을 높일 수 있습니다.

### 제네릭의 기본 구조

자바에서 제네릭을 사용하려면 클래스, 인터페이스, 메서드를 정의할 때 타입 매개변수를 사용합니다.

타입 매개변수는 데이터 타입의 일종으로, 실제 사용될 때 구체적인 타입으로 대체됩니다.

1. 클래스에서 제네릭 사용

```java
public class Box<T> {
    private T data;

    public void setData(T data) {
        this.data = data;
    }

    public T getData() {
        return data;
    }
}
```

위의 예제에서 Box 클래스는 제네릭을 사용하여 데이터를 담는 상자를 표현합니다.

T는 타입 매개변수로, 클래스를 실제로 사용할 때 어떤 타입의 데이터를 다룰 것인지를 나타냅니다.

2. 메서드에서 제네릭 사용

```java
public <T> T findFirst(List<T> list) {
    if (list != null && !list.isEmpty()) {
        return list.get(0);
    }
    return null;
}
```

위의 예제에서 findFirst 메서드는 제네릭을 사용하여 리스트의 첫 번째 요소를 반환합니다.

메서드 선언에서 <T>는 해당 메서드가 제네릭 타입을 사용한다는 것을 나타냅니다.

#### 제네릭의 장점

타입 안정성(Type Safety): 제네릭을 사용하면 컴파일러가 코드에서 타입 관련 오류를 잡아내기 쉬워집니다. 런타임 시점에 발생할 수 있는 타입 변환 오류를 컴파일 시점에 잡을 수 있습니다.

코드 재사용성: 제네릭을 사용하면 하나의 클래스나 메서드를 여러 종류의 타입에 대해 사용할 수 있습니다. 코드의 재사용성이 높아집니다.

알고리즘의 일반화: 제네릭을 통해 알고리즘을 더 일반적으로 작성할 수 있습니다. 특정 타입에 의존하지 않고 다양한 타입에서 사용할 수 있는 알고리즘을 작성할 수 있습니다.

#### 제네릭의 예제

```java
public class Main {
    public static void main(String[] args) {
        // Box 클래스를 활용한 제네릭 예제
        Box<String> stringBox = new Box<>();
        stringBox.setData("Hello, Generics!");
        String data = stringBox.getData();
        System.out.println(data);

        // 제네릭 메서드를 활용한 예제
        List<Integer> integerList = List.of(1, 2, 3, 4, 5);
        Integer firstElement = findFirst(integerList);
        System.out.println("First element: " + firstElement);
    }

    public static <T> T findFirst(List<T> list) {
        if (list != null && !list.isEmpty()) {
            return list.get(0);
        }
        return null;
    }
}
```

위의 예제에서 Box 클래스를 통해 문자열 데이터를 담은 상자를 만들고, findFirst 메서드를 통해 정수 리스트의 첫 번째 요소를 찾습니다.

이러한 예제를 통해 제네릭이 어떻게 사용되는지 감을 잡을 수 있습니다.

### 결론

제네릭은 자바에서 강력한 기능 중 하나로, 코드의 재사용성과 타입 안정성을 높여줍니다.

클래스, 인터페이스, 메서드를 정의할 때 타입을 파라미터화하여 다양한 타입에 대해 유연하게 대처할 수 있습니다.

제네릭을 활용하면 컴파일러가 더 많은 오류를 사전에 검출할 수 있으며, 코드의 일반성과 확장성을 증가시킬 수 있습니다.

자바 프로그래머들은 제네릭을 적절히 활용하여 더 간결하고 안정적인 코드를 작성할 수 있습니다.
