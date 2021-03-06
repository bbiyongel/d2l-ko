# Introduction
:label:`chapter_introduction`

Until recently, nearly all of the computer programs
that we interacted with every day were coded
by software developers from first principles.
Say that we wanted to write an application to manage an e-commerce platform.
After huddling around a whiteboard for a few hours to ponder the problem,
we would come up with the broad strokes of a working solution
that would probably look something like this:
(i) users would interact with the application
through an interface running in a web browser or mobile application
(ii) our application would rely on a commerical database engine
to keep track of each user's state and maintain records
of all historical transactions
(ii) at the heart of our application, running in parallel across many servers, the *business logic* (you might say, the *brains*)
would map out in methodical details the appropriate action to take
in every conceivable circumstance.

최근까지 우리가 매일 사용하는 거의 모든 컴퓨터 프로그램들은 첫번째 원칙에 입각하여 소프트웨어 개발자에 의해 코드로 만들어졌습니다.
E-커머스(e-commerce)플랫폼을 관리 하는 어플리케이션을 만들려고 한다면, 몇시간의 숙고와 화이트보딩을 통한 후에야, 해결 가능한 방법들을 폭넓게 시도할 생각을 하게 될 겁니다. 그것들은 아마도 다음과 슷할 겁니다.
(i) 사용자는 웹브라우저나 모바일앱을 이용할 것이다.
(ii) 우리의 어플리케이션은 각 유저의 상태, 모든 트랜잭션 기록을 위해 상용 데이터페이스 앤진을 사용할 것이다.
(iii) 병렬로 많은 수의 서버를 통해 동작할 우리 어플리케이션의 핵심 *비즈니스로직*(business logic)은 생각할 수 있는 모든 상황에 대해 체계적으로 세부사항 까지 적절한 액션을 취할 것입니다. (여러분은 아마 *지능*(brain)이라고 부를지 모르겠다.)

To build the *brains* of our application,
we'd have to step through every possible corner case
that we anticipate encountering, devising appropriate rules.
Each time a customer clicks to add an item to their shopping cart,
we add an entry to the shopping cart database table,
associating that user's ID with the requested product’s ID.
While few developers ever get it completely right the first time
(it might take some test runs to work out the kinks),
for the most part, we could write such a program from first principles
and confidently launch it *before ever seeing a real customer*.
Our ability to design automated systems from first principles
that drive functioning products and systems,
often in novel situations, is a remarkable cognitive feat.
And when you're able to devise solutions that work $100\%$ of the time,
*you should not be using machine learning*.

이 어플리케이션의 *지능*(brains)를 만들기 위해, 발생할 수 있는 모든 사항을 대응 할수 있도록 적절한 규칙을 만들어야 합니다.
고객이 매번 하나의 상품을 쇼핑 카트에 넣을 때마다, 우리는 쇼핑키트 데이터 테이블에, 고객의 사용자 ID와 상품ID를 연관시켜야 합니다.
프로그래머들이 처음부터 완벽하게 만들지는 못할 것입니다.
(몇몇의 문제를 풀기위해 몇개의 테스트를 만들어야 할 지도 모릅니다.) 대부분의 경우 *진짜 고객들이 보기 전에* 첫번째원칙에 따라 프로그램을 자신있게 만들수 있습니다. 제일 원칙에따라 자동화된 시스템을 설계할수 있는, 제품과 시스템의 기능을 운영하는 능력은, 종종 새로운 상황에서 주목할 만한 인지 능력 입니다. 
그리고 당신이 $100\%$시간 동안 운영 가능한 솔루션을 고안해 낼수 있수 있다면, *당신은 머신러닝을 사용하지 말아야 합니다*.


Fortunately—for the growing community of ML scientists—many
problems in automation don't bend so easily to human ingenuity.
Imagine huddling around the whiteboard with the smartest minds you know,
but this time you are tackling any of the following problems:

* Write a program that predicts tomorrow's weather given geographic
information, satellite images, and a trailing window of past weather.
* Write a program that takes in a question, expressed in free-form text, and
 answers it correctly.
* Write a program that given an image can identify all the people it contains,
 drawing outlines around each.
* Write a program that presents users with products that they are likely to
  enjoy but unlikely, in the natural course of browsing, to encounter.

다행스럽게도, 성장하는 머신러닝 과학자들의 공동체 덕에, 자동화 과정의 많은 문제들이 너무 쉽게 인간의 독창성에 무릎꿇지 않았습니다. 당신이 갖고 있는 가장 똑똑한 방법으로 화이트보드에 끄적이는 것을 상상해 봅시다, 다만 이번에는 다음과 같은 문제들을 다루고 있습니다.:

* 지정학적 정보, 위성 이미지 그리고 과거 날씨 이력등을 이용하여 내일의 날씨를 예측하는 프로그램 작성
* 자유 형식으로 작성된 질문을 받아, 올바르게 답을 하는 프로그램 작성.
* 주어진 이미지에 포함된 모든 사람들을 식별하고, 각각의 아웃라인을 그리는 프로그램 작성.
* 있을 것 같지는 않지만, 자연스러운 브라우징 중에 겪게될, 그들이 즐길것 같은 제품을 주는 프로그램 작성

In each of these cases, even elite programmers
are incapable of coding up solutions from scratch.
The reasons for this can vary.
Sometimes the program that we are looking for
follows a pattern that changes over time,
and we need our programs to adapt.
In other cases, the relationship
(say between pixels, and abstract categories)
may be too complicated, requiring thousands or millions of computations
that are beyond our conscious understanding
(even if our eyes manage the task effortlessly).
Machine learning (ML) is the study of powerful techniques
that can *learn behavior* from *experience*.
As ML algorithm accumulates more experience,
typically in the form of observational data
or interactions with an environment, their performance improves.
Contrast this with our deterministic e-commerce platform,
which performs according to the same business logic,
no matter how much experience accrues,
until the developers themselves *learn* and decide
that it's time to update the software.
In this book, we will teach you the fundamentals of machine learning,
and focus in particular on deep learning,
a powerful set of techniques driving innovations
in areas as diverse as computer vision, natural language processing,
healthcare, and genomics.

이러한 각각의 경우, 우수한 프로그래머 조차도 처음부터 솔루션을 만들수 없습니다.
그 이유는 매우 다양합니다. 때때로 우리가 찾는 프로그램은 시간이 흐름에 따라 변하는 패턴을 찾아내고, 적응할 수 있어야 합니다. 
다른 한편으로, 픽셀(pixel)과 추상 카테고리 사이의 관계는 너무 복잡하여, 이 관계를 추론하기엔 (우리의 눈이 별다른 노력없이 작업을 관리하더라도) 의식적인 이해를 초월하는, 수천 혹은 수백만의 연산을 필요로 합니다.
기계학습(Machine Learning)은 *경험*으로 부터 *행동을 배울수* 있는 강력한 기술에 대한 연구 입니다.
일반적으로 기계학습 알고리즘이 관찰데이터 혹은 환경과의 상호작용에 따른, 더 많은 경험의 축적을 통해 성능이 향상됩니다. 
개발자가 스스로 *배우고*, 소프트웨어를 수정할 때까지, 얼마나 많은 경험이 쌓였는지와 상관 없이, 정해진대로 동일한 비즈니스 로직에 따라동작하는 우리의 e-커머스(E-Commerce) 플랫폼과 비교해 보세요. 
이 책에서, 기계학습의 기초를 배우고, 특별히 자연어처리, 헬쓰케어(HealthCare), 유전체학 등과 같이 다양한 분야에서 강략한 도구인 컴퓨터비젼(Computer Vision)의 혁신을 주도하는 강략한 딥러닝(DeepLearning)에 중점을 둡니다.

## A Motivating Example

Before we could begin writing, the authors of this book,
like much of the work force, had to become caffeinated.
We hopped in the car and started driving.
Using an iPhone, Alex called out 'Hey Siri',
awakening the phone's voice recognition system.
Then Mu commanded 'directions to Blue Bottle coffee shop'.
The phone quickly displayed the transcription of his command.
It also recognized that we were asking for directions
and launched the Maps application to fulfill our request.
Once launched, the Maps app identified a number of routes.
Next to each route, the phone displayed a predicted transit time.
While we fabricated this story for pedagogical convenience,
it demonstrates that in the span of just a few seconds,
our everyday interactions with a smartphone
can engage several machine learning models.

저자들은 이 책을 쓰기 전에, 많은 노동력이 필요한 일처럼, 많은 카페인이 필요했습니다.. 상상해 봅시다. 우리는 차에 올라타서 운전을 하기 시작했습니다. 아이폰을 사용자인 Alex는 핸드폰의 음성 인식 시스템을 부르기 위해서 'Hey Siri'라고 외쳤습니다. 그러자 Mu는 '블루 보틀 커피샵으로 가는길을 알려줘'라고 명령 했습니다. 핸드폰은 그의 명령을 글로 바꿔서 화면에 빠르게 보여줍니다. 우리가 길을 묻는 것을 알아채고는 우리의 요청에 응하기 위해서 지도 앱을 띄웁니다. 지도 앱이 실행되자 마자 여러 경로를 찾아냅니다. 각 경로 옆에는 예상 소요 시간이 함께 표시됩니다. 설명을 위해서 지어낸 이야기이긴 하지만, 이 짧은 시나리오는 스마트폰을 통해 다양한 머신 러닝 모델이 사용되는 것을 보여주고 있습니다.

Imagine just writing a program to respond to a *wake word*
like 'Alexa', 'Okay, Google' or 'Siri'.
Try coding it up in a room by yourself
with nothing but a computer and a code editor.
How would you write such a program from first principles?
Think about it... the problem is hard.
Every second, the microphone will collect roughly 44,000 samples.
What rule could map reliably from a snippet of raw audio
to confident predictions ``{yes, no}``
on whether the snippet contains the wake word?
If you're stuck, don't worry.
We don't know how to write such a program from scratch either.
That's why we use ML.

 'Alexa', 'Okay, Google', 이나 'Siri' 같은 wake word 에 응답하는 프로그램을 작성한다고 생각해보세요. 컴퓨터와 코드 편집기만 사용해서 코드를 만들어 나간다고 했을때 제일 원칙을 이용해서 어떻게 그런 프로그램을 작성할 것인가요? 조금만 생각해 봐도 이 문제가 쉽지 않다는 것을 알 수 있습니다. 매 초마다 마이크는 대략 44,000개의 샘플을 수집합니다. 소리 조각으로 부터 그 소리 조각이 wake word를 포함하는지 신뢰있게 {yes, no} 로 예측하는 룰을 만들 수 있나요? 어떻게 할지를 모른다고 해도 걱정하지 마세요. 우리도 그런 프로그램을 처음부터 어떻게 작성해야하는지 모릅니다. 이것이 바로 우리가 머신 러닝을 사용하는 이유입니다.
 
![Identify an awake word.](../img/wake-word.svg)


Here's the trick.
Often, even when we don't know how to tell a computer
explicitly how to map from inputs to outputs,
we are nonetheless capable of performing the cognitive feat ourselves.
In other words, even if you don't know *how to program a computer*
to recognize the word 'Alexa',
you yourself *are able* to recognize the word 'Alexa'.
Armed with this ability,
we can collect a huge *dataset* containing examples of audio
and label those that *do* and that *do not* contain the wake word.
In the ML approach, we do not design a system *explicitly*
to recognize wake words.
Instead, we define a flexible program
whose behavior is determined by a number of *parameters*.
Then we use the dataset to determine
the best possible set of parameters,
those that improve the performance of our program
with respect to some measure of performance on the task of interest.

여기에 트릭이 있습니다. 컴퓨터에 명시적으로, 입력을 출력으로 맵핑하는 방법을 모르는 경우에도,  우리는 스스로 인지해서 이것을 해낼 수 있습니다. 즉, 여러분이 'Alexa'라는 단어를 인식하도록 *컴퓨터를 프로그래밍하는 방법*을 모르지만, 여러분은 'Alexa'라는 단어를 인식 할 수 있습니다. 이 기능을 탑제하여, 오디오 예제를 포함하는 거대한 데이터 세트를 수집하고, 웨이크 워드를 포함하지 않는 라벨을 표시 할 수 있습니다. ML 접근법에서 우리는 웨이크워드(wake word)를 인식하도록 시스템을 명시 적으로 설계하지 않습니다. 대신, 우리는 여러 가지 파라미터로 동작이 결정되는 유연한 프로그램을 정의합니다. 그런 다음 데이터 집합을 사용하여 가능한 파라미터 집합을 결정합니다. 파라미터 집합은 관심있는 작업의 성능 측정과 관련하여 프로그램 성능을 향상시킵니다.

You can think of the parameters as knobs that we can turn,
manipulating the behavior of the program.
Fixing the parameters, we call the program a *model*.
The set of all distinct programs (input-output mappings)
that we can produce just by manipulating the parameters
is called a *family* of models.
And the *meta-program* that uses our dataset
to choose the parameters is called a *learning algorithm*.

Before we can go ahead and engage the learning algorithm,
we have to define the problem precisely,
pinning down the exact nature of the inputs and outputs,
and choosing an appropriate model family.
In this case, our model receives a snippet of audio as *input*,
and it generates a selection among ``{yes, no}`` as *output*—which,
if all goes according to plan,
will closely approximate whether (or not)
the snippet contains the wake word.

파라미터를 우리가 움직일 수있는 손잡이라고 생각하면, 프로그램의 동작을 조종할 수 있습니다. 파라미터를 수정한 프로그램을 모델이라고 부릅니다. 파라미터를 조작하여 생성 할 수있는 모든 고유 한 프로그램 세트 (입력 - 출력 매핑)를 모델 패밀리라고합니다. 또한 매개 변수를 선택하기 위해 데이터 집합을 사용하는 메타 프로그램을 학습 알고리즘이라고합니다.

우리가 학습 알고리즘을 수행하기 전에 문제를 정확하게 정의하고 입력 및 출력의 정확한 특성을 고정하고 적절한 모델 군을 선택해야합니다. 이 경우 우리 모델은 오디오 스니펫(Snippet)을 입력으로 받고, 출력을 {예, 아니요} 하게 됩니다. 모두 계획대로 진행되면 스니펫에 웨이크 워드가 포함되어 있는지 (또는 설정되어 있지 않은지) 거의 맞출 수 있게 됩니다.

If we choose the right family of models,
then there should exist one setting of the knobs
such that the model fires ``yes`` every time it hears the word 'Alexa'.
Because the exact choice of the wake word is arbitrary,
we'll probably need a model family capable, via another setting of the knobs,
of firing ``yes`` on the word 'Apricot'.
We expect that the same model should apply to 'Alexa' recognition and 'Apricot' recognition because these are similar tasks.
However, we might need a different family of models entirely
if we want to deal with fundamentally different inputs or outputs,
say if we wanted to map from images to captions,
or from English sentences to Chinese sentences.

As you might guess, if we just set all of the knobs randomly,
it's not likely that our model will recognize 'Alexa', 'Apricot',
or any other English word.
In deep learning, the *learning* is the process
by which we discover the right setting of the knobs
coercing the desired behaviour from our model.

The training process usually looks like this:

1. Start off with a randomly initialized model that can't do anything useful.
1. Grab some of your labeled data (e.g. audio snippets and corresponding ``{yes,no}`` labels)
1. Tweak the knobs so the model sucks less with respect to those examples
1. Repeat until the model is awesome.

만약 여러분이 좋은 모델을 선택했다면, 'Alexa' 단어를 들을 때 마다 `yes` 를 출력하는 모델을 만드는 파라미터 세트 하나가 존재할 것입니다. 마찬가지로 'Apricot' 단어에 대해서 `yes` 를 출력하는 것이 다른 조합이 있을 수 있습니다. 우리는 이 두가지가 비슷하기 때문에, 동일한 모델이 'Alexa' 인식과 'Apricot' 인식에 적용되기를 기대합니다. 하지만 근본적으로 다른 입력 또는 출력을 다루기 위해서는 다른 모델이 필요할 수도 있습니다. 예를 들어, 이미지와 캡션을 매핑하는 머신과 영어 문장을 중국어 문장으로 매핑하는 모델은 서로 다른 것을 사용할 것입니다.

이미 예상했겠지만, 이 손잡이를 아무렇게나 설명할 경우, 아마도 그 모델은 'Alexa', 'Apricot'  또는 어떤 영어 단어도 인식하지 못할 것입니다. 일반적으로 딥러닝에서는 *학습(learning)* 은 여러 *학습 기간*에 걸쳐서 모델의 행동 (손잡이를 돌리면서)을 업데이트하는 것을 말합니다.

학습 과정은 보통 다음과 같습니다.

1. 임의로 초기화되서 아무것도 유용한 것을 못하는 모델로 시작합니다.
1. 레이블을 갖은 데이터를 수집합니다. (예, 오디오 조각과 그에 해당하는 `{yes,no}` 레이블들)
1. 주어진 예제들에 모델이 조금 덜 이상하게 작동하도록 손잡이를 조정합니다.
1. 모델이 좋아질 때까지 반복합니다.


![A typical training process. ](../img/ml-loop.svg)

