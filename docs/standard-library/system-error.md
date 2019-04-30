---
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: 9bba893f63ca935e0feeb891faa4e141e1958306
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412099"
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;

ヘッダーを含める\<system_error > 例外クラスを定義する`system_error`関連の低レベル システム エラーを処理するためのテンプレートとします。

## <a name="syntax"></a>構文

```cpp
#include <system_error>
```

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|一般的なエラーのカテゴリを表します。|
|[system_category](../standard-library/system-error-functions.md#system_category)|低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|`error_code` オブジェクトを作成します。|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|`error_condition` オブジェクトを作成します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](../standard-library/system-error-operators.md#op_eq_eq)|演算子の左辺のオブジェクトが右辺のオブジェクトと等しいかどうかを調べます。|
|[operator!=](../standard-library/system-error-operators.md#op_neq)|演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/system-error-operators.md#op_lt)|オブジェクトが比較のために渡されるオブジェクトより小さいかどうかをテストします。|

### <a name="enumerations"></a>列挙

|||
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|`<errno.h>` の Posix で定義されているすべてのエラー コードのマクロにシンボル名を提供します。|

### <a name="classes-and-structs"></a>クラスと構造体

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。|
|[error_code](../standard-library/error-code-class.md)|実装固有の低レベルなシステム エラーを表します。|
|[error_condition](../standard-library/error-condition-class.md)|ユーザー定義のエラー コードを表します。|
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|[error_code クラス](../standard-library/error-code-class.md)列挙型をテストする型の述語を表します。|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|[error_condition クラス](../standard-library/error-condition-class.md) 列挙型をテストする型の述語を表します。|
|[system_error](../standard-library/system-error-class.md)|低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラスを表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<system_error>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
