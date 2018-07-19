---
title: '&lt;スタック&gt;|Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <stack>
dev_langs:
- C++
helpviewer_keywords:
- stack, stack header
- stack header
ms.assetid: 89d8999e-c773-46f2-86c1-4b3b5aedb1c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68f16523b1fda7b8b3d6b8dca5b4d1960c5c815f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861754"
---
# <a name="ltstackgt"></a>&lt;stack&gt;

テンプレート クラスのスタックと 2 つのサポート用テンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <stack>

```

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](../standard-library/stack-operators.md#op_neq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/stack-operators.md#op_lt)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/stack-operators.md#op_lt_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以下かどうかを調べます。|
|[operator==](../standard-library/stack-operators.md#op_eq_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しいかどうかを調べます。|
|[operator>](../standard-library/stack-operators.md#op_gt)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/stack-operators.md#op_gt_eq)|演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以上かどうかを調べます。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[stack クラス](../standard-library/stack-class.md)|基になるコンテナー型に最も新しく追加された要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
