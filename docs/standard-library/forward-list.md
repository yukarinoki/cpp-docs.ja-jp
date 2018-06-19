---
title: '&lt;forward_list&gt; | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <forward_list>
dev_langs:
- C++
helpviewer_keywords:
- <forward_list>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a23fef80dd55e6c532df10cf64871849beda9bd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844472"
---
# <a name="ltforwardlistgt"></a>&lt;forward_list&gt;

コンテナーのテンプレート クラス forward_list と複数のサポート用テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <forward_list>
```

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](../standard-library/forward-list-operators.md#op_eq_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。|
|[operator!=](../standard-library/forward-list-operators.md#op_neq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/forward-list-operators.md#op_lt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。|
|[operator>](../standard-library/forward-list-operators.md#op_gt)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[swap](../standard-library/forward-list-functions.md#swap)|2 つの前方リストの要素を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[forward_list](../standard-library/forward-list-class.md)|要素の可変長シーケンスを制御するオブジェクトを表します。 シーケンスは要素のシングル リンク リストとして格納され、それぞれに `Type` 型のメンバーが含まれます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