To summarize, rather than code up a wake word recognizer,
we code up a program that can *learn* to recognize wake words,
*if we present it with a large labeled dataset*.
You can think of this act
of determining a program's behavior by presenting it with a dataset
as *programming with data*.
We can "program" a cat detector by providing our machine learning system
with many examples of cats and dogs, such as the images below:

요약하면, wake word를 인식하는 코드를 작성하는 것이 아니라, *아주 많은 레이블이 있는 데이터셋이 있을 경우에* wake word를 인식하는 것을 *배우는* 프로그램을 작성하는 것입니다. 데이터셋을 제공해서 프로그램의 행동을 결정하는 것을 *programming with data*라고 생각할 수 있습니다.

우리는 아래 이미지들과 같은 아주 많은 고양이와 개 샘플들을 머신 러닝 시스템에 제공해서 고양이 탐지기 프로그램을 만들 수 있습니다.

| ![cat1](../img/cat1.png) | ![cat2](../img/cat2.jpg) | ![dog1](../img/dog1.jpg) |![dog2](../img/dog2.jpg) |
|:---------------:|:---------------:|:---------------:|:---------------:|
|cat|cat|dog|dog|

This way the detector will eventually learn to emit
a very large positive number if it's a cat,
a very large negative number if it's a dog,
and something closer to zero if it isn't sure,
and this barely scratches the surface of what ML can do.

이런 방법으로 탐지기는 결국에 고양이를 입력으로 받으면 아주 큰 양수를 결과로 나오게, 그리고 개를 입력으로 받으면 아주 큰 음수를 결과로 나오게 학습될 것입니다. 이 모델은 잘 모르겠으면 0과 가까운 수를 결과로 출력할 것입니다. 이 예는 머신 러닝으로 할 수 있는 일의 일부에 불과합니다.

Deep learning is just one among many
popular frameworks for solving machine learning problems.
While thus far, we've only talked about machine learning broadly
and not deep learning, there's a couple points worth sneaking in here:
First, the problems that we've discussed thus far:
learning from raw audio signal,
directly from the pixels in images,
and mapping between sentences of arbitrary lengths and across languages
are problems where deep learning excels and traditional ML tools faltered.
Deep models are *deep* in precisely the sense that they learn
many *layers* of computation.
It turns out that these many-layered (or hierarchical) models
are capable of addressing low-level perceptual data
in a way that previous tools could not.
In bygone days, the crucial part of applying ML to these problems
consisted of coming up with manually engineered ways of transforming
the data into some form amenable to *shallow* models.
One key advantage of deep learning is that it replaces not only the *shallow* models
at the end of traditional learning pipelines,
but also the labor-intensive feature engineering.
Secondly, by replacing much of the *domain-specific preprocessing*,
deep learning has eliminated many of the boundaries
that previously separated computer vision, speech recognition,
natural language processing, medical informatics, and other application areas,
offering a unified set of tools for tackling diverse problems.


## The Key Components: Data, Models, and Algorithms

In our *wake-word* example, we described a dataset
consisting of audio snippets and binary labels
gave a hand-wavy sense of how we might *train*
a model to approximate a mapping from snippets to classifications.
This sort of problem, where we try to predict a designated unknown *label*
given known *inputs* (also called *features* or *covariates*),
and examples of both is called *supervised learning*,
and it's just one among many *kinds* of machine learning problems.
In the next section, we'll take a deep dive into the different ML problems.
First, we'd like to shed more light on some core components
that will follow us around, no matter what kind of ML problem we take on:

1. The **data** that we can learn from
2. A **model** of how to transform the data
3. A **loss** function that quantifies the *badness* of our model
4. An **algorithm** to adjust the model's parameters to minimize the loss

*wake word*를 인식하는 문제를 이야기할 때, 음성 조각과 레이블로 구성된 데이터셋을 언급했습니다. (추상적이긴 하지만) 음성 조각이 주어졌을 때 레이블을 예측하는 머신 러닝 모델을 어떻게 *학습*시킬 수 있는지 설명했습니다. 예제로부터 레이블을 예측하는 설정은 ML의 한 종류로 *지도학습(supervised learning)* 이라고 부릅니다. 딥러닝에서도 많은 접근법들이 있는데, 다른 절들에서 다루겠습니다. 머신 러닝을 진행하기 위해서는 다음 4가지가 필요합니다.

1. 학습에 필요한 *데이터*
2. 데이터를 어떻게 변환할지에 대한 *모델*
3. 우리가 얼마나 잘하고 있는지를 측정하는 *loss* 함수
4. loss 함수를 최소화하도록 모델 파라미터를 바꾸는 *알고리즘*


### Data

It might go without saying that you cannot do data science without data.
We could lose hundreds of pages pondering the precise nature of data
but for now we'll err on the practical side and focus on the key properties
to be concerned with.
Generally we are concerned with a collection of *examples*
(also called *data points*, *samples*, or *instances*).
In order to work with data usefully, we typically
need to come up with a suitable numerical representation.
Each *example* typically consists of a collection
of numerical attributes called *features* or *covariates*.

If we were working with image data,
each individual photograph might constitute an *example*,
each represented by an ordered list of numerical values
corresponding to the brightness of each pixel.
A $200\times200$ color photograph would consist of $200\times200\times3=120000$
numerical values, corresponding to the brightness
of the red, green, and blue channels corresponding to each spatial location.
In a more traditional task, we might try to predict
whether or not a patient will survive,
given a standard set of features such as age, vital signs, diagnoses, etc.

When every example is characterized by the same number of numerical values,
we say that the data consists of *fixed-length* vectors
and we describe the (constant) length of the vectors
as the *dimensionality* of the data.
As you might imagine, fixed length can be a convenient property.
If we wanted to train a model to recognize cancer in microscopy images,
fixed-length inputs means we have one less thing to worry about.

However, not all data can easily be represented as fixed length vectors.
While we might expect microscrope images to come from standard equipment,
we can't expect images mined from the internet to all show up in the same size.
While we might imagine cropping images to a standard size,
text data resists fixed-length representations even more stubbornly.
Consider the product reviews left on e-commerce sites like Amazon or TripAdvisor. Some are short: "it stinks!". Others ramble for pages.
One major advantage of deep learning over traditional methods
is the comparative grace with which modern models
can handle *varying-length* data.

Generally, the more data we have, the easier our job becomes.
When we have more data, we can train more powerful models,
and rely less heavily on pre-conceived assumptions.
The regime change from (comparatively small) to big data
is a major contributor to the success of modern deep learning.
To drive the point home, many of the most exciting models in deep learning either don't work without large data sets.
Some others work in the low-data regime,
but no better than traditional approaches.

Finally it's not enough to have lots of data and to process it cleverly.
We need the *right* data.
If the data is full of mistakes, or if the chosen features are not predictive of the target quantity of interest, learning is going to fail.
The situation is well captured by the cliché: *garbage in, garbage out*.
Moreover, poor predictive performance isn't the only potential consequence.
In sensitive applications of machine learning,
like predictive policing, resumé screening, and risk models used for lending,
we must be especially alert to the consequences of garbage data.
One common failure mode occurs in datasets where some groups of people
are unrepresented in the training data.
Imagine applying a skin cancer recognition system in the wild
that had never seen black skin before.
Failure can also occur when the data doesn't merely under-represent some groups,
but reflects societal prejudices.
For example if past hiring decisions are used to train a predictive model
that will be used to screen resumes, then machine learning models could inadvertently capture and automate historical injustices.
Note that this can all happen without the data scientist being complicit,
or even aware.


### Models


Most machine learning involves *transforming* the data in some sense.
We might want to build a system that ingests photos and predicts *smiley-ness*.
Alternatively, we might want to ingest a set of sensor readings
and predict how *normal* vs *anomalous* the readings are.
By *model*, we denote the computational machinery for ingesting data
of one type, and spitting out predictions of a possibly different type.
In particular, we are interested in statistical models
that can be estimated from data.
While simple models are perfectly capable of addressing
appropriately simple problems the problems
that we focus on in this book stretch the limits of classical methods.
Deep learning is differentiated from classical approaches
principally by the set of powerful models that it focuses on.
These models consist of many successive transformations of the data
that are chained together top to bottom, thus the name *deep learning*.
On our way to discussing deep neural networks, we'll discuss some more traditional methods.


###  Objective functions

Earlier, we introduced machine learning as "learning behavior from experience".
By *learning* here, we mean *improving* at some task over time.
But who is to say what constitutes an improvement?
You might imagine that we could propose to update our model,
and some people might disagree on whether the proposed update
constitued an improvement or a decline.

In order to develop a formal mathematical system of learning machines,
we need to have formal measures of how good (or bad) our models are.
In machine learning, and optimization more generally,
we call these objective functions.
By convention, we usually define objective funcitons
so that *lower* is *better*.
This is merely a convention. You can take any function $f$
for which higher is better, and turn it into a new function $f'$
that is qualitatively identical but for which lower is better
by setting $f' = -f$.
Because lower is better, these functions are sometimes called
*loss functions* or *cost functions*.

When trying to predict numerical values,
the most common objective function is squared error $(y-\hat{y})^2$.
For classification, the most common objective is to minimize error rate,
i.e., the fraction of instances on which
our predictions disagree with the ground truth.
Some objectives (like squared error) are easy to optimize.
Others (like error rate) are difficult to optimize directly,
owing to non-differentiability or other complications.
In these cases, it's common to optimize a surrogate objective.

Typically, the loss function is defined
with respect to the model's parameters
and depends upon the dataset.
The best values of our model's parameters are learned
by minimizing the loss incurred on a *training set*
consisting of some number of *examples* collected for training.
However, doing well on the training data
doesn't guarantee that we will do well on (unseen) test data.
So we'll typically want to split the available data into two partitions:
the training data (for fitting model parameters)
and the test data (which is held out for evaluation),
reporting the following two quantities:

 * **Training Error:**
 The error on that data on which the model was trained.
 You could think of this as being like
 a student's scores on practice exams
 used to prepare for some real exam.
 Even if the results are encouraging,
 that does not guarantee success on the final exam.
 * **Test Error:** This is the error incurred on an unseen test set.
 This can deviate significantly from the training error.
 When a model fails to generalize to unseen data,
 we say that it is *overfitting*.
 In real-life terms, this is like flunking the real exam
 despite doing well on practice exams.


### Optimization algorithms

Once we've got some data source and representation,
a model, and a well-defined objective function,
we need an algorithm capable of searching
for the best possible parameters for minimizing the loss function.
The most popular optimization algorithms for neural networks
follow an approach called gradient descent.
In short, at each step, they check to see, for each parameter,
which way the training set loss would move
if you perturbed that parameter just a small amount.
They then update the parameter in the direction that reduces the loss.


## Kinds of Machine Learning

In the following sections, we will discuss a few types of machine learning in some more detail. We begin with a list of *objectives*, i.e. a list of things that machine learning can do. Note that the objectives are complemented with a set of techniques of *how* to accomplish them, i.e. training, types of data, etc. The list below is really only sufficient to whet the readers' appetite and to give us a common language when we talk about problems. We will introduce a larger number of such problems as we go along.

### 지도 학습(Supervised learning)

Supervised learning addresses the task of predicting *targets* given input data.
The targets, also commonly called *labels*, are generally denoted *y*.
The input data points, also commonly called *examples* or *instances*, are typically denoted $\boldsymbol{x}$.
The goal is to produce a model $f_\theta$ that maps an input $\boldsymbol{x}$ to a prediction $f_{\theta}(\boldsymbol{x})$

지도학습(supervised learning)은 주어진 입력 데이터에 대한 *타켓(target)*을 예측하는 문제를 푸는 것입니다. 타겟은 종종 *레이블(label)* 이라고 불리고, 기호로는  *y* 로 표기합니다. 입력 데이터 포인트는 *샘플(sample)* 또는 *인스턴스(instance)* 라고 불리기도 하고,  $\boldsymbol{x}$ 로 표기됩니다. 입력  $\boldsymbol{x}$ 를 예측 on $f_{\theta}(\boldsymbol{x})$ 로 매핑하는 모델  $f_\theta$ 을 생성하는 것이 목표입니다.

To ground this description in a concrete example,
if we were working in healthcare,
then we might want to predict whether or not a patient would have a heart attack.
This observation, *heart attack* or *no heart attack*,
would be our label $y$.
The input data $\boldsymbol{x}$ might be vital signs such as heart rate, diastolic and systolic blood pressure, etc.

이해를 돕기 위해서 예를 들어보겠습니다. 여러분이 의료분야에서 일을 한다면, 어떤 환자에게 심장 마비가 일어날지 여부를 예측하기를 원할 것입니다. 이 관찰, *심장 마비* 또는 *정상*, 은 우리의 레이블 $y$ 가 됩니다. 입력 $x$ 는 심박동, 이완기 및 수축 혈압 등 바이탈 사인들이 될 것입니다.

The supervision comes into play because for choosing the parameters $\theta$, we (the supervisors) provide the model with a collection of *labeled examples* ($\boldsymbol{x}_i, y_i$), where each example $\boldsymbol{x}_i$ is matched up against its correct label.

파라미터 $\theta$ 를 선택하는데, 우리는(감독자) *레이블이 있는 예들* , ($\boldsymbol{x}_i, y_i$)을 모델에게 제공하기 때문에 감독이 작동합니다. 이 때,  $\boldsymbol{x}_i$ 는 정확한 레이블과 매치되어 있습니다.


In probabilistic terms, we typically are interested in estimating
the conditional probability $P(y|x)$.
While it's just one among several approaches to machine learning,
supervised learning accounts for the majority of machine learning in practice.
Partly, that's because many important tasks
can be described crisply as estimating the probability of some unknown given some available evidence:

* Predict cancer vs not cancer, given a CT image.
* Predict the correct translation in French, given a sentence in English.
* Predict the price of a stock next month based on this month's financial reporting data.

확률 용어로는 조건부 확률  $P(y|x)$을 추정하는데 관심이 있습니다. 이것은 머신 러닝의 여러 접근 방법 중에 하나이지만, 지도학습은 실제로 사용되는 머신 러닝의 대부분을 설명합니다. 부분적으로, 많은 중요한 작업들이 몇 가지 이용 가능한 증거가 주어졌을 때 알 수 없는 것의 확률을 추정하는 것으로 설명될 수 있기 때문입니다 :

* CT 이미지를 보고 암 여부를 예측하기
* 영어 문장에 대한 정확한 프랑스어 번역을 예측하기
* 이번달의 제정 보고 데이터를 기반으로 다음달 주식 가격을 예측하기

Even with the simple description 'predict targets from inputs'
supervised learning can take a great many forms and require a great many modeling decisions,
depending on the type, size, and the number of inputs and outputs.
For example, we use different models to process sequences (like strings of text or time series data)
and for processing fixed-length vector representations.
We'll visit many of these problems in depth throughout the first 9 parts of this book.

'입력으로 부터 타겟을 예측한다'라고 간단하게 설명했지만, 지도학습은 입력과 출력의 타입, 크기 및 개수에 따라서 아주 다양한 형식이 있고 다양한 모델링 결정을 요구합니다. 예를 들면, 텍스트의 문자열 또는 시계열 데이터와 같은 시퀀스를 처리하는 것과 고정된 백처 표현을 처리하는데 다른 모델을 사용합니다. 이 책의 처음 9 파트에서 이런 문제들에 대해서 상세하게 다룹니다.

Put plainly, the learning process looks something like this.
Grab a big pile of example inputs, selecting them randomly.
Acquire the ground truth labels for each.
Together, these inputs and corresponding labels (the desired outputs)
comprise the training set.
We feed the training dataset into a supervised learning algorithm.
So here the *supervised learning algorithm* is a function that takes as input a dataset,
and outputs another function, *the learned model*.
Then, given a learned model,
we can take a new previously unseen input, and predict the corresponding label.

명백히 말하면, 학습 과정은 다음과 같습니다. 예제 입력을 많이 수집해서, 임의로 고릅니다. 각각에 대해서 ground truth를 얻습니다. 입력과 해당하는 레이블 (원하는 결과)을 합쳐서 학습 데이터를 구성합니다. 학습 데이터를 지도학습 알고리즘에 입력합니다. 여기서 *지도학습 알고리즘(supervised learning algorithm)* 은 데이터셋을 입력으로 받아서 어떤 함수(학습된 모델)를 결과로 내는 함수 입니다. 그렇게 얻어진 학습된 모델을 이용해서 이전에 보지 않은 새로운 입력에 대해서 해당하는 레이블을 예측합니다.

![Supervised learning.](../img/supervised-learning.svg)



#### 회귀(Regression)

Perhaps the simplest supervised learning task to wrap your head around is Regression.
Consider, for example a set of data harvested
from a database of home sales.
We might construct a table, where each row corresponds to a different house,
and each column corresponds to some relevant attribute,
such as the square footage of a house, the number of bedrooms, the number of bathrooms,
and the number of minutes (walking) to the center of town.
Formally, we call one row in this dataset a *feature vector*,
and the object (e.g. a house) it's associated with an *example*.

아마도 여러분의 머리에 떠오르는 가장 간단한 지도학습은 회귀(regression)일 것입니다. 
주택 판매 데이터베이스에서 추출된 데이터를 예로 들어보겠습니다. 각 행은 하나의 집을, 
각 열은 관련된 속성(집의 면적, 침실 개수, 화장실 개수, 도심으로 부터의 도보 거리 등)을 갖는 테이블을 만듭니다. 우리는 이 데이터셋의 하나의 행을 *속성백터(feature vector)* 라고 부르고, 이와 연관된 객체는 *예제(example)* 이라고 부릅니다.

