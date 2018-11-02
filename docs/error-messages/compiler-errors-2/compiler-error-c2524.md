---
title: コンパイラ エラー C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 369aa5f21c072472808ffba06c3bc5c5e608ac22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640116"
---
# <a name="compiler-error-c2524"></a>コンパイラ エラー C2524

'デコンス トラクター': デストラクターまたはファイナライザーには、'void' パラメーター リストが必要です。

デストラクターまたはファイナライザーがないパラメーター リスト[void](../../cpp/void-cpp.md)します。 その他のパラメーターの型を指定することはできません。

## <a name="example"></a>例

次のコードでは、C2524 を再現します。

```
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>例

次のコードでは、C2524 を再現します。

```
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```