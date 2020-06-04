---
title: コンパイラ エラー C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 20b08c0d2cd89224ed3d3b8b34915deb947b0b4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205115"
---
# <a name="compiler-error-c2483"></a>コンパイラ エラー C2483

>'*identifier*': コンストラクターまたはデストラクターを持つオブジェクトを ' thread ' として宣言することはできません

このエラーメッセージは、Visual Studio 2015 以降のバージョンでは廃止されています。 以前のバージョンでは、`thread` 属性を使用して宣言された変数を、実行時の評価を必要とするコンストラクターまたはその他の式で初期化することはできません。 `thread` データを初期化するには、静的な式が必要です。

## <a name="example"></a>例

次の例では Visual Studio 2013 以前のバージョンで C2483 が生成されます。

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>参照

[thread](../../cpp/thread.md)
