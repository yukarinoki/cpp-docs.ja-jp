---
description: '詳細情報: #undef ディレクティブ (C/c + +)'
title: '#undef ディレクティブ (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 20dfd1d0b26f18a26e7ad407704d6cb0ffd563bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300437"
---
# <a name="undef-directive-cc"></a>#undef ディレクティブ (C/c + +)

`#define` で作成された名前を削除 (定義解除) します。

## <a name="syntax"></a>構文

> **#undef** *識別子*

## <a name="remarks"></a>解説

**#Undef** ディレクティブにより、*識別子* の現在の定義が削除されます。 その結果、プリプロセッサでは後続の *識別子* が無視されます。 **#Undef** を使用してマクロ定義を削除するには、パラメーターリストではなく、マクロ *識別子* だけを指定します。

また、以前の定義がない識別子に **#undef** ディレクティブを適用することもできます。 これにより、その識別子が未定義であることが保証されます。 マクロ置換は **#undef** ステートメント内では実行されません。

通常、 **#undef** ディレクティブは、 `#define` 識別子が特別な意味を持つソースプログラムで領域を作成するためのディレクティブと組み合わせて使用されます。 たとえば、ソース プログラムの特定の関数でマニフェスト定数を使用すると、プログラムの残り部分に影響を与えない環境固有の値を定義できます。 また、 **#undef** ディレクティブは、ディレクティブを使用して、 `#if` ソースプログラムの条件付きコンパイルを制御します。 詳細については、「 [#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)」を参照してください。

次の例では、 **#undef** ディレクティブによって、シンボリック定数とマクロの定義が削除されます。 マクロの識別子のみが指定されていることに注意してください。

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 固有の仕様**

マクロは、オプションを使用してコマンドラインから未定義にすることができ `/U` ます。その後、マクロ名を未定義にすることができます。 このコマンドを発行した場合の効果は、 `#undef` ファイルの先頭にある一連の *マクロ名* ステートメントと同じです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
