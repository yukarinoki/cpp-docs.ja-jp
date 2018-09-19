---
title: イメージの形式 |Microsoft Docs
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
ms.openlocfilehash: 0e69d1a7c62d4e9c52cc628f30f94c346d83647f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715417"
---
# <a name="image-format"></a>イメージ形式

実行可能ファイルのイメージ形式が必要な場合は、pe 32 + を使用しています。 (Dll と Exe) の実行可能イメージは、静的なイメージのデータに対処する 32 ビットの変位相対アドレスを使用できるように、2 ギガバイト単位の最大サイズに制限されます。 このデータにはインポート アドレス テーブル、文字列定数、グローバルな静的データ、およびなどが含まれます。

## <a name="see-also"></a>関連項目

[x64 ソフトウェア規約](../build/x64-software-conventions.md)