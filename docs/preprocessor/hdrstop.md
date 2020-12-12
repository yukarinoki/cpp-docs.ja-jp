---
description: '詳細情報: hdrstop プラグマ'
title: hdrstop プラグマ
ms.date: 08/29/2019
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: 1fec99503adfb1d81f7da324db83e4c2b56a3912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167514"
---
# <a name="hdrstop-pragma"></a>hdrstop プラグマ

プリコンパイルファイル名、およびコンパイル状態が保存されている場所に対する追加の制御を提供します。

## <a name="syntax"></a>構文

> **#pragma hdrstop** [("*ファイル名*")]

## <a name="remarks"></a>解説

*Filename* は、使用または作成するプリコンパイル済みヘッダーファイルの名前です ( [/Yu](../build/reference/yu-use-precompiled-header-file.md)または [/yc](../build/reference/yc-create-precompiled-header-file.md)が指定されているかどうかによって異なります)。 *Filename* にパスの指定が含まれていない場合、プリコンパイル済みヘッダーファイルはソースファイルと同じディレクトリに存在すると見なされます。

を指定してコンパイルしたときに、C ファイルまたは C++ ファイルに **hdrstop** プラグマが含まれている場合 `/Yc` 、コンパイラは、そのプラグマの位置までコンパイルの状態を保存します。 プラグマの後に続くコードのコンパイル済みの状態は保存されません。

コンパイル済みの状態を保存するプリコンパイル済みヘッダーファイルの名前を指定するには、 *filename* を使用します。 **Hdrstop** と *filename* の間のスペースは省略可能です。 **Hdrstop** プラグマで指定されたファイル名は文字列であるため、C または C++ 文字列の制約が適用されます。 具体的には、文字列を引用符で囲み、エスケープ文字 (円記号) を使用してディレクトリ名を指定する必要があります。 次に例を示します。

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

プリコンパイル済みヘッダー ファイルの名前は、次の規則 (優先度順に表示) に従って決定されます。

1. コンパイラオプションの引数 `/Fp`

2. の *filename* 引数 `#pragma hdrstop`

3. 拡張子 .PCH を持つソース ファイルのベース名

オプションとオプションについて、 `/Yc` `/Yu` 2 つのコンパイルオプションと **hdrstop** プラグマのどちらもファイル名を指定しない場合、ソースファイルの基本名がプリコンパイル済みヘッダーファイルのベース名として使用されます。

また、次のように、プリプロセス コマンドを使用してマクロ置換を実行することもできます。

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

**Hdrstop** プラグマを配置できる場所は、次の規則によって決まります。

- すべてのデータ宣言、関数宣言、および定義の外にある必要があります。

- ヘッダー ファイルにではなく、ソース ファイルに指定する必要があります。

## <a name="example"></a>例

```C
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    // ...                           // Some code to display string
}
#pragma hdrstop
```

この例では、2つのファイルが含まれ、インライン関数が定義された後に **hdrstop** プラグマが表示されます。 この場所は、最初はプラグマの位置が奇数であるように見えます。 ただし、手動プリコンパイルオプションを使用すると、 `/Yc` および `/Yu` を **hdrstop** プラグマと共に使用することで、インラインコードでもソースファイル全体をプリコンパイルできることを考慮してください。 Microsoft コンパイラでは、データ宣言以外のプリコンパイルも実行できます。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
