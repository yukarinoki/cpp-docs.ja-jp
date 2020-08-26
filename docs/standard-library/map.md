---
title: '&lt;map&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 9a58160c573fac7d4ad170f589c04c75b456299a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846434"
---
# <a name="ltmapgt"></a>&lt;map&gt;

コンテナークラステンプレート map および multimap とそのサポートテンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<map>

**名前空間:** std

> [!NOTE]
> ライブラリは、 \<map> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|map バージョン|multimap バージョン|説明|
|-----------------|----------------------|-----------------|
|[operator! = (map)](../standard-library/map-operators.md#op_neq)|[operator! = (multimap)](../standard-library/map-operators.md#op_neq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しくないかどうかをテストします。|
|[operator< (map)](../standard-library/map-operators.md#op_eq_eq)|[< 演算子 (multimap)](../standard-library/map-operators.md#op_eq_eq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより小さいかどうかをテストします。|
|[operator<= (map)](../standard-library/map-operators.md#op_lt)|[operator \< = (multimap)](../standard-library/map-operators.md#op_lt)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以下かどうかをテストします。|
|[operator = = (map)](../standard-library/map-operators.md#op_eq_eq)|[operator = = (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しいかどうかをテストします。|
|[operator> (map)](../standard-library/map-operators.md#op_gt)|[> 演算子 (multimap)](../standard-library/map-operators.md#op_gt_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより大きいかどうかを調べます。|
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[operator>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以上であるかどうかをテストします。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|map バージョン|multimap バージョン|説明|
|-----------------|----------------------|-----------------|
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap_multimap)|2 個の map または multimaps の要素を交換します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[value_compare クラス](../standard-library/value-compare-class-map.md)|要素のキーの値を比較し要素のマップ内の相対順序を決定して、マップの要素を比較できる関数オブジェクトを提供します。|
|[map クラス](../standard-library/map-class.md)|各要素にデータを自動的に並べる一意キーを持つコレクションからデータを格納および取得するために使用します。|
|[multimap クラス](../standard-library/multimap-class.md)|各要素にデータを自動的に並べるキー (一意の値である必要はありません) を持つコレクションからデータを格納および取得するために使用します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
