**CAL PROJECT**

**Tech Stack**

Lovable: [https://lovable.dev/](https://lovable.dev/?via=hill)  
n8n: [https://n8n.io/](https://n8n.partnerlinks.io/hill)

**Lovable Prompt \- Create APP**

```
Project: Hill Calories AI – Simple Landing Page + Image Nutrition Analyzer

Goal: Build a fast, mobile-first landing page that lets a user upload (or capture) a meal photo and get instant macronutrient analytics (protein, carbs, fat) via a POST request. Keep it simple, pretty, and production-ready.
```

**Fix Design Issues with ChatGPT**

```
Roast this web design and tell me how to fix it. Give answer in one paragraph.
```

**Lovable \- How to handle photo uploads**

```
When the user submits a photo analyze the meal, then send it to the following webhook:

https://n8n.hillfusion.com/webhook-test/hill-cal-ai

with the image. Once you receive the response display it.

Here is a example response json:

[
  {
    "output": {
      "status": "success",
      "food": [
        {
          "name": "Grilled Chicken Breast",
          "quantity": "150g",
          "calories": 248,
          "protein": 46,
          "carbs": 0,
          "fat": 5.3
        },
        {
          "name": "Cherry Tomatoes",
          "quantity": "100g",
          "calories": 18,
          "protein": 0.9,
          "carbs": 3.9,
          "fat": 0.2
        },
        {
          "name": "Chopped Carrots",
          "quantity": "100g",
          "calories": 41,
          "protein": 0.9,
          "carbs": 10,
          "fat": 0.2
        },
        {
          "name": "Green Beans",
          "quantity": "100g",
          "calories": 31,
          "protein": 1.8,
          "carbs": 7,
          "fat": 0.1
        },
        {
          "name": "Kiwi",
          "quantity": "80g",
          "calories": 42,
          "protein": 0.8,
          "carbs": 10.1,
          "fat": 0.4
        },
        {
          "name": "Apple Slices",
          "quantity": "100g",
          "calories": 52,
          "protein": 0.3,
          "carbs": 14,
          "fat": 0.2
        },
        {
          "name": "Mixed Berries (Blackberry, Blueberry)",
          "quantity": "50g",
          "calories": 29,
          "protein": 0.4,
          "carbs": 7,
          "fat": 0.3
        },
        {
          "name": "Lemon Wedge",
          "quantity": "20g",
          "calories": 6,
          "protein": 0.1,
          "carbs": 2,
          "fat": 0
        }
      ],
      "total": {
        "calories": 467,
        "protein": 51.2,
        "carbs": 54,
        "fat": 6.7
      }
    }
  }
]

```

**n8n Agent Prompt**

```
Analyze the dish in this image and provide a detailed nutritional breakdown, including estimated calories, macronutrients (protein, carbs, fats), and any notable micronutrients or health considerations.
```

**n8n Agent Format**

```
{
  "status": "success",
  "food": [
    {
      "name": "Grilled Chicken Breast",
      "quantity": "150g",
      "calories": 240,
      "protein": 45,
      "carbs": 0,
      "fat": 5
    },
    {
      "name": "Steamed Broccoli",
      "quantity": "100g",
      "calories": 35,
      "protein": 3,
      "carbs": 7,
      "fat": 0
    }
  ],
  "total": {
    "calories": 275,
    "protein": 48,
    "carbs": 7,
    "fat": 5
  }
}
```

