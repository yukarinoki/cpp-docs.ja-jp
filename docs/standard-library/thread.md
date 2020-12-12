---
description: '詳細情報: &lt; thread&gt;'
title: '&lt;thread&gt;'
ms.date: 11/04/2016
f1_keywords:
- <thread>
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
ms.openlocfilehash: 3387d96772f1ed3322ce79b744e17b6bf494140d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289622"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

標準ヘッダーをインクルードして、 \<thread> クラス `thread` とさまざまなサポート関数を定義します。

## <a name="syntax"></a>構文

```cpp
#include <thread>
```

## <a name="remarks"></a>解説

> [!NOTE]
> **/Clr** を使用してコンパイルされたコードでは、このヘッダーはブロックされます。

マクロは、 `__STDCPP_THREADS__` このヘッダーでスレッドがサポートされていることを示す0以外の値として定義されます。

## <a name="members"></a>メンバー

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[thread クラス](../standard-library/thread-class.md)|アプリケーションの実行スレッドを観察および管理するために使用されるオブジェクトを定義します。|

### <a name="public-structures"></a>パブリック構造体

|名前|説明|
|----------|-----------------|
|[hash 構造体 (C++ 標準ライブラリ)](../standard-library/hash-structure-stl.md)|によって一意に決定される値を返すメンバー関数を定義 `thread::id` します。 このメンバー関数は、 [](../standard-library/hash-class.md)型の値 `thread::id` をインデックス値の分布にマッピングするのに適したハッシュ関数を定義します。|

### <a name="public-functions"></a>パブリック関数

|名前|説明|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|現在の実行スレッドを一意に識別します。|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|呼び出し元のスレッドをブロックします。|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|少なくとも指定された時間まで、呼び出し元スレッドをブロックします。|
|[スワップ](../standard-library/thread-functions.md#swap)|2つのオブジェクトの状態を交換 `thread` します。|
|[yield](../standard-library/thread-functions.md#yield)|現在のスレッドが通常引き続き実行される場合であっても、他のスレッドを実行するようオペレーティング システムに通知します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator>= 演算子](../standard-library/thread-operators.md#op_gt_eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。|
|[operator> 演算子](../standard-library/thread-operators.md#op_gt)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。|
|[operator<= 演算子](../standard-library/thread-operators.md#op_lt_eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。|
|[operator< 演算子](../standard-library/thread-operators.md#op_lt)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。|
|[operator! = 演算子](../standard-library/thread-operators.md#op_neq)|2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。|
|[operator = = 演算子](../standard-library/thread-operators.md#op_eq_eq)|2 つの `thread::id` オブジェクトが等しいかどうかを比較します。|
|[operator<< 演算子](../standard-library/thread-operators.md#op_lt_lt)|`thread::id` オブジェクトのテキスト表現をストリームに挿入します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
