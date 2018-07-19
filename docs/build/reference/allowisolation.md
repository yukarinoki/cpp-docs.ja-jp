---
title: -ALLOWISOLATION |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cb92a7f31d48dad4a7fb608703c71ccc661e176
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368975"
---
# <a name="allowisolation"></a>/ALLOWISOLATION
マニフェスト検索の動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/ALLOWISOLATION**により、オペレーティング システムはマニフェストの検索と読み込みがします。  
  
 **/ALLOWISOLATION**既定値です。  
  
 **/ALLOWISOLATION:NO**マニフェスト、および原因がない場合に、実行可能ファイルが読み込まれていることを示します[EDITBIN リファレンス](../../build/reference/editbin-reference.md)を設定する、 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` optional ヘッダーのビット`DllCharacteristics`フィールドです。  
  
 実行可能ファイルの分離が無効の場合、Windows ローダーは、新しく作成されたプロセスに対応するアプリケーション マニフェストの検索を試行しません。 実行可能ファイル自体に、マニフェストがか、名前を持つ場合はマニフェストがある場合でも、新しいプロセスは既定のアクティベーション コンテキストにありません*実行可能ファイル名*。 exe.manifest です。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [/ALLOWISOLATION (マニフェスト検索)](../../build/reference/allowisolation-manifest-lookup.md)   
 [マニフェスト ファイルのリファレンス](http://msdn.microsoft.com/library/aa375632.aspx)