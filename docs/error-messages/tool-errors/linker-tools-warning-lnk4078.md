---
title: リンカー ツールの警告 LNK4078 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 252e2e7bdd011b289dbb3ec6164444bbe0bc7b44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4078"></a>リンカー ツールの警告 LNK4078
複数の 'section name' セクションが別の属性を持つが見つかりました。  
  
 リンクが検出された 2 つまたは複数のセクションでは、同じを名前で異なる属性。  
  
 この警告は、以前のバージョンのリンクまたは LIB によって作成されたインポート ライブラリまたはエクスポート ファイルによって可能性があります。  
  
 ファイルと再リンクを再作成します。  
  
## <a name="example"></a>例  
 LNK4078 は重大な変更によっても発生する: で指定されるセクション[init_seg](../../preprocessor/init-seg.md) x86 が読み取り/書き込み、読み取り専用ようになりました。  
  
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