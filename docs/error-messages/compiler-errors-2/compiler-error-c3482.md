---
title: コンパイラ エラー C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 0463f6de51e324bd02c8b766fd39909ee2803ecd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212580"
---
# <a name="compiler-error-c3482"></a>コンパイラ エラー C3482

'this' は非静的メンバー関数内でのラムダ キャプチャとしてのみ使用できます

**`this`** 静的メソッドまたはグローバル関数で宣言されているラムダ式のキャプチャリストにを渡すことはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 外側の関数を静的でないメソッドに変換します。または、

- **`this`** ラムダ式のキャプチャリストからポインターを削除します。

## <a name="example"></a>例

次の例では、C3482 が生成されます。

```cpp
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
