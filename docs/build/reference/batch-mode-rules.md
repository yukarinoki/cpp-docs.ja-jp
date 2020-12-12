---
description: '詳細情報: Batch-Mode の規則'
title: バッチモード規則
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 73439082b4e2ad8e33b104329d861ddd1919ec63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182737"
---
# <a name="batch-mode-rules"></a>バッチモード規則

```
{frompath}.fromext{topath}.toext::
   commands
```

バッチモード推論規則は、N 個のコマンドがこの推論規則を通過するときに、推論規則の呼び出しを1回だけ提供します。 バッチモードの推論規則を使用しない場合は、N 個のコマンドを呼び出す必要があります。 N は、推論規則をトリガーする依存の数です。

バッチモードの推論規則を含むメイクには、NMAKE バージョン1.62 以降を使用する必要があります。 NMAKE のバージョンを確認するには、NMAKE バージョン1.62 以降で使用可能な _NMAKE_VER マクロを実行します。 このマクロは、Visual C++ 製品バージョンを表す文字列を返します。

標準の推定規則との構文上の違いは、バッチモードの推論規則が2つのコロン (::) で終了することです。

> [!NOTE]
> 呼び出されるツールは、複数のファイルを処理できる必要があります。 バッチモードの推論規則では、 `$<` 依存ファイルにアクセスするためにマクロとしてを使用する必要があります。

バッチモードの推論規則を使用すると、ビルド処理を高速化できます。 コンパイラドライバーが呼び出されるのは1回だけなので、バッチでコンパイラにファイルを渡す方が高速です。 たとえば、C および C++ コンパイラは、一連のファイルを処理するときにパフォーマンスが向上します。これは、プロセス中にメモリが常駐したままになる可能性があるためです。

次の例では、バッチモード推論規則を使用する方法を示します。

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE は、バッチモードの推論規則を使用せずに次の出力を生成します。

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE は、バッチモードの推論規則に従って次の結果を生成します。

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>関連項目

[推論規則](inference-rules.md)
