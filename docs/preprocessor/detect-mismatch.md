---
description: pragmaMicrosoft C/c + + での detect_mismatch ディレクティブの詳細については、こちらを参照してください。
title: detect_mismatch pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragma, detect_mismatch
- detect_mismatch pragma
no-loc:
- pragma
ms.openlocfilehash: 33bc899eaaed73329e24e7f210fa91adc8addaa9
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713676"
---
# <a name="detect_mismatch-no-locpragma"></a>`detect_mismatch` pragma

オブジェクト内にレコードを配置します。 リンカーは、不一致の可能性を探してこれらのレコードをチェックします。

## <a name="syntax"></a>構文

> **`#pragma detect_mismatch(`** "*name*" **`,`** "*値*" **`)`**

## <a name="remarks"></a>解説

プロジェクトをリンクするときに、プロジェクトに同じ *名前* の2つのオブジェクトが含まれており、それぞれの *値* が異なる場合、リンカーは [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md)エラーをスローします。 これ pragma は、不整合なオブジェクトファイルがリンクされないようにするために使用します。

*名前* と *値* の両方が文字列リテラルであり、エスケープ文字と連結に関して文字列リテラルの規則に従います。 大文字と小文字が区別され、コンマ、等号、引用符、または **null** 文字を含めることはできません。

## <a name="example"></a>例

この例では、同じバージョン ラベルの異なるバージョン番号を持つ 2 つのファイルを作成します。

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

コマンドラインを使用してこれらのファイルの両方をコンパイルすると、 `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` エラー LNK2038 が表示されます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
