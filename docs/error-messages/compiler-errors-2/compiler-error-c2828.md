---
title: コンパイラ エラー C2828 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2828
dev_langs:
- C++
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65d9c36946459372924adc23caa5a44c40568f33
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051933"
---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828

'operator 演算子' は、バイナリ形式でグローバルに上書きすることはできません。

演算子は、オブジェクトの外部でバイナリ形式を持つことはできません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. オブジェクトにオーバー ロードされた演算子をローカルに行います。

1. 適切な単項演算子をオーバー ロードを選択します。