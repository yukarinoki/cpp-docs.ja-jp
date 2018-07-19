---
title: コンパイラ エラー C3813 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e947b281c90c4d2ace83971f1de972c29bde72ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273108"
---
# <a name="compiler-error-c3813"></a>コンパイラ エラー C3813
プロパティ宣言はマネージ型または WinRT 型の定義内でのみ使用できます  
  
A[プロパティ](../../dotnet/how-to-use-properties-in-cpp-cli.md)またはマネージ Windows ランタイム内でのみ宣言可能型です。 ネイティブ型では、`property` キーワードがサポートされていません。  
  
## <a name="example"></a>例  
次の例では、C3813 を生成し、その修正方法を示しています。  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```