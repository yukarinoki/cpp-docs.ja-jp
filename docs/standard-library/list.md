---
title: '&lt;リスト&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
- std::<list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: f2c04bb73bfa379ea87ba4c950bf805931c16ba1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245561"
---
# <a name="ltlistgt"></a>&lt;リスト&gt;

コンテナーのテンプレート クラス list と複数のサポート用テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <list>
```

> [!NOTE]
> \<リスト > ライブラリで使用することも、`#include <initializer_list>`ステートメント。

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

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
