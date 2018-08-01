---
title: 配列の初期化 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1ecb15cfc34ec518f46474497a3577a51b00c4e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408957"
---
# <a name="initializing-arrays"></a>配列の初期化
クラスにコンストラクターがある場合、そのクラスの配列はコンストラクターによって初期化されます。 配列の要素よりも初期化子リスト内の項目が少ない場合、残りの要素には既定のコンストラクターが使用されます。 クラスに対して既定のコンストラクターが定義されていない場合は、完全な初期化子リストが必要です。つまり、配列の各要素に 1 つずつ初期化子が必要です。  
  
 2 つのコンストラクターを定義する `Point` クラスを考えます。  
  
```cpp 
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 `aPoint` の最初の要素はコンストラクター `Point( int, int )` を使用して構築されます。残りの 2 つの要素は既定のコンストラクターを使用して構築されます。  
  
 静的メンバー配列 (かどうか**const**か) の定義 (宣言の外側のクラス) で初期化することができます。 例えば:  
  
```cpp 
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  