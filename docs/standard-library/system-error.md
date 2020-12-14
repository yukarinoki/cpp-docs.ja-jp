---
description: '詳細については、次を参照してください: &lt; system_error&gt;'
title: '&lt;system_error&gt;'
ms.date: 03/15/2019
f1_keywords:
- <system_error>
- system_error
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
ms.openlocfilehash: 77ff4cae7d40ae4edb393e5d4f6743be1563556c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259410"
---
# <a name="ltsystem_errorgt"></a>&lt;system_error&gt;

例外クラス `system_error` を定義するヘッダー \<system_error> と、低レベルのシステム エラーを処理する関連テンプレートを含みます。

## <a name="requirements"></a>要件

**ヘッダー:**\<system_error>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="objects"></a>Objects

|名前|説明|
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|一般的なエラーのカテゴリを表します。|
|[is_error_code_enum_v](../standard-library/system-error-functions.md#is_error_code_enum_v)||
|[is_error_condition_enum_v](../standard-library/system-error-functions.md#is_error_condition_enum_v)||
|[system_category](../standard-library/system-error-functions.md#system_category)|低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|`error_code` オブジェクトを作成します。|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|`error_condition` オブジェクトを作成します。|

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator = =](../standard-library/system-error-operators.md#op_eq_eq)|演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。|
|[operator! =](../standard-library/system-error-operators.md#op_neq)|演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。|
|[<演算子 ](../standard-library/system-error-operators.md#op_lt)|オブジェクトが比較のために渡されるオブジェクトより小さいかどうかをテストします。|
|[<<演算子 ](../standard-library/system-error-operators.md#op_ostream)||

### <a name="enums"></a>列挙型

|名前|説明|
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|の POSIX で定義されているすべてのエラーコードマクロにシンボル名を提供 `<errno.h>` します。|

### <a name="classes-and-structs"></a>クラスと構造体

|名前|説明|
|-|-|
|[error_category](../standard-library/error-category-class.md)|エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。|
|[error_code](../standard-library/error-code-class.md)|実装固有の低レベルなシステム エラーを表します。|
|[error_condition](../standard-library/error-condition-class.md)|ユーザー定義のエラー コードを表します。|
|[hash](../standard-library/hash-structure.md#system_error)||
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|[error_code クラス](../standard-library/error-code-class.md)列挙型をテストする型の述語を表します。|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|[error_condition クラス](../standard-library/error-condition-class.md) 列挙型をテストする型の述語を表します。|
|[system_error](../standard-library/system-error-class.md)|低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラスを表します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
