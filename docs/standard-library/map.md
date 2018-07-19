---
title: '&lt;map&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac523342cc175721b9c1ef33a3d8ac4cad83033b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853366"
---
# <a name="ltmapgt"></a>&lt;map&gt;

コンテナーのテンプレート クラス map と multimap およびサポート テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <map>

```

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|map バージョン|multimap バージョン|説明|
|-----------------|----------------------|-----------------|
|[operator!= (map)](../standard-library/map-operators.md#op_neq)|[operator!= (multimap)](../standard-library/map-operators.md#op_neq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しくないかどうかをテストします。|
|[operator< (map)](../standard-library/map-operators.md#op_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#op_eq_eq)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより小さいかどうかをテストします。|
|[operator<= (map)](../standard-library/map-operators.md#op_lt)|[operator\<= (multimap)](../standard-library/map-operators.md#op_lt)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以下かどうかをテストします。|
|[operator== (map)](../standard-library/map-operators.md#op_eq_eq)|[operator== (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトと等しいかどうかをテストします。|
|[operator> (map)](../standard-library/map-operators.md#op_gt)|[operator> (multimap)](../standard-library/map-operators.md#op_gt_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクトより大きいかどうかを調べます。|
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[operator>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|演算子の左側の map または multimap オブジェクトが右側の map または multimap オブジェクト以上であるかどうかをテストします。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|map バージョン|multimap バージョン|説明|
|-----------------|----------------------|-----------------|
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap_multimap)|2 個の map または multimaps の要素を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[value_compare クラス](../standard-library/value-compare-class-map.md)|要素のキーの値を比較し要素のマップ内の相対順序を決定して、マップの要素を比較できる関数オブジェクトを提供します。|
|[map クラス](../standard-library/map-class.md)|各要素にデータを自動的に並べる一意キーを持つコレクションからデータを格納および取得するために使用します。|
|[multimap クラス](../standard-library/multimap-class.md)|各要素にデータを自動的に並べるキー (一意の値である必要はありません) を持つコレクションからデータを格納および取得するために使用します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
