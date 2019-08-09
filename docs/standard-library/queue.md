---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: d7a13b98ba8cff78839b2afb98371ffba5ced461
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458334"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

テンプレート クラスの priority_queue と queue、および複数のサポート テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<queue>

**名前空間:** std

> [!NOTE]
> Queue \<> ライブラリは、 `#include <initializer_list>`ステートメントも使用します。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator!=](../standard-library/queue-operators.md#op_neq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しくないかどうかをテストします。|
|[operator<](../standard-library/queue-operators.md#op_lt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより小さいかどうかをテストします。|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以下かどうかをテストします。|
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しいかどうかをテストします。|
|[operator>](../standard-library/queue-operators.md#op_gt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以上かどうかをテストします。|

### <a name="functions"></a>関数

|||
|-|-|
|[swap]()||

### <a name="classes"></a>クラス

|||
|-|-|
|[queue クラス](../standard-library/queue-class.md)|基になるコンテナー型の前後の要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|
|[priority_queue クラス](../standard-library/priority-queue-class.md)|基になるコンテナー型の先頭にあって常に最大になる要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)
