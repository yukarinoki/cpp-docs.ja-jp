---
title: Abort の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e63c3134dee6c316519dfcc34cff30b591b56460
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465397"
---
# <a name="using-abort"></a>abort の使用
呼び出す、[中止](../c-runtime-library/reference/abort.md)関数によっては直ちに終了します。 初期化されたグローバルな静的オブジェクトの通常のデストラクション処理は実行されません。 また、`atexit` 関数を使用して指定されている特殊な処理も実行されません。  
  
## <a name="see-also"></a>関連項目  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)