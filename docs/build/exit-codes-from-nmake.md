---
title: NMAKE の終了コード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e71442e1e36dbd69afa65051cbf08f403bf8b31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367096"
---
# <a name="exit-codes-from-nmake"></a>NMAKE で返される終了コード
(Nmake の) には、次の終了コードが返されます。  
  
|コード|説明|  
|----------|-------------|  
|0|エラー (場合によっては警告)|  
|1|(発行/K を使用する場合にのみ) ビルドが不完全です。|  
|2|プログラム エラー: 次のいずれかの原因として考えられます。|  
||-メイクファイルで構文エラー|  
||のコマンドからエラーまたは終了コード|  
||-ユーザーにより中断|  
|4|システム エラー: メモリ不足|  
|255|ターゲットが最新でありません (/Q を使用する場合にのみ発行)|  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の実行](../build/running-nmake.md)