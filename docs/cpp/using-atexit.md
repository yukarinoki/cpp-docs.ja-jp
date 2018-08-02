---
title: Atexit の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4acd81a5420f9fe2685e7570f26fea61691b845
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467405"
---
# <a name="using-atexit"></a>atexit の使用
[Atexit](../c-runtime-library/reference/atexit.md)関数の場合、プログラムの終了前に実行される終了処理関数を指定することができます。 呼び出す前に初期化されてグローバルな静的オブジェクト**atexit**終了処理関数の実行前に破棄されません。  
  
## <a name="see-also"></a>関連項目  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)