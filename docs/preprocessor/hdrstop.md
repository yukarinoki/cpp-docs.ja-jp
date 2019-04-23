---
title: hdrstop
ms.date: 11/04/2016
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: 1590b5916a8d9c00b6e988bacc7cd857c29d6775
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035216"
---
# <a name="hdrstop"></a>hdrstop
プリコンパイル ファイル名およびコンパイル状態が保存される場所に対する追加の制御を指定します。

## <a name="syntax"></a>構文

```
#pragma hdrstop [( "filename" )]
```

## <a name="remarks"></a>Remarks

*Filename*を使用して、または作成するには、プリコンパイル済みヘッダー ファイルの名前を指定します (かどうかに応じて[/Yu](../build/reference/yu-use-precompiled-header-file.md)または[/Yc](../build/reference/yc-create-precompiled-header-file.md)を指定)。 場合*filename*パスの指定が含まれていない、プリコンパイル済みヘッダー ファイルは、ソース ファイルと同じディレクトリにあると見なされます。

C または C++ ファイルが含まれている場合、 **hdrstop**プラグマでコンパイルされたときに`/Yc`コンパイラはプラグマの位置までのコンパイル状態を保存します。 プラグマの後ろにあるコードのコンパイル状態は保存されません。

使用*filename*コンパイル済みの状態を保存するプリコンパイル済みヘッダー ファイルの名前。 間にスペース**hdrstop**と*filename*は省略可能です。 指定されたファイル名、 **hdrstop**プラグマは文字列であり、C または C++ の文字列の制約を前提となります。 具体的には、文字列を引用符で囲み、エスケープ文字 (円記号) を使用してディレクトリ名を指定する必要があります。 例えば:

```
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

プリコンパイル済みヘッダー ファイルの名前は、次の規則 (優先度順に表示) に従って決定されます。

1. 引数、`/Fp`コンパイラ オプション

2. *Filename*への引数 `#pragma hdrstop`

3. 拡張子 .PCH を持つソース ファイルのベース名

`/Yc`と`/Yu`オプションは、2 つのコンパイル オプションのどちらでもない場合も**hdrstop**プラグマは、ファイル名を指定、ソース ファイルの基本名がプリコンパイル済みヘッダー ファイルのベース名として使用されます。

また、次のように、プリプロセス コマンドを使用してマクロ置換を実行することもできます。

```
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

次の規則は、where、 **hdrstop**プラグマを配置することができます。

- すべてのデータ宣言、関数宣言、および定義の外にある必要があります。

- ヘッダー ファイルにではなく、ソース ファイルに指定する必要があります。

## <a name="example"></a>例

```
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    ...                              // Some code to display string
}
#pragma hdrstop
```

この例で、 **hdrstop**プラグマは、2 つのファイルが含まれているし、インライン関数が定義されているが表示されます。 初めは、プラグマの位置が不自然に見えるかもしれません。 検討してください、ただし、手動プリコンパイル オプションを使用している`/Yc`と`/Yu`で、 **hdrstop**プラグマにより、ソース ファイル全体をプリコンパイルする — インライン コードも含みます。 Microsoft コンパイラでは、データ宣言以外のプリコンパイルも実行できます。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)