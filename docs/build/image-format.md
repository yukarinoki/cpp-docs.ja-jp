---
title: 画像の書式 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 356480333a62d998213726016f3940b318c218a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367941"
---
# <a name="image-format"></a>イメージ形式
実行可能イメージの形式は pe 32 + です。 (Dll と Exe) の実行可能イメージは、静的なイメージのデータに対処する 32 ビットの変位相対アドレスを使用できるように、2 ギガバイト単位の最大サイズに制限されます。 このデータには、インポート アドレス テーブル、文字列定数、グローバルな静的データ、およびなどが含まれています。  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)