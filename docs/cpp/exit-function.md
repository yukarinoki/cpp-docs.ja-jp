---
title: exit 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5767f6b08b4adcd3d1a8d367c6286a746eeecec3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412531"
---
# <a name="exit-function"></a>exit 関数
**終了**標準インクルード ファイルで宣言された関数\<stdlib.h >、C++ プログラムを終了します。  
  
 引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。  
  
> [!NOTE]
>  定数を使用することができます`EXIT_FAILURE`と`EXIT_SUCCESS`で定義されている\<stdlib.h >、プログラムの成功または失敗を示すためにします。  
  
 発行、`return`ステートメントから、**メイン**関数が呼び出すことと同じ、**終了**引数として戻り値を持つ関数です。  
  
 詳細については、次を参照してください。[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [プログラムの終了](../cpp/program-termination.md)