---
title: コンパイラ エラー C3284
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
ms.openlocfilehash: 6e79de18e277de9ee79945d319640fa906dea622
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511632"
---
# <a name="compiler-error-c3284"></a>コンパイラ エラー C3284

ジェネリック パラメーター 'parameter' (関数 ’function’) に対する制約は、ジェネリック パラメーター 'parameter' (関数 'function') に対する制約と一致しなければなりません。

仮想ジェネリック関数は、基底クラス内にある、名前と引数のセットが同一の仮想関数と同じ制約を使用しなければなりません。

次の例では C3284 が生成されます。

```
// C3284.cpp
// compile with: /clr /c
// C3284 expected
public interface class IGettable {
   int Get();
};

public interface class B {
   generic<typename T>
   where T : IGettable
   virtual int mf(T t);
};

public ref class D : public B {
public:
   generic<typename T>
   // Uncomment the following line to resolve.
   // where T : IGettable
   virtual int mf(T t) {
      return 4;
   }
};
```