---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: cbc93500c3fe61b2a4640008b869f3a6b71b5c6c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833310"
---
# <a name="ltlistgt"></a>&lt;list&gt;

コンテナークラステンプレートリストといくつかのサポートテンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <list>
```

> [!NOTE]
> ライブラリは、 \<list> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator! =](../standard-library/list-operators.md#op_neq)|演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/list-operators.md#op_lt)|演算子の左辺の list オブジェクトが右辺の list オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクト以下かどうかを調べます。|
|[operator = =](../standard-library/list-operators.md#op_eq_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しいかどうかを調べます。|
|[>演算子 ](../standard-library/list-operators.md#op_gt)|演算子の左辺の list オブジェクトが右辺の list オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|演算子の左辺の list オブジェクトが右辺の list オブジェクト以上かどうかを調べます。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[スワップ](../standard-library/list-functions.md#swap)|2 つのリストの要素を交換します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[list クラス](../standard-library/list-class.md)|シーケンスコンテナーのクラステンプレート。要素を線形の配置に維持し、シーケンス内の任意の場所での効率的な挿入と削除を可能にします。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
