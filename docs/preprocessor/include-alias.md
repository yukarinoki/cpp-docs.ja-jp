---
description: pragmaMicrosoft C/c + + での include_alias ディレクティブの詳細については、こちらを参照してください。
title: include_alias pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragma, include_alias
- include_alias pragma
no-loc:
- pragma
ms.openlocfilehash: a9586748794704b3b3bcaf3d8ede7ef2f2f74545
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713598"
---
# <a name="include_alias-no-locpragma"></a>`include_alias` pragma

ディレクティブで *alias_filename* が見つかった場合に、 `#include` コンパイラが代わりに *actual_filename* に置き換えることを指定します。

## <a name="syntax"></a>構文

<!-- localization note - it's important to have the italic and bold characters immediately adjacent here. -->
> **`#pragma include_alias(`** "*alias_filename*" **`,`** "*actual_filename*" **`)`**\
> **`#pragma include_alias(`** \<*alias_filename*> **`,`** \<*actual_filename*> **`)`**

## <a name="remarks"></a>解説

**`include_alias`** pragma ディレクティブを使用すると、ソースファイルに含まれるファイル名に対して異なる名前またはパスを持つファイルを置き換えることができます。 たとえば、ファイルシステムによっては、8.3 FAT ファイルシステムの制限よりも長いヘッダーファイル名が許可されている場合があります。 長い方のヘッダーファイル名の最初の8文字が一意でない可能性があるため、コンパイラは長い名前を8.3 に切り捨てるだけではありません。 ディレクティブで *alias_filename* 文字列が参照されるたびに、 `#include` 代わりに名前 *actual_filename* 置き換えられます。 次に、 *actual_filename* ヘッダーファイルを読み込みます。 これは pragma 、対応するディレクティブの前に記述する必要があり `#include` ます。 例:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

検索するエイリアスは、仕様と正確に一致している必要があります。 大文字と小文字、スペル、二重引用符や山かっこの使用はすべて一致している必要があります。 は、 **`include_alias`** pragma ファイル名に対して単純な文字列照合を行います。 他のファイル名の検証は実行されません。 たとえば、次のようなディレクティブがあるとします。

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

ヘッダーファイルの文字列が正確に一致しないため、別名の置換は行われません。 また、およびコンパイラオプションの引数として使用されるヘッダーファイル名、 **`/Yu`** またはに置き換えられ **`/Yc`** `hdrstop` pragma ません。 たとえば、ソース ファイルに次のディレクティブが含まれている場合、

```cpp
#include <AppleSystemHeaderStop.h>
```

対応するコンパイラ オプションは、次のようになります。

> **`/YcAppleSystemHeaderStop.h`**

を使用すると、 **`include_alias`** pragma 任意のヘッダーファイル名を別のファイル名にマップできます。 例:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

二重引用符で囲まれたファイル名と、山かっこで囲まれたファイル名を混在させないでください。 たとえば、上記の2つのディレクティブを指定した場合、 `#pragma include_alias` コンパイラは次のディレクティブを置き換えません `#include` 。

```cpp
#include <api.h>
#include "stdio.h"
```

さらに、次のディレクティブはエラーになります。

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

エラーメッセージまたは定義済みマクロの値として報告されたファイル名は、 `__FILE__` 置換が実行された後のファイル名です。 たとえば、次のディレクティブの後の出力を参照してください。

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

でエラーが発生すると *`VERYLONGFILENAME.H`* 、次のエラーメッセージが生成されます。

```Output
myfile.h(15) : error C2059 : syntax error
```

また、推移性はサポートされていないことに注意してください。 次のようなディレクティブがあるとします。

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

コンパイラは、ではなく、ファイルを検索し *`two.h`* *`three.h`* ます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
