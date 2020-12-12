---
description: 詳細については、「コンパイラエラー C2601」を参照してください。
title: コンパイラエラー C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: 373ba519633034ddf63889eb82cd71dccfa4a743
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119997"
---
# <a name="compiler-error-c2601"></a>コンパイラエラー C2601

' function ': ローカル関数の定義が正しくありません。

コードは関数内で関数を定義しようとします。

または、C2601 エラーの場所の前に、ソースコードに余分な中かっこが含まれている可能性があります。

次の例では、C2601 が生成されます。

```cpp
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```
