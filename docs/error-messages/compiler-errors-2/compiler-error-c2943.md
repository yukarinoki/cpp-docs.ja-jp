---
description: 詳細については、「コンパイラエラー C2943」を参照してください。
title: コンパイラ エラー C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: f85000ae554e25f2ca783b605b036abb3f04eadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249582"
---
# <a name="compiler-error-c2943"></a>コンパイラ エラー C2943

'class': type-class-id が、テンプレートの型引数として再定義されています

ジェネリック クラスまたはテンプレート クラスは、シンボルの代わりに、ジェネリック型またはテンプレート型の引数として使用できません。

次の例では C2943 が生成されます。

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
