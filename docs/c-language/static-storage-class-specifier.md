---
description: '詳細情報: static ストレージ クラス指定子'
title: static ストレージ クラス指定子
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: da7ca4ea71b3e450da986ec175adcaf08852d81b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168749"
---
# <a name="static-storage-class-specifier"></a>static ストレージ クラス指定子

**`static`** ストレージ クラス指定子を使用して内部レベルで宣言された変数には、グローバルな有効期間がありますが、宣言されたブロック内でしか参照できません。 定数文字列の場合、 **`static`** を使用すると、頻繁に呼び出される関数内の頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。

## <a name="remarks"></a>Remarks

**`static`** 変数を明示的に初期化しない場合は、既定で 0 に初期化されます。 関数内では、 **`static`** によってストレージが割り当てられ、定義として動作します。 内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。

## <a name="see-also"></a>関連項目

[C ストレージ クラス](c-storage-classes.md)<br/>
[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)
