---
title: 致命的なエラー C1045 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c18d6f9b502e818992097c3042689cf66457792
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024776"
---
# <a name="fatal-error-c1045"></a>致命的なエラー C1045

コンパイラの制限 : 外部参照の入れ子のレベルがコンパイラの限界を超えています。

入れ子になった外部参照がコンパイラの制限を超えています。 入れ子になった外部参照は、 `extern` "C++" などの外部リンケージの種類で許可されます。 エラーを解決するには、入れ子になった外部参照の数を減らします。