---
title: 添字演算子の解釈
ms.date: 08/27/2018
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
ms.openlocfilehash: 1c3d5bca66cb294503805fd5b7691331ac380ae5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375315"
---
# <a name="interpretation-of-subscript-operator"></a>添字演算子の解釈

などの他の演算子では、添字演算子 (**\[]**)、ユーザーによって再定義することができます。 添字演算子の既定の動作では、オーバーロードしない場合、次のメソッドを使用して配列名と添字を組み合わせます。

\*((*array-name*) + (*subscript*))

ポインター型を含むすべての加算と同様に、スケーリングは型のサイズを調整するように自動的に実行されます。 そのため、結果の値はありませんは*添字*の配信元からのバイト*配列名*ではなくは、*添字*番目の要素の配列。 (この変換の詳細については、次を参照してください[加法演算子](../cpp/additive-operators-plus-and.md)。)。

同様に、多次元配列の場合は、次のメソッドを使用してアドレスが派生されます。

((*配列名*) + (*添字*1 \* *max*2 \* *max*3 \* .\* *max*n) + (*添字*2 \* *max*3 \* .\* *max*n) +… +*添字*n))

## <a name="see-also"></a>関連項目

[配列](../cpp/arrays-cpp.md)<br/>
