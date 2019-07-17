---
title: '&lt;forward_list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <forward_list>
helpviewer_keywords:
- <forward_list>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: d20c5b83e0ce00c7634d32e6b63c92242c24d1b2
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240652"
---
# <a name="ltforwardlistgt"></a>&lt;forward_list&gt;

コンテナーのテンプレート クラス forward_list と複数のサポート用テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<forward_list>

**名前空間:** std

> [!NOTE]
> \<Forward_list > ライブラリで使用することも、`#include <initializer_list>`ステートメント。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator==](../standard-library/forward-list-operators.md#op_eq_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。|
|[operator!=](../standard-library/forward-list-operators.md#op_neq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/forward-list-operators.md#op_lt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。|
|[operator>](../standard-library/forward-list-operators.md#op_gt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。|

### <a name="functions"></a>関数

|||
|-|-|
|[swap](../standard-library/forward-list-functions.md#swap)|2 つの前方リストの要素を交換します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[forward_list](../standard-library/forward-list-class.md)|要素の可変長シーケンスを制御するオブジェクトを表します。 シーケンスは要素のシングル リンク リストとして格納され、それぞれに `Type` 型のメンバーが含まれます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
