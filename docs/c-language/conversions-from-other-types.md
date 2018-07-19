---
title: 他の型からの変換 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e919782022ee64f657611a14d6eae6173a67b8c0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382680"
---
# <a name="conversions-from-other-types"></a>他の型からの変換

**enum** 値は、定義上、**int** 値であるため、**enum** 値との相互変換は **int** 型との相互変換と同じです。 Microsoft C コンパイラの場合、整数は **long** と同じです。

**Microsoft 固有の仕様**

構造体型または共用体型の間の変換はできません。

任意の値を **void** 型に変換できますが、このような変換の結果は、式ステートメントなど、式の値が破棄されるコンテキストでのみ使用できます。

**void** 型には定義上、値がありません。 したがって、他の型に変換できず、他の型を代入によって **void** に変換することはできません。 ただし、「[型キャスト変換](../c-language/type-cast-conversions.md)」で説明されているように、値を明示的に **void** 型にキャストすることができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[代入の変換](../c-language/assignment-conversions.md)  
