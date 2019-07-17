---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: 1bf5663d3e6891d45e2139c612d8e16860b6cace
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246383"
---
# <a name="ltsetgt"></a>&lt;set&gt;

コンテナー テンプレート クラスの set と multiset、およびそのサポート用テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<set>

**名前空間:** std

> [!NOTE]
> \<設定 > ライブラリで使用することも、`#include <initializer_list>`ステートメント。

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|set のバージョン|multiset のバージョン|説明|
|-|-|-|
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しくないかどうかをテストします。|
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト未満かどうかをテストします。|
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以下かどうかをテストします。|
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しいかどうかをテストします。|
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトより大きいかどうかをテストします。|
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以上かどうかをテストします。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|set のバージョン|multiset のバージョン|説明|
|-|-|-|
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|2 つの set または multiset の要素を交換します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[set クラス](../standard-library/set-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意です。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|
|[multiset クラス](../standard-library/multiset-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意とは限りません。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
