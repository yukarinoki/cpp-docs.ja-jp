---
title: Microsoft の拡張機能 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5699ce82a6e8537f12da50fdcb8288da167ecca3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752240"
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