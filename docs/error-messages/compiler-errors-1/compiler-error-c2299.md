---
title: コンパイラ エラー C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 39659baebf7dc1859a69021f60ed452964ae61af
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447957"
---
# <a name="compiler-error-c2299"></a>コンパイラ エラー C2299

'function': 動作変更: 明示的な特殊化することはできません、コピー コンス トラクターまたはコピー代入演算子

このエラーは、for Visual Studio 2005 で行ったコンパイラ準拠作業の結果として生成することもできます。 以前のバージョンの VisualC++コピー コンス トラクターまたはコピー代入演算子を明示的な特殊化を許可します。

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