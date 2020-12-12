---
description: 詳細については、「コンパイラエラー C2483」を参照してください。
title: コンパイラ エラー C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 5edafbbb0852eb622f34698421ce9a2b794f9209
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123878"
---
# <a name="compiler-error-c2483"></a>コンパイラ エラー C2483

>'*identifier*': コンストラクターまたはデストラクターを持つオブジェクトを ' thread ' として宣言することはできません

このエラーメッセージは、Visual Studio 2015 以降のバージョンでは廃止されています。 以前のバージョンでは、属性を使用して宣言された変数を、 `thread` 実行時の評価を必要とするコンストラクターまたはその他の式で初期化することはできません。 データを初期化するには、静的な式が必要です `thread` 。

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

## <a name="see-also"></a>関連項目

[レッド](../../cpp/thread.md)
