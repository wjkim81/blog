---
layout: post
title: "I Over-Engineered My Blog and All I Got Was This Lesson"
date: 2025-11-28
published: true
categories: [Reflection, Blogging]
tags: [Writing, Productivity, Jekyll, DeveloperLife]
permalink: /execution-over-perfection/
---

*Why I'm finally writing 10 years later using GitHub Pages instead of Django*

# **"I Over-Engineered My Blog and All I Got Was This Lesson"**

---

## **The 2015 Plan: "I'll Build My Own Blog!"**

**Me in 2015:**
"I'm going to build the PERFECT blog system!"

**My grand vision:**
- Custom Django backend ✨
- Beautiful frontend design ✨
- User authentication system ✨
- Comment management ✨
- Tag system ✨
- Search functionality ✨
- Admin dashboard ✨
- RSS feed generator ✨
- SEO optimization ✨
- Image upload system ✨

**Time allocated for building:** 6 months  
**Time allocated for writing:** "After it's done!"

---

## **What Actually Happened**

### **Month 1-2: Database Design**
```python
class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    author = models.ForeignKey(User, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
    tags = models.ManyToManyField(Tag)
    category = models.ForeignKey(Category)
    # ... 50 more lines of "perfect" schema
```

**Articles written:** 0

---

### **Month 3: Authentication Hell**
```python
# Spent weeks on:
- User registration
- Email verification
- Password reset
- Social login (never finished)
- Session management
- CSRF protection
```

**Articles written:** Still 0

---

### **Month 4: Frontend Struggles**
```javascript
// Learning:
- jQuery (it was 2015!)
- Bootstrap customization
- Responsive design
- Cross-browser compatibility
- Image optimization
```

**Articles written:** You guessed it, 0

---

### **Month 5-6: "Almost Done!"**
```python
# Still working on:
- Comment spam prevention
- Markdown rendering
- Syntax highlighting
- SEO meta tags
- Sitemap generation
- Cache optimization
```

**Articles written:** ZERO 😭

---

## **The Final Result**

**After 6 months:**
- ✅ Learned Django
- ✅ Learned web development
- ✅ Learned frontend basics
- ✅ Learned deployment
- ❌ Wrote ZERO articles
- ❌ Had ZERO readers
- ❌ Achieved ZERO of original goal

---

## **Fast Forward to 2025**

**My colleague last week:**
"You're starting a blog? Why don't you use Django?"

**Me:**
"ABSOLUTELY NOT."

**Colleague:**
"But you know Django!"

**Me:**
"EXACTLY WHY I'M NOT USING IT."

---

## **The 2025 Plan: Keep It Stupid Simple**

### **My new tech stack:**
```yaml
Platform: GitHub Pages
Generator: Jekyll
Theme: Minima (default)
Customization: None (yet)
Time to setup: 1 hour
Time to first post: Same day
```

---

## **What I Learned After 10 Years**

### **Lesson 1: The Best Blog System is The One You Actually Write On**

**2015 me:** 
"I need the perfect system before I can write!"

**2025 me:** 
"I need to write. The system doesn't matter."

---

### **Lesson 2: Building ≠ Blogging**

**Building a blog system:**
- Feels productive
- Is actually procrastination
- Teaches tech skills
- Produces zero content

**Actually blogging:**
- Feels scary
- Is actually productive
- Teaches writing skills
- Produces real value

---

### **Lesson 3: "I'll Write After I Build" is a Lie**

**The truth:**
Building becomes the goal.
Writing becomes "later."
Later never comes.

