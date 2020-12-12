---
description: '詳細については、次を参照してください: detect_mismatch プラグマ'
title: detect_mismatch プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: e57ffac731409fb14b61d35f780ee19094108655
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300737"
---
# <a name="detect_mismatch-pragma"></a>detect_mismatch プラグマ

オブジェクト内にレコードを配置します。 リンカーは、不一致の可能性を探してこれらのレコードをチェックします。

## <a name="syntax"></a>構文

> **#pragma detect_mismatch (** "*name*" **,** "*value*" **)**

## <a name="remarks"></a>解説

プロジェクトをリンクするときに、プロジェクトに同じ *名前* の2つのオブジェクトが含まれており、それぞれの *値* が異なる場合、リンカーは [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md)エラーをスローします。 整合性のないオブジェクト ファイルのリンクを防止するには、このプラグマを使用します。

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

コマンド ライン `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` を使用してこれらの両方のファイルをコンパイルすると、エラー `LNK2038` が表示されます。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
