---
title: "Prefab Templates"
icon: "📝"
created: 2024-11-08
updated: 2024-11-08
---

# Prefab Templates

If you want to add your own templates to the GameObject Create menu, it's as simple as enabling "Show In Menu" on a Prefab File:

 ![](./images/2ca0aa88-1e0c-4dd1-9fe8-d40aa90166b8.png " =556x279")

Now you'll see your template as one of the options in the Create menu

 ![](./images/129bf867-ac48-4dd8-bc2a-d8ac9d045235.png " =410x521")

You can make it look nicer by fiddling with the other variables, and even throw it in a sub-menu:

 ![](./images/e779cdb7-ab15-487c-8d33-bb97aeba7220.png "left-50 =471x246") ![](./images/6c1e7903-9fa2-4e83-b5d4-3c66226b3a69.png "right-50 =257x233")





The final option is whether or not the prefab should be treated as a template. Templates will always break the prefab when created, otherwise the prefab reference will be maintained:

[DontBreakAsTemplate = false VS DontBreakAsTemplate = true
 508x544](./images/64c10c57-ce45-45bb-831f-b7885ab81d6f.png)
