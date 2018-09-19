---
title: コンパイラ エラー C2223 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2223
dev_langs:
- C++
helpviewer_keywords:
- C2223
ms.assetid: e4506f0f-0317-4a96-8a90-877a156d7939
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0ca3cd091b349536046b0ead8e52805db3dff9b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067663"
---
# <a name="compiler-error-c2223"></a>コンパイラ エラー C2223

'識別子を ->' の左側が構造体/共用体をポイントする必要があります。

`->` の左側のオペランドがクラス、構造体、または共用体へのポインターではありません。

このエラーは、未定義の変数には、左側のオペランドによって発生することができます (したがって入力`int`)。