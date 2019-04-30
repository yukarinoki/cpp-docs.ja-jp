---
title: コンパイラ エラー C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 00cb13d1999b00dfcaa5a2bc7bfb3b8eb16af5f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386981"
---
# <a name="compiler-error-c2533"></a>コンパイラ エラー C2533

'identifier': コンストラクターの宣言に戻り値の型が含まれています。

コンストラクターに戻り値の型を指定することはできません (戻り値の型が `void` であっても)。

このエラーの一般的な原因は、クラス定義の末尾と最初のコンストラクターの実装の間にセミコロンがないことです。 コンパイラはクラスをコンストラクター関数の戻り値の型の定義として認識し、C2533 を生成します。

次の例では、C2533 を生成し、その修正方法を示しています。

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```