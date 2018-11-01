---
title: Microsoft 拡張機能
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: d8104c2df2335e11dcb711108d566e0fdd069762
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592206"
---
# <a name="microsoft-extensions"></a>Microsoft 拡張機能

*asm ステートメント*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _asm***アセンブリ命令* **;**<sub>選択  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _asm {***アセンブリの命令リスト***};**<sub>選択    </sub>

*アセンブリの命令リスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*アセンブリ命令* **;**<sub>選択</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*アセンブリ命令* **;***アセンブリの命令リスト* **;**<sub>選択</sub>

*リスト修飾子 ms ・*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ms 修飾子**リスト修飾子 ms ・*<sub>選択</sub>

*ms 修飾子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _syscall** (今後の実装の予約済み)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _oldcall** (今後の実装の予約済み)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _unaligned** (今後の実装の予約済み)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ベースの修飾子*

*ベース修飾子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ _based (** *ベース型* **)**

*ベース型*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*名*