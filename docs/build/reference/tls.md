---
title: -TLS |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5e510f406ceae7508f9b84f99e7ab397d22f114
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373525"
---
# <a name="tls"></a>/TLS
実行可能ファイルから IMAGE_TLS_DIRECTORY 構造を表示します。  
  
## <a name="remarks"></a>コメント  
 /TLS には、TLS 構造体のフィールドだけでなく、TLS のコールバック関数のアドレスが表示されます。  
  
 プログラムにスレッド ローカル ストレージが使用していない場合、そのイメージには、TLS 構造は含まれません。  参照してください[スレッド](../../cpp/thread.md)詳細についてはします。  
  
 IMAGE_TLS_DIRECTORY は、winnt.h で定義されます。  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)