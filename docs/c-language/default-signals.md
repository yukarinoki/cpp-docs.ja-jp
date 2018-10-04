---
title: 既定のシグナル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78c369665d398d4b326cf8d27ad0944a594fe1a4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758938"
---
# <a name="default-signals"></a>既定のシグナル

**ANSI 4.7.1.1** シグナル ハンドラーの呼び出しの前に `signal(sig, SIG_DFL)` と同等の処理が実行されない場合、実行中のシグナルがブロッキングされます

プログラムの実行開始時にシグナルは既定の状態に設定されます。  
  
## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)