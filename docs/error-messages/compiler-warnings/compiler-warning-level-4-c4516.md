---
title: コンパイラの警告 (レベル 4) C4516 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5ca56734d5bd9f2ddf66732ed894d805e368664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4516"></a>コンパイラの警告 (レベル 4) C4516
'class::symbol': アクセス宣言は非推奨です。メンバー using 宣言がより優れた代替手段を提供します。  
  
 ANSI C 委員会がアクセス宣言 (せずに、派生クラスのメンバーのアクセスを変更して、[を使用して](../../cpp/using-declaration.md)キーワード) 旧式であります。 アクセス宣言は、C++ の将来のバージョンでサポートされていません可能性があります。  
  
 次の例では、C4516 が生成されます。  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```