---
title: '&lt;forward_list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <forward_list>
helpviewer_keywords:
- <forward_list>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 6966d8513d78b6bbe3831709f52daa04c67b4572
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835741"
---
# <a name="ltforward_listgt"></a>&lt;forward_list&gt;

コンテナークラステンプレート forward_list といくつかのサポートテンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<forward_list>

**名前空間:** std

> [!NOTE]
> ライブラリは、 \<forward_list> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator = =](../standard-library/forward-list-operators.md#op_eq_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。|
|[operator! =](../standard-library/forward-list-operators.md#op_neq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/forward-list-operators.md#op_lt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。|
|[>演算子 ](../standard-library/forward-list-operators.md#op_gt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[スワップ](../standard-library/forward-list-functions.md#swap)|2 つの前方リストの要素を交換します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[forward_list](../standard-library/forward-list-class.md)|要素の可変長シーケンスを制御するオブジェクトを表します。 シーケンスは要素のシングル リンク リストとして格納され、それぞれに `Type` 型のメンバーが含まれます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
