---
title: イメージ形式
ms.date: 11/04/2016
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
ms.openlocfilehash: 71456af35960114ab64b076ebb9c0f9102613744
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509942"
---
# <a name="image-format"></a>イメージ形式

実行可能ファイルのイメージ形式が必要な場合は、pe 32 + を使用しています。 (Dll と Exe) の実行可能イメージは、静的なイメージのデータに対処する 32 ビットの変位相対アドレスを使用できるように、2 ギガバイト単位の最大サイズに制限されます。 このデータにはインポート アドレス テーブル、文字列定数、グローバルな静的データ、およびなどが含まれます。

## <a name="see-also"></a>関連項目

[x64 ソフトウェア規約](../build/x64-software-conventions.md)