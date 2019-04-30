---
title: '#undef ディレクティブ (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 4f4f5ce244be6d7f4e13d7a2abc5d21232c08d9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409851"
---
# <a name="undef-directive-cc"></a>#undef ディレクティブ (C/C++)
`#define` で作成された名前を削除 (定義解除) します。

## <a name="syntax"></a>構文

```
#undef
identifier
```

## <a name="remarks"></a>Remarks

**#Undef**ディレクティブの現在の定義を削除します*識別子*します。 その結果、後続の*識別子*はプリプロセッサによって無視されます。 使用してマクロ定義を削除する **#undef**のマクロのみ*識別子*; パラメーター リストが得られない。

適用することも、 **#undef**ディレクティブを以前の定義を持たない識別子。 これにより、その識別子が未定義であることが保証されます。 内ではマクロ置換は実行されません **#undef**ステートメント。

**#Undef**ディレクティブと組み合わせるは通常、`#define`識別子が必要がある特別な意味をソース プログラムに領域を作成するディレクティブ。 たとえば、ソース プログラムの特定の関数でマニフェスト定数を使用すると、プログラムの残り部分に影響を与えない環境固有の値を定義できます。 **#Undef**ディレクティブでも使用できます、`#if`ディレクティブをソース プログラムの条件付きコンパイルを制御します。 参照してください[#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)詳細についてはします。

次の例では、 **#undef**ディレクティブは、シンボリック定数およびマクロの定義を削除します。 マクロの識別子のみが指定されていることに注意してください。

```
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 固有の仕様**

マクロを使用してコマンドラインからに定義できます、`/U`オプションを定義するマクロ名を続けています。 このコマンドを発行の効果は一連の`#undef`*マクロ名*ステートメントをファイルの先頭にあります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)