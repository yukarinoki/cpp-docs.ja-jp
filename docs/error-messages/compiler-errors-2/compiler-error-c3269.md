---
title: コンパイラ エラー C3269 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3269
dev_langs:
- C++
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98e4e2a2df4271a3a0213b8abedc385f22c871aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249743"
---
# <a name="compiler-error-c3269"></a>コンパイラ エラー C3269
'function': マネージまたは WinRTtype のメンバー関数は、'…' で宣言することはできません  
  
マネージ クラスと WinRT クラスのメンバー関数では可変長のパラメーター リストを宣言できません。  
  
次の例では C3269 を生成し、その修正方法を示しています。  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  
