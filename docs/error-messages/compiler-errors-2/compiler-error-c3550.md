---
title: コンパイラ エラー C3550 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08c22d7e371fda7a229b541f78d4385f2943ee54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047786"
---
# <a name="compiler-error-c3550"></a>コンパイラ エラー C3550

このコンテキストでは単純な 'decltype(auto)' のみが許可されます

`decltype(auto)` を関数の戻り値の型のプレースホルダーとして使用する場合は、単独で使用する必要があります。 ポインターの宣言 (`decltype(auto*)`)、参照の宣言 (`decltype(auto&)`)、またはその他の修飾の一部として使用することはできません。

## <a name="see-also"></a>関連項目

[auto](../../cpp/auto-cpp.md)