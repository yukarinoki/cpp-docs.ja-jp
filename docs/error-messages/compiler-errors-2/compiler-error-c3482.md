---
description: 詳細については、「コンパイラエラー C3482」を参照してください。
title: コンパイラ エラー C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 752ce53b590ef5c10c25e0d0e850c7c4cc2776bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315700"
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
