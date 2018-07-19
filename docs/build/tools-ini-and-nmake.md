---
title: Tools.ini と NMAKE |Microsoft ドキュメント
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
ms.openlocfilehash: 860a334274a3a1a4ac9e11c3e7b5e9a0f136ecc0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380551"
---
# <a name="toolsini-and-nmake"></a>Tools.ini と NMAKE
NMAKE 読み取ります Tools.ini、メイクファイルを読み取る前に/R を使用しない場合。 検索 Tools.ini 最初に、現在のディレクトリに、次の初期化環境変数で指定されたディレクトリです。 初期化ファイル (nmake の) の設定セクションの先頭で`[NMAKE]`メイクファイル情報を含めることができます。 番号記号で始まる個別の行にコメントを指定 (#)。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の実行](../build/running-nmake.md)