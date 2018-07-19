---
title: 数値演算エラー M6111 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b03937ed442b169b960d573b44c0eb6ebca9660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317997"
---
# <a name="math-error-m6111"></a>数値演算エラー M6111
スタック アンダー フロー  
  
 浮動小数点演算では、8087/287/387 コプロセッサまたはエミュレーター スタック アンダー フローが発生しました。  
  
 このエラーの原因への呼び出しでは、多くの場合、`long double`値を返さない関数。 たとえば、次このエラーを生成コンパイルして実行時に。  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 プログラムは、終了コード 139 で終了します。