---
title: バッチモード規則
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 38402e7b8a937cebb823ce13fa1ac01fc1099878
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328409"
---
# <a name="batch-mode-rules"></a>バッチモード規則

```
{frompath}.fromext{topath}.toext::
   commands
```

バッチ モード推論規則では、N コマンドがこの推論規則を通過する場合、推論規則の呼び出しが 1 つだけ提供されます。 バッチ モードの推論規則がない場合は、N コマンドを呼び出す必要があります。 N は、推論規則をトリガーする従属の数です。

バッチ モード推論規則を含むメイク ファイルでは、NMAKE バージョン 1.62 以降を使用する必要があります。 NMAKE バージョンを確認するには、NMAKE バージョン 1.62 以降で使用できる_NMAKE_VER マクロを実行します。 このマクロは、Visual C++ 製品バージョンを表す文字列を返します。

標準的な推論規則との唯一の構文上の違いは、バッチ モード推論規則が二重コロン (::)で終了することです。

> [!NOTE]
> 呼び出されるツールは、複数のファイルを処理できる必要があります。 バッチ モード推論規則は、従属ファイルに`$<`アクセスするマクロとして使用する必要があります。

バッチ モード推論規則を使用すると、ビルド 処理を高速化できます。 コンパイラ ドライバは一度だけ呼び出されるため、ファイルをバッチでコンパイラに提供するほうが高速です。 たとえば、C および C++ コンパイラは、プロセス中にメモリ常駐を維持できるため、一連のファイルを処理する場合のパフォーマンスが向上します。

次の例は、バッチ モード推論規則の使用方法を示しています。

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

NMAKE は、バッチ モードの推論規則を使用せずに次の出力を生成します。

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

NMAKE は、バッチ モードの推論規則を使用して、次の結果を生成します。

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