**What actually works:**
Write first.
Build if needed.
(Spoiler: It's never needed.)

---

### **Lesson 4: Your Readers Don't Care About Your Stack**

**What readers want:**
- Good content
- Clear writing
- Useful insights

**What readers don't care about:**
- Whether you built it yourself
- What framework you used
- How "custom" your design is
- Your deployment pipeline

---

### **Lesson 5: Done > Perfect**

**2015:**
"I can't publish until everything is perfect!"

**2025:**
"I'll publish and fix typos later."

**Result:**
- 2015: 0 articles, perfect system
- 2025: 5 articles in one week, default theme

**Which one is more valuable?** 🤔

---

## **The Comparison**

| 2015 Custom Blog             | 2025 GitHub Pages           |
| ---------------------------- | --------------------------- |
| 6 months to build            | 1 hour to setup             |
| 0 articles written           | 5 articles in one week      |
| Perfect custom design        | Default Minima theme        |
| Complex deployment           | `git push`                  |
| Database to maintain         | Static files, zero db       |
| Server costs                 | $0 (free)                   |
| SSL certificate hassle       | Automatic HTTPS             |
| "I'll write soon!"           | Actually writing            |
| Felt like accomplishment     | **Actually accomplished**   |

---

## **What I Would Tell 2015 Me**

**Dear Past Me,**

Stop.

Just stop building.

Use WordPress.
Use Medium.
Use Blogger.
Use literally anything that lets you write TODAY.

The blog system is NOT the product.
The writing is the product.

You're going to spend 6 months building,
write zero articles,
and abandon the whole thing.

Then 10 years later you'll use Jekyll
and wish you had just done that from the start.

Love,
**2025 Me**

P.S. - You were right about one thing though:
Building the blog DID teach you web development.
So it wasn't completely wasted.
Just... 99% wasted.

---

## **The Happy Ending**

**2025:**
- Set up blog: 1 hour ✅
- Write first post: Same day ✅
- Publish second post: Next day ✅
- Five posts: One week ✅
- Custom features: Zero ✅
- Regrets: None ✅

**Turns out:**
The simplest solution was the best solution all along.

---

## **For Everyone Building "The Perfect Blog System" Right Now**

**Stop.**

**Just:**
1. Pick any platform (Jekyll, Hugo, Ghost, Medium, WordPress, anything)
2. Use the default theme
3. Write ONE post
4. Publish it
5. Repeat

**Customize later.**
**Build features later.**
**Obsess over design later.**

**But WRITE NOW.**

Because in 10 years,
you won't remember what framework you used.

You WILL remember whether you actually created something.

---

## **P.S. - Was It Really Wasted?**

**Honestly?**

Those 6 months taught me:
- Django framework
- Frontend basics
- Deployment
- Web architecture

**That knowledge shaped my technology insight.**

So no, it wasn't wasted.

**But:**
I could have learned Django by building something people actually used.
Instead of building something nobody ever saw.

**The lesson:**
Learn by building things that SHIP.
Not things that stay in "almost done" forever.

---

## **The End (Finally)**

**2015:** Built a blog, wrote nothing  
**2025:** Used GitHub Pages, actually writing

**Moral of the story:**
Sometimes the best technology choice is the boring one.

**Now excuse me while I go write my 6th article this week.**

*(On a site I set up in an hour using default Jekyll.)*

**🎉 THE END 🎉**

---

---

### 🔍 Ready to Dive Into the Series?

If you're curious how “execution over perfection” applies to building modern AI teams, start here:

👉 **Unicorn Series · Part 1 — _From Handsome Horses to Actual Unicorns_**  
(Why companies search for AI experts who mathematically cannot exist.)

**Read Part 1 →** [From Handsome Horses to Actual Unicorns](https://www.wjkim.com/unicorn-series/part-1/)

---

# 🇰🇷 **실행이 완벽함을 이긴다: 유니콘 시리즈에 앞서 남기는 작은 이야기**

*나는 10년 만에 Django가 아닌 GitHub Pages로 글을 쓴다:*
*블로그 시스템을 만드는데 6개월, 글 쓰는 데 0초*

---

## **유니콘 시리즈를 시작하며: 복잡함보다 단순함이 이기는 순간들**

요즘 기술 글을 쓰면서, 또 여러 프로젝트를 설계하면서
가끔씩 드는 생각 한가지

**“완벽함을 추구하기보다, 실행이 중요할 때가 많다.”**

특히나 요즘 같이 기술이 빠르게 바뀌는 시대에서는 
생각만 하다 보면 실행하지 못하고 지나가는 경우가 수두룩 하다.

그래서 이번에 블로그를 만들면서 완벽보다 글쓰는 것에 초점을 맞추기로 했다.

그리고 이런 생각도 AI 개발과 연결될 수도 있기에 
지난 번 쓰기 시작한 시리즈도 보면 좋을 듯.

👉 **Unicorn Series · Part 1 — *From Handsome Horses to Actual Unicorns***
(기업들이 왜 ‘존재할 수 없는’ AI 전문가를 찾고 있는지 설명한 글)

총 4 파트로 써는데 중간 중간 다른 글도 올리려고 한다.

---

## **2015년의 나: “직접 블로그를 만들어야지!”**

**2015년의 나:**
블로그를 내가 직접 기술을 익혀서 하나하나 다 만들겠다!”

**그때 내가 꿈꾼 블로그:**

* 커스텀 Django 백엔드 ✨
* 아름다운 프론트엔드 ✨
* 회원 가입/로그인/권한 시스템 ✨
* 댓글 시스템 ✨
* 태그/카테고리 ✨
* 검색 기능 ✨
* 관리자 페이지 ✨
* RSS 생성 ✨
* SEO 최적화 ✨
* 이미지 업로드 ✨

**개발 기간 목표:** 6개월
**글쓰기 기간 목표:** “우선 기술적으로 이해하자!”

---

## **실제로 있었던 일…**

### **1–2개월 차: DB 스키마 만들기**

```python
class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    author = models.ForeignKey(User)
    created_at = DateTimeField(auto_now_add=True)
    updated_at = DateTimeField(auto_now=True)
    tags = ManyToManyField(Tag)
    category = ForeignKey(Category)
    # ... 이하 50줄
```

**작성한 글:** 0편

---

### **3개월 차: 인증 지옥**

* 회원가입
* 이메일 인증
* 패스워드 초기화
* 소셜 로그인 (미완성)
* 세션 관리
* CSRF 처리

**작성한 글:** 여전히 0편

---

### **4개월 차: 프론트엔드와의 전쟁**

* jQuery (2015년이었다…)
* Bootstrap 커스터마이징
* 반응형 디자인
* 브라우저 호환성
* 이미지 최적화

**작성한 글:** 0편

---

### **5–6개월 차: “거의 다 왔다!”**

* 댓글 스팸 방지
* Markdown 렌더링
* 코드 하이라이트
* SEO 태그
* sitemap 생성
* 캐시 최적화

**작성한 글:** 0편 😭

---

## **결과**

6개월 후:

* ✔ Django 배움
* ✔ 웹 개발 배움
* ✔ 프론트엔드 기초 익힘
* ✔ 배포 경험
* ❌ 작성한 글: 0
* ❌ 방문자: 0
* ❌ 달성 목표: 0

---

## **2025년의 나**

**동료:**
“블로그 만든다고? Django 쓰면 되지 않나?”

**나:**
“엥? 싫은데?”

**동료:**
“기술자잖아?”

**나:**
“해봐서 쓰면 안 되는 거 안다.”

---

## **2025년 계획: 무조건 단순하게**

```yaml
플랫폼: GitHub Pages
정적 생성기: Jekyll
테마: Minima (기본)
커스터마이징: 없음
설치 시간: 1시간
첫 글 작성: 당일
```

---

## **10년 만에 배운 교훈**

### **교훈 1: 블로그는 기술을 익히려고 하는게 아니라 ‘글 쓰는 것’이 중요하다**

**2015년의 나:**
“엔지니어니까 기술을 알고 직접 구현한 다음에 글을 쓸 수 있어!”

**2025년의 나:**
“글 쓰는 게 중요하다. 굳이 기술 알고 싶지 않다.”

---

### **교훈 2: ‘만드는 것’과 ‘쓰는 것’은 전혀 다르다**

**블로그 시스템 개발:**

* 겉보기엔 생산적
* 실제로는 미뤄두기의 형태
* 기술은 배우지만
* 콘텐츠는 0

**실제로 쓰는 것:**

* 겉보기엔 부담됨
* 실제로는 제대로 생산적
* 글쓰기 스킬 증가
* 무언가 남음

---

### **교훈 3: “다 만들고 쓸게”는 거짓말이다**

시스템을 만들기 시작하는 순간
목표는 ‘만들기’가 되어버렸다.

‘쓰기는 나중에’
그리고 그‘나중’은 절대 오지 않았다는 것.

---

### **교훈 4: 글 읽는 사람은 사실 당신의 기술 스택에 관심 없다**

독자가 원하는 것은:

* 좋은 내용
* 명확한 문장
* 전달되는 인사이트

독자가 **관심 없는 것**:

* 당신이 Django로 만들었는지
* Jekyll인지 Hugo인지
* 배포 파이프라인
* CSS 커스터마이징

---

### **교훈 5: 완벽보다 실제 쓰는게 증요하다**

**2015년:**
“완벽해야 공개할 수 있어!”

**2025년:**
“공개 먼저, 수정은 나중에.”

그래서 지금은?

* 2015년: 절대 완벽할 수 없지만 애써 직접 만든 시스템 + 글 0
* 2025년: 기본 테마 + 일주일 5편 작성

당연히 가치는 2025년의 현재 모습이다.

---

### **비교 요약**

| 2015년 커스텀 블로그 | 2025년 GitHub Pages |
| ------------- | ------------------ |
| 제작 6개월        | 셋업 1시간             |
| 작성 글 0편       | 일주일 5편             |
| 완벽한 디자인       | 기본 테마              |
| 복잡한 배포        | `git push`         |
| DB 관리 필요      | 정적 파일              |
| 서버 비용 있음      | 무료                 |
| SSL 처리해야 함    | 자동 HTTPS           |
| “곧 쓸게요!”      | 실제로 씀              |
| 형식적 성취감       | **실질적 성취**         |

---

## **2015년의 나에게 보내는 편지**

**과거의 나에게,**

삽질... 그만!

그냥 
WordPress나 Medium, Blogger 중 아무거나 쓰자.
그리고 글도 좀 쓰자.

너의 목표는 사실 블로그 글이였지
기술이 아니였는데.

그 블로그 6개월 동안 만들고,
번아웃해서 글 하나도 안 쓰고,
그냥 버리더라

10년 후에는 기술 스택도 까먹고,
가장 간단한 Jekyll을 쓰게 됐어
그때도 알았으면 좋았을 걸.

“아… 그냥 기존 솔루션 있는 거 사용할 걸.”

— 2025년의 나

P.S:
그래도 사실 블로그 만든 6개월이 완전한 낭비는 아니었다.
웹 개발을 배우긴 했으니까.
다만 볼질을 생각하면 99%는 낭비.

---

## **해피 엔딩**

2025년:

* 블로그 셋업: 1시간
* 첫 글 작성: 당일
* 두 번째 글: 다음 날
* 일주일 5편
* 커스터마이징: 없음
* 후회: 없음

결국 가장 단순한 방법이 가장 좋은 방법이었다.

---

## **지금 ‘완벽한 블로그 시스템’을 만들고 있는 모든 사람들에게**

**무엇이 중요한지 한번 고민하자.**

기술을 배우고 싶어서 구축하는 건지.
블로그에서 글을 쓰고 싶은 건지.

만약 블로그 글 쓰는게 중요하면:

1. 플랫폼 아무거나 고르고 (Jekyll, Hugo, Ghost, WordPress…)
2. 기본 테마 그대로 쓰고
3. 글 하나 쓰고
4. 바로 공개하고
5. 반복

커스터마이징은 나중에 해도 되지만,
**지금은 글을 쓰는 것이 먼저다.**

10년 후 기억하는 것은
프레임워크가 아니라
**당신이 실제 하고자 했던 일을 했는지가 더 중요**하더라.

---

## **다행인 건 정말 낭비였을까?**

사실 Django를 만들며 배운 것들:

* 웹 프레임워크
* 프론트엔드 기초
* 배포
* 아키텍처

웹 어플리케이션에 대헌 이해를 처음으로 하게 해준 경험이다.

그래서 솔직히 도움은 많이 됐다.
하지만…

그 시간에 실제로 내가 원했던 
글을 썼으면 더 좋았을 것 같다.

**“원래 내가 목표했던 걸 이룩하는게 더 가치 있으니까.**

---

## **마무리!**

**2015:** 블로그 만들고 글 0
**2025:** Jekyll로 세팅하고 글 실제로 작성

**교훈:**
때론 가장 ‘간단한 기술 선택’이 가장 현명한 선택이다.

이제 다음 글을 쓰러 간다.
*(그리고 이 사이트는 내가 기본 Jekyll 테마로 1시간 만에 만든 사이트다.)*

🎉 **끝** 🎉
