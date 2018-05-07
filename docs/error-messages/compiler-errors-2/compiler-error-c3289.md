---
title: コンパイラ エラー C3289 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3289
dev_langs:
- C++
helpviewer_keywords:
- C3289
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0564d3472c46e01bc9f45d2f5d85446db0bb2ff3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3289"></a>コンパイラ エラー C3289
'property': trivial プロパティはインデックスできません  
  
 プロパティが正しく宣言されませんでした。 インデックス付きプロパティに対してアクセサーを定義する必要があります。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3289 が生成されます。  
  
```  
// C3289.cpp  
// compile with: /clr  
public ref struct C {  
   // user-defined simple indexer  
   property int indexer1[int];   // C3289  
  
   // user-defined indexer  
   property int indexer2[int] {  
      int get(int i) { return 0; }  
      void set(int i, int j) {}  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->indexer2[0] = 1;  
}  
```