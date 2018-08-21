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
ms.openlocfilehash: 70b1e0e6ef1294ff23952816db6f468022609f4f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408376"
---
# <a name="microsoft-extensions"></a>Microsoft 拡張機能
*asm ステートメント*:  
 **_ _asm***アセンブリ命令* **;** オプトイン    
  
 **_ _asm {***アセンブリの命令リスト***};** オプトイン      
  
 *アセンブリの命令リスト*:  
 *アセンブリ命令* **;** オプトイン  
  
 *アセンブリ命令* **;***アセンブリの命令リスト* **;** オプトイン  
  
 *リスト修飾子 ms ・*:  
 *ms 修飾子 ms 修飾子リスト*選択  
  
 *ms 修飾子*:  
 **__cdecl**  
  
 **__fastcall**  
  
 **__stdcall**  
  
 **_ _syscall** (今後の実装の予約済み)  
  
 **_ _oldcall** (今後の実装の予約済み)  
  
 **_ _unaligned** (今後の実装の予約済み)  
  
 *ベースの修飾子*  
  
 *ベース修飾子*:  
 **_ _based (** *ベース型* **)**  
  
 *ベース型*:  
 *name*  