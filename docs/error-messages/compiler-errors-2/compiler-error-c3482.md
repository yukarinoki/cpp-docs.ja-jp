---
title: コンパイラ エラー C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 6ff269d719dd354932ef79946ae99a9b60490199
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039425"
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