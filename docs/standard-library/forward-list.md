---
title: '&lt;forward_list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <forward_list>
helpviewer_keywords:
- <forward_list>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: a8b343fbe5e175828b4b8470da486a6dea9f3455
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457006"
---
# <a name="ltforwardlistgt"></a>&lt;forward_list&gt;

コンテナーのテンプレート クラス forward_list と複数のサポート用テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<forward_list>

**名前空間:** std

> [!NOTE]
> Forward_list \<> ライブラリは、 `#include <initializer_list>`ステートメントも使用します。

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

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
