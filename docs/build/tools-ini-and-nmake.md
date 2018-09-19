---
title: Tools.ini と NMAKE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84406886c9aa0c0053ed7c183912bf8a7f1f4771
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723581"
---
# <a name="toolsini-and-nmake"></a>Tools.ini と NMAKE

NMAKE 読み取ります Tools.ini、メイクファイルを読み取る前に/R を使用しない場合。 検索 Tools.ini まず現在のディレクトリにし、INIT 環境変数で指定されたディレクトリにします。 初期化ファイル (nmake の) 設定セクションの先頭で`[NMAKE]`メイクファイル情報を含めることができます。 番号記号で個別の行の先頭にコメントを指定 (#)。

## <a name="see-also"></a>関連項目

[NMAKE の実行](../build/running-nmake.md)