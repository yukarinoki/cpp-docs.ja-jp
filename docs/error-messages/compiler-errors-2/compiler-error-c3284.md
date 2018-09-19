---
title: コンパイラ エラー C3284 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6be84043d7c475cbd023d870e524f7bf9e6190
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105220"
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