If you live in New York or San Francisco, and you are not the CEO of Amazon, Google, Microsoft, or Facebook,
the (sq. footage, no. of bedrooms, no. of bathrooms, walking distance) feature vector for your home
might look something like: $[100, 0, .5, 60]$.
However, if you live in Pittsburgh,
it might look more like $[3000, 4, 3, 10]$.
Feature vectors like this are essential for all the classic machine learning problems.
We'll typically denote the feature vector for any one example $\mathbf{x_i}$
and the set of feature vectors for all our examples $X$.

만약 여러분이 뉴욕이나 샌프란시스코에서 살고, 아마존, 구글, 마이크소프트, 페이스북의 CEO가 아니라면, 여러분 집의 속성 백터(집 면적, 침실수, 화장실수, 도심까지 도보 거리)는 아마도 $[100, 0, .5, 60]$ 가 될 것입니다. 하지만, 피츠버그에 산다면  $[3000, 4, 3, 10]$ 와 가까울 것입니다. 이런 속성 백터는 모든 전통적인 머신 러닝 문제에 필수적인 것입니다. 우리는 일반적으로 어떤 예제에 대한 속성 백터를 $\mathbf{x_i}$ 로 표기하고, 모든 예제에 대한 속성 백터의 집합은  $X$ 로 표기합니다.

What makes a problem a *regression* is actually the outputs.
Say that you're in the market for a new home,
you might want to estimate the fair market value of a house,
given some features like these.
The target value, the price of sale, is a *real number*.
We denote any individual target $y_i$ (corresponding to example $\mathbf{x_i}$)
and the set of all targets $\mathbf{y}$ (corresponding to all examples X).
When our targets take on arbitrary real values in some range,
we call this a regression problem.
The goal of our model is to produce predictions (guesses of the price, in our example)
that closely approximate the actual target values.
We denote these predictions $\hat{y}_i$
and if the notation seems unfamiliar, then just ignore it for now.
We'll unpack it more thoroughly in the subsequent chapters.

결과에 따라서 어떤 문제가 *회귀(regression)* 인지를 결정됩니다. 새 집을 사기 위해서 부동산을 돌아다니고 있다고 하면, 여러분은 주어진 속성에 대해서 합당한 집 가격을 추정하기를 원합니다. 타겟 값, 판매 가격,은 *실제 숫자(real number)* 가 됩니다. 샘플  $\mathbf{x_i}$에 대응하는 각 타겟은  $y_i$ 로 표시하고, 모든 예제 X 에 대한 모든 타겟들은  $\mathbf{y}$ 로 적습니다. 타겟이 어떤 범위에 속하는 임의의 실수값을 갖는 다면, 우리는 이를 회귀 문제라고 부릅니다. 우리의 모델의 목표는 실제 타겟 값을 근접하게 추정하는 예측 (이 경우에는 집가격 추측)을 생성하는 것입니다. 이 예측을 $\hat{y}_i$ 로 표기합니다. 만약 표기법이 익숙하지 않다면, 다음 장들에서 더 자세히 설명할 것이기 때문에 지금은 그냥 무시해도 됩니다.  

