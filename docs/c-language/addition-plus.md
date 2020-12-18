---
description: '詳細情報: 加算 (+)'
title: 加算 (+)
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
ms.openlocfilehash: 33cc1284c9ab36988d9fcba2fcc9e27d052cb4cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280184"
---
# <a name="addition-"></a>加算 (+)

加算演算子 ( **+** ) は、2 つのオペランドを加算します。 両方のオペランドが整数または浮動小数型でもかまいません。または、1 個のオペランドがポインターで他方が整数でもかまいません。

整数をポインターに追加すると、整数値 (*i*) は、ポインターが参照している値のサイズを乗算することによって変換されます。 変換後、整数値が *i* のメモリ位置を表します。ここでは、各位置にポインター型で指定された長さがあります。 変換された整数値がポインター値に追加されると、結果は、元のアドレスからのアドレス *i* 位置を表す新しいポインター値です。 新しいポインター値は、元のポインター値と同じ型の値をアドレス指定します。したがって、配列インデックスと同じです (「[1 次元配列](../c-language/one-dimensional-arrays.md)」と「[多次元配列](../c-language/multidimensional-arrays-c.md)」を参照してください)。 合計ポインターが、ハイ エンドを超える最初の位置を除き、配列外を指している場合、結果は未定義になります。 詳細については、「[ポインター演算](../c-language/pointer-arithmetic.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C 加法演算子](../c-language/c-additive-operators.md)
