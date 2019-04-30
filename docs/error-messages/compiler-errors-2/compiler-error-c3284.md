---
title: コンパイラ エラー C3284
ms.date: 11/04/2016
f1_keywords:
- C3284
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
ms.openlocfilehash: acefcac849b9ce36bcf24d45f3ce85ba220b3698
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381372"
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