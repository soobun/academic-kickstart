---
title: Python测试代码
summary: 代码测试
date: "2020-02-24T00:00:00Z"
tags: ["Teaching","Python"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

### 函数的单元测试

```python
import unittest
def get_formatted_name(first, last):
    full_name = first + ' ' + last
    return full_name.title()

class NamesTestCase(unittest.TestCase):
    def test_first_last_name(self):		#方法需要以test开头
        formatted_name=get_formatted_name('eric','brown')
        self.assertEqual(formatted_name,'Eric Brown')

unittest.main()
```

### 类的测试

```python
import unittest
class AnonymousSurvey():	# 收集匿名调查问卷的答案
    def __init__(self, question):	# 存储一个问题，并为存储答案做准备
        self.question = question
        self.responses = []
    def show_question(self):	# 显示调查问卷
        print(question)
    def store_response(self, new_response):		# 存储单份调查答卷
        self.responses.append(new_response)
    def show_results(self):		# 显示收集到的所有答卷
        print("Survey results:")
        for response in responses:
            print('- ' + response)

class TestAnonymousSurvey(unittest.TestCase):   # 针对AnonymousSurvey类的测试
    def test_store_three_responses(self):   # 测试三个答案会被妥善地存储
        question = "What language did you first learn to speak?"
        my_survey = AnonymousSurvey(question)
        responses = ['English', 'Spanish', 'Mandarin']
        for response in responses:
            my_survey.store_response(response)
        for response in responses:
            self.assertIn(response, my_survey.responses)

unittest.main()

```

可以定义类方法`setUp(self)`，预先创建一个对象