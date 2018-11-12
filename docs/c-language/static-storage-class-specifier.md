---
title: static ストレージ クラス指定子
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: 2596e257ae6e22e207451b97b0361aecdfffba03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594039"
---
# <a name="static-storage-class-specifier"></a>static ストレージ クラス指定子

**static** のストレージ クラス指定子により内部レベルで宣言された変数には、グローバル有効期間がありますが、宣言されたブロック内でのみ表示されます。 定数文字列の場合、**static** を使用すると、頻繁に呼び出される関数で頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。

## <a name="remarks"></a>コメント

明示的に**静的**変数を初期化しない場合、既定で 0 に初期化されます。 関数内で、**static** はストレージを割り当てますが、定義として動作します。 内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。

## <a name="see-also"></a>参照

[C ストレージ クラス](c-storage-classes.md)<br/>
[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)