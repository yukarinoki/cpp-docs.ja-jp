---
description: '詳細情報: &lt; deque&gt;'
title: '&lt;deque&gt;'
ms.date: 11/04/2016
f1_keywords:
- <deque>
helpviewer_keywords:
- deque header
ms.assetid: 4521fe92-5a91-4853-9e9f-59600bf9e46f
ms.openlocfilehash: dfd8224dfc46418f3fbba67e4cae0e90e899fee2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232825"
---
# <a name="ltdequegt"></a>&lt;deque&gt;

コンテナークラステンプレート deque といくつかのサポートテンプレートを定義します。

## <a name="requirements"></a>要件

**ヘッダー**: \<deque>

> [!NOTE]
> ライブラリは、 \<deque> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator! =](../standard-library/deque-operators.md#op_neq)|演算子の左側の deque オブジェクトが右側の deque オブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/deque-operators.md#op_lt)|演算子の左側の deque オブジェクトが右側の deque オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/deque-operators.md#op_gt_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクト以下かどうかを調べます。|
|[operator = =](../standard-library/deque-operators.md#op_eq_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクトと等しいかどうかを調べます。|
|[>演算子 ](../standard-library/deque-operators.md#op_gt)|演算子の左側の deque オブジェクトが右側の deque オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/deque-operators.md#op_gt_eq)|演算子の左側の deque オブジェクトが右側の deque オブジェクト以上かどうかを調べます。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[スワップ](../standard-library/deque-functions.md#swap)|2 つの deque の要素を交換します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[deque クラス](../standard-library/deque-class.md)|指定された型の要素を線形の配置に配置し、ベクターと同様に、任意の要素への高速なランダムアクセスを可能にし、コンテナーの後ろでの効率的な挿入と削除を可能にする、シーケンスコンテナーのクラステンプレート。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
