---
title: 既定のシグナル
ms.date: 11/04/2016
helpviewer_keywords:
- default signals
- defaults, signals
ms.assetid: db9fc17b-75c0-4d33-86be-c536584bbede
ms.openlocfilehash: 91d054f32a072f9ad9ebc15a8932bf2d52a43597
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647747"
---
# <a name="default-signals"></a>既定のシグナル

**ANSI 4.7.1.1** シグナル ハンドラーの呼び出しの前に `signal(sig, SIG_DFL)` と同等の処理が実行されない場合、実行中のシグナルがブロッキングされます

プログラムの実行開始時にシグナルは既定の状態に設定されます。

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)