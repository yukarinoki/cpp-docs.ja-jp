---
title: 必要な値を計算する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8f51e448aab0978d6a7eb39a753c2274d2cae6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369329"
---
# <a name="calculating-necessary-values"></a>必要な値の計算
2 つの重要な情報は、遅延読み込みヘルパー ルーチンで計算される必要があります。 そのために、2 つのインライン関数にはこの情報を計算するための delayhlp.cpp です。  
  
-   1 つ目は、(インポート アドレス テーブル (IAT)、バインドのインポート アドレス テーブル (BIAT)、およびバインドされていないインポート アドレス テーブル (UIAT))、3 つの異なるテーブルにインポートする現在のインデックスを計算します。  
  
-   2 つ目は、有効な IAT のインポートの数をカウントします。  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## <a name="see-also"></a>関連項目  
 [ヘルパー関数について](understanding-the-helper-function.md)