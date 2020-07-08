---
title: '#line ディレクティブ (C/C++)'
description: 'プリプロセッサマクロによって報告される行番号とファイル名を設定するために使用される #line ディレクティブについて説明します。'
ms.date: 07/06/2020
f1_keywords:
- '#line'
helpviewer_keywords:
- preprocessor, directives
- line directive (#line)
- '#line directive'
ms.assetid: 585c1dc4-5184-4f01-98f4-80c1909744d7
ms.openlocfilehash: 7b671cfdf5d5ce43024ac3e038c214396ac8679c
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058621"
---
# <a name="line-directive-cc"></a>#line ディレクティブ (C/c + +)

**#Line**ディレクティブは、コンパイラの行番号とファイル名について報告された値を、指定した行番号とファイル名に設定するようにプリプロセッサに指示します。

## <a name="syntax"></a>構文

> **`#line`***digit-sequence* ["*filename*"]

## <a name="remarks"></a>解説

コンパイラは、行番号および省略可能なファイル名を使用して、コンパイル時に見つかったエラーを参照します。 通常、行番号は現在の入力行を参照し、ファイル名は現在の入力ファイルを参照します。 行番号は、各行が処理された後、インクリメントします。

*数字シーケンス*値には、任意の整数定数を指定できます。 プリプロセストークンではマクロ置換を使用できますが、結果は正しい構文に評価される必要があります。 *ファイル名*は任意の文字の組み合わせにすることができ、二重引用符 () で囲む必要があり `" "` ます。 *Filename*を省略した場合、以前のファイル名は変更されません。

ディレクティブを記述することによって、ソース行番号とファイル名を変更できます **`#line`** 。 ディレクティブは、 **`#line`** ソースファイル内のディレクティブの直後にある行の値を設定します。 変換プログラムでは、行番号とファイル名を使用して、定義済みのマクロとの値を決定し `__FILE__` `__LINE__` ます。 これらのマクロを使用して、説明的なエラー メッセージをプログラム テキストに挿入できます。 これらの定義済みマクロの詳細については、「[定義済みマクロ](../preprocessor/predefined-macros.md)」を参照してください。

マクロは、 `__FILE__` ファイル名が二重引用符 () で囲まれた文字列に展開され `" "` ます。

行番号とファイル名を変更すると、コンパイラでは以前の値が無視され、新しい値で処理が続行されます。 **#Line**ディレクティブは、通常、プログラムジェネレーターによって使用されます。 これは、エラーメッセージが生成されたプログラムではなく、元のソースファイルを参照するようにするために使用されます。

## <a name="example"></a>例

次の例で **`#line`** は、およびマクロとを示し `__LINE__` `__FILE__` ます。

最初の例では、行番号が10に、次に20に設定され、ファイル名が*hello .cpp*に変更されます。

```cpp
// line_directive.cpp
// Compile by using: cl /W4 /EHsc line_directive.cpp
#include <stdio.h>

int main()
{
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 10
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 20 "hello.cpp"
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
}
```

```Output
This code is on line 7, in file line_directive.cpp
This code is on line 10, in file line_directive.cpp
This code is on line 20, in file hello.cpp
This code is on line 21, in file hello.cpp
```

この例では、マクロは、 `ASSERT` 定義済みのマクロとを使用して、 `__LINE__` 指定されたアサーションが true で `__FILE__` ない場合にソースファイルに関するエラーメッセージを出力します。

```C
#define ASSERT(cond) if( !(cond) )\
{printf( "assertion error line %d, file(%s)\n", \
__LINE__, __FILE__ );}
```

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