Lots of practical problems are well-described regression problems.
Predicting the rating that a user will assign to a movie is a regression problem,
and if you designed a great algorithm to accomplish this feat in 2009,
you might have won the [$1 million Netflix prize](https://en.wikipedia.org/wiki/Netflix_Prize).
Predicting the length of stay for patients in the hospital is also a regression problem.
A good rule of thumb is that any *How much?* or *How many?* problem should suggest regression.

* 'How many hours will this surgery take?' - *regression*
* 'How many dogs are in this photo?' - *regression*.

많은 실질적인 문제들이 잘 정의된 회귀 문제들입니다. 관객이 영화에 줄 평점을 예측하는 것은 회귀의 문제인데, 여러분이 2009년에 이를 잘 예측하는 대단한 알고리즘을 디자인했다면  [$1 million Netflix prize](https://en.wikipedia.org/wiki/Netflix_Prize) 를 받았을 것입니다. 환자가 입원일 수를 예측하는 것 또한 회귀 문제입니다. 문제가 회귀의 문제인지를 판단하는 좋은 경험의 법칙은 *얼마나 만큼*  또는 *얼마나 많이* 로 대답이되는지 보는 것입니다.

* 이 수술은 몇 시간이 걸릴까요? - *회귀*
* 이 사진에 개가 몇 마리 있나요? - *회귀*


However, if you can easily pose your problem as 'Is this a _ ?',
then it's likely, classification, a different fundamental problem type that we'll cover next.
Even if you've never worked with machine learning before,
you've probably worked through a regression problem informally.
Imagine, for example, that you had your drains repaired
and that your contractor spent $x_1=3$ hours removing gunk from your sewage pipes.
Then she sent you a bill of $y_1 = \$350$.
Now imagine that your friend hired the same contractor for $x_2 = 2$ hours
and that she received a bill of $y_2 = \$250$.
If someone then asked you how much to expect on their upcoming gunk-removal invoice
you might make some reasonable assumptions,
such as more hours worked costs more dollars.
You might also assume that there's some base charge and that the contractor then charges per hour.
If these assumptions held true, then given these two data points,
you could already identify the contractor's pricing structure:
\$100 per hour plus \$50 to show up at your house.
If you followed that much then you already understand the high-level idea behind linear regression (and you just implicitly designed a linear model with bias).

그런데 만약 주어진 문제에 대한 질문을 '이것은 ... 인가요?' 라고 쉽게 바꿀 수 있다면, 분류의 문제입니다. 이는 다른 기본적인 문제 유형입니다. 머신 러닝을 이전에 다뤄보지 않은 경우에도 비공식적으로는 회귀의 문제들을 다뤄왔습니다. 예를 들어, 여러분의 집의 배수구를 수리하고, 수리공이  $x_1=3$ 시간이 걸려서 하수관에서 덩어리를 제거했습니다. 이에 대해서 수리공은 $y_1 = \$350$ 청구를 합니다. 여러분의 친구가 같은 수리공을 공용해서 or $x_2 = 2$ 시간 걸려서 일하고,  $y_2 = \$250$ 를 청구했습니다. 어떤 사람이 하수관에서 덩어리를 제거하는 데 비용이 얼마가 될지를 물어보면, 여러분은 논리적인 추정 - 시간이 더 소요되면 더 비싸다 -을 할 것입니다. 기본 비용이 있고, 시간당 비용이 있을 것이라고까지 추정할 것입니다. 이 가정이 맞다면, 위 두 데이터 포인트를 활용해서 수리공의 가격 구조를 알아낼 수 있습니다: 시간당 100달러 및 기본 비용 50달러. 여러분이 여기까지 잘 따라왔다면 선형 회귀에 대한 고차원의 아이디어를 이미 이해한 것입니다. (선형모델을 bias를 사용해서 디자인했습니다.)

In this case, we could produce the parameters that exactly matched the contractor's prices.
Sometimes that's not possible, e.g., if some of the variance owes to some factors besides your two features.
In these cases, we'll try to learn models that minimize the distance between our predictions and the observed values.
In most of our chapters, we'll focus on one of two very common losses,
the
[L1 loss](http://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.L1Loss)
where


위 예에서는 수리공의 가격을 정확하게 계산하는 파라미터를 찾아낼 수 있었습니다. 때로는 불가능한데, 예를 들면 만약 어떤 차이가 이 두 피쳐 외에 작용하는 경우가 그렇습니다. 그런 경우에는 우리는 우리의 예측과 관찰된 값의 차이를 최소화하는 모델을 학습시키고자 노력합니다. 대부분 장들에서 우리는 아주 일반적인 loss 둘 중에 하나에 집중할 것입니다. 하나는 [L1 loss](http://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.L1Loss) 로, 다음과 같고, 

$$l(y,y') = \sum_i |y_i-y_i'|$$

and the least mean squares loss, aka
[L2 loss](http://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.L2Loss)
where

다른 하나는 최소 평균 제곱 손실(least mean square loss), 즉 [L2 loss](http://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.L2Loss) 입니다. 이는 다음과 같이 표기 됩니다.

$$l(y,y') = \sum_i (y_i - y_i')^2.$$

As we will see later, the $L_2$ loss corresponds to the assumption that our data was corrupted by Gaussian noise, whereas the $L_1$ loss corresponds to an assumption of noise from a Laplace distribution.

나중에 보겠지만, $L_2$ loss는 우리의 데이터가 가우시안 노이즈에 영향을 받았다고 가정에 관련이 되고, $L_1$ loss는 라플라스 분포(Laplace distribution)의 노이즈를 가정합니다.

#### 분류(classification)

While regression models are great for addressing *how many?* questions,
lots of problems don't bend comfortably to this template. For example,
a bank wants to add check scanning to their mobile app.
This would involve the customer snapping a photo of a check with their smartphone's camera
and the machine learning model would need to be able to automatically understand text seen in the image.
It would also need to understand hand-written text to be even more robust.
This kind of system is referred to as optical character recognition (OCR),
and the kind of problem it solves is called a classification.
It's treated with a distinct set of algorithms than those that are used for regression.

회귀 모델은 *얼마나 많이* 라는 질문에 답을 주는데는 훌륭하지만, 많은 문제들이 이 템플렛에 잘 들어맞지 않습니다. 예를 들면, 은행이 모바일앱에 수표 스캐닝 기능을 추가하고자 합니다. 이를 위해서 고객은 스마트폰의 카메라로 수표를 찍으면, 이미지에 있는 텍스트를 자동으로 이해하는 기능을 하는 머신 러닝 모델이 필요합니다. 손으로 쓴 글씨에 더 잘 동작을 해야할 필요가 있습니다. 이런 시스템은 문자인식(OCR, optical character recognition)이라고 하고, 이것이 풀려는 문제의 종류를 분류라고 합니다. 회귀 문제에 사용되는 알고리즘과는 아주 다른 알고리즘이 이용됩니다.

In classification, we want to look at a feature vector, like the pixel values in an image,
and then predict which category (formally called *classes*),
among some set of options, an example belongs.
For hand-written digits, we might have 10 classes,
corresponding to the digits 0 through 9.
The simplest form of classification is when there are only two classes,
a problem which we call binary classification.
For example, our dataset $X$ could consist of images of animals
and our *labels* $Y$ might be the classes $\mathrm{\{cat, dog\}}$.
While in regression, we sought a *regressor* to output a real value $\hat{y}$,
in classification, we seek a *classifier*, whose output $\hat{y}$ is the predicted class assignment.

분류는 이미지의 픽셀값과 같은 속성 백터를 보고, 그 예제가 주어진 종류들 중에서 어떤 카테고리에 속하는지를 예측합니다. 손으로 쓴 숫자의 경우에는 숫자 0부터 9까지 10개의 클래스가 있습니다. 가장 간단한 분류의 형태는 단 두개의 클래스가 있는 경우로, 이를 이진 분류(binary classificatio)이라고 부릅니다. 예를 들어, 데이터셋 $X$ 가 동물들의 사진이고, 이에 대한 *레이블*  $Y$ 이 {고양이, 강아지}인 경우를 들 수 있습니다. 회귀에서는 결과가 실수 값 $\hat{y}$ 가 되지만, 분류에서는 결과가 예측된 클래스인 *분류기* 를 만들고자 합니다.

For reasons that we'll get into as the book gets more technical, it's pretty hard to optimize a model that can only output a hard categorical assignment, e.g. either *cat* or *dog*.
It's a lot easier instead to express the model in the language of probabilities.
Given an example $x$, the model assigns a probability $\hat{y}_k$ to each label $k$.
Because these are probabilities, they need to be positive numbers and add up to $1$.
This means that we only need $K-1$ numbers to give the probabilities of $K$ categories.
This is easy to see for binary classification.
If there's a 0.6 (60%) probability that an unfair coin comes up heads,
then there's a 0.4 (40%) probability that it comes up tails.
Returning to our animal classification example, a classifier might see an image
and output the probability that the image is a cat $\Pr(y=\mathrm{cat}| x) = 0.9$.
We can interpret this number by saying that the classifier is 90% sure that the image depicts a cat.
The magnitude of the probability for the predicted class is one notion of confidence.
It's not the only notion of confidence and we'll discuss different notions of uncertainty in more advanced chapters.

이 책에서 더 기술적인 내용을 다룰 때, 고정된 카테고리 - 예를 들면 고양이 또는 개 -에 대한 결과만을 예측하는 모델을 최적화하는 것은 어려워질 것입니다. 대신 확률에 기반한 모델로 표현하는 것이 훨씬 더 쉽습니다. 즉, 예제 $x$ 가 주어졌을 때, 모델은 각 레이블 $k$ 에 확률  $\hat{y}_k$ 를 할당하는 것입니다. 결과가 확률값이기 때문에 모두 양수이고, 합은 1이됩니다. 이는 $K$ 개의 카테고리에 대한 확률을 구하기 위해서는 $K-1$ 개의 숫자만 필요하다는 것을 의미합니다. 이진 분류를 예로 들어보겠습니다. 공정하지 않은 동전을 던져서 앞면이 나올 확률이 0.6 (60%)라면, 뒷면이 나올 확률은 0.4 (40%)다 됩니다. 동물 분류의 예로 돌아가보면, 분류기는 이미지를 보고 이미지가 고양이일 확률 $\Pr(y=\mathrm{cat}| x) = 0.9$ 을 출력합니다. 우리는 이 숫자를 이미지가 고양이를 포할 것이라고 90% 정도 확신한다라고 해석할 수 있습니다. 예측된 클래스에 대한 확률의 정도는 신뢰에 대한 개념을 나타냅니다. 신뢰의 개념일 뿐만 아니라, 고급 내용을 다루는 장에서는 여러 비신뢰의 개념도 논의하겠습니다.

When we have more than two possible classes, we call the problem *multiclass classification*.
Common examples include hand-written character recognition `[0, 1, 2, 3 ... 9, a, b, c, ...]`.
While we attacked regression problems by trying to minimize the L1 or L2 loss functions,
the common loss function for classification problems is called cross-entropy.
In MXNet Gluon, the corresponding loss function can be found [here](https://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.SoftmaxCrossEntropyLoss).

두 개보다 많은 클래스가 있을 경우에 우리는 이 문제를 *다중클래스 분류(multiclass classification)* 이라고 합니다. 흔한 예로는 손으로 쓴 글씨 -  `[0, 1, 2, 3 ... 9, a, b, c, ...]` - 를 인식하는 예제가 있습니다. 우리는 회귀 문제를 풀 때 L1 또는 L2 loss 함수를 최소화하는 시도를 했는데, 분류 문제에서 cross-entropy 함수가 흔히 사용되는 loss 함수는 입니다. MXNet Gluon에서는 관련된 loss 함수에 대한 내용을 [여기](https://mxnet.incubator.apache.org/api/python/gluon/loss.html#mxnet.gluon.loss.SoftmaxCrossEntropyLoss)에서 볼 수 있습니다.

Note that the most likely class is not necessarily the one that you're going to use for your decision. Assume that you find this beautiful mushroom in your backyard:

가장 그럴듯한 클래스가 결정을 위해서 사용하는 것이 꼭 아닐 수도 있습니다. 여러분의 뒷뜰에서 이 아름다운 버섯을 찾는다고 가정해보겠습니다.

![알광대 버섯(Death cap) - !](../img/death_cap.jpg)
:width:`400px`

Now, assume that you built a classifier and trained it
to predict if a mushroom is poisonous based on a photograph.
Say our poison-detection classifier outputs $\Pr(y=\mathrm{death cap}|\mathrm{image}) = 0.2$.
In other words, the classifier is 80% confident that our mushroom *is not* a death cap.
Still, you'd have to be a fool to eat it.
That's because the certain benefit of a delicious dinner isn't worth a 20% risk of dying from it.
In other words, the effect of the *uncertain risk* by far outweighs the benefit.
Let's look at this in math. Basically, we need to compute the expected risk that we incur, i.e. we need to multiply the probability of the outcome with the benefit (or harm) associated with it:

자, 사진이 주어졌을 때 버섯이 독이 있는 것인지를 예측하는 분류기를 만들어서 학습했다고 가정합니다. 우리의 독버섯 탐기 분류기의 결과가 $\Pr(y=\mathrm{death cap}|\mathrm{image}) = 0.2$ 로 나왔습니다. 다르게 말하면, 이 분류기는 80% 확신을 갖고 이 버섯이 알광대버섯(death cap)이 *아니다*라고 말하고 있습니다. 하지만, 이것을 먹지는 않을 것입니다. 이 버섯으로 만들어질 멋진 저녁식사의 가치가 독버섯을 먹고 죽을 20%의 위험보다 가치가 없기 때문입니다. 이것을 수학적으로 살펴보겠습니다. 기본적으로 우리는 예상된 위험을 계산해야합니다. 즉, 결과에 대한 확률에 그 결과에 대한 이익 (또는 손해)를 곱합니다.

$$L(\mathrm{action}| x) = \mathbf{E}_{y \sim p(y| x)}[\mathrm{loss}(\mathrm{action},y)]$$

Hence, the loss $L$ incurred by eating the mushroom is $L(a=\mathrm{eat}| x) = 0.2 * \infty + 0.8 * 0 = \infty$, whereas the cost of discarding it is $L(a=\mathrm{discard}| x) = 0.2 * 0 + 0.8 * 1 = 0.8$.

따라서 버섯을 먹을 경우 우리가 얻는 loss $L$ 은  $L(a=\mathrm{eat}| x) = 0.2 * \infty + 0.8 * 0 = \infty$ 인 반면에, 먹지 않을 경우 cost 또는 loss는  $L(a=\mathrm{discard}| x) = 0.2 * 0 + 0.8 * 1 = 0.8$ 이 됩니다.

Our caution was justified: as any mycologist would tell us, the above mushroom actually *is* a death cap.
Classification can get much more complicated than just binary, multiclass, or even multi-label classification.
For instance, there are some variants of classification for addressing hierarchies.
Hierarchies assume that there exist some relationships among the many classes.
So not all errors are equal - we prefer to misclassify to a related class than to a distant class.
Usually, this is referred to as *hierarchical classification*.
One early example is due to [Linnaeus](https://en.wikipedia.org/wiki/Carl_Linnaeus),
who organized the animals in a hierarchy.

우리의 주의 깊음이 옳았습니다. 균학자들은 위 버섯이 실제로 독버섯인 알광대버섯이라고 알려줄 것이기 때문입니다. 분류 문제는 이진 분류보다 복잡해질 수 있습니다. 즉, 다중클래스 분류 문제이거나 더 나아가서는 다중 레이블 분류의 문제일 수 있습니다.  예를 들면, 계층을 푸는 분류의 종류들이 있습니다. 계층은 많은 클래스들 사이에 관계가 있는 것을 가정합니다. 따라서, 모든 오류가 동일하지 않습니다. 즉, 너무 다른 클래스로 예약하는 것보다는 관련된 클래스로 예측하는 것을 더 선호합니다. 이런 문제를 *계층적 분류(hierarchical classification)* 이라고 합니다. 계층적 분류의 오랜 예는 [Linnaeus](https://en.wikipedia.org/wiki/Carl_Linnaeus) 가 동물을 계층으로 분류한 것을 들수 있습니다.

![Classify sharks](../img/sharks.png)
:width:`500px`

In the case of animal classification, it might not be so bad to mistake a poodle for a schnauzer,
but our model would pay a huge penalty if it confused a poodle for a dinosaur.
Which hierarchy is relevant might depend on how you plan to use the model.
For example, rattle snakes and garter snakes might be close on the phylogenetic tree,
but mistaking a rattler for a garter could be deadly.


동물 분류의 경우 푸들을 슈나이저라고 실수로 분류하는 것이 그렇게 나쁘지 않을 수 있지만, 푸들을 공룡이라고 분류한다면 그 영향이 클 수도 있습니다. 어떤 계층이 적절할지는 여러분이 모델을 어떻게 사용할 것인지에 달려있습니다. 예를 들면, 딸랑이 뱀(rattle snake)와 가터스 뱀(garter snake)은 계통 트리에서는 가까울 수 있지만, 딸랑이 뱀을 가터스 뱀으로 잘못 분류한 결과는 치명적일 수 있기 때문입니다.


#### 태깅(Tagging)

Some classification problems don't fit neatly into the binary or multiclass classification setups.
For example, we could train a normal binary classifier to distinguish cats from dogs.
Given the current state of computer vision,
we can do this easily, with off-the-shelf tools.
Nonetheless, no matter how accurate our model gets, we might find ourselves in trouble when the classifier encounters an image of the Town Musicians of Bremen.

어떤 분류의 문제는 이진 또는 다중 클래스 분류 형태로 딱 떨어지지 않습니다. 예를 들자면,  고양이와 강아지를 구분하는 정상적인 이진 분류기를 학습시킬 수 있습니다. 현재의 컴퓨터 비전의 상태를 고려하면, 이는 상용도구을 이용해서도 아주 쉽게 할 수 있습니다. 그럼에도 불구하고, 우리의 모델이 얼마나 정확하든지 상관없이 브레맨 음악대의 사진지 주어진다면 문제가 발생할 수도 있습니다.

![A cat, a roster, a dog and a donkey](../img/stackedanimals.jpg)
:width:`500px`


As you can see, there's a cat in the picture, and a rooster, a dog, a donkey and a bird, with some trees in the background.
Depending on what we want to do with our model ultimately,
treating this as a binary classification problem
might not make a lot of sense.
Instead, we might want to give the model the option
of saying the image depicts a cat *and* a dog *and* a donkey *and* a rooster *and* a bird.

사진에는 고양이, 수닭, 강아지, 당나귀 그리고 배경에는 나무들이 있습니다. 우리의 모델을 이용해서 주로 무엇을 할 것인지에 따라서, 이 문제를 이진 분류의 문제로 다룰 경우 소용이 없어질 수 있습니다. 대신, 우리는 모델이 이미지에 고양이, 강아지, 당나귀 그리고 수닭이 있는 것을 알려주도록 하고 싶을 것입니다.

The problem of learning to predict classes
that are *not mutually exclusive*
is called multi-label classification.
Auto-tagging problems are typically best described
as multi-label classification problems.
Think of the tags people might apply to posts on a tech blog,
e.g., 'machine learning', 'technology', 'gadgets',
'programming languages', 'linux', 'cloud computing', 'AWS'.
A typical article might have 5-10 tags applied
because these concepts are correlated.
Posts about 'cloud computing' are likely to mention 'AWS'
and posts about 'machine learning' could also deal with 'programming languages'.

*서로 배타적이 아닌(not mutually exclusive)* 아닌 클래스들을 예측하는 문제를 멀티-레이블 분류라고 합니다. 자동 태깅 문제가 전형적인 멀티 레이블 분류 문제입니다. 태그의 예는 기술 문서에 붙이는 태그 - 즉, '머신 러닝', '기술', '가젯', '프로그램언어', '리눅스', 클라우드 컴퓨팅', 'AWS' - 를 생각해봅시다. 일반적으로 기사는 5-10개 태그를 갖는데, 그 이유는 태그들이 서로 관련이 있기 때문입니다. '클라우드 컴퓨팅'에 대한 글은 'AWS'를 언급할 가능성이 높고, '머신 러닝' 관련 글은 '프로그램 언어'와 관련된 것일 수 있습니다.

We also have to deal with this kind of problem when dealing with the biomedical literature,
where correctly tagging articles is important
because it allows researchers to do exhaustive reviews of the literature.
At the National Library of Medicine, a number of professional annotators
go over each article that gets indexed in PubMed
to associate it with the relevant terms from MeSH,
a collection of roughly 28k tags.
This is a time-consuming process and the annotators typically have a one year lag between archiving and tagging. Machine learning can be used here to provide provisional tags
until each article can have a proper manual review.
Indeed, for several years, the BioASQ organization has [hosted a competition](http://bioasq.org/)
to do precisely this.

우리는 연구자들이 리뷰를 많이 할 수 있도록 하기 위해서 올바른 태그를 다는 것이 중요한 생물 의학 문헌을 다룰 때 이런 문제를 다뤄야합니다. 의학 국립 도서관에는 많은 전문 주석자들이 PubMed에 색인된 아티클들을 하나씩 보면서 MeSH (약 28,000개 태그의 집합) 중에 관련 된 태그를 연관시키는 일을 하고 있습니다. 이것은 시간이 많이 소모되는 일로서, 주석자들이 태그를 다는데는 보통 1년이 걸립니다. 머신 러닝을 사용해서 임시 태그를 달고, 이후에 매뉴얼 리뷰를 하는 것이 가능합니다. 실제로 몇 년 동안 [BioASQ](http://bioasq.org/) 에서는 이에 대한 대회를 열었었습니다.

#### 검색(Search)과 랭킹(ranking)

Sometimes we don't just want to assign each example to a bucket or to a real value. In the field of information retrieval, we want to impose a ranking on a set of items. Take web search for example, the goal is less to determine whether a particular page is relevant for a query, but rather, which one of the plethora of search results should be displayed for the user. We really care about the ordering of the relevant search results and our learning algorithm needs to produce ordered subsets of elements from a larger set. In other words, if we are asked to produce the first 5 letters from the alphabet, there is a difference between returning ``A B C D E`` and ``C A B E D``. Even if the result set is the same, the ordering within the set matters nonetheless.

때로는 각 예제들에 대해서 어떤 클래스 또는 실제 값을 할당하는 것만을 원하지 않습니다. 정보 검색 분야의 경우에는 아이템 집합에 순위를 매기고 싶어합니다. 웹 검색을 예로 들어보면, 목표는 특정 페이지가 쿼리에 관련이 있는지 여부를 판단하는 것보다는 검색 결과들 중에 어떤 것이 사용자에게 먼저 보여줘야하는 것에 있습니다. 관련 검색 결과의 순서에 대해서 관심이 많고, 우리의 러닝 알고리즘은 큰 집합의 일부에 대한 순서를 매길 수 있어야합니다. 즉, 알파벳에서 처음 5개 글자가 무엇인지를 물어봤을 경우,  ``A B C D E`` 를 결과로 주는 것과  ``C A B E D`` 를 결과로 주는 것에는 차이가 있습니다. 결과 집합은 같은 경우라도,  집합안에서 순서도 중요합니다.

One possible solution to this problem is to score every element in the set of possible sets along with a corresponding relevance score and then to retrieve the top-rated elements. [PageRank](https://en.wikipedia.org/wiki/PageRank) is an early example of such a relevance score. One of the peculiarities is that it didn't depend on the actual query. Instead, it simply helped to order the results that contained the query terms. Nowadays search engines use machine learning and behavioral models to obtain query-dependent relevance scores. There are entire conferences devoted to this subject.

이 문제에 대한 가능한 해결방법은 가능한 집합의 원소들에 관련성 점수를 부여하고, 점수가 높은 항목들을 검색하는 것입니다. [PageRank](https://en.wikipedia.org/wiki/PageRank) 가 관련성 점수를 적용한 예로, 특성 중 하나는 이것은 실제 쿼리에 의존하지 않는다는 것입니다. 대신, 쿼리 단어들을 포함한 결과들을 순서를 부여하는 것을 합니다. 요즘의 검색 엔진은 머신 러닝과 행동 모델을 이용해서 쿼리와 관련된 관련성 점수를 얻습니다. 이 주제만 다루는 컨퍼런스가 있습니다.


<!-- Add / clean up-->

#### Recommender systems

Recommender systems are another problem setting that is related to search and ranking. The problems are  similar insofar as the goal is to display a set of relevant items to the user. The main difference is the emphasis on *personalization* to specific users in the context of recommender systems. For instance, for movie recommendations, the results page for a SciFi fan and the results page for a connoisseur of Woody Allen comedies might differ significantly.

추천 시스템은 검색과 랭킹과 관련된 또다른 문제 세팅입니다. 사용자에게 관련된 상품을 보여주는 것이 목표이기에 문제는 비스합니다. 주요 차이점은 추천 시스템에서는 특정 사용자에 대한 *개인화(personalization)* 를 중점으로 한다는 것입니다. 예를 들어, 영화 추천의 경우에는 SciFi 에 대한 결과 페이지와 우디 엘런 코미디에 대한 결과 페이지가 아주 다르게 나옵니다.

Such problems occur, e.g. for movie, product or music recommendation. In some cases, customers will provide explicit details about how much they liked the product (e.g. Amazon product reviews). In some other cases, they might simply provide feedback if they are dissatisfied with the result (skipping titles on a playlist). Generally, such systems strive to estimate some score $y_{ij}$, such as an estimated rating or probability of purchase, given a user $u_i$ and product $p_j$.


이런 문제는 영화, 제품 또는 음악 추천에서 발생합니다. 어떤 경우에는 고객은 얼마나 그 제품을 좋아하는지를 직접 알려주기도 합니다 (예를 들면 아마존의 제품 리뷰). 어떤 경우에는 결과에 만족하지 못한 경우 피드백을 간단하게 주기도 합니다 (재생 목록의 타이틀을 건너뛰는 형식으로). 일반적으로는 이런 시스템은 어떤 점수 $y_{ij}$ 를 예측하고자 하는데, 이 예측은 사용자 $u_i$ 와 제품  $p_j$가 주어졌을 때 예상된 평점 또는 구매 확률이 될 수 있습니다.

Given such a model, then for any given user, we could retrieve the set of objects with the largest scores $y_{ij}$, which are then used as a recommendation. Production systems are considerably more advanced and take detailed user activity and item characteristics into account when computing such scores. The following image is an example of deep learning books recommended by Amazon based on personalization algorithms tuned to the author's preferences.

이런 모델은 어떤 사용자에 대해서 가장 큰 점수  $y_{ij}$ 를 갖는 객체들의 집합을 찾아주는데, 이것이 추천으로 사용됩니다. 운영 시스템은 매우 복잡하고, 점수를 계산할 때 자세한 사용자의 활동과 상품의 특징까지 고려합니다. 아래 이미지는 아마존이 저자들의 관심을 반영한 개인화 알고리즘을 기반으로 아마존이 추천한 딥러닝 책들의 예입니다.

![Deep learning books recommended by Amazon.](../img/deeplearning_amazon.png)


#### 시퀀스 러닝(Sequence Learning)

So far we've looked at problems where we have some fixed number of inputs
and produce a fixed number of outputs.
Before we considered predicting home prices from a fixed set of features:
square footage, number of bedrooms, number of bathrooms, walking time to downtown.
We also discussed mapping from an image (of fixed dimension),
to the predicted probabilities that it belongs to each of a fixed number of classes,
or taking a user ID and a product ID, and predicting a star rating.
In these cases, once we feed our fixed-length input into the model to generate an output,
the model immediately forgets what it just saw.

지금까지는 고정된 개수의 입력을 받아서 고정된 개수의 결과를 출력하는 문제를 봤습니다. 면적, 침실 개수, 욕실 개수, 다운타운까지 도보 거리와 같은 고정된 특성들로 부터 주택 가격을 예측하는 것을 고려하기 앞서서, (고정된 차원의) 이미지를 고정된 수의 클래스들에 속할 예측된 확률로 매핑하는 것, 사용자 ID와 제품 ID를 받아서 별점수를 예측하는 문제들도 논의햇습니다. 이 경우들은, 우리가 고정된 길이의 입력을 모델에 넣어서 결과를 얻으면, 모델은 무엇을 봤는지 바로 잊어버립니다.

This might be fine if our inputs truly all have the same dimensions
and if successive inputs truly have nothing to do with each other.
But how would we deal with video snippets?
In this case, each snippet might consist of a different number of frames.
And our guess of what's going on in each frame
might be much stronger if we take into account
the previous or succeeding frames.
Same goes for language.
One popular deep learning problem is machine translation:
the task of ingesting sentences in some source language
and predicting their translation in another language.

만약 입력이 정말로 모두 같은 차원을 갖거나, 연속된 입력들이 서로 관련이 아무런 관련이 없을 경우에는 문제가 없습니다. 하지만, 비디오 영상의 단편을 다뤄야 한다면 어떨까요? 이 경우에는 각 단편은 서로 다른 여러 프레임들로 구성되어 있을 거십니다. 각 프레임에서 무엇이 일어나고 있는지에 대한 추측은 이전 또는 이후 프레임을 고려할 경우에 더 확실할 것입니다. 언어도 마찬가지 입니다. 기계번역은 유명한 딥러닝 문제들 중에 하나입니다: 이는, 어떤 언어의 문장을 받아서, 다른 언어로 번역을 추측하는 것입니다.

These problems also occur in medicine.
We might want a model to monitor patients in the intensive care unit and to fire off alerts
if their risk of death in the next 24 hours exceeds some threshold.
We definitely wouldn't want this model to throw away everything it knows about the patient history each hour,
and just make its predictions based on the most recent measurements.

이와 같은 문제는 의학에서도 찾을 수 있습니다. 우리는 중환자실의 환자를 모니터링하면서, 24시간 안에 생명에 대한 위험은 어느 정도를 넘을 경우 경고를 발생하는 모델을 원할 수 있습니다. 당연히 이 모델이 사용했던 지난 몇 시간 동안의 기록을 버리고, 오직 가장 최근의 기록만을 사용해서 예측을 하는 것을 원하지는 않을 것입니다.

These problems are among the most exciting applications of machine learning
and they are instances of *sequence learning*.
They require a model to either ingest sequences of inputs
or to emit sequences of outputs (or both!).
These latter problems are sometimes referred to as ``seq2seq`` problems.
Language translation is a ``seq2seq`` problem.
Transcribing text from spoken speech is also a ``seq2seq`` problem.
While it is impossible to consider all types of sequence transformations,
a number of special cases are worth mentioning:

머신 러닝의 아주 흥미로운 응용들이 이런 문제들에 속합니다. 이런 문제들은 *시퀀스 러닝(sequence learning)*의 예들입니다. 입력 시퀀스들을 받거나, 출력 시퀀스를 생성하는 (또는 모두) 모델이 필요합니다. 종종 우리는 이런 문제들을 `seq2seq` 문제라고 합니다. 언어 번역은 `seq2seq` 문제입니다. 음성으로 부터 텍스트를 추출하는 것 또한 `seq2seq` 문제입니다. 시퀀스 변환(sequence transformation)의 모든 종류를 고려하기는 어렵지만, 특별한 몇 가지 사례는 여기서 언급할 가치가 있습니다.


##### 태깅(Tagging)과 파싱(Parsing)

This involves annotating a text sequence with attributes. In other words, the number of inputs and outputs is essentially the same. For instance, we might want to know where the verbs and subjects are. Alternatively, we might want to know which words are the named entities. In general, the goal is to decompose and annotate text based on structural and grammatical assumptions to get some annotation. This sounds more complex than it actually is. Below is a very simple example of annotating a sentence with tags indicating which words refer to named entities.

이것은 텍스트 시퀀스에 속성들로 주석을 다는 것입니다. 이 때, 입력과 출력의 개수가 정확하게 같습니다. 예를 들면, 동사와 주어가 어디에 있는지를 알기를 원합니다. 또는, 어떤 단어가 이름을 갖는 개체인지를 알고자 할 수 있습니다. 일반적으로, 이런 예들에서는 구조나 문법적인 추정에 근거해서 분해(decompose)를 하고 주석을 다는 것이 목표입니다. 다음은 문장이 주어졌을 때 어떤 단어가 이름을 갖는 개체를 가르키는지를 태그로 주석을 다는 아주 간단한 예제입니다.

```text
Tom has dinner in Washington with Sally.
Ent  -    -    -     Ent      -    Ent
```


##### 자동 음성 인식(Automatic Speech Recognition)

With speech recognition, the input sequence $x$ is the sound of a speaker,
and the output $y$ is the textual transcript of what the speaker said.
The challenge is that there are many more audio frames (sound is typically sampled at 8kHz or 16kHz) than text, i.e. there is no 1:1 correspondence between audio and text,
since thousands of samples correspond to a single spoken word.
These are ``seq2seq`` problems where the output is much shorter than the input.

음성 인식에서는 입력 시퀀스 $x$ 는 화자의 음성이고, 출력 $y$ 는 화자가 말한 원문의 기록입니다. 텍스트보다 오디오 프레임의 수가 훨신 더 많다는 점이 챌린지입니다. 즉, 수천개의 오디오 샘플이 하나의 발화된 단어에 해당되기 때문에, 오디오와 텍스트의 1:1 대응이 없습니다.

![`-D-e-e-p- L-ea-r-ni-ng-`](../img/speech.png)
:width:`700px`

##### 텍스트를 음성으로 변환하기(Text to Speech)

Text-to-Speech (TTS) is the inverse of speech recognition.
In other words, the input $x$ is text
and the output $y$ is an audio file.
In this case, the output is *much longer* than the input.
While it is easy for *humans* to recognize a bad audio file,
this isn't quite so trivial for computers.

Text-to-Speech(TTS)는 음성 인식과 정반대입니다. 즉, 입력 $x$는 텍스트이고, 출력 $y$는 오디오 파일입니다. 이 경우, 출력은 입력보다 *훨신 깁니다*. *사람*이 잘못된 음성 파일을 알아내는 것은 쉽지만, 컴퓨터에게는 쉬운일이 아닙니다.

##### 기계 번역(Machine Translation)

Unlike the case of speech recognition, where corresponding inputs and outputs occur in the same order (after alignment),
in machine translation, order inversion can be vital.
In other words, while we are still converting one sequence into another,
neither the number of inputs and outputs
nor the order of corresponding data points
are assumed to be the same.
Consider the following illustrative example of the obnoxious tendency of Germans

대응하는 입력과 출력이 같은 순서인 음성 인식과는 다르게, 기계 번역의 경우 순서가 뒤바뀌는 것이 중요할 수 있습니다. 즉, 하나의 시퀀스를 다른 시퀀스로 바꾸는 일을 하지만, 입력과 출력의 개수나 대응하는 데이터 포인트들의 순서가 같다고 가정하지 않습니다. 동사를 문장의 맨 끝에 놓는 독일인의 경향에 대한 예제를 생각해보겠습니다.

<!-- Alex writing here -->
to place the verbs at the end of sentences.

```text
독일어:           Haben Sie sich schon dieses grossartige Lehrwerk angeschaut?
영어:          Did you already check out this excellent tutorial?
잘못된 배치:  Did you yourself already this excellent tutorial looked-at?
```

A number of related problems exist.
For instance, determining the order in which a user reads a webpage
is a two-dimensional layout analysis problem.
Likewise, for dialogue problems,
we need to take world-knowledge and prior state into account.
This is an active area of research.

비슷한 문제는 아주 많이 존재합니다. 예를 들면, 사용자가 웹 페이지를 어떤 순서로 읽는지를 결정하는 것은 2차원적인 레이아웃 분석 문제입니다. 비슷하게 대화 문제에서는 세상에 대한 지식과 이전 상태를 고려해야 합니다. 이것들은 활발한 연구 영역입니다.

### 비지도 학습(Unsupervised learning)

All the examples so far were related to *Supervised Learning*,
i.e. situations where we feed the model
a bunch of examples and a bunch of *corresponding target values*.
You could think of supervised learning as having an extremely specialized job and an extremely anal boss.
The boss stands over your shoulder and tells you exactly what to do in every situation until you learn to map from situations to actions.
Working for such a boss sounds pretty lame.
On the other hand, it's easy to please this boss. You just recognize the pattern as quickly as possible and imitate their actions.


지금까지 모든 예제들은 *지도 학습(supervised learning)*과 관련된 것들 였습니다. 즉, 모델에 예제들과 *관련된 타겟 값들*을 입력하는 학습였습니다. 지도 학습을 굉장히 특화된 일과 매우 분석적인 상사를 갖는 것으로 생각할 수 있습니다. 상사는 여러분의 어깨 넘어에서 모든 상황마다 정확히 무엇을 해야하는지를 알려주며, 이는 여러분이 상황을 행동으로 연결하는 것을 배울 때까지 지속됩니다. 그런 상사와 일하는 것은 아주 귀찮은 것입니다. 다른 한편으로는 이런 상사를 기쁘게 만드는 것은 쉽습니다. 패턴을 가능한 빨리 인지해서 그들의 행동을 모방하면 됩니다.

In a completely opposite way,
it could be frustrating to work for a boss
who has no idea what they want you to do.
However, if you plan to be a data scientist, you'd better get used to it.
The boss might just hand you a giant dump of data and tell you to *do some data science with it!*
This sounds vague because it is.
We call this class of problems *unsupervised learning*,
and the type and number of questions we could ask
is limited only by our creativity.
We will address a number of unsupervised learning techniques in later chapters. To whet your appetite for now, we describe a few of the questions you might ask:

이와는 완전히 반대인 경우, 즉 여러분이 무엇을 해야할지를 전혀 모르는 상사와 일하는 것이 실망스러울 수 있습니다. 하지만, 여러분이 데이터 과학자가 되기를 계획하고 있다면, 이에 익숙해져야 합니다. 여러분의 상사는 엄청나게 많은 데이터를 주면서, *이것으로 데이터 과학을 좀 해봐!*라고 할수도 있습니다. 이것은 모호하기 때문에, 모호하게 들립니다. 이런 문제 종류를 우리는 *비지도 학습(unsupervised learning)*이라고 하며, 우리가 물을 수 있는 질문의 종류와 수는 우리들의 창의성에 달려있습니다. 다음 장들에서 다양한 비지도 학습 기법에 대해서 알아볼 예정이나, 여러분의 궁금증을 달래주기 위해서, 여러분이 물을 몇가지 질문들에 대해서 설명하겠습니다.

* Can we find a small number of prototypes that accurately summarize the data? Given a set of photos, can we group them into landscape photos, pictures of dogs, babies, cats, mountain peaks, etc.? Likewise, given a collection of users' browsing activity, can we group them into users with similar behavior? This problem is typically known as **clustering**.
* Can we find a small number of parameters that accurately capture the relevant properties of the data? The trajectories of a ball are quite well described by velocity, diameter, and mass of the ball. Tailors have developed a small number of parameters that describe human body shape fairly accurately for the purpose of fitting clothes. These problems are referred to as **subspace estimation** problems. If the dependence is linear, it is called **principal component analysis**.
* Is there a representation of (arbitrarily structured) objects in Euclidean space (i.e. the space of vectors in $\mathbb{R}^n$) such that symbolic properties can be well matched? This is called **representation learning** and it is used to describe entities and their relations, such as Rome - Italy + France = Paris.
* Is there a description of the root causes of much of the data that we observe? For instance, if we have demographic data about house prices, pollution, crime, location, education, salaries, etc., can we discover how they are related simply based on empirical data? The field of **directed graphical models** and **causality** deals with this.
* An important and exciting recent development is **generative adversarial networks**. They are basically a procedural way of synthesizing data. The underlying statistical mechanisms are tests to check whether real and fake data are the same. We will devote a few notebooks to them.

* 데이터를 정확하게 요약하는 작은 개수의 프로토타입을 찾을 수 있을까요? 사진들이 주어졌을 때, 사진들을 풍경 사진, 강아지 사진, 아기들, 고양이들, 산정상 등으로 그룹을 나눌 수 있을까요? 비슷하게, 사용자의 브라우징 행동들에 대한 데이터가 주어졌을 때, 비슷한 행동을 하는 사용자들로 그룹을 나눌 수 있나요? 이런 문제는 일반적으로 **클러스터링(clustering)**이라고 합니다.
* 데이터에 대해서 관련있는 특성을 정확하게 포착하는 몇 개의 파라미터들 찾을 수 있을까요? 공의 궤적은 공의 속도, 직경, 질량으로 아주 잘 설명됩니다. 재봉사는 옷을 맞출 목적에 따라서 사람 몸 모양을 꽤 정확하게 설명하는 몇 개의 파라미터를 만들었습니다. 이 문제들은 **부분공간 추정(subspace estimation)** 문제로 알려져 있습니다. 의존이 선형인 경우에는 우리는 이를 **주성분 분석(principal component analysis)**이라고 합니다.
* 유클리디인 공간에서 (임의로 조직화된) 객체에 대해서 심볼릭 성질이 잘 일치하는 표현이 있나요? 이는 **표현 학습(representation learning)**이라고 불리며, 엔터티들과 그것들의 관계를 설명하는데 사용돕니다. 예를 들면, Rome - Italy + France = Paris.
* 우리가 관찰한 많은 양의 데이터에 대한 주원인(root cause)에 대한 설명이 있나요? 예를 들면, 주택 가격, 공해, 범죄, 위치, 교육, 급여 등에 대한 인구 통계학 데이터가 있을 때, 단순히 경험적인 데이터를 기반으로 이것들이 어떻게 연관되어 있는지를 찾을 수 있나요? **방향성 그래프 모델(directed graphical model)**과 **인과 관계(causality)**가 이것을 다룹니다.
* **Generative adversarial network**는 최근에 개발된 중요하고 흥미로운 네트워크입니다. 기본적으로는 이것은 데이터를 합성하는 단계적인 방법입니다. 근본적인 통계적 메카니즘은 실제 데이터와 가짜 데이터가 같은지를 점검하는 테스트들입니다. 나중에 몇 개의 노트북에 걸쳐서 살펴보도록 하겠습니다.


### 환경과 상호 작용하기(Interacting with an Environment)

So far, we haven't discussed where data actually comes from,
or what actually *happens* when a machine learning model generates an output.
That's because supervised learning and unsupervised learning
do not address these issues in a very sophisticated way.
In either case, we grab a big pile of data up front,
then do our pattern recognition without ever interacting with the environment again.
Because all of the learning takes place after the algorithm is disconnected from the environment,
this is called *offline learning*.
For supervised learning, the process looks like this:

지금까지는 데이터가 실제로 어디서 왔는지 또는 머신 러닝 모델이 결과를 만들 때 실제로 어떤 일이 *일어나는지*를 논의하지 않았습니다. 그 이유는 지도 학습과 비지도 학습은 이런 이슈를 아주 복잡한 방법으로 해결하지 않기 때문입니다. 둘 중 어떤 경우에도, 우리는 많은 양의 데이터를 받아서, 환경과 상호 작용을 하지 않고 패턴 인식을 수행합니다. 이런 모든 학습은 알고리즘이 환경와 분리된 상태에서 일어나기 때문에, 이를 *오프라인 학습(offline learning)*이라고 합니다. 지도 학습의 경우, 프로세스는 다음과 같습니다.

![Collect data for supervised learning from an environment.](../img/data-collection.svg)


This simplicity of offline learning has its charms.
The upside is we can worry about pattern recognition in isolation without these other problems to deal with,
but the downside is that the problem formulation is quite limiting.
If you are more ambitious, or if you grew up reading Asimov's Robot Series,
then you might imagine artificially intelligent bots capable not only of making predictions,
but of taking actions in the world.
We want to think about intelligent *agents*, not just predictive *models*.
That means we need to think about choosing *actions*, not just making *predictions*.
Moreover, unlike predictions, actions actually impact the environment.
If we want to train an intelligent agent,
we must account for the way its actions might
impact the future observations of the agent.

오프라인 학습의 간결함은 매력적입니다. 좋은 점은 다른 문제들을 고려할 필요없는 격리된 상태에서 패턴 인식을 하면 된다는 것이지만, 단점은 문제를 공식화(problem formulation)하는 것이 아주 제한적이라는 것입니다. 여러분이 더 의욕적이거나, Asimov's Robot Series를 읽으면서 자랐다면, 예측을 할 뿐만 아니라 세상에서 행동을 취할 수 있는 인공지능 봇을 떠올릴 수도 있습니다. 이는 단지 예측을 하는 것이 아니라 행동을 선택하는 것을 생각해봐야한다는 것을 뜻합니다. 나아가 예측과는 달리 행동은 실제로 환경에 영향을 미칩니다. 우리가 지능적인 에이전트를 학습시키기를 원한다면, 행동이 에이전트의 미래 관찰에 미치는 영향에 대해서도 설명해야합니다.


Considering the interaction with an environment opens a whole set of new modeling questions. Does the environment:

* remember what we did previously?
* want to help us, e.g. a user reading text into a speech recognizer?
* want to beat us, i.e. an adversarial setting like spam filtering (against spammers) or playing a game (vs an opponent)?
* not  care (as in most cases)?
* have shifting dynamics (steady vs. shifting over time)?

환경과의 상호 작용을 고려하는 것은 완전히 새로운 모델링에 대한 질문을 가져옵니다. 환경이,

* 우리가 이전에 행한 것을 기억하나요?
* 우리를 돕기를 원하나요? 즉, 사용자가 음성 인식기에 텍스트를 읽는 경우.
* 우리를 이기기를 원하나요? 즉, 스팸 필터(스팸 발송자에 대항하는) 같은 적대적 설정 또는 (상대와) 게임을 플레이하는 것.
* not  care (as in most cases)?
* 변하는 역동성을 가지고 있나요(시간에 따라 그대로인지 변하는지)?

This last question raises the problem of *covariate shift*,
(when training and test data are different).
It's a problem that most of us have experienced when taking exams written by a lecturer,
while the homeworks were composed by his TAs.
We'll briefly describe reinforcement learning and adversarial learning,
two settings that explicitly consider interaction with an environment.

마지막 질문은 공변량 변화(covariate shift) 문제를 일으킵니다.(학습 데이터와 테스트 데이터가 다를 때) 숙제는 TA가 제출하는 반면에, 시험은 강의를 하는 사람이 낸 문제를 풀 때 이런 것을 경험했을 것입니다. 환경과 상호 작용을 명시적으로 고려하는 강화 학습(reinforcement learning)와 적대적 학습(adversarial learning)에 대해서 간단히 살펴보겠습니다.

### 강화 학습(Reinforcement learning)

If you're interested in using machine learning to develop an agent that interacts with an environment and takes actions, then you're probably going to wind up focusing on *reinforcement learning* (RL).
This might include applications to robotics, to dialogue systems,
and even to developing AI for video games.
*Deep reinforcement learning* (DRL), which applies deep neural networks
to RL problems, has surged in popularity.
The breakthrough [deep Q-network that beat humans at Atari games using only the visual input](https://www.wired.com/2015/02/google-ai-plays-atari-like-pros/) ,
and the [AlphaGo program that dethroned the world champion at the board game Go](https://www.wired.com/2017/05/googles-alphago-trounces-humans-also-gives-boost/) are two prominent examples.

환경과 작용을 하면서 행동을 위하는 에이전트를 만드는 머신 러닝에 관심이 있다면, 여러분은 아맞도 *강화 학습(reinforcement learning, RL)*에 집중할 것입니다. 로보틱스, 분석 시스템 심지어는 비디오 게임에 대한 AI 개발에 적용될 수 있습니다. 딥 뉴럴 네트워크를 RL 문제에 적용한 *딥 강화 학습(deep reinforcement learning, DRL)*이 인기가 높습니다. [deep Q-network that beat humans at Atari games using only the visual input](https://www.wired.com/2015/02/google-ai-plays-atari-like-pros/)와 [AlphaGo program that dethroned the world champion at the board game Go](https://www.wired.com/2017/05/googles-alphago-trounces-humans-also-gives-boost/)이 유명한 두 예입니다.


Reinforcement learning gives a very general statement of a problem,
in which an agent interacts with an environment over a series of *time steps*.
At each time step $t$, the agent receives some observation $o_t$ from the environment,
and must choose an action $a_t$ which is then transmitted back to the environment.
Finally, the agent receives a reward $r_t$ from the environment.
The agent then receives a subsequent observation, and chooses a subsequent action, and so on.
The behavior of an RL agent is governed by a *policy*.
In short, a *policy* is just a function that maps from observations (of the environment) to actions.
The goal of reinforcement learning is to produce a good policy.

강화 학습은 에이전트가 일련의 *시간 단계(time steps)*에 걸쳐서 환경과 작용을 문제에 대한 일반적인 기술을 정의합니다. 각 시간 단계 $t$ 마다, 에이전트는 환경으로 부터 어떤 관찰 $o_t$ 를 받아서, 행동 $a_t$을 선택해야하고, 이 행동은 다시 환경으로 전달이 됩니다. 그리고 나면 에이전트는 환경으로 부터 보상 $r_t$를 받습니다. 그 후, 에이전트는 다음 관찰을 받아서, 다음 행동을 취하는 것을 반복합니다. RL 에이전트의 행동은 *정책(policy)*에 의해서 정의됩니다. 간단하게 말하면, *정책(policy)*은 (환경으로 부터 얻은) 관찰을 행동으로 매핑시키는 함수입니다. 강화 학습의 목표는 좋은 정책을 만드는 것입니다.

![The interaction between reinforcement learning and an environment.](../img/rl-environment.svg)

It's hard to overstate the generality of the RL framework.
For example, we can cast any supervised learning problem as an RL problem.
Say we had a classification problem.
We could create an RL agent with one *action* corresponding to each class.
We could then create an environment which gave a reward
that was exactly equal to the loss function from the original supervised problem.

RL 프레임워크의 일반성을 과장하는 것은 어렵습니다. 예를 들어, 임의의 강화 학습 문제를 RL 문제로 바꿀 수 있습니다. 분류의 문제를 예로 들어보겠습니다. 우리는 한 *행동(action)*이 각 클래스 대응하는 에이전트를 만들 수 있습니다. 그리고는 원래의 지도 학습에서 사용하는 손실 함수(loss function)와 완전히 같은 보상을 주는 환경을 생성합니다.


That being said, RL can also address many problems that supervised learning cannot.
For example, in supervised learning we always expect
that the training input comes associated with the correct label.
But in RL, we don't assume that for each observation,
the environment tells us the optimal action.
In general, we just get some reward.
Moreover, the environment may not even tell us which actions led to the reward.

즉, RL은 지도 학습이 해결하지 못하는 많은 문제를 해결할 수 있습니다. 예를 들면, 지도 학습에서는 학습 입력에 대한 정확한 레이블이 있어야합니다. 하지만 RL의 경우에는 관찰에 대해서 환경은 최적의 행동을 알려준다고 가정하지 않습니다. 일반적으로 우리는 어떤 보상을 받을 뿐 입니다. 즉, 환경은 어떤 행동이 보상을 받을 수 있는지 조차 알려주지 않을 수도 있습니다.

Consider for example the game of chess.
The only real reward signal comes at the end of the game when we either win, which we might assign a reward of 1,
or when we lose, which we could assign a reward of -1.
So reinforcement learners must deal with the *credit assignment problem*.
The same goes for an employee who gets a promotion on October 11.
That promotion likely reflects a large number of well-chosen actions over the previous year.
Getting more promotions in the future requires figuring out what actions along the way led to the promotion.

체스게임의 예를 생각해보면,
실제의 보상 신호는 게임이 끝났을 때나옵니다. 이기면 1의 보상을 , 지면 -1의 보상을 줄 수 있습니다.
그래서 강화학습은 학습자는  *credit assignment problem*을 다루어야 합니다. 같은 방식으로 10월 11일에 승진한 직원이 있다면, 이 승진은
이전 년도에 걸쳐 수많은 잘 선택된 행동(Action)이 반영된 것과 같습니다. 앞으로 더 많은 프로모션을 하기 위해선, 어떠한 행동들이 프로모션에 영향을 미치는지 알아 내야 합니다.

Reinforcement learners may also have to deal with the problem of partial observability.
That is, the current observation might not tell you everything about your current state.
Say a cleaning robot found itself trapped in one of many identical closets in a house.
Inferring the precise location (and thus state) of the robot
might require considering its previous observations before entering the closet.

강화학습 학습자는 또한 부분적인 관찰가능성의 문제를 다룰 수 있어야 합니다. 그것은, 현재 관찰된 사항이 현재 상태의 모든 정보를 말하고 있지 않을 수 있기 때문입니다.
청소로봇이 집안의 옷장에 자주 갇히는 것으로 나타났습니다. 정확한 로봇의 위치를 추정하는 것은 옷장에 들어가기 전에 이전의 관찰 정보를 고려하도록 해야 할 수 있습니다.

Finally, at any given point, reinforcement learners might know of one good policy,
but there might be many other better policies that the agent has never tried.
The reinforcement learner must constantly choose
whether to *exploit* the best currently-known strategy as a policy,
or to *explore* the space of strategies,
potentially giving up some short-run reward in exchange for knowledge.

마지막으로, 어떠한 주어진 점수에 따라, 강화학습자는 하나의 좋은 정책(Policy)를 알게 됩니다. 그러나 에이전트(agent)가 시도해 보지 않은, 많은 더 좋은 정책들이 있을 수 있습니다. 강화학습 러너는 항상, 지금까지 알려진 최적의 전략에 따라 *탐험*을 할지, 이외의 전략 공간을 *모험*을 할지 선택해야 합니다.


#### MDPs, bandits, and friends

The general reinforcement learning problem
is a very general setting.
Actions affect subsequent observations.
Rewards are only observed corresponding to the chosen actions.
The environment may be either fully or partially observed.
Accounting for all this complexity at once may ask too much of researchers.
Moreover not every practical problem exhibits all this complexity.
As a result, researchers have studied a number of *special cases* of reinforcement learning problems.

일반적인 강화학습 문제는 매우 일반적인 설정입니다.
액션들은 이후의 관찰들에 영향을 미칩니다.
선택된 액션과 일치하는 상황이 관찰될 때에만 보상이 이루어 집니다. 
환경은 완전하게 혹은 부분적으로 관찰될 수 있습니다.
이 모든 복잡도를 한번에 설명하는 것은 매우 많은 연구자들에게 물어봐야 할 수도 있다.
더욱이 모든 실제 문제들이 이러한 복잡도를 나타내지도 않습니다.
그러한 결과로, 연구자들은 강화학습 문제들 중 몇개의 *특별한*를 연구 하였다.

When the environment is fully observed,
we call the RL problem a *Markov Decision Process* (MDP).
When the state does not depend on the previous actions,
we call the problem a *contextual bandit problem*.
When there is no state, just a set of available actions with initially unknown rewards,
this problem is the classic *multi-armed bandit problem*.

완전히 관찰 가능한 환경일 때, 우리는 RL 문제를 *Markov Decision Process* (MDP)라고 부릅니다.
이전 액션을 의존하지 않을 때, 우리는 문제를 *contextual bandit problem* 이라고 부릅니다.
상태가 없고, 초기의 알수 없는 보상을 갖는 가능한 액션 조합만이 있을 때, 이 문제는 고전적인 *multi-armed bandit problem* 입니다.

# 딥러닝 소개

2016년, 네임드 데이터 과학자인 죠엘 그루스(Joel Grus)는 한 유명 인터넷 기업에서 [면접](http://joelgrus.com/2016/05/23/fizz-buzz-in-tensorflow/)을 보았습니다. 보통 그러하듯이 인터뷰 담당자는 그의 프로그래밍 기술을 평가하는 문제를 냈습니다. 간단한 어린이 게임인 FizzzBuzz를 구현하는 것이 과제였습니다. 그 안에서 플레이어는 1부터 카운트하면서 3으로 나눌 수 있는 숫자는 'fizz' 로, 5로 나눌 수 있는 숫자는 'buzz' 로 바꿉니다. 15로 나눌 수 있는 숫자는 'FizzBuzz' 가 됩니다. 즉, 플레이어는 시퀀스를 생성합니다.

```
1 2 fizz 4 buzz fizz 7 8 fizz buzz 11 ...
```

전혀 예상하지 못한 일이 벌어졌습니다. 거의 몇 줄의 Python 코드로 *알고리즘* 을 구현해서 문제를 해결하는 대신, 그는 데이터를 활용한 프로그램으로 문제를 풀기로 했습니다. 그는 (3, fizz), (5, buzz), (7, 7), (2, 2), (15, fizzbuzz) 의 쌍을 활용하여 분류기를 학습시켰습니다. 그가 작은 뉴럴 네트워크(neural network)를 만들고, 그것을 이 데이터를 활용하여 학습시켰고 그 결과 꽤 높은 정확도를 달성하였습니다(면접관이 좋은 점수를 주지 않아서 채용되지는 못했습니다).

이 인터뷰와 같은 상황은 프로그램 설계가 데이터에 의한 학습으로 보완 되거나 대체되는 컴퓨터 과학의 획기적인 순간입니다. 예로 든 상황은 면접이라서가 아니라 어떠한 목표를 손쉽게 달성 할 수 있게 해 준다는 점에서 중요성을 가집니다. 일반적으로는 위에서 설명한 오버스러운 방식으로 FizzBuzz를 해결하지는 않겠지만, 얼굴을 인식하거나, 사람의 목소리 또는 텍스트로 감정을 분류하거나, 음성을 인식할 때는 완전히 다른 이야기입니다. 좋은 알고리즘, 많은 연산 장치 및 데이터, 그리고 좋은 소프트웨어 도구들로 인해 이제는 대부분의 소프트웨어 엔지니어가 불과 10년전에는 최고의 과학자들에게도 너무 도전적이라고 여겨졌던 문제를 해결하는 정교한 모델을 만들 수 있게 되었습니다.

이 책은 머신러닝을 구현하는 여정에 들어선 엔지니어를 돕는 것을 목표로 합니다. 우리는 수학, 코드, 예제를 쉽게 사용할 수 있는 패키지로 결합하여 머신러닝을 실용적으로 만드는 것을 목표로 합니다. 온라인으로 제공되는 Jupyter 노트북 예제들은 노트북이나 클라우드 서버에서 실행할 수 있습니다. 우리는 이를 통해서 새로운 세대의 프로그래머, 기업가, 통계학자, 생물학자 및 고급 머신러닝 알고리즘을 배포하는 데 관심이 있는 모든 사람들이 문제를 해결할 수 있기를 바랍니다.

## 데이터를 활용하는 프로그래밍

코드를 이용하는 프로그래밍과 데이터를 활용하는 프로그래밍의 차이점을 좀 더 자세히 살펴 보겠습니다. 이 둘은 보이는 것보다 더 심오하기 때문입니다. 대부분의 전통적인 프로그램은 머신러닝을 필요로 하지 않습니다. 예를 들어 전자 레인지용 사용자 인터페이스를 작성하려는 경우 약간의 노력으로 몇 가지 버튼을 설계할 수 있습니다. 다양한 조건에서 전자 레인지의 동작을 정확하게 설명하는 몇 가지 논리와 규칙을 추가하면 완료됩니다. 마찬가지로 사회 보장 번호의 유효성을 확인하는 프로그램은 여러 규칙이 적용되는지 여부를 테스트하면 됩니다. 예를 들어, 이러한 숫자는 9 자리 숫자를 포함해야 하며 000으로 시작하지 않아야 한다와 같은 규칙입니다.

위의 두 가지 예에서 프로그램의 논리를 이해하기 위해 현실 세계에서 데이터를 수집할 필요가 없으며, 그 데이터의 특징을 추출할 필요가 없다는 점에 주목할 가치가 있습니다. 많은 시간이 있다면, 우리의 상식과 알고리즘 기술은 우리가 작업을 완료하기에 충분합니다.

우리가 전에 관찰 한 바와 같이, 심지어 최고의 프로그래머의 능력을 넘는 많은 예가 있지만, 많은 아이들, 심지어 많은 동물들이 쉽게 그들을 해결할 수 있습니다. 이미지에 고양이가 포함되어 있는지 여부를 감지하는 문제를 고려해보겠습니다. 어디서부터 시작해야 할까요? 이 문제를 더욱 단순화해 보겠습니다. 모든 이미지가 동일한 크기 (예, 400x400 픽셀)이라고 가정하고, 각 픽셀이 빨강, 녹색 및 파랑 값으로 구성된 경우 이미지는 480,000 개의 숫자로 표시됩니다. 우리의 고양이 탐지기가 관련된 정보가 어디에 있는지 결정하는 것은 불가능합니다. 그것은 모든 값의 평균일까요? 네 모서리의 값일까요? 아니면 이미지의 특정 지점일까요? 실제로 이미지의 내용을 해석하려면 가장자리, 질감, 모양, 눈, 코와 같은 수천 개의 값을 결합 할 때만 나타나는 특징을 찾아야합니다. 그래야만 이미지에 고양이가 포함되어 있는지 여부를 판단할 수 있습니다.

다른 전략은 최종 필요성에 기반한 솔루션을 찾는 것입니다. 즉, 이미지 예제 및 원하는 응답 (cat, cat 없음) 을 출발점으로 사용하여 *데이터로 프로그래밍하는 것*입니다. 우리는 고양이의 실제 이미지 (인터넷에서 인기있는 주제)들과 다른 것들을 수집할 수 있습니다. 이제 우리의 목표는 이미지에 고양이가 포함되어 있는지 여부를 *배울 수 있는* 함수를 찾는 것입니다. 일반적으로 함수의 형태 (예, 다항식)는 엔지니어에 의해 선택되며 그 함수의 파라미터들은 데이터에서 *학습*됩니다.

일반적으로 머신러닝은 고양이 인식과 같은 문제를 해결하는 데 사용할 수 있는 다양한 종류의 함수를 다룹니다. 딥 러닝은 특히 신경망에서 영감을 얻은 특정 함수의 클래스를 사용해서, 이것을 특별한 방법으로 학습(함수의 파라미터를 계산하는 것)시키는 방법입니다. 최근에는 빅 데이터와 강력한 하드웨어 덕분에 이미지, 텍스트, 오디오 신호 등과 같은 복잡한 고차원 데이터를 처리하는 데 있어 딥 러닝이 사실상의 표준으로(de facto choice) 자리잡았습니다.

## 기원

딥 러닝은 최근의 발명품이지만, 인간은 데이터를 분석하고 미래의 결과를 예측하려는 욕구를 수세기 동안 가지고 있어왔습니다. 사실, 자연 과학의 대부분은 이것에 뿌리를 두고 있습니다. 예를 들어, 베르누이 분포는 [야곱 베르누이 (1655-1705)](https://en.wikipedia.org/wiki/Jacob_Bernoulli) 의 이름을 따서 명명되었으며, 가우시안 분포는 [칼 프리드리히 가우스 (1777-1855)](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss) 에 의해 발견되었습니다. 예를 들어, 그는 최소 평균 제곱 알고리즘을 발명했는데, 이것은 보험 계산부터 의료 진단까지 다양한 분야에서 오늘날 까지도 계속 사용되고 있습니다. 이러한 기술들은 자연 과학에서 실험적인 접근법을 불러 일으켰습니다. 예를 들어 저항기의 전류 및 전압에 관한 옴의 법칙은 선형 모델로 완벽하게 설명됩니다.

중세 시대에도 수학자들은 예측에 대한 예리한 직관을 가지고 있었습니다. 예를 들어, [야곱 쾨벨 (1460-1533)](https://www.maa.org/press/periodicals/convergence/mathematical-treasures-jacob-kobels-geometry)의 기하학책에서는 발의 평균 길이를 얻기 위해 성인 남성 발 16개의 평균을 사용했습니다.

![Estimating the length of a foot](../img/koebel.jpg)

그림 1.1은 이 평균이 어떻게 얻어졌는지를 보여줍니다. 16명의 성인 남성은 교회를 떠날 때 한 줄로 정렬하도록 요구받았습니다. 그런 다음 총 길이를 16으로 나누어 현재 1피트 금액에 대한 추정치를 얻습니다. 이 '알고리즘'은 나중에 잘못된 모양의 발을 다루기 위해 개선되었습니다 - 각각 가장 짧고 긴 발을 가진 2 명의 남성은 제외하고 나머지 발들에 대해서만 평균값을 계산합니다. 이것은 절사 평균 추정치의 초기 예 중 하나입니다.

통계는 실제로 데이터의 수집 및 가용성으로 시작되었습니다. 거장 중 한명인 [로널드 피셔 (1890-1962)](https://en.wikipedia.org/wiki/Ronald_Fisher)는 이론과 유전학의 응용에 크게 기여했습니다. 그의 알고리즘들 (예, 선형 판별 분석)과 수식들(예, Fisher 정보 매트릭스)은 오늘날에도 여전히 자주 사용되고 있습니다 (1936년에 발표한 난초(Iris) 데이터셋도 머신러닝 알고리즘을 설명하는 데 사용되기도 합니다).

머신러닝에 대한 두 번째 영향은 정보 이론 [(클로드 섀넌, 1916-2001)](https://en.wikipedia.org/wiki/Claude_Shannon) 과 [앨런 튜링 (1912-1954)](https://en.wikipedia.org/wiki/Alan_Turing)의 계산 이론에서 나왔습니다. 튜링은 그의 유명한 논문, [기계 및 지능 컴퓨팅, Computing machinery and intelligence](https://www.jstor.org/stable/2251299) (Mind, 1950년10월)에서, 그는  “기계가 생각할 수 있습니까?” 라는 질문을 제기했습니다. 그의 튜링 테스트로 설명 된 것처럼, 인간 평가자가 텍스트 상호 작용을 통해 기계와 인간의 응답을 구별하기 어려운 경우 ''기계는 지능적이다''라고 간주될 수 있습니다. 오늘날까지 지능형 기계의 개발은 신속하고 지속적으로 변화하고 있습니다.

또 다른 영향은 신경 과학 및 심리학에서 발견 될 수 있습니다. 결국, 인간은 분명히 지적인 행동을 합니다. 이러한 행동 및 이에 필요한 통찰력을 설명하고, 아마도 리버스 엔지니어링 할 수 있는지 여부를 묻는 것은 합리적입니다. 이를 달성하기위한 가장 오래된 알고리즘 중 하나는 [도널드 헤브 (1904-1985)](https://en.wikipedia.org/wiki/Donald_O._Hebb) 에 의해 공식화 되었습니다.

그의 획기적인 책 [행동의 조직, The Organization of Behavior](http://s-f-walker.org.uk/pubsebooks/pdfs/The_Organization_of_Behavior-Donald_O._Hebb.pdf) (John Wiley & Sons, 1949) 에서, 그는 뉴런이 긍정적인 강화를 통해 학습할 것이라고 가정했습니다. 이것은 Hebbian 학습 규칙으로 알려지게 되었습니다. 그것은 Rosenblatt의 퍼셉트론 학습 알고리즘의 원형이며 오늘날 딥 러닝을 뒷받침하는 많은 stochastic gradient descent 알고리즘의 기초를 마련했습니다: 뉴럴 네트워크의 좋은 가중치를 얻기 위해 바람직한 행동은 강화하고 바람직하지 않은 행동을 감소시킵니다.

생물학적 영감으로부터 신경망(Neural Network)이라는 명칭이 탄생하였습니다. 알렉산더 베인(1873)과 제임스 셰링턴(1890)이 신경망 모델을 제안한 이래 한세기 이상 연구자들은 상호 작용하는 뉴런들의 네트워크와 유사한 계산 회로를 구현하려고 시도해 왔습니다. 시간이 지남에 따라 생물학과의 연관성은 느슨해 졌지만 신경망이라는 이름은 그대로 사용하고 있습니다. 오늘날 대부분의 신경망에서 찾을 수 있는 몇 가지 주요 핵심 원칙은 다음과 같습니다:

* '레이어'라고 불리우는 선형 및 비선형 처리 유닛들의 교차 구조
* 체인 규칙 (일명 역 전파)을 사용하여 한 번에 전체 네트워크의 매개 변수를 조정

초기 급속한 진행 이후, 뉴럴 네트워크의 연구는 1995년경부터 2005년까지 쇠퇴했습니다. 여러 가지 이유들이 있습니다. 우선 네트워크 학습은 매우 많은 계산량을 필요로합니다. 지난 세기 말경에 이르러 메모리는 충분해 졌지만 계산 능력이 부족했습니다. 두번째 이유는 데이터셋이 상대적으로 작았다는 것 입니다. 실제로 1932년에 나온 피셔(Fisher)의 '[난초(Iris) 데이터셋](https://en.wikipedia.org/wiki/Iris_flower_data_set)'은 각각 50장의 세 종류의 난초 사진으로 구성되어 있는데 알고리즘의 효능을 테스트하는 데 널리 사용되는 도구였습니다. 지금은 학습 예제에 흔히 쓰이는 60,000개의 손으로 쓴 숫자들로 구성된 MNIST조차 당시에는 너무 거대한 데이터로 취급되었습니다.

데이터 및 계산능력이 부족한 경우, 커널 방법, 의사 결정 트리 및 그래픽 모델과 같은 강력한 통계 도구쪽이 우수한 성능을 보여줍니다. 신경망과는 달리 이것들은 훈련하는 데 몇 주씩 걸리지 않으면서도 강력한 이론적 보장으로 예측 가능한 결과를 제공합니다.

## 딥 러닝으로의 길

시간이 흐르면서 월드 와이드 웹이 등장하고 수억명의 온라인 사용자에게 서비스를 제공하는 회사가 출현하였으며 저렴한 고품질의 센서, 데이터 저장 비용 감소([Kryder의 법칙](https://en.wikipedia.org/wiki/Mark_Kryder)), 그리고 특히 원래 컴퓨터 게임을 위해 설계된 GPU의 가격 하락([무어의 법칙](https://ko.wikipedia.org/wiki/%EB%AC%B4%EC%96%B4%EC%9D%98_%EB%B2%95%EC%B9%99))이 진행됨에 따라 많은 것들이 바뀌게 되었습니다. 갑자기 계산이 불가능한 것처럼 보이는 알고리즘과 모델이 의미를 지니게 된 것입니다(반대의 경우도 마찬가지입니다). 이것은 아래 표에 가장 잘 설명되어 있습니다.

|연대|데이터셋|메모리|초당 부동소수점 연산수|
|:--|:-|:-|:-|
|1970|100 (Iris)|1 KB|100 KF (Intel 8080)|
|1980|1 K (House prices in Boston)|100 KB|1 MF (Intel 80186)|
|1990|10 K (optical character recognition)|10 MB|10 MF (Intel 80486)|
|2000|10 M (web pages)|100 MB|1 GF (Intel Core)|
|2010|10 G (advertising)|1 GB|1 TF (NVIDIA C2050)|
|2020|1 T (social network)|100 GB|1 PF (NVIDIA DGX-2)|

RAM이 데이터의 증가와 보조를 맞추지 않은 것은 매우 분명합니다. 동시에 계산 능력의 향상은 사용 가능한 데이터의 증가를 앞서고 있습니다. 즉, 통계 모델은 메모리 효율성이 향상 되어야하고 (일반적으로 비선형을 추가하여 달성됨) 컴퓨팅 예산 증가로 인해 이러한 매개변수를 최적화하는 데 더 많은 시간을 할애해햐야 했습니다. 결국 머신러닝 및 통계에 적절한 방법은 선형 모델 및 커널 방법에서 딥 네트워크로 이동했습니다. 이것은 다층 퍼셉트론(Multilayer Perceptron) (예, 맥컬록 & 피츠, 1943), 컨볼루션 뉴럴 네트워크(Convolutional Neural Network) (Le Cun, 1992), Long Short Tem Memory (Hochreiter & Schmidhuber, 1997), Q-러닝 (왓킨스, 1989) 과 같은 딥 러닝의 많은 주류 이론들이 상당 시간 동안 휴면기에 있다가 최근 10년간 재발견된 이유 중에 하나입니다.

통계 모델, 응용 프로그램 및 알고리즘의 최근 발전은 때때로 캄브리아 폭발 (Cambrian Dexplosion) 에 비유되고 있습니다: 종의 진화가 급속히 진행되는 순간입니다. 실제로, 현 시점에서 가장 좋은 성과들(state of art)은 수십 년동안 만들어져온 오래된 알고리즘이 적용된 결과가 아닙니다. 아래 목록은 연구자들이 지난 10년간 엄청난 진전을 달성하는 데 도움이 된 아이디어의 극히 일부분 입니다.

* 드롭아웃(Drop out) [3] 과 같은 새로운 용량 제어 방법, 즉 학습 데이터의 큰 부분을 암기하는 위험 없이 비교적 큰 네트워크의 학습이 가능합니다. 이것은 학습 목적을 위해 무작위 변수로 가중치를 대체하여 네트워크 전체에 노이즈 주입 [4] 을 적용하여 달성되었습니다.
* 어텐션 메커니즘(Attention Mechanism)은 1 세기 이상 통계를 괴롭히던 두 번째 문제를 해결했습니다: 수를 늘리지 않고 시스템의 메모리와 복잡성을 증가시키는 방법, 학습 가능한 매개 변수. [5] 는 학습 가능한 포인터 구조로만 볼 수 있는 것을 사용하여 우아한 해결책을 찾았습니다. 즉, 전체 문장을 기억할 필요없이 (예: 고정 차원 표현의 기계 번역의 경우) 저장해야하는 모든 것은 번역 프로세스의 중간 상태에 대한 포인터였습니다. 이것은 문장을 생성하기 전에 모델이 더 이상 전체 문장을 기억할 필요가 없기 때문에 긴 문장의 정확도를 크게 높일 수 있었습니다. 
* 다단계 디자인 (예: Memory Network [6] 및 Neural programmer-interpreters [7]) 를 통해 통계 모델러가 추론에 대한 반복적인 접근법을 이용해 묘사할 수 있게 하였습니다. 이러한 기술은 딥 네트워크의 내부 상태가 반복적으로 변경가능하도록 하였습니다. 그에따라 추론 체인의 후속단계를 진행하고, 이는 프로세서가 계산을 위해 메모리를 수정할 수 있는 것과 유사합니다. 
* 또 다른 중요한 발전은 적대적 생성 신경망(Generative Adversarial Netoworks)의 발명 입니다[8]. 밀도추정 및 생성모델에 대한 전통적인 통계 방법은, 적절한 확률 분포와 그들로부터 샘플링에 대한 (종종 근사) 알고리즘을 찾는 데 초점을 맞추었습니다. 결과적으로, 이러한 알고리즘은 통계 모델에 내재 된 유연성 부족으로 인해 크게 제한되었습니다. GAN의 중요한 혁신은 샘플러를 다른 파라미터들을 가진 임의의 알고리즘으로 대체한 것입니다. 그런 다음 Discriminator(사실상 두 샘플 테스트)에 의해 가짜와 실제 데이터를 구분할 수 없도록 조정됩니다. 임의의 알고리즘을 이용하여 데이터를 생성하는 기술을 통해, 다양한 분야의 밀도추정이 가능해 졌습니다. 달리는 얼룩말[9] 과 가짜 유명인 얼굴 [10] 의 예는 이러한 발전에 대한 증명입니다.
* 대부분의 경우 단일 GPU는 학습에 필요한 많은 양의 데이터를 처리하기에는 부족합니다. 지난 10년간 병렬 분산 학습 알고리즘을 개발하는 능력은 크게 향상되었습니다. 확장 가능한 알고리즘을 설계할 때, 가장 큰 과제 중 하나는 딥 러닝 최적화, 즉 확률적 그래디언트 디센트의 핵심은 처리할 데이터에 비해 상대적으로 작은 미니배치(minibatches)에 의존한다는 점입니다. 이러한 미니배치(minibatch) 그래서, 하나의 작은 batch 때문에 GPU를 최대한 활용하지 못합니다. 따라서 1024개의 GPU로, batch당 32개의 이미지를 처리하는 미니배치 학습은, 한번의 병합된 32K개의 이미지 처리와 같습니다. 최근에는, 처음 Li [11] 에 이어 You[12] 와 Jia[13]가 최대 64K개의 데이터를 ResNet50으로 ImageNet을 학습 시간을 7분 미만으로 단축시켰습니다. 초기에 이 학습 시간 측정은 일 단위 이었습니다.
* 계산을 병렬화 하는 능력은, 시뮬레이션이 가능한 상황에서 강화학습(Reinforcement learning) 분야에 결정적인 기여를 하였습니다. 이것은 바둑, 아타리 게임, 스타크래프트, 그리고 물리 시뮬레이션(예를 들면 MuJoCo의 사용) 분야에서 컴퓨터가 인간능력에 다가서거나 넘어 설 수 있도록 하는데 필요한 중요한 발전을 이끌어 내었습니다. 실예로, Silver [18]는 AlphaGo가 어떻게 이것을 달성 했는지 설명하고 있습니다. 요컨대, 많은 양의 상태, 행동, 보상의 세가지 조합 데이터들을 사용할 수 있다면, 강화학습은 각각의 데이터들을 어떻게 연관시킬 수 있을 지, 매우 많은 양의 데이터로 시도해 볼수 있게 합니다. 시뮬레이션은 그런 방법을 제공합니다. 
* 딥러닝 프레임워크는 아이디어를 널리 퍼트리는데 중요한 역할을 했습니다. 손쉬운 모델링을 위한 프레임워크의 첫 번째 세대는 [Caffe](https://github.com/BVLC/caffe), [Torch](https://github.com/torch), [Theano](https://github.com/Theano/Theano) 입니다. 많은 영향력 있는 논문들이 이 도구를 이용해 작성 되었습니다. 지금에 이르러 이들은 TensorFlow[TensorFlow](https://github.com/tensorflow/tensorflow)로 대체 되었습니다. 고수준 API 인 [Keras](https://github.com/keras-team/keras), [CNTK](https://github.com/Microsoft/CNTK), [Caffe 2](https://github.com/caffe2/caffe2) 및  [Apache MxNet](https://github.com/apache/incubator-mxnet)도 이를 사용합니다. 3 세대 툴, 즉 딥러닝을 위한 명령형 툴은 틀림없이, 모델을 기술하기 위해 파이썬 NumPy와 유사한 구문을 사용하는 [Chainer](https://github.com/chainer/chainer)에 의해 주도될 것입니다. 이 아이디어는 [PyTorch](https://github.com/pytorch/pytorch)와 MxNet의 [Gluon API](https://github.com/apache/incubator-mxnet)에도 채택 되었습니다. 이 책에서는 MxNet의 Gluon API을 사용하였습니다.

학습을 위해 더 나은 툴을 만드는 연구자와 더 나은 신경망을 만들기 위한 통계모델러 간, 작업 시스템 분리는 많은 것들을 단순화 하였습니다. 한 예로, 2014년 카네기멜론대학의 머신러닝 박사과정 학생에게 선형 회귀 분석 모델을 학습시키는 것은 매우 중요한 과제 였습니다. 지금은 이 작업은 10줄이 안되는 코드로 완료 가능하고, 프로그래머들이 확실히 이해할수 있게 만들었습니다.

## 성공 사례

인공지능은 풀기 어려웠던 여러가지 문제들을 다른 방법으로 해결해 온 오래된 역사가 있습니다. 하나의 예로, 편지는 광학 문자 인식 기술을 이용해 정렬됩니다. 이 시스템은 90년대부터 사용되었습니다.(이것이 결국, 유명한 MINIST 및 USPS 필기 숫자셋의 출처 입니다.) 동시에 은행 예금의 수표책과 신청자의 신용 점수를 읽는 데에도 적용됩니다. 또 금융 거래에서는 자동으로 사기 여부를 체크 합니다. 페이팔, 스트라이프, 알리페이, 위챗, 애플, 비자, 마스터카드 등과 같은 많은 e-커머스 지불 시스템의 근간을 이룹니다. 체스 프로그램은 수십 년간 경쟁력을 유지해 왔습니다. 머신러닝은 인터넷상에서 검색, 추천, 개인화 및 랭킹을 제공해 왔습니다. 즉, 인공 지능과 머신러닝은 비록, 종종 시야에서 숨겨져 있지만, 널리 퍼져 있습니다.

최근에야 AI가 각광을 받고 있는데, 이는 대부분 이전에 다루기 어려운 문제들을 AI가 해결하고 있기 때문입니다.

* 애플의 시리 (Siri), 아마존의 알렉사 (Alexa), 구글의 조수 (assistant)와 같은 지능형 조수들은 말로 전달된 질문에 대해 합당한 정도의 정확도로 대답 할 수 있습니다. 여기에는 조명 스위치를 켜고 이발사와 약속을 잡고, 대화형 전화 지원을 제공하는 등의 일상적인 작업이 포함됩니다. 이것은 AI가 우리 삶에 영향을 미치는 가장 두드러진 사례들 일 것입니다.
* 디지털 조수의 핵심 요소는 말을 정확하게 인식 할 수있는 능력입니다. 점차적으로 이러한 시스템의 정확도는 특정 응용 분야에서 인간과 유사한 수준에 도달 할 정도로 올라갔습니다[14].
* 마찬가지로 객체 인식은 먼 길을왔다. 그림에서 개체를 추정하는 것은 2010 년에 상당히 어려운 작업이었습니다. ImageNet 벤치 마크 Lin 외. [15] 는 28% 의 상위 5 오류율을 달성했습니다. 2017 후 등. [16] 이 오류율을 2.25% 로 줄였습니다. 마찬가지로 놀라운 결과는 새를 식별하거나 피부암을 진단하기 위해 달성되었습니다. 
* 게임은 인간의 지능의 보루로 사용되었습니다. TDGammon에서 시작 [23], 시간 차이 (TD) 강화 학습, 알고리즘 및 계산 진행을 사용하여 주사위 놀이를 재생하는 프로그램은 광범위한 응용 프로그램을위한 알고리즘을 주도하고있다. 주사위 놀이와 달리 체스는 훨씬 더 복잡한 상태 공간과 일련의 행동을 가지고 있습니다. DeepBlue는 게리 카스파로프를 이길, 캠벨 등. [17], 게임 트리를 통해 대규모 병렬 처리, 특수 목적 하드웨어와 효율적인 검색을 사용하여. 이동은 거대한 상태 공간 때문에 여전히 더 어렵습니다. AlphaGo는 2015 년에 인간의 패리티를 달성, 실버 등. [18] 몬테 카를로 트리 샘플링과 결합 된 딥 러닝을 사용하여. 포커의 도전은 상태 공간이 크고 완전히 관찰되지 않는다는 것입니다 (우리는 상대방의 카드를 모릅니다). 천교는 효율적으로 구조화 된 전략을 사용하여 포커에서 인간의 성능을 초과; 브라운과 샌드 홀름 [19]. 이것은 게임의 인상적인 진전과 고급 알고리즘이 그들에게 중요한 역할을 했다는 사실을 보여줍니다. 
* AI의 진보의 또 다른 표시는 자율 주행 자동차와 트럭의 출현입니다. 아직 완전한 자율 주행에 도달한  것은 아니지만, [모멘타](http://www.momenta.com), [테슬라](https://www.tesla.com/), [엔비디아](http://www.nvidia.com), [모바일아이](http://www.mobileye.com), [Waymo.com](http://www.waymo.com) 등의 회사들은 적어도 부분적인 자율 주행을 구현하는 놀라운 진전을 이루어 냈습니다. 완전한 자율성을 너무 어렵게 만드는 것은 올바른 운전을 위해서는 규칙을 인식하고 추론하고 시스템에 통합하는 능력이 필요하다는 것 입니다. 현재 딥 러닝은 컴퓨터 영상 처리 측면의 문제를 해결하기 위해 주로 사용됩니다. 나머지는 엔지니어에 의해 많이 조정됩니다.

다시 말하지만, 위의 목록은 지능적인 것으로 간주되는 것과 머신러닝이 분야에서 일어난 놀라운 발견들의 극히 일부분에 불과합니다. 오늘날의 로봇 공학, 물류, 전산생물학, 입자 물리학, 천문학은 크던 작던 머신러닝의 발전의 혜택을 누리고 있습니다. 이제 머신러닝은 엔지니어와 과학자를 위한 범용적인 도구가 되어가고 있는 것 입니다.

종종 AI 종말론이나 인공 지능 특이성에 대한 질문들이 비기술적인 기사에서 제기되곤 합니다. 머신러닝 시스템이 지각을 갖게 될 것이고, 그것을 만든 프로그래머와는 독립적으로 인간의 생활에 직접적인 영향을 끼칠 것들을 결정할 것이라는 것을 두려워합니다. 하지만 이미 AI는 인간의 삶에 영향을 미치고 있습니다. 신용도가 자동으로 평가되고, 오토파일럿(autopilot)은 자동차를 안전하게 운전할 수 있게 해 주며, 통계 데이터를 입력을 사용해서 보석 허용 여부를 결정하고 있습니다. 조금 더 친근한 사례로 우리는 Alexa에게 커피 머신을 켜달라고 요청할 수 있으며, Alexa가 장치에 연결되어 있다면 요청을 수행할 수 있습니다.

다행히도 우리는 인간 창조자를 노예로 만들거나 커피를 태울 준비가 된 지각 있는 AI 시스템과는 거리가 멀었습니다. 첫째, AI 시스템은 특정 목표 지향적 방식으로 설계, 학습, 배포됩니다. 그들의 행동은 범용AI에 대한 환상을 줄 수 있지만, 어디까지나 현재 인공지능 디자인의 기초는 규칙, 휴리스틱, 통계 모델의 조합입니다. 둘째, 아직까지는 일반적인 일을 수행하면서 스스로 개선하고, 스스로에 대해서 사고, 스스로의 아키텍처를 개선확장하고 개선하는 일반적인 인공지능을 위한 도구는 존재하지 않습니다.

훨씬 더 현실적인 관심사는 AI가 일상생활에서 어떻게 사용되는지입니다. 트럭 운전사 및 상점 보조자가 수행하는 사소한 일들이 자동화될 수 있고 자동화될 가능성이 있습니다. 농장 로봇은 유기 농업 비용을 줄일 수 있있고, 또한 수확 작업을 자동화할 것입니다. 산업 혁명의 이 단계는 사회의 많은 이들의 삶에 있어서 중대한 변화를 가져올 것입니다. 트럭 운전사와 매장 점원은 많은 주에서 가장 일반적인 직업중 하나입니다. 게다가 통계 모델이 부주의하게 적용되면 인종적, 성별 또는 연령 편견이 발생할 수 있습니다. 이러한 알고리즘이 세심한 주의를 가지고 사용되는지 확인하는 것이 중요합니다. 이것은 인류를 멸망시킬 수 있는 악의적인 초지능의 탄생에 대해 걱정하는 것보다 훨씬 더 현실적이고 중요한 문제입니다.

## 주요 요소들

머신러닝은 데이터를 사용하여 예제 간의 변환을 학습합니다. 예를 들어 숫자 이미지는 0에서 9 사이의 정수로 변환되고, 오디오는 텍스트(음성 인식)로 변환되고, 텍스트는 다른 언어의 텍스트로 변환되거나(기계 번역), 머그샷이 이름으로 변환됩니다(얼굴 인식). 그렇게 할 때, 알고리즘이 데이터를 처리하는 데 적합한 방식으로 데이터를 표현해야 하는 경우가 종종 있습니다. 이러한 특징 변환(feature transformation)의 정도는 표현 학습을 위한 수단으로 딥 러닝을 언급하는 이유로서 종종 사용됩니다. 사실, 국제 학습 표현 회의(the International Conference on Learning Representations)의 명칭은 이것으로부터 유래합니다. 동시에 머신러닝은 통계(특정 알고리즘이 아닌 매우 큰 범위의 질문까지)와 데이터 마이닝(확장성 처리)을 똑같이 사용합니다.

현기증 나는 알고리즘 및 응용 프로그램 집합으로 인해 딥 러닝을 위한 성분이 무엇인지 *구체적으로* 평가하기가 어렵습니다. 이것은 피자에 필요한 재료를 고정시키는 것만큼 어렵습니다. 거의 모든 구성 요소는 대체 가능합니다. 예를 들어 다층 퍼셉트론이 필수 성분이라고 가정할 수 있습니다. 그러나 convolution 만 사용하는 컴퓨터 비전 모델이 있습니다. 다른 것들은 시퀀스 모델만 사용하기도 합니다.

틀림없이 이러한 방법에서 가장 중요한 공통점은 종단간(end-to-end) 학습을 사용하는 것입니다. 즉, 개별적으로 튜닝된 구성 요소를 기반으로 시스템을 조립하는 대신 시스템을 구축한 다음 성능을 공동으로 튜닝합니다. 예를 들어, 컴퓨터 비전 과학자들은 머신러닝 모델을 구축하는 과정과 특징 엔지니어링 프로세스를 분리하곤 했습니다. Canny 에지 검출기 [20] 와 Lowe의 SIFT 특징 추출기 [21] 는 이미지를 형상 벡터에 매핑하기 위한 알고리즘으로 10여 년간 최고로 통치했습니다. 불행히도 알고리즘에 의해 자동으로 수행 될 때 수천 또는 수백만 가지 선택에 대한 일관된 평가와 관련하여 인간이 독창성으로 성취 할 수있는 많은 것들이 있습니다. 딥 러닝이 적용되었을 때, 이러한 특징 추출기는 자동으로 튜닝된 필터로 대체되어 뛰어난 정확도를 달성했습니다.

마찬가지로 자연 언어 처리에서 Salton과 McGill [22] 의 bag-of-words 모델은 오랫동안 기본으로 선택되었습니다. 여기서 문장의 단어는 벡터로 매핑되며 각 좌표는 특정 단어가 발생하는 횟수에 해당합니다. 이것은 단어 순서 ('개가 사람을 물었다' 대 '사람이 개를 물었다') 또는 구두점 ('먹자, 할머니' 대 '할머니를 먹자') 을 완전히 무시합니다. 불행히도, 더 나은 특징을 *수동으로* 엔지니어링하는 것은 다소 어렵습니다. 반대로 알고리즘은 가능한 특징(feature) 설계의 넓은 공간을 자동으로 검색 할 수 있습니다. 이것은 엄청난 진전을 이끌어 왔습니다. 예를 들어 의미상 관련성이 있는 단어 임베딩은 벡터 공간에서 '베를린 - 독일 + 이탈리아 = 로마' 형식의 추론을 허용합니다. 다시 말하지만, 이러한 결과는 전체 시스템의 end-to-end 학습을 통해 달성됩니다.

End-to-end 학습 외에도 두 번째로 중요한 것은 파라미터 기반의 통계 설명에서 완전 비파라미터 기반의 모델로의 전환을 경험하고 있다는 것입니다. 데이터가 부족한 경우, 유용한 모델을 얻기 위해서는 현실에 대한 가정을 단순화하는 데 의존해야합니다 (예, 스펙트럼 방법을 통해). 데이터가 풍부하면 현실에 더 정확하게 맞는 비파라미터 기반의 모형으로 대체될 수 있습니다. 어느 정도, 이것은 컴퓨터의 가용성과 함께 이전 세기 중반에 물리학이 경험한 진전과 비슷합니다. 전자가  어떻게 동작하는지에 대한 파라메트릭 근사치를 직접 해결하는 대신, 이제 연관된 부분 미분 방정식의 수치 시뮬레이션에 의존 할 수 있습니다. 이것은 설명 가능성을 희생시키면서 종종 훨씬 더 정확한 모델을 이끌어 냈습니다. 

예를 들어 Generative Aversarial Networks가 있습니다. 그래픽 모델이 적절한 확률적 공식 없이도 데이터 생성 코드로 대체됩니다. 이것은 현혹적으로 현실적으로 보일 수 있는 이미지의 모델을 이끌어 냈는데 이는 오랜 시간 동안 너무 어려운 것으로 여겨졌왔던 것입니다.

이전 작업의 또 다른 차이점은 볼록하지 않은 비선형 최적화 문제(nonconvex nonlinear optimization problem)를 다루면서 차선책 솔루션을 받아들이고, 이를 증명하기 전에 시도하려는 의지입니다. 통계적 문제를 다루는 새로운 경험주의와 인재의 급속한 유입은 실질적인 알고리즘의 급속한 발전으로 이어졌습니다 (많은 경우에도 불구하고 수십 년간 존재했던 도구를 수정하고 다시 발명하는 대신). 

마지막으로 딥 러닝 커뮤니티는 학술 및 기업 경계를 넘어 도구를 공유하는 것을 자랑으로 하고 있으며, 많은 우수한 라이브러리, 통계 모델 및 학습된 네트워크를 오픈 소스로 공개합니다. 이 과정을 구성하는 노트북은 배포 및 사용이 자유됩다는 것이 이러한 정신입니다. 우리는 모든 사람들이 딥 러닝에 대해 배울 수 있는 접근의 장벽을 낮추기 위해 열심히 노력했으며 독자가 이것의 혜택을 누릴 수 있기를 바랍니다.

## 요약

* 머신러닝은 컴퓨터 시스템이 어떻게 데이터를 사용하여 성능을 향상시킬 수 있는지 연구합니다. 통계, 데이터 마이닝, 인공 지능 및 최적화의 아이디어를 결합합니다. 종종 인위적으로 지능형 솔루션을 구현하는 수단으로 사용됩니다. 
* 머신러닝의 클래스로서 표현 학습은 데이터를 나타내는 적절한 방법을 자동으로 찾는 방법에 초점을 맞춥니다. 이것은 종종 학습된 변환의 진행에 의해 성취됩니다. 
* 최근 진전의 대부분은 값싼 센서와 인터넷 규모 응용 프로그램에서 발생하는 풍부한 데이터와 주로 GPU를 통한 계산의 상당한 진전으로 인해 트리거되었습니다. 
* 전체 시스템 최적화가 핵심입니다. 구성 요소를 사용하여 좋은 성능을 얻을 수 있습니다. 효율적인 딥 러닝 프레임워크의 가용성으로 인해 이 프레임워크의 설계와 구현이 훨씬 쉬워졌습니다.

## 문제

1. 현재 작성중인 코드의 어느 부분이 '학습' 될 수 있습니까? 즉, 코드에서 만들어진 디자인 선택을 학습하고 자동으로 결정함으로써 개선 될 수 있습니까? 코드에 휴리스틱 디자인 선택이 포함되어 있습니까? 
1. 어떤 문제가 발생하는지이를 해결하는 방법에 대한 많은 예가 있지만 자동화하는 구체적인 방법은 없습니다. 이들은 딥 러닝을 사용하기위한 주요 후보 일 수 있습니다. 
1. 새로운 산업 혁명으로 인공 지능의 발전을 보고, 알고리즘과 데이터의 관계는 무엇인가? 증기 엔진과 석탄과 비슷합니까 (근본적인 차이점은 무엇입니까)? 
1. End-to-end 학습 접근 방식을 어디에서 적용할 수 있습니까? 물리학? 엔지니어링? 경제학? 
1. 왜 인간의 뇌처럼 구조화된 딥 네트워크를 만들고 싶습니까? 장점은 무엇입니까? 왜 그렇게하고 싶지 않습니까 (마이크로 프로세서와 뉴런의 주요 차이점은 무엇입니까)?

## 참고문헌

[1] Turing, A. M. (1950). Computing machinery and intelligence. Mind, 59(236), 433.

[2] Hebb, D. O. (1949). The organization of behavior; a neuropsychological theory. A Wiley Book in Clinical Psychology. 62-78.

[3] Srivastava, N., Hinton, G., Krizhevsky, A., Sutskever, I., & Salakhutdinov, R. (2014). Dropout: a simple way to prevent neural networks from overfitting. The Journal of Machine Learning Research, 15(1), 1929-1958.

[4] Bishop, C. M. (1995). Training with noise is equivalent to Tikhonov regularization. Neural computation, 7(1), 108-116.

[5] Bahdanau, D., Cho, K., & Bengio, Y. (2014). Neural machine translation by jointly learning to align and translate. arXiv preprint arXiv:1409.0473.

[6] Sukhbaatar, S., Weston, J., & Fergus, R. (2015). End-to-end memory networks. In Advances in neural information processing systems (pp. 2440-2448).

[7] Reed, S., & De Freitas, N. (2015). Neural programmer-interpreters. arXiv preprint arXiv:1511.06279.

[8] Goodfellow, I., Pouget-Abadie, J., Mirza, M., Xu, B., Warde-Farley, D., Ozair, S., … & Bengio, Y. (2014). Generative adversarial nets. In Advances in neural information processing systems (pp. 2672-2680).

[9] Zhu, J. Y., Park, T., Isola, P., & Efros, A. A. (2017). Unpaired image-to-image translation using cycle-consistent adversarial networks. arXiv preprint.

[10] Karras, T., Aila, T., Laine, S., & Lehtinen, J. (2017). Progressive growing of gans for improved quality, stability, and variation. arXiv preprint arXiv:1710.10196.

[11] Li, M. (2017). Scaling Distributed Machine Learning with System and Algorithm Co-design (Doctoral dissertation, PhD thesis, Intel).

[12] You, Y., Gitman, I., & Ginsburg, B. Large batch training of convolutional networks. ArXiv e-prints.

[13] Jia, X., Song, S., He, W., Wang, Y., Rong, H., Zhou, F., … & Chen, T. (2018). Highly Scalable Deep Learning Training System with Mixed-Precision: Training ImageNet in Four Minutes. arXiv preprint arXiv:1807.11205.

[14] Xiong, W., Droppo, J., Huang, X., Seide, F., Seltzer, M., Stolcke, A., … & Zweig, G. (2017, March). The Microsoft 2016 conversational speech recognition system. In Acoustics, Speech and Signal Processing (ICASSP), 2017 IEEE International Conference on (pp. 5255-5259). IEEE.

[15] Lin, Y., Lv, F., Zhu, S., Yang, M., Cour, T., Yu, K., … & Huang, T. (2010). Imagenet classification: fast descriptor coding and large-scale svm training. Large scale visual recognition challenge.

[16] Hu, J., Shen, L., & Sun, G. (2017). Squeeze-and-excitation networks. arXiv preprint arXiv:1709.01507, 7.

[17] Campbell, M., Hoane Jr, A. J., & Hsu, F. H. (2002). Deep blue. Artificial intelligence, 134 (1-2), 57-83.

[18] Silver, D., Huang, A., Maddison, C. J., Guez, A., Sifre, L., Van Den Driessche, G., … & Dieleman, S. (2016). Mastering the game of Go with deep neural networks and tree search. Nature, 529 (7587), 484.

[19] Brown, N., & Sandholm, T. (2017, August). Libratus: The superhuman ai for no-limit poker. In Proceedings of the Twenty-Sixth International Joint Conference on Artificial Intelligence.

[20] Canny, J. (1986). A computational approach to edge detection. IEEE Transactions on pattern analysis and machine intelligence, (6), 679-698.

[21] Lowe, D. G. (2004). Distinctive image features from scale-invariant keypoints. International journal of computer vision, 60(2), 91-110.

[22] Salton, G., & McGill, M. J. (1986). Introduction to modern information retrieval.

[23] Tesauro, G. (1995), Transactions of the ACM, (38) 3, 58-68

## Scan the QR Code to [Discuss](https://discuss.mxnet.io/t/2310)

![](../img/qr_deep-learning-intro.svg)
