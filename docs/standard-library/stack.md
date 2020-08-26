---
title: '&lt;stack&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stack>
helpviewer_keywords:
- stack, stack header
- stack header
ms.assetid: 89d8999e-c773-46f2-86c1-4b3b5aedb1c1
ms.openlocfilehash: b2130994ca69dd23f7df3e521deb67263b13d0cc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844289"
---
# <a name="ltstackgt"></a>&lt;stack&gt;

クラステンプレートスタックと2つのサポートテンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<stack>

**名前空間:** std

> [!NOTE]
> ライブラリは、 \<stack> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator! =](../standard-library/stack-operators.md#op_neq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/stack-operators.md#op_lt)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/stack-operators.md#op_lt_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以下かどうかを調べます。|
|[operator = =](../standard-library/stack-operators.md#op_eq_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しいかどうかを調べます。|
|[>演算子 ](../standard-library/stack-operators.md#op_gt)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/stack-operators.md#op_gt_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以上かどうかを調べます。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[stack クラス](../standard-library/stack-class.md)|基になるコンテナー型に最も新しく追加された要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
