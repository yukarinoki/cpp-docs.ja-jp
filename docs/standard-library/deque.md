---
title: '&lt;deque&gt;'
ms.date: 11/04/2016
f1_keywords:
- <deque>
helpviewer_keywords:
- deque header
ms.assetid: 4521fe92-5a91-4853-9e9f-59600bf9e46f
ms.openlocfilehash: 145ce22091ea1a42619ad7b1fd25507c6315a9ec
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454485"
---
# <a name="ltdequegt"></a>&lt;deque&gt;

コンテナーのテンプレート クラス deque および複数のサポート用テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー**: \<deque>

> [!NOTE]
> Deque \<> ライブラリは、 `#include <initializer_list>`ステートメントも使用します。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator!=](../standard-library/deque-operators.md#op_neq)|演算子の左側の deque オブジェクトが右側の deque オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/deque-operators.md#op_lt)|演算子の左側の deque オブジェクトが右側の deque オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/deque-operators.md#op_gt_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクト以下かどうかを調べます。|
|[operator==](../standard-library/deque-operators.md#op_eq_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクトと等しいかどうかを調べます。|
|[operator>](../standard-library/deque-operators.md#op_gt)|演算子の左側の deque オブジェクトが右側の deque オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/deque-operators.md#op_gt_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクト以上かどうかを調べます。|

### <a name="functions"></a>関数

|||
|-|-|
|[swap](../standard-library/deque-functions.md#swap)|2 つの deque の要素を交換します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[deque クラス](../standard-library/deque-class.md)|特定の型の要素を線形に配列させ、ベクターのように、任意の要素への高速なランダム アクセスや、コンテナーの背後での効率的な挿入と削除を実行できるようにするシーケンス コンテナーのテンプレート クラス。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
