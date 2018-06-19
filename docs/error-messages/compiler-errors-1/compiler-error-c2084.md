---
title: コンパイラ エラー C2084 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce1510dd6e78b8774d3cc433f583c16cdbb8d06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33173878"
---
# <a name="compiler-error-c2084"></a>コンパイラ エラー C2084
関数 '*関数*'、本文には既に  
  
 関数は既に定義されています。  
  
 バージョンの Visual Studio の 2002 年前に Visual C  
  
-   コンパイラは、追加の定義を使用することは決して同じの実際の型に解決される複数のテンプレートの特殊化を受け入れるは。 コンパイラは、今すぐこれら複数の定義を検出します。  
  
-   `__int32` および`int`別個の型として扱われました。 コンパイラはこれで扱います`__int32`のシノニムとして`int`です。 これは、コンパイラでは、両方の関数がオーバー ロードする場合、複数の定義がによって検出されたことを意味`__int32`と`int`エラーとなります。  
  
## <a name="example"></a>例  
 次の例では、C2084 が生成されます。  
  
```cpp  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
このエラーを解決するには、重複する定義を削除します。  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```