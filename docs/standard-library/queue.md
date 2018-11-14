---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: ed1960dffa4bfe8b1ae4105f9f31943fa7a30212
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525056"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

テンプレート クラスの priority_queue と queue、および複数のサポート テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <queue>
```

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](../standard-library/queue-operators.md#op_neq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しくないかどうかをテストします。|
|[operator<](../standard-library/queue-operators.md#op_lt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより小さいかどうかをテストします。|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以下かどうかをテストします。|
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しいかどうかをテストします。|
|[operator>](../standard-library/queue-operators.md#op_gt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以上かどうかをテストします。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[queue クラス](../standard-library/queue-class.md)|基になるコンテナー型の前後の要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|
|[priority_queue クラス](../standard-library/priority-queue-class.md)|基になるコンテナー型の先頭にあって常に最大になる要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
