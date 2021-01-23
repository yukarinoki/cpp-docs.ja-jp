---
description: pragmaMicrosoft C/c + + での hdrstop ディレクティブの詳細について説明します。
title: hdrstop pragma
ms.date: 01/22/2021
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragma, hdrstop
no-loc:
- pragma
ms.openlocfilehash: caeaeb4a44182b6ba2edfa385a1504fde998cc43
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713611"
---
# <a name="hdrstop-no-locpragma"></a>`hdrstop` pragma

を使用すると、プリコンパイルファイル名、およびコンパイル状態が保存される場所をより細かく制御できます。

## <a name="syntax"></a>構文

> **`#pragma hdrstop`** [("*ファイル名*")]

## <a name="remarks"></a>解説

*Filename* は、使用または作成するプリコンパイル済みヘッダーファイルの名前です (またはが指定されているかどうかによって異なり [`/Yu`](../build/reference/yu-use-precompiled-header-file.md) [`/Yc`](../build/reference/yc-create-precompiled-header-file.md) ます)。 *Filename* にパスの指定が含まれていない場合、プリコンパイル済みヘッダーファイルはソースファイルと同じディレクトリに存在すると見なされます。

でコンパイルしたときに C ファイルまたは C++ ファイルにが含まれている場合 **`hdrstop`** pragma **`/Yc`** 、コンパイラはの場所までコンパイルの状態を保存し pragma ます。 に続くコードのコンパイル済みの状態は pragma 保存されません。

コンパイル済みの状態を保存するプリコンパイル済みヘッダーファイルの名前を指定するには、 *filename* を使用します。 と filename の間のスペース **`hdrstop`** は省略可能です。  で指定されたファイル名 **`hdrstop`** pragma は文字列であり、任意の C または C++ 文字列の制約が適用されます。 特に、引用符で囲み、エスケープ文字 (円記号) を使用してディレクトリ名を指定する必要があり **`\`** ます。 例:

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

プリコンパイル済みヘッダー ファイルの名前は、次の規則 (優先度順に表示) に従って決定されます。

1. コンパイラオプションの引数 **`/Fp`**

2. の *filename* 引数 `#pragma hdrstop`

3. PCH 拡張子を持つソースファイルのベース名

とのいずれの **`/Yc`** **`/Yu`** オプションも、もファイル名を指定しない場合は、 **`hdrstop`** pragma ソースファイルの基本名がプリコンパイル済みヘッダーファイルのベース名として使用されます。

また、次のように、プリプロセス コマンドを使用してマクロ置換を実行することもできます。

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

次の規則は、を配置できる場所を制御し **`hdrstop`** pragma ます。

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

この例では、 **`hdrstop`** pragma 2 つのファイルが含まれ、インライン関数が定義された後にが表示されます。 この場所は、最初はの位置が奇数であるように見え pragma ます。 ただし、手動のプリコンパイルオプションを使用すると、を使用して、 **`/Yc`** **`/Yu`** **`hdrstop`** pragma ソースファイル全体またはインラインコードだけをプリコンパイルできるようになります。 Microsoft コンパイラでは、データ宣言のみをプリコンパイルすることはできません。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
