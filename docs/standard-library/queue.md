---
description: '詳細情報: &lt; キュー&gt;'
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: f219cf3f457ed43eb2d9ca1658244a40ceacb265
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327591"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

クラステンプレート priority_queue とキュー、およびいくつかのサポートテンプレートを定義します。

## <a name="requirements"></a>要件

**ヘッダー:**\<queue>

**名前空間:** std

> [!NOTE]
> ライブラリは、 \<queue> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator! =](../standard-library/queue-operators.md#op_neq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しくないかどうかをテストします。|
|[<演算子 ](../standard-library/queue-operators.md#op_lt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより小さいかどうかをテストします。|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以下かどうかをテストします。|
|[operator = =](../standard-library/queue-operators.md#op_eq_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトと等しいかどうかをテストします。|
|[>演算子 ](../standard-library/queue-operators.md#op_gt)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|演算子の左側のキュー オブジェクトが右側のキュー オブジェクト以上かどうかをテストします。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[queue クラス](../standard-library/queue-class.md)|基になるコンテナー型の前後の要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|
|[priority_queue クラス](../standard-library/priority-queue-class.md)|基になるコンテナー型の先頭にあって常に最大になる要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
