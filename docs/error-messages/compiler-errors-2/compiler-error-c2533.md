---
title: コンパイラ エラー C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 6c598c2c5b3ac6d88fb843534cae240c65a2d322
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207915"
---
# <a name="compiler-error-c2533"></a>コンパイラ エラー C2533

'identifier': コンストラクターの宣言に戻り値の型が含まれています。

コンストラクターに戻り値の型を含めることはできません (戻り値の型でもありません **`void`** )。

このエラーの一般的な原因は、クラス定義の末尾と最初のコンストラクターの実装の間にセミコロンがないことです。 コンパイラはクラスをコンストラクター関数の戻り値の型の定義として認識し、C2533 を生成します。

次の例では、C2533 を生成し、その修正方法を示しています。

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
