---
title: コンパイラ エラー C3409 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 338a98adb45ee9fc8eb392853a5693d10a171940
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058836"
---
# <a name="compiler-error-c3409"></a>コンパイラ エラー C3409

属性ブロックを空にすることはできません。

角かっこ、コンパイラによってとして解釈されていましたが[属性](../../windows/cpp-attributes-reference.md)どの属性も、ブロックが見つかりました。

ラムダ式の定義の一部としての角かっこを使用すると、コンパイラはこのエラーを生成可能性があります。 このエラーは、コンパイラは角かっこまたは属性ブロック、ラムダ式の定義の一部であるかどうかを判断できないときに発生します。 ラムダ式について詳しくは、「[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」をご覧ください。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 角かっこが属性ブロックの一部である場合。

   1. 属性ブロック内の 1 つまたは複数の属性を提供します。

   1. 属性ブロックを削除します。

1. 角かっこがラムダ式の一部である場合。

   1. ラムダ式が有効な構文規則に従うことを確認します。

         ラムダ式の構文の詳細については、次を参照してください。[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)します。

    2.

## <a name="example"></a>例

次の例では、C3409 を生成します。

```
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

## <a name="example"></a>例

ラムダ式を使用するために次の例が c3409、`mutable`仕様では、パラメーター リストは提供されません。 コンパイラは、角かっこまたは属性ブロック、ラムダ式の定義の一部であるかどうかを判断できません。

```
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>関連項目

[attribute](../../windows/cpp-attributes-reference.md)<br/>
[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)<br/>
[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)