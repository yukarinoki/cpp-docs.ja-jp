---
description: '詳細情報: &lt; set&gt;'
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: 821e48fd6c5760900a955fe10d94a873d7454dc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154111"
---
# <a name="ltsetgt"></a>&lt;set&gt;

コンテナークラステンプレートセットおよびマルチセットとそのサポートテンプレートを定義します。

## <a name="requirements"></a>要件

**ヘッダー:**\<set>

**名前空間:** std

> [!NOTE]
> ライブラリは、 \<set> ステートメントも使用し `#include <initializer_list>` ます。

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|set のバージョン|multiset のバージョン|説明|
|-|-|-|
|[operator! = (set)](../standard-library/set-operators.md#op_neq)|[operator! = (マルチセット)](../standard-library/set-operators.md#op_neq)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しくないかどうかをテストします。|
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[演算子< (マルチセット)](../standard-library/set-operators.md#op_lt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト未満かどうかをテストします。|
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以下かどうかをテストします。|
|[operator = = (set)](../standard-library/set-operators.md#op_eq_eq)|[operator = = (マルチセット)](../standard-library/set-operators.md#op_eq_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しいかどうかをテストします。|
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[演算子> (マルチセット)](../standard-library/set-operators.md#op_gt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトより大きいかどうかをテストします。|
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (マルチセット)](../standard-library/set-operators.md#op_gt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以上かどうかをテストします。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|set のバージョン|multiset のバージョン|説明|
|-|-|-|
|[スワップ](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|2 つの set または multiset の要素を交換します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[クラスの設定](../standard-library/set-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意です。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|
|[マルチセットクラス](../standard-library/multiset-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意とは限りません。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
