---
title: Microsoft 拡張機能 |Microsoft ドキュメント
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
ms.openlocfilehash: beac75a8a27fc4638b541228330e83e7b665fbcb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419824"
---
# <a name="microsoft-extensions"></a>Microsoft 拡張機能
*asm ステートメント*:  
 **_ _asm***アセンブリ命令* **;** オプトイン    
  
 **_ _asm {***アセンブリ命令リスト***};** オプトイン      
  
 *アセンブリ命令リスト*:  
 *アセンブリ命令* **;** オプトイン  
  
 *アセンブリ命令* **;***アセンブリ命令リスト* **;** オプトイン  
  
 *ms 修飾子リスト*:  
 *ms 修飾子 ms 修飾子リスト*オプトイン  
  
 *ms 修飾子*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **_ _syscall** (将来の実装のために予約されています)  
  
 **_ _oldcall** (将来の実装のために予約されています)  
  
 **_ _unaligned** (将来の実装のために予約されています)  
  
 *ベース修飾子*  
  
 *ベース修飾子*:  
 **_ _based (** *ベース型* **)**  
  
 *ベース型*:  
 *name*  
