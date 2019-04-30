---
title: リンカー ツールの警告 LNK4078
ms.date: 11/04/2016
f1_keywords:
- LNK4078
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
ms.openlocfilehash: d20eb0523ffebe9229d05b6316772259661f6020
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399938"
---
# <a name="linker-tools-warning-lnk4078"></a>リンカー ツールの警告 LNK4078

複数の 'section name' セクションが見つかりました。 別の属性

リンクが 2 つ見つかりましたまたは複数のセクションでは同じであるが異なる属性の名前します。

この警告は、以前のバージョンのリンクまたは LIB によって作成されたインポート ライブラリまたはエクスポート ファイルによることができます。

ファイルと再リンクを再作成します。

## <a name="example"></a>例

LNK4078 は重大な変更によっても発生: されるセクション[init_seg](../../preprocessor/init-seg.md) x86 が読み取り/書き込み、読み取り専用ようになりました。

次の例では、LNK4078 が生成されます。

```
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```