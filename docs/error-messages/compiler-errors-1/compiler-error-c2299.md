---
title: コンパイラ エラー C2299 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4977f4a5ac81cf4c04d3b143f6f7e670a9d9279
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049619"
---
# <a name="compiler-error-c2299"></a>コンパイラ エラー C2299

'function': 動作変更: 明示的な特殊化することはできません、コピー コンス トラクターまたはコピー代入演算子

このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成することもできます。 以前のバージョンの Visual c では、コピー コンス トラクターまたはコピー代入演算子の明示的な特殊化が許可されています。

C2299 を解決するのにはしないで、コピー コンス トラクターまたは代入演算子、テンプレート関数がクラス型を受け取る非テンプレート関数ではなく。 テンプレート引数を明示的に指定して、コピー コンス トラクターまたは代入演算子を呼び出すコードでは、テンプレート引数を削除する必要があります。

次の例では、C2299 が生成されます。

```
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```