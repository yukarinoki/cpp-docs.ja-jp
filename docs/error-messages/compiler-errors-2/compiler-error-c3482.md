---
title: コンパイラ エラー C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: ec0018fc1aafc7e3e0423608f4db9f78946e4597
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432640"
---
# <a name="compiler-error-c3482"></a>コンパイラ エラー C3482

'this' は非静的メンバー関数内でのラムダ キャプチャとしてのみ使用できます

静的メソッドまたはグローバル関数で宣言されているラムダ式のキャプチャ リストに `this` を渡すことはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 外側の関数を静的でないメソッドに変換します。または、

- ラムダ式のキャプチャ リストから `this` ポインターを削除します。

## <a name="example"></a>例

次の例では、C3482 が生成されます。

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)