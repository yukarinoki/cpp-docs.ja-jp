---
title: コンパイラ エラー C3409
ms.date: 11/06/2018
f1_keywords:
- C3409
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
ms.openlocfilehash: d3800998ded1758ab1de92af689d9d4613c2c61e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502335"
---
# <a name="compiler-error-c3409"></a>コンパイラ エラー C3409

> 空の属性ブロックは使用できません

## <a name="remarks"></a>注釈

角かっこは、コンパイラによって [属性](../../windows/attributes/attributes-alphabetical-reference.md) ブロックとして解釈されましたが、属性が見つかりませんでした。

ラムダ式の定義の一部として角かっこを使用すると、コンパイラはこのエラーを生成することがあります。 このエラーは、コンパイラが、角かっこがラムダ式または属性ブロックの定義の一部であるかどうかを判断できない場合に発生します。 ラムダ式について詳しくは、「[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」をご覧ください。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 角かっこが属性ブロックの一部である場合は、次のようになります。

   1. 属性ブロックに1つまたは複数の属性を指定します。

   1. 属性ブロックを削除します。

1. 角かっこがラムダ式の一部である場合は、ラムダ式が有効な構文規則に従っていることを確認してください。

   ラムダ式の構文の詳細については、「 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)」を参照してください。

## <a name="examples"></a>例

次の例では、C3409 が生成されます。

```cpp
// C3409.cpp
// compile with: /c
#include <windows.h>
[]   // C3409
class a {};

// OK
[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface x {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class b : public x {};
```

次の例では、ラムダ式が **`mutable`** 仕様を使用していますが、パラメーターリストが指定されていないため、C3409 が生成されます。 コンパイラは、角かっこがラムダ式または属性ブロックの定義の一部であるかどうかを判断できません。

```cpp
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>関連項目

[attribute](../../windows/attributes/attributes-alphabetical-reference.md)<br/>
[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)<br/>
[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)
