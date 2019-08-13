---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: f3b4896a3cb4774e46b36480dd9769fa131fc287
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957173"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

コンテナーのテンプレート クラス `optional` と複数のサポート用テンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<オプション >

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|オブジェクトが別のオブジェクトと等しいかどうかをテストします。|
|[operator!=](../standard-library/optional-operators.md#op_neq)|オブジェクトが別のオブジェクトと等しくないかどうかをテストします。|
|[operator<](../standard-library/optional-operators.md#op_lt)|左側のオブジェクトが右側のオブジェクトより小さいかどうかをテストします。|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|左側のオブジェクトが右側のオブジェクト以下かどうかをテストします。|
|[operator>](../standard-library/optional-operators.md#op_gt)|左側のオブジェクトが右側のオブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|左側のオブジェクトが右側のオブジェクト以上かどうかをテストします。|

> [!NOTE]
> 関係比較に加えて、 \<オプションの > 演算子は**nullopt**と`T`の比較もサポートします。

### <a name="functions"></a>関数

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|オブジェクトを省略可能にします。|
|[swap](../standard-library/optional-functions.md#swap)|2つ`optional`のオブジェクトの格納されている値を交換します。|

### <a name="classes-and-structs"></a>クラスと構造体

|||
|-|-|
|hash|含まれているオブジェクトのハッシュを返します。|
|[省略可能なクラス](../standard-library/optional-class.md)|値を保持できるか、または保持できないオブジェクトを表します。|
|[nullopt_t 構造体](../standard-library/nullopt-t-structure.md)|値を保持しないオブジェクトを記述します。|
|[bad_optional_access クラス](../standard-library/bad-optional-access-class.md)|存在しない値にアクセスしようとしたことを報告する例外としてスローされるオブジェクトを表します。|

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|比較のため`nullopt_t`ののインスタンス。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
