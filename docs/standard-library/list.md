---
title: '&lt;リスト&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
- std::<list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: 8eb497e6a4380affd0f13f41c7b55990c562b7d3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453657"
---
# <a name="ltlistgt"></a>&lt;リスト&gt;

コンテナーのテンプレート クラス list と複数のサポート用テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <list>
```

> [!NOTE]
> リスト\<> ライブラリは、 `#include <initializer_list>`ステートメントも使用します。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/list-operators.md#op_lt)|演算子の左辺の list オブジェクトが右辺の list オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクト以下かどうかを調べます。|
|[operator==](../standard-library/list-operators.md#op_eq_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しいかどうかを調べます。|
|[operator>](../standard-library/list-operators.md#op_gt)|演算子の左辺の list オブジェクトが右辺の list オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクト以上かどうかを調べます。|

### <a name="functions"></a>関数

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|2 つのリストの要素を交換します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[list クラス](../standard-library/list-class.md)|要素を線形の配置に維持し、シーケンス内の任意の場所での効率的な挿入と削除を可能にする、シーケンス コンテナーのテンプレート クラス。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
