---
title: 既定のシグナル
ms.date: 11/04/2016
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
ms.openlocfilehash: bb84e168d0693313373395e8d5f44be0eca9891e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234513"
---
# <a name="default-signals"></a>既定のシグナル

**ANSI 4.7.1.1** シグナル ハンドラーの呼び出しの前に `signal(sig, SIG_DFL)` と同等の処理が実行されない場合、実行中のシグナルがブロッキングされます

プログラムの実行開始時にシグナルは既定の状態に設定されます。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)
