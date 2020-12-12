---
description: '詳細情報: メイクファイル内のコメント'
title: メイクファイルのコメント
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: 9edee594c0299d8e93928c1284b7244af71f61e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182295"
---
# <a name="comments-in-a-makefile"></a>メイクファイルのコメント

コメントの前にシャープ記号 (#) を付けます。 NMAKE は、シャープ記号から次の改行文字までのテキストを無視します。 例 :

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

リテラルのシャープ記号を指定するには、その前に次のようにカレット () を付け **^** ます。

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>関連項目

[メイクファイルの内容](contents-of-a-makefile.md)
